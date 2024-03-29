If we take a structured log storage segment and begin to sort it by key, this becomes an SSTable - sorted by string table -. With this format we can't append new key-value pairs to the segment immediately since writes can happen in any order. There are several advantages to this over using in memory logs with hashes.

1. Merging segments is much easier, even if the segments are larger than the available memory. All we need to do is read each segment side by side and write the lowest key ( effectively apply mergesort ) . If the same key appears in multiple segments we just choose the most recent key as segments are closed at specific times so we know which came before which. 
2. To find a key instead of storing the exact byte offset, we can store a byte offset around a single key (I.E. the first word beginning with h) and since the segment is sorted we can loop starting at that index. This is still O(n) but n is effectively constant so it's closer to O(1).
3. Since we're storing one key to reference groups of keys, we can store the reference in memory and store the group ( I.E. all words beginning with h) on disk thus decreasing memory usage.

[[Constructing and maintaining SSTables]]
[[Making an LSM-Tree out of SSTables]]
[[Performance Optimizations]]
