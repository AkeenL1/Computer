A large business likely has tons of different transaction processing systems, each of these systems is likely complex and operates independently from one another. These OLTP systems are customer facing, therefore they're generally expected to highly available and process transactions with low latency. Meaning large cumbersome queries like the ones performed in business analytics can slow down the performance. 

A data warehouse solves this issue by allowing for business analysts to query as much as needed. They do this by holding a copy of data that is read only, from all the OLTP systems in the company. Data is extracted from these OLTP databases, transformed into an analysis friendly schema and loaded into the data warehouse. This process is nown as Extract-Transform-Load or ETL. 

Data warehousing is common in large scale business, but smaller scale business usually don't have one as a conventional databases usually work well for the amount of data they have. 

The main advantage to a data warehouse is that it can be optimized for the analytic queries, the indexing methods discussed in previous chapters, are not very good at answer analytic queries. 

[[The Divergence between OLTP databases and data warehouses]]