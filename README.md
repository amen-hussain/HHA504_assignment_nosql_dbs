# HHA504_assignment_nosql_dbs
Working with Managed No-SQL Database


## Fake dataset to use: 

- data set url: [https://raw.githubusercontent.com/hantswilliams/HHA-504-2024/refs/heads/main/other/module8/module8_nosql_hw.csv](https://raw.githubusercontent.com/hantswilliams/HHA-504-2024/refs/heads/main/other/module8/module8_nosql_hw.csv)

```csv
PatientID,Name,Age,Gender,DiagnosisCode,VisitDate,Hospital,TreatmentPlan,FollowUpDate
1,John Doe,45,M,M54.5,2024-09-10,Stony Brook Hospital,Physical Therapy,2024-09-20
2,Jane Smith,29,F,E11.9,2024-08-15,Stony Brook Hospital,Insulin,2024-09-15
3,Bob Johnson,65,M,I10,2024-10-01,Long Island Clinic,Hypertension Medication,2024-11-01
4,Alice Williams,50,F,J45.909,2024-07-22,Southampton Hospital,Bronchodilators,2024-08-22
5,Michael Brown,37,M,G43.909,2024-06-12,Stony Brook Hospital,Triptans,
6,Susan Davis,54,F,I25.10,2024-05-10,Stony Brook Hospital,Statins,2024-06-10
```

- Dataset Explanation
  - *PatientID*: Unique identifier for each patient (integer).
  - *Name*: Patient's full name (string).
  - *Age*: Age of the patient (integer).
  - *Gender*: Gender of the patient (string: M or F).
  - *DiagnosisCode*: ICD-10 code representing the patient’s diagnosis (string).
  - *VisitDate*: Date of the hospital visit (YYYY-MM-DD format).
  - *Hospital*: Name of the hospital or clinic where the visit took place (string).
  - *TreatmentPlan*: The prescribed treatment plan for the patient (string).
  - *FollowUpDate*: Date for a follow-up visit, if applicable (YYYY-MM-DD format).

## Instructions

### 1. Start and Configure Databases
<img width="1421" alt="image" src="https://github.com/user-attachments/assets/44f4241c-4c05-468d-9025-4d8c5345ce1a">


- **MongoDB Atlas (Cloud):**
  - Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) and register for the free tier using your Stony Brook email.
  - Create a new database instance and configure it with basic settings.
  - Insert the provided healthcare dataset into a collection, ensuring each row is converted to a JSON document.
  - Document the steps and connection details.
  - **Hints**:
    - Each row in the CSV file corresponds to a document in MongoDB.
    - You’ll need to convert the CSV into JSON format, which could look like this for one patient:
      ```json
      {
        "PatientID": 1,
        "Name": "John Doe",
        "Age": 45,
        "Gender": "M",
        "DiagnosisCode": "M54.5",
        "VisitDate": "2024-09-10",
        "Hospital": "Stony Brook Hospital",
        "TreatmentPlan": "Physical Therapy",
        "FollowUpDate": "2024-09-20"
      }
      ```
    - You can use python to help convert it into json-like format: 
      - Example:
        ```python
        # Convert the DataFrame to a list of dictionaries (JSON-like)
        data = df.to_dict(orient='records')
        ```
      - Then using the `pymongo` library to insert the data into MongoDB.
        ```python
        # Insert the data into the MongoDB collection
        collection.insert_many(data)
        ```
mongodb+srv://amenhussain:<db_password>@amen-test.zjdgm.mongodb.net/
<img width="1393" alt="image" src="https://github.com/user-attachments/assets/3bdabd6e-3ec5-4a2a-9044-1d066eb5b5eb">


- **Redis Cloud:**
  - Go to [Redis Cloud](https://redis.io/cloud/) and sign up for a free tier account using your Stony Brook email.
  - Set up a new Redis database instance.
  - Use `PatientID` as the key and the rest of the patient data as the value (either as a serialized JSON string or separate fields).
  - Document the process and connection details.
  - **Hints**:
    - Redis is a key-value store, so you'll need to treat the `PatientID` as the unique key, with the patient data being the value.
    - Example in python, using the `redis` library: 
      ```python

      df = pd.read_csv('file.csv')

      # Connect to Redis
      r = redis.StrictRedis(
          host='your_redis_host',
          port='your_redis_port',
          password='your_redis_password',
          decode_responses=True
      )

      for _, row in df.iterrows():
          patient_data = row.to_dict()
          r.set(patient_data['PatientID'], json.dumps(patient_data))
        ```

### 2. Explore BigQuery (GCP)
- **BigQuery:**
  - In the Google Cloud Console, run a simple SQL query against the dataset you uploaded:
      ```sql
      SELECT * FROM `your_project_id.your_dataset_id.your_table_id` WHERE Age > 40
      ```
  - Monitor the usage and cost associated with running the query.


### 3. Modify and Explore the Data in MongoDB Atlas and Redis Cloud
- **MongoDB Atlas**:
  - Insert the dataset into MongoDB Atlas, converting each row into a JSON-like document.
  - Ensure fields like PatientID and VisitDate are treated appropriately (i.e., unique identifiers and date types).
  - Run a simple query to retrieve patient data based on a condition (e.g., `Age > 40`).

- **Redis Cloud**:
  - Insert key-value pairs where the PatientID is the key, and the rest of the patient data is the value.  
  - For example, retrieve the data for `PatientID=1`, then update the `TreatmentPlan` value.
  - Explore Redis's capabilities to update and query the dataset, e.g., retrieving all data for `PatientID`=1.


### 4. Describe Your Experience
- For each of the three services (BigQuery, MongoDB Atlas, Redis Cloud), document your experience creating and working with the healthcare dataset:
  - Describe the setup process and any configuration steps.
  - Share your reflections on the interface and usability of each platform.

### 5. Submit Your Work
- Create a Markdown document that includes:
  - Screenshots of the database creation and configuration process in BigQuery, MongoDB Atlas, and Redis Cloud.
  - The SQL query run in BigQuery and the results.
  - Documentation of your experience and reflections on working with each platform (BigQuery, MongoDB Atlas, Redis Cloud).
  
- Commit and push this Markdown document, along with the screenshots and query results, to your GitHub repository.

## Deliverables
- A Markdown document in a GitHub repository called `HHA504_assignment_nosql_dbs` that includes:
  - Screenshots of database creation and configuration for BigQuery, MongoDB Atlas, and Redis Cloud.
  - BigQuery dataset creation and query results.
  - Reflections on working with each of the three platforms.
