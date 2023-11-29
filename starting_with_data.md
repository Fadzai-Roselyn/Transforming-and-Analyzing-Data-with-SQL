Question 1: Find out the products with sentiment score of 0.7 to 1 and those with a sentiment score less than 0.3


SQL Queries:


SELECT
    a.v2ProductName,
    a.productsku,
    s.sentimentscore
FROM
    all_sessions a
JOIN
    sales_report s ON a.productsku = s.productsku
WHERE
    s.sentimentscore >= 0.7 AND s.sentimentscore <= 1

UNION

SELECT
    a.v2ProductName,
    a.productsku,
    s.sentimentscore
FROM
    all_sessions a
JOIN
    sales_report s ON a.productsku = s.productsku
WHERE
    s.sentimentscore < 0.3
ORDER BY sentimentscore desc;

Answer:
Monitoring sentiment scores helps identify potential issues that could lead to customer churn. Proactively addressing concerns and improving products based on customer feedback can contribute to higher customer retention rates.
In summary, analyzing sentiment scores for products is a valuable practice for an ecommerce company, providing actionable insights that can positively impact product development, marketing strategies, customer satisfaction, and overall business performance.

Monitoring sentiment scores is crucial for identifying potential issues that might lead to customer attrition. Addressing concerns and proving improved products based on customer feedback can markedly increase customer retention rates. Analyzing sentiment scores for products is important for ecommerce companies, providing actionable insights that can inform marketing strategies, customer satisfaction, and overall business performance. The two screen shots show some of the bottom 6 which are less than 0, therefore showing a negative impact on customers, and some of the top 6 which show a positive impact on customer satisfaction
<img width="488" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/98492280-8381-4a1d-953d-2cdce28b9e59">
<img width="485" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/5da42abd-a372-4d25-8e2c-38066d50b2be">

Question 2: Which products have the highest restocking lead time? Give the top 10.

SQL Queries:

SELECT DISTINCT
    name AS product_name,
    restockingleadtime
FROM
    products
ORDER BY
    restockingleadtime DESC
LIMIT 10;
Answer: 
Keeping tabs and managing the restocking lead time can help the business to have a pulse on their inventory levels. Ultimately the risk of having popular or even average products out of stock is reduced and customer demand for products is met efficiently.


<img width="284" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/1e656593-d24a-48f9-b959-e05e50fd8009">



Question 3: Based on the various ways in which people visit the ecommerce site, which channel grouping is responsible for the most visits? Show how the other groupings compare.

SQL Queries: 
SELECT
    channelgrouping,
    COUNT(DISTINCT fullvisitorid) AS site_visitors
FROM
    all_sessions
GROUP BY
    channelGrouping
ORDER BY
    site_visitors DESC;


Answer: 

Organic search being #1 out of 7 groupings account for the most visits, while paid searches are #4 out of 7 behind direct and referral but ahead of affiliates, display and others. As the leading margin of the first 3 is greater than that of paid searches, the business might want to keep an eye on the KPI to always be sure it is worth paying for paid searches seeing as customers are mostly visiting the site through other means.

<img width="211" alt="image" src="https://github.com/Fadzai-Roselyn/SQL-Project-LHL/assets/146916613/5dfac097-a5cf-4c20-a353-73f5fd700e31">


