## Issues that will be addressed by cleaning the data
<li>Ensuring that I am not working with duplicates when I call on some columns
<li>Conversion of data types when tables are not importing
<li>Standardization of formats and units to ensure consistency across datasets






Queries:
Below, provide the SQL queries you used to clean your data.
SELECT DISTINCT
    name AS product_name,
    restockingleadtime
FROM
    products
ORDER BY
    restockingleadtime DESC
SELECT
    channelgrouping,
    COUNT(DISTINCT fullvisitorid) AS site_visitors
FROM
    all_sessions
GROUP BY
    channelGrouping
ORDER BY
    site_visitors DESC;
