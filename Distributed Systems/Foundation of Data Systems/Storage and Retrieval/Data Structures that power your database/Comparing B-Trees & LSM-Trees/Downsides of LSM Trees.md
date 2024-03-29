A downside of LSM-Trees is the compaction process can decrease performance of reads and writes. Disks have limited space so if the disk waits while an expensive compaction is being executed, at higher percentiles, can slow down throughput and response time heavily.

Another issue is the disk has finite write bandwidth, and if compaction cannot keep up with the incoming writes the number of unmerged segments on disk will keep growing until the disk is full. Usually the rate of incoming writes is not throttled by the database so you need explicit monitoring to catch this situation.

One advantage of B-Tree indexes is that the keys are stored in a single place, as opposed to multiple keys being stored in a LSM-Tree. This is good in transaction relational databases that want to have storng transactional semantics as you can lock certain keys and transfer those locks to the B-Tree.

For these reasons B-trees are the most popular and will likely stay that way, however log-structured data stores are becoming increasingly popular.