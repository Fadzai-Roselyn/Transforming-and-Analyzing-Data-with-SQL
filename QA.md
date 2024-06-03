### Identifying and describing risk areas.

Data completeness;
One of the difinitions is as follows; refers to the extent to which a dataset has all the relevant and necessary information for a given purpose. A complete dataset should not have any missing, duplicated, or irrelevant values that could affect the analysis.

There were a lot of nulls/ missing data for columns that are critical including revenue, country, city and more. I would have needed communication with the company to understand why it is missing so I can decide how to go about the analysis in a way that does not give far fetched results.

Data duplication;
This would give inaccurate results if we are computing duplicated data with an assumption that it is a unique set of data.

Data consistency;
The naming should be more accurate to allow for better analysis. There were inconsistencies in data naming for example, within country and city, there are valid country names, in some places in place of the country or city name, there is 'not available in demo dataset' or 'not set' if we have to analyse for data that requires comparison within regions and the output contains 'not set' or 'not available in demo dataset', we can not proceed with meaningful analysis.



## QA Process:
### Describing QA process and the SQL queries used to execute it.

To ensure I am getting out put that excludes missing data, I used the NOT NULL query;
For example, with transactionrevenue;

select country, city, max(transactionrevenue) as total
from all_sessions
where transactionrevenue IS NOT NULL
group by country, city
order by total desc;

To ensure I am not getting duplicates, below is an example of a query I used;

    channelgrouping,
    COUNT(DISTINCT fullvisitorid) AS site_visitors
FROM
    all_sessions
GROUP BY
    channelGrouping
ORDER BY
    site_visitors DESC;
