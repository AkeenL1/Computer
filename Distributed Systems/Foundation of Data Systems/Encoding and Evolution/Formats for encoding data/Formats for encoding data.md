Programs work with data in either 2 ways
1. In memory, where data is stored in some data structure designed for fast lookup - usually using pointers
2. Encoded as some sequence of bytes as a way to send it over a network or write it to a file
The encoded sequence of bytes is of course different from the pointer based data structures, meaning we need a way of encoding ( converting from pointers to byte sequence) and decoding ( vice-versa ). 

[[Language-Specific Formats]]
[[JSON XML and Binary Variants]]
[[Thrift and Protocol Buffers]]
[[Avro]]
[[The merits of schemas]]