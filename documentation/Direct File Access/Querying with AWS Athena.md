AWS Athena provides a powerful SQL interface to query data from the OpenAQ Archive S3 bucket. 



> 🚧
> -
> 
> To use AWS Athena, an Amazon Web Services (AWS ) account is required and is subject to AWS pricing for data; see more about pricing on the [Athena pricing page](https://aws.amazon.com/athena/pricing/)



> 📘
> -
> 
> This guide is not meant to replace a thorough tutorial of AWS Athena. We recommend reading the official [Athena documentation](https://docs.aws.amazon.com/athena/index.html).


To start create a table.


Shell
```
CREATE EXTERNAL TABLE `openaqMeasurements`(
  `location_id` INT,
  `sensors_id` INT,
  `location` STRING,
  `datetime` STRING,
  `lat` float,
  `lon` float,
  `parameter` STRING,
  `units` STRING,
  `value` float
)
PARTITIONED BY (provider string, country string, locationid string, year string, month string)
ROW FORMAT DELIMITED
  FIELDS TERMINATED BY ','
  ESCAPED BY '\\'
  LINES TERMINATED BY '\n'
LOCATION
  's3://openaq-data-archive/records/csv.gz/'
  TBLPROPERTIES ('skip.header.line.count'='1')

```

The Athena table definition defines all the columns and partitions for the data file in the OpenAQ Archive. The Apache Hive Partitioning format help limit objects scans throughout the bucket, reducing cost and time for querying. Partitions are optional and are typically best optimized on a case by case basis. Read more about Athena partitioning on S3 on the [AWS docs](https://docs.aws.amazon.com/athena/latest/ug/partitions.html).


Example
-------


Loading all partitions can be very slow, so for this example we will partition manually for a single location and month that we are interested in:



```
ALTER TABLE openaqMeasurements ADD
  PARTITION (year='2022', month='12',locationid='2178');

```

Now with the table defined we can query the dataset using the SQL. To get all measurements for a single location (locationid 2178\) in a single month (December 2022\) we can use the following:


SQL
```
SELECT parameter, value, from_iso8601_timestamp(datetime) AS datetime FROM openaqMeasurements WHERE locationid='2178' AND year='2022' AND month='12'

```

This will return all measurements for December 2022 in this following form:



```
"parameter","value","datetime"
"pm10","30.0","2022-12-12 01:00:00.000 -07:00"
"pm10","18.0","2022-12-12 02:00:00.000 -07:00"
"pm10","17.0","2022-12-12 03:00:00.000 -07:00"
"pm10","10.0","2022-12-12 04:00:00.000 -07:00"
"pm10","10.0","2022-12-12 05:00:00.000 -07:00"
"pm10","26.0","2022-12-12 06:00:00.000 -07:00"
"pm10","13.0","2022-12-12 07:00:00.000 -07:00"
"pm10","13.0","2022-12-12 08:00:00.000 -07:00"
"pm10","11.0","2022-12-12 09:00:00.000 -07:00"
"pm10","16.0","2022-12-12 10:00:00.000 -07:00"
"pm10","16.0","2022-12-12 11:00:00.000 -07:00"
"pm10","24.0","2022-12-12 12:00:00.000 -07:00"
"pm10","11.0","2022-12-12 13:00:00.000 -07:00"
"pm10","19.0","2022-12-12 14:00:00.000 -07:00"
"pm10","12.0","2022-12-12 15:00:00.000 -07:00"
...

```
Updated about 1 month ago 



---

