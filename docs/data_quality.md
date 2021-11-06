# Data quality

In this document, I will explain how to define data quality: attributes, measures, and metrics?

## 1 What is data quality? 

Data quality is the state of data, which is tightly connected with its ability (or inability) to solve business tasks.
The state of data can be either “good” or “bad”, depending on to what extent data corresponds to the following attributes:
- Accuracy
- Auditability
- Completeness
  
- Consistency
- Credibility
- Orderliness
- Timeliness
- Uniqueness

### 1.1 Accuracy
- Definition: Accuracy refers to the correctness of data, that is, whether the recorded value is in conformity with the 
actual value in reality, with respect to its intended use.
- Good example: You have a user named “John Doe”, and in the CRM database record is also “John Doe”.
- Bad example: You have a user named “John Doe”, and in the CRM database record is also “Jane Doe”.
- Measurement Metric: The ratio/percentage of the error data.

### 1.2  Auditability
- Definition: Auditability indicates that whether the user can trace all modifications of a dataset (from creation, through modification/transformation, till deletion).
- Good example: Someone changes the birth date of user “John Doe”, we know who did the change, when the change has been made, and what lines are changed.
- Bad example: Someone changes the birth date of user “John Doe”, it’s impossible to know who change it.
- Measurement Metric: The ratio/percentage of the missing metadata that describes the data modification process (include creation and deletion).

### 1.3  Completeness
- Definition: Completeness indicates that whether the record has all required values. Note in some cases the null value makes sense and should not consider as incomplete data. For example, some weather station does not have snow depth measurement equipment, so they use null in the “snow_depth” column to indicate that. Because put “value 0” is miss leading.  
- Good example: All rows of the column birth date of user table have value.
- Bad example: The birth date of user “John Doe” is unknown, because the cell is null.
- Measurement Metric: The number of missing data.


### 1.4  Consistency
- Definition: Consistency indicates that whether there are contradictions inside your data set.  
- Good example: All user age values of user “John Doe” from all tables are the same.
- Bad example: The age of user “John Doe” in the marketing table is different from the table of CRM.
- Measurement Metric: The number of inconsistencies.

### 1.5  Credibility
- Definition: Credibility indicates the trustworthiness of the source as well as its content
- Good example: We know who is the data provider, and how the data is constructed.
- Bad example: We have no idea who produced the data, and how the data is constructed.
- Measurement Metric: The ratio/percentage of the missing metadata that describes the data provider and how data is constructed.

### 1.6 Orderliness
- Definition: Orderliness indicates whether the ingested data set respected the required format, structure, and schema.
- Good example: Data governance defines that date must respect ISO 8601. All the date values inside ingested data respect ISO 8601
- Bad example: The date values of the CRM database do not respect ISO 8601.
- Measurement Metric: The ratio/percentage of the data that does not respect the defined format, structure, and schema.

### 1.7 Timeliness
- Definition: Timeliness indicates that the recorded value is up-to-date for the task at hand.
- Good example: The marketing team wants to send a mail to users on their registered address. All users’ address is 
  up-to-date at the time of sending emails. All users receive the mail.
- Bad example: Some addresses of users are out-of-date at the time of sending emails. Some users did not receive the mail.
- Measurement Metric: Number of records that are out-of-date.

### 1.8 Uniqueness
- Definition: Uniqueness indicates that one record with specific details only appears once in the database.
- Good example: We only have one record for the user’s name, address, and birthdate.
- Bad example: We have multiple duplicated records for the user’s name, address, and birthdate.
- Measurement Metric: Number of duplicated data and how many times the data has been duplicated.

## 2. Common data quality metric
- The ratio of data to errors: monitors the number of known data errors compared to the entire data set. 
  
- The number of empty values: counts the times you have an empty field within a data set.
   
- Data time-to-value: evaluates how long it takes you to gain insights from a data set. There are other factors influencing it, yet the quality is one of the main reasons this time can increase.
   
- Data transformation error rate: this metric tracks how often a data transformation operation fails.
   
- Data storage costs: when your storage costs go up while the amount of data you use remains the same, or worse, decreases, it might mean that a significant part of the data stored has a quality to low to be used.

## 3. Data quality management: process stages described
   
### 3.1 Define data quality thresholds and rules
### 3.2 Assess the quality of data
### 3.3 Resolve data quality issues
### 3.4 Monitor and control data quality continuously


Note:
A data schema is simply a type of data structure. A data structure is a representation of the arrangement, relationships, and contents of data  in an organization’s data resource
https://www.scnsoft.com/blog/guide-to-data-quality-management