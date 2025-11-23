## End-to-End Data Engineering Project on Azure: Hospital Patient Records

This project demonstrates how to build an end-to-end data pipeline in Azure using the example of patient encounters to a Hospital. The goal is to show how raw data moves through the stages of ingestion, transformation, storage, and reporting using Azure services.

## Solution Architecture
![Solution Architecture](https://drive.google.com/file/d/1Y8QfGV8xLqBADxhb8lTy_Wk1M90Mcoo9/view)

1. The data (CSV files) is initially stored on the web (GitHub, in this case). 
2. Use Azure Data Factory (ADF) to ingest the data and bring it into the *raw layer/folder* of Azure Data Lake Storage (ADLS) Gen2.
3. The data is then transformed using Azure Data Flows and subsequently, ADF is used to run the pipeline(s) to move data from the raw folder to the *processed folder* in ADLS Gen2.
4. The transformed data is finally copied into tables in Azure SQL DB via ADF.
5. Finally, Azure SQL DB connects to Power BI to help the Data Analyst create reports for the business users.

## Services Used

-   **Azure Data Factory:** For copying and ingesting the data.
    
-   **Data Flows:** For transforming raw data into structured, meaningful datasets.
    
-   **Azure Data Lake Storage Gen2:** For storing raw and transformed data.
    
-   **Azure SQL Database:** For structured storage and reporting queries.
    
-   **Power BI:** For visualizing key business metrics.

  ## Dataset Description

  - **patients.csv:** Contains information about the patients that visited Massachusetts General Hospital. The file contains columns like Id (unique, not null), birth date, death date (if present), name, marital status, race, ethnicity, gender, address, etc.
  - **payers.csv:** Contains information about the Insurance that the patients used on their trip to the Hospital. Alongside *NO_INSURANCE*, the file contains information about the various Insurance providers and their contact details.
  - **encounters.csv:** 
