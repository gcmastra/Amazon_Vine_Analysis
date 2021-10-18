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

![image](https://user-images.githubusercontent.com/86205000/137651107-61cc50fa-75a0-4f34-8bcf-dbb516ce4f48.png)

Lets show all the dataframes before we move ahead to Deliverable 2

Data Frame # 2 - Products table

![image](https://user-images.githubusercontent.com/86205000/137649494-22b979b8-c5f5-4807-b826-f28696bbe4ad.png)

This is what the table looks like in pgAdmin after uploading the dataframe to AWS RDS

![image](https://user-images.githubusercontent.com/86205000/137649785-59e8191b-eca0-4602-86d9-992c2a073a59.png)


Data Frame # 3 - the review_id_table dataframe: 

![image](https://user-images.githubusercontent.com/86205000/137649464-9719b482-77ae-4581-b47b-a09fd4740bf4.png)

Here is the table in pgAdmin after uploading to AWS RDS

![image](https://user-images.githubusercontent.com/86205000/137669350-f736ed84-ad73-4505-b22d-800ae9d85f38.png)


Table # 4 - The vine_df dataframe

Here is a screen capture of the  select statement in the code as well as the data frame header . . . 

![image](https://user-images.githubusercontent.com/86205000/137649423-d58c35fc-15a3-402b-8e71-e6961faeb3ff.png)

Here is what the vine_table looks like after upload to AWS - there are 2,302,041 rows in the table! 

![image](https://user-images.githubusercontent.com/86205000/137650510-aecfa01a-cc9f-468c-adde-cd5a1309cce4.png)

## Deliverable #2 - Vine Review Analysis 

Four new data frames were created based on the vine_table data frame shown above.
The definition and contents of these dataframes can be found in the Vine_Review_Analysis.ipynb notebook file.

Here is a screen capture of the header of one of the dataframes (reviews with total_votes > 20 and vine == Y) . . .

![image](https://user-images.githubusercontent.com/86205000/137665533-41381cc0-aed8-406d-b04e-d6613072e78c.png)

Here is a summary table of the results for the "Outdoors" product category . . .

![image](https://user-images.githubusercontent.com/86205000/137663455-d6c0fe57-8614-4e99-99a5-09b5041e5e70.png)

Can we conclude that paid reviews are more biased towards "5 stars" positive reviews vs non-paid reviews?  The data does NOT support this conclusion. 
- The difference in the ratio of 5 star review is approximately 52 percent for both paid and non-paid reviews
- Should a difference of  a fraction of one percent be considered statistically significant enough to indicate bias? I do not think so

Alternative approaches?  In this analysis we looked at reviews for "Outdoors" products only. One idea I have is to look at other product categories and perform a similar analysis, to see if the percentages might be different in different product categories.  Then  a comparison could be done showing the ratios for multiple categories, and deciding which prduct category has the more bias than the others. 


## Deliverable #3 is this README file.

### Technical Issues Encountered

Here are some issues I had during this activity

- The file size of the vine_table dataframe for the dataset I used was too big to upload to GitHub (size 54.4 MB > 50 MB which is the recommended limit on GitHub)
- In Deliverable 1, all dataframes were working without errors when I took screen captures used in the README file, but after I began uploading the dataframes to AWS, I began to get errors which I believe were caused by the runtime kernal exceeding its buffer limit.  
- This resulted in some cells which previously ran with no errors to begin experiencing errors. 
- As a result, I had to split the COLAB notebooks into two versions, a V1 and a V2, in order to complete the uploads without losing any data
- Specific issues with each cell are explained in the comments inside the two notebook files uploaded
- I solved as many of the issues as I could when I encountered them, but I had to use a few workarounds to complete the activity by the deadine
