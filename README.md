## End-to-End Data Engineering Project on Azure: Hospital Patient Records

This project demonstrates how to build an end-to-end data pipeline in Azure using the example of patient encounters to a Hospital. The goal is to show how raw data moves through the stages of ingestion, transformation, storage, and reporting using Azure services.

## Solution Architecture
![Solution Architecture](https://github.com/snowydata-sarthak/Hospital-Patient-Records/blob/340e642bd818258f90f603ab9545125195d69d31/Solution%20Architecture.png)

1. The data (CSV files) is initially stored on the web (GitHub, in this case). 
2. Azure Data Factory (ADF) is used to ingest the data and bring it into the *raw layer/folder* of Azure Data Lake Storage (ADLS) Gen2.
3. The data is then transformed using Azure Data Flows and subsequently, ADF is used to run the pipeline(s) to move data from the raw folder to the *processed folder* in ADLS Gen2.
4. The transformed data is copied into tables in Azure SQL DB via ADF.
5. Finally, Azure SQL DB connects to Power BI to help the Data Analyst create reports for the business users.

## Services Used

-   **Azure Data Factory:** For copying and ingesting the data.
    
-   **Data Flows:** For transforming raw data into structured, meaningful datasets.
    
-   **Azure Data Lake Storage Gen2:** For storing raw and transformed data.
    
-   **Azure SQL Database:** For structured storage and reporting queries.
    
-   **Power BI:** For visualizing key business metrics.

  ## Dataset Description

  - **patients.csv:** Contains information about the patients that visited Massachusetts General Hospital. The file contains columns such as Id (unique, not null), birth date, death date (if applicable), name, marital status, race, ethnicity, gender, address, and other relevant information.
  - **payers.csv:** Contains information about the Insurance that the patients used on their trip to the Hospital. Alongside *NO_INSURANCE*, the file contains information about the various Insurance providers and their contact details.
  - **encounters.csv:** Contains information about the encounters/visits of the patient to the Hospital. Each encounter contains an Id (unique, not null), the start & stop time of the encounter, patient id, encounter class (ambulatory, outpatient, wellness, etc.), information about costs, and other similar details.
  - **procedures.csv:** Each encounter involves a patient going through some procedures. This file contains information about the procedures performed during a particular encounter. This file also contains the start & stop time of the procedure, patient information, encounter id, and finally details about the performed procedure (Intramuscular injection, Colonoscopy, Electrical cardioversion, etc.)

## Learning Objectives

1. How to build pipelines that satisfy business needs and make the downstream users' lives easier
2. How to orchestrate data pipelines in Azure
3. How to use Data Flows for transformation
   - Performing data quality/validation checks
   - Window Function transformation
   - Hashing and masking confidential data
   - Renaming columns
4. How to move data between Lake and SQL Database
5. How to build a basic reporting layer

## Link to the Project Video

[Azure End-to-End Data Engineering Project 2025 (From SCRATCH!) | Azure Data Factory + ADLS + SQL DB](https://youtu.be/ZXAUHyMQ5VI)
