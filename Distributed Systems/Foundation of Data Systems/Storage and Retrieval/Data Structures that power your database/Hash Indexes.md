One way to index data ( in this case as example key-value data) we can use a hashmap in memory ( RAM ). If we have data storage that only appends to a file, we can keep an in memory hashmap where every key is mapped to a byte offset representing the location of the data on disk (I.E. a each key's value is a pointer `key:0ab4d2`). Whenever we append to our read only log, we can update the hashmap to reflect the location of the new insertion. When we want to read a vlue we can use the hashmap find the byte offset then find the data at that offset. 

* This is similar to what *bitcask* db does, providing high performance read and writes as long as long as all keys fit in ram b/c the hashmap is kept completely in memory.

This is well suited for data where the *values* are updated frequently but the *keys* aren't. Meaning if you have a lot of writes *per key*.

In this log , one issue is memory space. Because it's an append-only log it will increasingly grow in size. One solution is to break the log up in segments of certain sizes and close a segment for writing when it reaches a certain size, and make writes to a new segment. On closed segments we can perform ***compaction*** on them, combining them to a new segment and throwing away all but the most recent keys. 

This compaction process can be performed in a background thread, and while it's happening we can perform any write requests to the new segment and continue to read from whatever segment is needed. Once we've finished merging we can switch reads to the new segment and delete the old segment files. 

Each segment has it's own in-memory hash table mapping the keys to the file offsets, to find a value for a key we can check the most in order of most recent segments. Because continuously merge, the segment count remains small. 

There are a few things to note
* File Formats - for max performance we should not store this data as a csv but rather binary
* Deletion - To delete a record we need to append a deletion record of that key ( sometimes called a tombstone ) when log segments are merged the tombstone tells the merging process to throw away that key.
* Crash recovery - If the database crashes the in-memory hashmaps are gone. We can rebuild them by looping through each segment but this could take a long time. Another strategy is to store a snapshot of each segment on disk,
* Partially Written Records - The database can crash in the middle of a write, we need to make sure there's validation mechanism and throw away corruption.
* Concurrency - Writes to a log are generally sequential so it's common to have a single write thread and make data segments append only so they can be read safely by any thread.

It's better to have an append-only log instead of updating in place because
* Appending and merging are sequential write operations, which are much faster than random writes
* Concurrency and crash recover are easier if you don't have to worry about overwritten data.
* Merging old segments prevents fragmentation of old data.

The hash table does have some limitations
* As discussed previously the hash table must fit in memory, so if there is a large number of keys it cannot be used as efficiently. You can store the hashmap on disk but there are performance and operability issue. 
* Searching for a range of keys is not efficient as you need to look up each key indivdually.

SSM Tables and LSM Trees don't have some of these issues.