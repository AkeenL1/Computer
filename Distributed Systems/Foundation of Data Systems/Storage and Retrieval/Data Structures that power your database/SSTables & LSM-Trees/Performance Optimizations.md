There is quite a bit of detail that goes into optimizing the performance of Log Structered Merge trees. One instance where LSM-Trees are slow is on reads in which the key does not exist in the database. In these cases you would end up checking the memtable then checking every segment all the way to the oldest to be sure the key doesn't exist. One way this is alleviated is by using a *Bloom Filter*, this is a memory effecient data structure that allows for approximating the contents of a set. You can use it to know if a key exists or not and save disk reads.

Another detail is in the specifics of how the SSTables are compacted and merged together. There are two solutions
1. Size-tiered compaction - Here smaller and newer segments are compared with and merged into larger older segments
2. Leveled Compaction - The key range is split into smaller SSTables and older data is moved to separate levels, so we can preform compaction more incrementally.
Different databases provide support for either both of one of these methods of compaction

Even with the differences in detail the core idea of a LSM-Tree, storing many SSTables and merging and compacting them based on some condition, is consistently effective and simple. Even if there's more keys than available memory we can find things efficiently while being able to perform range queries and having high write throughput.