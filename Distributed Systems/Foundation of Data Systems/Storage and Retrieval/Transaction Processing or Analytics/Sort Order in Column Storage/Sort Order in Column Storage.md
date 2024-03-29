In a column store it doesn't matter which order the rows are stored, we can store them in order of their insertion, and then we just need to append on insertion. However we can sort them so we can index on certain columns
- Note: we can't sort the columns individually because we need to be able to construct rowws from column position

So we sort by specific columns, which are hopefully the most common to access data in queries. We can sort a second column and this will sort all of the rows that have the same first column values so now queries looking for those first two columns can be performed efficiently. 

This is not the only bonus, another important one is the efficiency of compression, previously we discussed how we can use a run-length and build bitmaps of the column data, because the data is sorted there will be longer sequences where data is repeated many times in a row, this is strongest on the first key less so on the second key etc .

[[Several Different sort orders]]