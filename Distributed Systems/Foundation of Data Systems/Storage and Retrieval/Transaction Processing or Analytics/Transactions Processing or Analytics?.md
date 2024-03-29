In the early days of data processing writes to a database usually were commercial transactions. This term stuck and continues to refer to groups of reads and writes forming some logic.  Even though databases became used for more than just business transactions, the transactional style of processing data still worked and because these applications were interactive this access pattern became known as online transactions processing or (OLTP).

Eventually databases began to be used for data analytics, which meant large amounts of data needed be scanned, only reading a few columns per second and calculate some aggregate statistic. These were often written for business analysts to enhance business intelligence. While SQL turned out to be quite flexible, there was still a wan't to run databases specifically for analytics. This was called a data warehouse

[[Data Warehousing]]
[[Stars and Snowflakes- Schemas for Analytics]]
[[Column Oriented Storage]]
[[Column Compression]]
[[Sort Order in Column Storage]]
[[Writing to Column-Oriented Storage]]
[[Aggregation - Data Cubes and Materialized Views]]
