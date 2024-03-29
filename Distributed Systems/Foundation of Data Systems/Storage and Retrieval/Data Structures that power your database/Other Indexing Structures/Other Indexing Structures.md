So far we've discussed indexes for ***primary keys*** (primary key indexes), I.E. the things that a database will automatically index such as a document ID. There are also ***secondary*** key indexes that index certain values, these are usually important for joins amongst other things. 

A secondary index can easily be constructed from a key-value index, the only difference being that the indexed value is not necessarily unique. We can solve this in two ways
1. Making each value in the index a list of matching row identifiers
2. Making each entry unique by appending a row identifier to it. 

[[Storing values within the index]]
[[Multi-column indexes]]
[[Full-text search and fuzzy indexes]]
[[Keeping everything in memory]]