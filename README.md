# Amazon_Vine_Analysis
Module 17 - Big Data
## The Data
Thus dataset contains all product reviews of Vine customers, which is a serve the allows sellers to receive require reviews for their products sold. This helps with updates and quality of the products. Of the 50 different datasets o choose from, this analysis focuses on the personal care products. With this data, we will utilize PySpark to perform ETL (extract, transform, and load). Additionally, we will use AWS RDS instances, pgAdmin, Pandas, and SQL to perform proper analysis. The goal is to determine if there is any bias toward the reviews of certain products and from certain vine members in the dataset.
## The Results
### Performing ETL on Amazon Product Reviews
We have created a AWS RDS instance to examine the personal care products dataset. The variables included in this dataset (as well as the other 49 datasets) are marketplace, customer id, review id, product id, product parent, product title, product category, etc. (see all variable below in the table below)
Next, we will run a query to create four different tables of the dataset which are called customers_table, products_table, review_id_table, and vine_table. We transformed the dataset into four DataFrames that match the schema in the pgAdmin tables. Some functions that were used to conduct analysis include groupby(), agg(), count() withColumnRenamed(), etc. 
---
![table_1](https://user-images.githubusercontent.com/119131202/230527846-d020a73d-7b50-496b-a899-af3b87e4c8a6.PNG)
---
We first grouped the customer id column, the counted all customer ids. This new table can be seen below:
---
![customer_table](https://user-images.githubusercontent.com/119131202/230527916-9001b2af-044a-48de-9f0f-c37ca79ef1cf.PNG)
---
To create the products table, we selected the product id and product title columns, then dropped the duplicates to retrieve unique values. This table is shown below:
---
![product_table](https://user-images.githubusercontent.com/119131202/230527936-c5f27fea-ca5c-49c7-a35a-f6ee913ff5b9.PNG)
---
To create the review id table, we selected the columns that are in the pdAdmin table, which includes review id, customer id, produtct id, product parent, and review data columns. Next, the review date column was converted to a date type. This table is shown below:
---
![vine_table](https://user-images.githubusercontent.com/119131202/230527957-3af39cb1-e97a-401b-b0e7-43ccbbff4dda.PNG)
---
To create the vine table, we selected columns review id, star rating, helpful votes, total votes, vine, and verified purchase columns. This table is shown below:
---
![review_table](https://user-images.githubusercontent.com/119131202/230527986-3b1299f1-5c3b-47e0-afc8-7b3258d1b89a.PNG)
---
### Bias of Vine Reviews
With the help of PySpark, Pandas, SQL, and filtering options, we will determine if there is bias on the product reviews. We must first filter the data and grab all rows where the total vote count is greater than or equal to 20. Next, we will filter once again to retrieve all rows where the number of helpful votes divided by total votes is greater than or equal to 50%. Next, we will retrieve all rows that contained a written review (which is a process required for a vine member). We will repeat this process, but we will find the rows that do not have a written review this time (meaning they are not a vine member).
---
Additionally, we will determine the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types of review (paid vs. unpaid).
---
When analyzing the personal care products, I found that there was a total of 127 paid reviews, and of those paid reviews, there were 36 5-star reviews (28.3%). There were 41279 unpaid reviews, of which, 14284 were 5-star reviews (34.6%). This shows that not many people are giving personal care products a 5-star review, whether they were paid or unpaid.
---
#### Data Anlysis Performed by Katelin Catton
#### 4/6/2023






