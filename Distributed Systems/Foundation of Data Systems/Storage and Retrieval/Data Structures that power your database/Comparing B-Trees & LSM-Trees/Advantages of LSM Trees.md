A B-Tree index needs to write everything twice, once to the write-ahead log, and again to the tree itself. Theres also overhead from writing everything again even when only a few bytes change, or when more redundancy is added to increase reliability. 

Log-Structured indexes also rewrite data due compaction & merging of tables, this writing to a database causing multiple different writes on disk is known as ***write amplification***. Preferably we keep this as low as possible especially on SSDs which can only overwrite blocks a limited amount of times before wearing out.

Write amplification can have a direct performance cost on write-heavy applications as the more that is stored on disk the fewer writes per second can be handled.

LSM-Trees are able to sustain higher write throughput than B-Trees because they have lower write amplification & less overhead on writes b/c the segments are written to sequentially. They can also be compressed better producing smaller files on disk than B-Trees ( b-trees leave space on disk unused in some cases such as when a page is split ) this combined with the periodic rewrites to remove fragmentation means LSM-Trees have less storage overhead.

On many SSDs the firmware uses a log-structered algorithm to turn random writes into sequential writes on the storage chips, so the storage pattern is less pronounced, however lower write amplification and reduced fragmentation are still advantageous.