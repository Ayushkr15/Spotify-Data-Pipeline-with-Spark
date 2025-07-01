A serverless ETL pipeline that fetches Spotify data daily, processes it with Apache Spark on AWS Glue, and loads it into Snowflake for analytics.

# Project Overview
This project automates the flow of Spotify music data from extraction to analytics:

## Extract:
- AWS CloudWatch triggers a Glue Python job daily.
- The job pulls playlist data from the Spotify API and stores raw JSON in Amazon S3.

## Transform:
- An S3 event triggers a Glue Spark job.
- Spark scripts clean, normalize, and split the data into albums, artists, and songs tables, then save them as CSVs in S3.

## Load:
- Snowpipe automatically loads transformed data from S3 into Snowflake.
- Data in Snowflake is ready for analysis in Power BI.

# Architecture Diagram
![Architecture](https://github.com/user-attachments/assets/a9486279-8ae7-4947-8234-41e39385991e)

# Key Features:
1. Fully automated, serverless workflow
2. Scalable data processing with Apache Spark
3. Real-time analytics with Snowflake

