Imagine if we had a database that was simply a text file that implemented a key-value store. I.E. every time we wanted to write to a database we'd save it like `42: {name:akeen}` and every time we wanted to read we could just look for the specific key.

In terms of performance this is actually very good on write because we can simply append to the end of a file (if we maintain a pointer to this line this operation is O(1)! ). This is called a **log** and is actually what databases use (sort of), they have more to worry about like concurrency control and handling disk space but the core idea is the same. However doing a read is a bit tricky since we don't want to delete or overwrite duplicate keys when doing a read we need to find the latest key we're looking for. This means a read is O(n) which is highly inefficient.

To find these values more efficiently, we can use an ***index***, which put simply is an additional data structure derived from the main data. Indexes allow us to look for this specific data more efficiently **but** we now no longer just append to a file and we incur write overhead!

So that's the tradeoff, any index we add decreases the performance of doing writes, but increase the performance of doing reads because of this databases generally don't index everything and leave it up to the developer to manually add and remove indexes according to their use case. This section discusses many concepts around indexing structures

[[Hash Indexes]]
[[SSTables & LSM-Trees]]
[[B-Trees]]
[[Comparing B-Trees and LSM-Trees]]
[[Other Indexing Structures]]