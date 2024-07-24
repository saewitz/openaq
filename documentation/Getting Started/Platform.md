Implementation
--------------


OpenAQ aggregates air quality data from disparate sources around the world to provide access to these data in a single location.


![](https://files.readme.io/43d1b8f-platform-diagram.png "platform-diagram.png")


OpenAQ uses an ETL (Extract\-Transform\-Load) process to ingest and harmonize air quality data. The data process has four main components: fetch, storage, presentation and archive.


### Fetch


After identifying a source of air quality data, a fetch adapter is developed to pull data from the source and parse the data into a standard file format. OpenAQ fetch scripts range from HTML scrapers and FTP directory scanners to REST API scrapers, depending on the source of the data.


Currently data fetching is split between two repositories:


* [https://github.com/openaq/openaq\-fetch](https://github.com/openaq/openaq-fetch) — primarily reference grade/government sources written in NodeJS and runs on AWS Fargate processes.
* [https://github.com/openaq/openaq\-lcs\-fetch](https://github.com/openaq/openaq-lcs-fetch) — a newer generation of fetch processes, primarily fetching air sensor sources. Written in NodeJS and runs on AWS lambda processes.


### Storage


Data is stored in a PostgreSQL database using the [TimeScale](https://www.timescale.com/) extension for added time series functionality and [PostGIS](https://postgis.net/) for geospatial functionality. 


View the source code for the database on GitHub [(https://github.com/openaq/openaq\-db](https://github.com/openaq/openaq-db)


### Presentation


OpenAQ provides a REST API for programmatic access of the database.


Read more in the [API section](/docs/about-api) below or in the [API Reference](/reference) for detailed API reference.


View the source code for the REST API on GitHub [https://github.com/openaq/openaq\-api\-v2](https://github.com/openaq/openaq-api-v2)


### Archive


After insertion into the database, data is stored in a publicly available AWS S3 bucket via the [Open Data on AWS](https://aws.amazon.com/opendata) program.

Updated about 1 month ago 



---

