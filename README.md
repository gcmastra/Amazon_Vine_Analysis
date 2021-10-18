# Amazon_Vine_Analysis
Module 16 Challenge

### Student Name: Christopher Mastrangelo 

The purpose of this challenge is to complete an "end to end" data download, ETL process, upload to AWS RDS, and interact with AWS from PostGres (pgAdmin).  The purpose is to show an end to end solution integrating multiple platforms, and answer some questions about the data.  This is to show completence in key skills important in data analysis utilizing cloud-based services. 

## Deliverable 1- Perform ETL on Vine Reviews

Performed these steps on thu dataset fpr "Outdoors" product reviews from 2015
- Extract- select a dataset and import into PySpark
- Transform the dataframe into four smaller dataframes that fit the schema of the four tables in pgAdmin
- Load (Upload) each Dataframe to the corresponding table in AWS RDS
- Confirm the tables are loaded correctly in pgAdmin

Here is the URL of the Vine review dataset I selected = "Outdoors products reviews from 2015"
url = "https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Outdoors_v1_00.tsv.gz"

Here is the first dataframe of revew_id data after selecting columns from the main dataframe and grouping/aggregating by customer_id.
The python (PySpark) code used is also shown . .  <br>
![image](https://user-images.githubusercontent.com/86205000/137646462-afc6eb92-0f20-418d-a498-4289a0e8019d.png)

Confirmation of successful data upload- here is the contents of the review_id_table from inside pgAdmin connected to AWS RDS database . . .  

![image](https://user-images.githubusercontent.com/86205000/137646697-5eb4e5b9-daf7-4990-bfb3-1defe337d4be.png)

Lets show all the dataframes before we move ahead to Deliverable 2

Data Frame # 2 - Products table

![image](https://user-images.githubusercontent.com/86205000/137649494-22b979b8-c5f5-4807-b826-f28696bbe4ad.png)

This is what the table looks like in pgAdmin after uploading the dataframe to AWS RDS

![image](https://user-images.githubusercontent.com/86205000/137649785-59e8191b-eca0-4602-86d9-992c2a073a59.png)




Data Frame # 3 - the review_id_table dataframe: 

![image](https://user-images.githubusercontent.com/86205000/137649464-9719b482-77ae-4581-b47b-a09fd4740bf4.png)

Here is the table in pgAdmin after uploading to AWS RDS

![image](https://user-images.githubusercontent.com/86205000/137651107-61cc50fa-75a0-4f34-8bcf-dbb516ce4f48.png)




Table # 4 - The vine_df dataframe

Here is a screen capture of the  select statement in the code as well as the data frame header . . . 

![image](https://user-images.githubusercontent.com/86205000/137649423-d58c35fc-15a3-402b-8e71-e6961faeb3ff.png)

Here is what the vine_table looks like after upload to AWS - there are 2,302,041 rows in the table! 

![image](https://user-images.githubusercontent.com/86205000/137650510-aecfa01a-cc9f-468c-adde-cd5a1309cce4.png)

## Next - Deliverable #2

Additional text will appear here. 

## Deliverable #3 is this README file.



