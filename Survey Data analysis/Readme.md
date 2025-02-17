This dataset contains information from a survey conducted by an YouTube Channel named 'Chandoo'. I have taken it as reference to showcase my datacleaning skills in PowerBI

On initial observation I have found some columns to be redundant as they do not contain any data. Columns such as Browser, OS, City Country, Referrer are redundant. Further, email column
is deleted as well becuase there is no useful information in it

Coming to actual cleaning of values columns - Q1, Q4, Q5, Q11 needed significant cleaning 

Data cleaning steps I have worked on for the dataset are:
1. Name with different representation. For example Ecommerce is represented as E-comm, ecommerce, ... etc
   ![image](https://github.com/user-attachments/assets/2eea67e1-00e1-4aa3-b110-7542fc0f7914)

2. Incomplete name, name with additional spaces
   ![image](https://github.com/user-attachments/assets/073cc92b-f13c-4061-ac5b-024df0a57003)

4. Salary column where it was represented as a range and in text format. So, numerical data is extracted and average salary is calculated
   ![image](https://github.com/user-attachments/assets/0542618e-56b7-439a-8b3c-0cf795aafff6)
 

