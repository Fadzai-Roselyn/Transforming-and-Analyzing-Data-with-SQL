# Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
Get hands on and familar with SQL

Learn about query strucruring and data analysis with SQL

Generate questions from the data and also answer business questions from the data

## Questions to answer;
<li>Find out the products with sentiment score of 0.7 to 1 and those with a sentiment score less than 0.3
<li>Which products have the highest restocking lead time? Give the top 10
<li>Based on the various ways in which people visit the ecommerce site, which channel grouping is responsible for the most visits? Show how the other groupings compare
<li>Which cities and countries have the highest level of transaction revenues on the site?
<li>What is the average number of products ordered from visitors in each city and country?
<li>Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?
<li>What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?
<li>Can we summarize the impact of revenue generated from each city/country?

## Process
i. Creating the ecommerce database
ii. Creating tables, example;


     CREATE TABLE all_sessions (
     
  fullVisitorId NUMERIC,
  
  channelGrouping VARCHAR,
  
  time_ VARCHAR,
  
  country VARCHAR,
  
  city VARCHAR,
  
  totalTransactionRevenue NUMERIC,
  
  transactions NUMERIC,
  
  timeOnSite NUMERIC,
  
  pageviews INTEGER,
  
  sessionQualityDim NUMERIC,
  
  date DATE,
  
  visitId NUMERIC,
  
  type VARCHAR,
  
  productRefundAmount NUMERIC,
  
  productQuantity NUMERIC,
  
  productPrice NUMERIC,
  
  productRevenue NUMERIC,
  
  productSKU VARCHAR,
  
  v2ProductName VARCHAR,
  
  v2ProductCategory VARCHAR,
  
  productVariant VARCHAR,
  
  currencyCode VARCHAR,
  
  itemQuantity INTEGER,
  
  itemRevenue NUMERIC,
  
  transactionRevenue NUMERIC,
  
  transactionId VARCHAR,
  
  pageTitle VARCHAR,
  
  searchKeyword VARCHAR,
  
  pagePathLevel1 VARCHAR,
  
  eCommerceAction_type NUMERIC,
  
  eCommerceAction_step NUMERIC,
  
  eCommerceAction_option VARCHAR

)


iii. Loading the data into the created tables by right clicking on table and choosing the import option which leads to selecting the location of the data before clicking OK to confirm

### Step 2
Answering questions from the data set and generating up my own questions from the data. Data cleaning and QA

## Results
I discovered the data could tell me about revenue. This is important as the business can make informed decisions including marketing campaigns and possibly customer loyalty programs based on the revenue. It also informs them about any growth or loss and it can be handled accordingly.

There is also some geographical data which shows how customers in different places behave or contribute to the business.
Given the product details, it is possible to analyse which products do well and which underperform. The geographical data if clean also shows patterns that will inform what products perform based in certain countries/cities, that forms a pattern and can inform the business on what to prioritize for certain regions.

The sentiment scores are an indicator of customer satisfaction or lack thereof, so it is an opprtunity for the business to retain customers by proactively addressing concerns, this goes hand in hand with the data that shows the top selling products, it means other data like restocking lead time can be used to ensure that the stock inventory is up to date with fast moving products and possibly on the look out to avoid stocking products that are not preferred by customers.

There is also a lot of data that shows customer behaviour in terms of how they interact with the ecommerce site. Most of the customers that end up there are from an organic search and from the data available, they are 57.4% of the visitors, in all, there are 7 ways in which they may find themselves there. The fourth highest way is paid search which amounts for 3.3% of the site visitors, it comes behind direct and referral which are 20% and 17% respectively. It means the business may want todo further analysis to see if the paid searches are worth the cost. Other customer behaviour data include page views and time spent on the site in addition to bounce, which is the percentage of site visitors who arrive but leave before ever progressing onto a second page. All this customer behaviour data can be used to drive marketing campaigns and other business decisions.

The ERD;


![schema png](https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/954c626b-4a44-4abe-a14c-3495c0dc50c8)



## Challenges 
I had some challenges that included importing difficulties. Some tables imported well but there were others that needed permission to be read by pgAdmin4 and I ended up copying them to the folder where postgresql is located.
During table creation, I had named some primary keys and it presented problems during importation, lesson learnt; Proceed with key allocation later rather than as an initial step.

## Future Goals
Look at alternative cleaning and DA processes.
Project presentation;
https://drive.google.com/file/d/1QhxT6ewD9IaMbk9sg-ORRMMiXssKS9d4/view?usp=drive_link


