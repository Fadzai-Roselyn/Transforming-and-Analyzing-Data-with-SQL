Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**
SQL Queries:
select country, city, max(transactionrevenue) as total
from all_sessions
where transactionrevenue IS NOT NULL
group by country, city
order by total desc;

Answer:


<img width="332" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/a504ad02-c61a-46e4-9dd8-5fe7a99ff0d8">

**Question 2: What is the average number of products ordered from visitors in each city and country?**
SQL Queries:
SELECT
    a.city,
    a.country,
    AVG(s.total_ordered) AS avg_order_quantity
FROM
    all_sessions a
JOIN
    sales_report s ON a.productsku = s.productsku
GROUP BY
    a.city, a.country;

Answer: Screenshot of the first 5


<img width="406" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/ef9b0374-f6fb-4d4e-ac3e-2c19aa7114e0">

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**
SQL Queries:
SELECT
    a.city,
    a.country,
    a.v2productcategory,
    COUNT(s.productsku) AS total_orders
FROM
    all_sessions a
JOIN
    sales_report s ON a.productsku = s.productsku
WHERE
    a.v2ProductCategory IS NOT NULL
	AND s.productsku IS NOT NULL
GROUP BY
    a.city, a.country, a.v2productcategory
ORDER BY
    total_orders DESC;



Answer: It is difficult to determine a pattern with regards to city as it has some data unavailable in the demo dataset. A screenshot of the first 5;


<img width="584" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/47928ec9-8b1b-4bc1-bf1f-c0ed456ebbae">


**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**
SQL Queries:
WITH RankedProducts AS (
    SELECT
        a.city,
        a.country,
        a.productsku,
        a.v2ProductName,
        s.total_ordered,
        RANK() OVER (PARTITION BY a.city, a.country ORDER BY s.total_ordered DESC) AS product_rank
    FROM
        all_sessions a
    JOIN
        sales_report s ON a.productsku = s.productsku
)
SELECT
    city,
    country,
    productsku,
    v2ProductName,
    total_ordered
FROM
    RankedProducts
WHERE
    product_rank = 1;

Answer: As there is data missing from city/country, it is difficult to determine a pattern, though we at least know the top selling product in the available regions. That will help the store to ensure they always have stock for the products that are the best movers, and they can find out why the least performing products are not moving better.
Screenshot of the first 5 results;


<img width="657" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/89583e21-889d-4e6b-81e4-5faa8a91404f">


**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:
SELECT
    city,
    country,
    SUM(totalTransactionRevenue) AS total_revenue
FROM
    all_sessions
WHERE totalTransactionRevenue IS NOT NULL AND city IS NOT NULL AND country IS NOT NULL
GROUP BY
    city, country
ORDER BY total_revenue desc ;


Answer: The results from the query, looking at data that is not null shows that the top 5 revenue generators are cities in the United states.
The screenshot of the result shows 6 rows where the fifth city/ country is Tel Aviv-Yafo/ Israel. The United States continues to dominate though other countries also made it to the list.


<img width="347" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/db927766-e88f-431f-8f72-e4646675ecb5">








