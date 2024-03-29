The key is whats actually being search for in a query, but the value can be one of two things
1. The document itself
2. The documents location elsewhere 

The location these documents are stored is known as a *heap file* it stores data in no particular order (it can be append-only, keep track of deleted rows to overwrite them later etc.). This approach is common because it avoids duplicating data if there are multiple secondary indexes by having them all represent one source of truth.

Using a heap file can be great when updating a value without changing the size. If the size does change, you may not have enough space & may need to move it to a new location in the heap & either all indexes need to be updated or a forwarding pointer is left in the old heap.

This extra hop from the index to the heap file can be slow in some cases and have poor performance, instead we can store the indexed row on the index, this is known as a *clustered index* in some databases they use a clustered index for their primary key & all secondary indexes reference the primary key instead of a heap file.

A nice in-between a clustered index & using a heap file is a covering index or index w/ included columns. This stores ***some*** of the tables columns which allows some queries to be covered by the index. 

Utilizing these indexes can speed up reads, but require additional storage and can slowdown writes. Also there needs to be transactional guarantees because applications should not see inconsistencies due to the duplication.