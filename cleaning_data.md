What issues will you address by cleaning the data?
Ensuring that I am not working with duplicates when I call on some columns
Conversion of data types when tables are not importing
Standardization of formats and units to ensure consistency across datasets






Queries:
Below, provide the SQL queries you used to clean your data.
SELECT DISTINCT
    name AS product_name,
    restockingleadtime
FROM
    products
ORDER BY
    restockingleadtime DESC
**********************************
SELECT
    channelgrouping,
    COUNT(DISTINCT fullvisitorid) AS site_visitors
FROM
    all_sessions
GROUP BY
    channelGrouping
ORDER BY
    site_visitors DESC;
