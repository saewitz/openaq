For larger data queries, OpenAQ data can be directly accessed as gzipped csv (comma\-separated values) files from the Open Data on AWS Program's S3 bucket. Data are updated by location every 72 hours and organized to allow for filtering by country, location, year and month.


Bucket structure
----------------


The bucket root url is 



```
https://openaq-data-archive.s3.amazonaws.com/

```

The files are organized with the the following structure:



```
/
│ README.md   
│
└───records/
     │  
     └───{file format}/
         │   
         └───locationid={locationid}/
             │
             └───year={year}/
                 │  
                 └───month={month}/
                      │ location-{locationid}-{year}{month}{day}.csv.gz
                      │ location-{locationid}-{year}{month}{day}.csv.gz
                      │...

```

example file path:



```
/records/csv.gz/locationid=2178/year=2022/month=05/location-2178-20220503.csv.gz

```

### Prefixes


The prefix structure follows the [Apache Hive partitioning format](https://athena.guide/articles/hive-style-partitioning/) with key value pairing in the directory title i.e. `key=value`. Hive formatting is not used for the top two directories named `records` and `csv.gz` (or other data formats TBD)


 `records`


Top level directory containing individual records from sensors.


 `file format`


The file format of the data. Currently only `csv.gz` (gzip csv)


 `locationid={locationid}`


The OpenAQ id for the location, a numerical value, e.g. location\_id\=42


 `year={year}`


The four digit number of the year, e.g. year\=2022


`month={month}`


The zero padded two digit number of the month, e.g. month\=02


Measurement File
----------------


Measurements are stored as csv (comma\-separated values) compressed with gzip (csv.gz). The measurements file holds measurement values for all sensors for a given location on a given day. The file follows the following naming convention: 


`loc-{locationid}-{year}{month}{day}.{ext}`


### File structure


Data is stored in [narrow](https://en.wikipedia.org/wiki/Wide_and_narrow_data#Narrow) format with the following columns: 




| Column name | description | example |
| --- | --- | --- |
| location\_id | the OpenAQ location id of the station | 2178 |
| sensor\_id | the OpenAQ sensor id of the pollutant measured | 3919 |
| location | name of location | Del Norte\-2178 |
| datetime | date and time in ISO\-8601 format with timezone offset of the measurement | 2021\-12\-16 01:00:00\+00:00 |
| lat | decimal degree (EPSG:4326\) representation of the latitude (Y) of the sensor. Minimum of \-90\. Maximum of 90\. | 35\.1353 |
| lon | decimal degree (EPSG:4326\) representation of the longitude (X) of the sensor. Minimum of \-180, Maximum of 180\. | \-106\.584702 |
| parameter | type of pollutant being reported | pm10 |
| unit | unit of the parameter | µg/m³ |
| value | the decimal value of the measurement | 42\.2 |


#### example file



```
location_id,sensors_id,location,datetime,lat,lon,parameter,units,value
2178,3919,Del Norte-2178,2023-02-22T01:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,14.0
2178,3919,Del Norte-2178,2023-02-22T02:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,4.0
2178,3919,Del Norte-2178,2023-02-22T03:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,7.0
2178,3919,Del Norte-2178,2023-02-22T04:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,6.0
2178,3919,Del Norte-2178,2023-02-22T05:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,5.0
2178,3919,Del Norte-2178,2023-02-22T06:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,9.0
2178,3919,Del Norte-2178,2023-02-22T07:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,20.0
2178,3919,Del Norte-2178,2023-02-22T08:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,28.0
2178,3919,Del Norte-2178,2023-02-22T09:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,19.0
2178,3919,Del Norte-2178,2023-02-22T10:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,26.0
2178,3919,Del Norte-2178,2023-02-22T11:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,127.0
2178,3919,Del Norte-2178,2023-02-22T12:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,318.0
2178,3919,Del Norte-2178,2023-02-22T13:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,241.0
2178,3919,Del Norte-2178,2023-02-22T14:00:00-07:00,35.1353,-106.584702,pm10,µg/m³,9.0
...


```

SNS Notification
----------------


An AWS SNS Topic is available for subscribing to S3 object creation events.


SNS ARN:



```
arn:aws:sns:us-east-1:817926761842:openaq-data-archive-object_created

```

To learn more about how to subscribe to SNS topics, view the [AWS SNS documentation](https://docs.aws.amazon.com/sns/latest/dg/sns-create-subscribe-endpoint-to-topic.html).


Update frequency
----------------


Files are written 72 hours after the end of day, i.e. 0:00 for the given location's timezone. Files may be retroactively patched if data are missing due to fetching error or from historical data scrape.


Examples
--------


To access large amounts of data from the S3 bucket from our computer's command line, the [AWS CLI](https://aws.amazon.com/cli/) is recommended. The AWS CLI profile must be configured to the `us-east-1` region for the `copy` command to work. We can configure the AWS CLI to use AWS credentials or optionally anonymously request using the `--no-sign-request flag`e.g. 


.aws/config



```
[default]
region = us-east-1
output = json

```

To copy all data from [location 2178](https://explore.openaq.org/locations/2178) during the year 2020 to a local directory named `data`:


Shell
```
aws s3 cp --no-sign-request s3://openaq-data-archive/records/csv.gz/locationid=2178/year=2020 data --recursive

```

To copy all data from AirNow in the United States to a local directory named `data`:


Shell
```
aws s3 cp --no-sign-request s3://openaq-data-archive/records/country=us data --recursive

```

To handle more complex queries, utilize the OpenAQ REST API to query specific location ids, sources and countries using geospatial queries and filtering.

Updated about 1 month ago 



---

