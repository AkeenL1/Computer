If you have trillions of rows in a fact table, querying efficiently is a challenging problem. However a typical data warehouse doesnt need to query over all the columns, rather a few at a time (I.E. we look for specific data, user.name instead of * FROM USER)

In most OLTP databases data is layed out next to each other, one row after another encoded on disk. If we do this with a fact table and try to have some indexes on the data we want, we'll need to load in every row then parse and filter them for the specific data we want.

An alternative is to store all the values from each column together in order of the row their in. This means a query only needs to parse the columns used in the query. This method of storage is called *column oriented storage*

Column-Oriented storage relies on each column file containing the rows in order, this way if we need to reassemble an entire roe we can put individual coluns together. 