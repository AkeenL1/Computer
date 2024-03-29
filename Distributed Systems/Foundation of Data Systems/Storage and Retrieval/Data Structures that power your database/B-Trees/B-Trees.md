Thus far we've discussed log-structured storage engines and how to optimize them, however a much more common indexing method is to use a B-Tree.

A B-Tree similarly to an SSTable stores the key-values pairs sorted by key, however instead of using segments it breaks the database down into fixed size blocks or pages ( this mimics how disks save data ) and read and write to one page at a time. Each page can be identified by a pointer stored in another page.  One page is designated as the root of the B-Tree, so when we want to lookup a value we always start here this page contains several keys and references to child pages, each child has a range of keys and the keys between the references in the parent page dictate the range. Meaning we can look for a specific page holding a specific range of keys. It should be noted the B-tree can have multiple levels before reaching a child node containing the data ( or pointers to the data )

The number of references to child pages in one page of the B-Tree is called the branching factor, the branching factor is dictated by how much space is needed to store the keys and the references. 

If we want to update a key we find the key and update it in place, all references to the page remain valid, if we want to add a new key we need to find where it belongs in the range and write it to that page. If we overflow and writing would increase the page size to much, we split the page into two and update the parent page to references the two new pages and the new range. 

Doing this makes the tree balances, a balanced B-Tree will have a depth of O(log(n)). Most databases can easily fit onto a B-Tree with only a few levels, so there aren't many page references. 

[[Making B-Trees Reliable]]
[[B-Tree Optimization]]
