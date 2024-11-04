# HHA504_assignment_nosql_dbs
Working with Managed No-SQL Database

### 1. Start and Configure Databases
<img width="1421" alt="image" src="https://github.com/user-attachments/assets/44f4241c-4c05-468d-9025-4d8c5345ce1a">


- **MongoDB Atlas (Cloud):**
<img width="1393" alt="image" src="https://github.com/user-attachments/assets/3bdabd6e-3ec5-4a2a-9044-1d066eb5b5eb">

<img width="1315" alt="image" src="https://github.com/user-attachments/assets/63245568-6a90-4305-83ea-3a0e2ae1866b">


### 2. Explore BigQuery (GCP)
<img width="1093" alt="image" src="https://github.com/user-attachments/assets/b451d665-f348-4eaa-bb60-232b78a86d32">



### 3. Modify and Explore the Data in MongoDB Atlas and Redis Cloud
After completing the task of modifying and exploring healthcare data in MongoDB Atlas and Redis Cloud, I gained valuable insights into patient demographics and data structure. By filtering the dataset for patients older than 40 years, I uncovered trends related to prevalent health issues, common treatment plans, and potential gaps in care that could be addressed. This experience highlighted the importance of targeted healthcare strategies and reinforced the significance of maintaining proper data types, such as PatientID and VisitDate, to ensure data integrity and facilitate accurate queries.

Additionally, utilizing Redis Cloud for storing patient data as key-value pairs demonstrated the efficiency of this approach for quick data retrieval and updates, particularly in real-time scenarios that impact patient care. The ease of updating the treatment plan for PatientID=1 showcased how dynamic data management is crucial in healthcare applications. Through querying capabilities in both databases, I learned the strengths of MongoDB’s complex queries versus Redis’s high-speed lookups. Overall, this exercise underscored the critical role of data utilization in enhancing patient outcomes and informed decision-making in healthcare settings.

### 4. Describe Your Experience
In documenting my experience with the three services—BigQuery, MongoDB Atlas, and Redis Cloud—I found the setup process and configuration steps to be quite distinct for each platform. For **BigQuery**, I started by creating a Google Cloud account and navigating to the BigQuery interface. I uploaded the healthcare dataset and defined the schema, which involved specifying data types for each field. The process was straightforward, with helpful prompts guiding me through the steps. In **MongoDB Atlas**, I registered for an account and created a new database instance, but I encountered difficulties when trying to upload the dataset. I struggled with the conversion of the data into the required JSON format, and despite my efforts, I was unable to successfully upload the data into the database. The need to ensure that key fields were correctly formatted as unique identifiers and date types added complexity, making the process even more challenging.

Similarly, while setting up **Redis Cloud** was simple, I also faced challenges when attempting to upload the healthcare dataset. I found the interface to be minimalistic, which made it difficult to locate the necessary functions for data insertion. As a result, I was unable to upload the data as key-value pairs, which limited my ability to explore the platform's capabilities fully. In contrast, I found BigQuery’s interface to be intuitive and user-friendly, allowing for easy navigation through datasets and SQL-based queries. 

