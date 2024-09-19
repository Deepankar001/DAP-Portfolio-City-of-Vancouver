# Descriptive Analysis of 311-Service request closed by providing services 

## Overview

The City of Vancouver is improving its services with a *Data Analytics Platform (DAP), enabling smarter decision-making. My role in this project focused on analyzing the **311-Service Request closed   **by providing services*

## Objective

The main goal of this project was to *identify the APR of total service request closed in 2023 and 2024 focusing on closure reason “Service Provided”

## Dataset

The dataset all the requests closed records from Vancouver, spanning March 2023 to Augustr 2024. It includes the following key features:

- *Department*: Type of department.
- *Service request type*: Request type.
- *Status*: Status of service.
- *Closure Reason*: reason of service request closed.
- *Service request open timestamp*: Time of request open.
- *Service request close year*: Time of request close.
-*Service request close year*: Year of request close.
-*Last modified timestamp*: Last Updated time of request closed.

-*Address*: Location of request received.
-*Local Area*: Local area of request received.
-*Channel*: Channel through which request received.
-*Latitude*: Geographical region of that area.
-*Longitude*: Geographical region of that area.

Dataset link: [*311-Servide Requests dataset*](https://opendata.vancouver.ca/explore/dataset/3-1-1-service-requests/export/?disjunctive.department&disjunctive.service_request_type&disjunctive.status&disjunctive.closure_reason&disjunctive.local_area&disjunctive.channel)

<![DAP](https://github.com/user-attachments/assets/02821cff-9ee8-4abb-8a06-4fed1d9b578e)>


## Data Analytical Question Formulation

### Goal
To *analyze the APR  of total request closed* for the years 2023 and 2024.

## Methodology

### 1. Data Collection and Storage

- *AWS S3*: The datasets for year 2023 and 2024 stored in S3 bucket.
  
### 2. Data Cleaning and Preprocessing

- *AWS DataBrew*: To clean up the data and add missing values in the address, longitude and latitude cloumns .

### 3. ETL Pipeline

- *AWS Glue*: Used Glue Feature to transform the data and that high quality data stored in the curated folder.
<![ETL](https://github.com/user-attachments/assets/66daeed5-f71b-48bf-b37f-4441c6d3e51e)>

### 4. Data Analysis

- *AWS Athena*: I used Athena services to  get the data by running SQL queries from the data which was generated in data product folder. 

Here is the exact query used to retrieve the necessary data from Athena:

sql
SELECT * FROM cityofvancouver_311servicerequest_table1_deepankar;


## Data Visualization

- *Excel*: Bar charts and histograms were created from the data retrieved by running SQL queries.

*Visualization 1*: Histogram of Lost Breed Rates %

<img width="1441" alt="Screenshot 2024-09-18 at 2 57 03 AM" src="https://github.com/user-attachments/assets/53c0feb6-7a56-4f43-ab3b-41eb860e91f9">


## Publishing and Web Hosting

- *AWS EC2*: The result and analysis based on these queries in the form of graph were published on Webserver

## Data Protection and Governance

- *AWS Key Management Service (KMS)*: Encryption was applied on the data which was in Storage bucket by using KMS.
- *Data Replication*: Replication was applied to get the backup of whole data in the backup bucket 
- *AWS Glue*: Again ETL pipeline was made and resulted files were stored in the trusted folder. 

## Data Monitoring

- *AWS CloudTrail*: CloudTrail was used to track API calls and user activities in the AWS environment, helping to improve auditing and security.
- *AWS CloudWatch*: CloudWatch  Tracked performance and alarms were created.

## Data Insights and Findings

APR of total closed requests count for the year 2023 and 2024 was 60.75%

## Tools and Technologies Used

- *AWS S3*: For data storage.
- *AWS DataBrew*: For cleaning and structuring the dataset.
- *AWS Glue*: To transform the data make ETL pipeline for High quality data .
- *AWS Athena*: For Analyzing data and fetch data from datasets.
- *Excel*: For visualizing the data using charts and histograms.
- *AWS EC2*: For Publishing the result on Webserver.
- *AWS Key Management Service (KMS)*: For encryption and data protection.
- *AWS CloudTrail*: For monitoring and scaling.
- *AWS CloudWatch*: For tracking, creating Alarm and health check of services 
## Deliverables

1. Reports summarizes all the tools and techniques used to find the APR.
2. Histograms and bar graphs for publishing the data and analysing.

## Conclusion
This project analyze the APR of total service request closed by providing services in Vancouver area. The only closure reason I have taken is service provided and neglected other reasons like escalated, not resolved. Using AWS services, the project achieved scalability and efficiency while also ensuring high-level security and strong data governance.

