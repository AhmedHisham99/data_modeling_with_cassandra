# data_modeling_with_cassandra

## Purpose

Sparkify are a new music streaming app. They've been collecting data on the songs in their catalogue as well as user activity. The data are currently found in a directory of JSON logs on user activity, as well as a directory with JSON metadata on the songs in their app. The analytics team wish to understand what songs users are listening to, but there's currently no straightforward and simply way to query the data in its current form.

## Schema
As this is a NoSQL database, which are optimized for reads over writes, a unique table is modelled for each query. Using Apache Cassandra, the database is created in denormalized form which implies that we will have multiple copies of the data. In Cassandra, there are **no duplicates**, thus a unique `PRIMARY KEY` must be created for each table. Composite primary keys are a good way to achieve this. The schema uses the framework of 'partition' and 'clustering' keys when creating a `PRIMARY KEY`. The partition key determines the column on which the data will be partitioned - having equal sized partitions is preferred.

## Database records	

<img src="image_event_datafile_new.jpg" alt="Database records" width="800"/>


