# Amazon_Vine_Analysis
Module 16 Challenge

### Student Name: Christopher Mastrangelo 

## Deliverable 1- preform ETL on Vine Reviews

Performed these steps on thu dataset fpr "Outdoors" product reviews from 2015
- 1. Extract
- 2. Transform the dataframe into four smaller dataframes that fit the schema of the four tables in pgAdmin
- 3. Load (Upload) each Dataframe to the corresponding table in AWS RDS
- 4. Confirm the tables are loaded correctly in pgAdmin


Here is the first dataframe of revew_id data after selecting columns from the main dataframe and grouping/aggregating by customer_id.
The python (PySpark) code used is also shown . .  <br>
![image](https://user-images.githubusercontent.com/86205000/137646462-afc6eb92-0f20-418d-a498-4289a0e8019d.png)

Confirmation of successful data upload- here is the contents of the review_id_table from inside pgAdmin connected to AWS RDS database . . .  

![image](https://user-images.githubusercontent.com/86205000/137646697-5eb4e5b9-daf7-4990-bfb3-1defe337d4be.png)


