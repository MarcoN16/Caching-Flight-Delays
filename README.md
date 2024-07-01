# Caching-Flight-Delays

In this activity, I imported three datasets, creating partitions, filter the data, and create temporary views of the three datasets. Then, I wrote queries to join three datasets and determine the execution times of the queries. Finally, I cached data and compare query execution times with the cached data.

**Instructions:**

1. importing packages, creating a Spark session, and setting the shuffle partitions to 4 or 8.

2. Importing the datasets into Spark session.

3. Filtering the airport codes Spark DataFrame to only contain those whose `country` equals `USA`.

4. Filtering the 500 city latitude and longitude DataFrame to only contain the `name`,`latitude`,`longitude`,`admin1_code` fields and rows whose `country_code` equals `US`.

5. Creating temporary views for all three Spark DataFrames. Naming the temporary views as follows:

    * The delayed flight temporary view as, `delayed`
    * The latitude and longitude temporary view as, `lookup_geo`
    * The airport codes temporary view as, `lookup_city`

6. Modifying the provided SparkSQL query that was used in the instructor demonstration to add `origin_latitude`, `origin_longitude`, `dest_latitude` and `dest_longitude` fields from the joined temporary views.

7. Using the same SQL query as in step 5, but this time add a "Broadcast" hint for either the `lookup_geo` or `lookup_city` temporary views and run your query again.

8. Using the same SQL query as in step 5, but this time use an aggregate function (i.e. `avg()`, `sum()`, etc.) on some of the fields from the `delayed` flights temporary view.

9. Using SparkSQL to cache the `delayed` temporary view, since it is the largest table.

10. Verify that the code successfully cached the table using the `spark.catalog.isCached()` method.

11. Once again, rerun the aggregating SparkSQL query from step 9 and note the runtime.

12. Cache one of the lookup tables.

13. Running the query from step 8 again. It should continue to see improvement.

14. Uncache anything that it has previously cached.

15. Verify that nothing is cached using the `spark.catalog.isCached()` method.


## Data Source:

[Airlines Delay](https://www.kaggle.com/datasets/giovamata/airlinedelaycauses)


