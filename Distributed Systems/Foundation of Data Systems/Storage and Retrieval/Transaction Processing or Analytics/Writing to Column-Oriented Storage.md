These optimizations are good for data warehouses because most of the load is large read only queries, however this process makes writes more difficult, as you must keep the column data sorted to reconstruct the rows. 

However we can use LSM-Trees, as the columns are basically SSTables, we write to a sorted memory store and when the segment gets to large close it for writes and merge it into the other segments.

