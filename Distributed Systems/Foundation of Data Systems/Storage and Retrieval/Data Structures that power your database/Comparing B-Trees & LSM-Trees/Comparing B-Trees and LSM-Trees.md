When comparing the two data structured, B-Trees & LSM-Trees, B-Trees are generally considered to be faster for reads because LSM-Trees have to check several different data structured and SSTables at different stages of compaction. LSM-Trees are generally fast for writes.

However these are only generalities and the real answer of which is is faster is dependent on the workload and circumstance of your use case. This section discusses the advantages and downsides of using LSM-Trees in a storage engine compared to B-Trees.

[[Advantages of LSM Trees]]
[[Downsides of LSM Trees]]