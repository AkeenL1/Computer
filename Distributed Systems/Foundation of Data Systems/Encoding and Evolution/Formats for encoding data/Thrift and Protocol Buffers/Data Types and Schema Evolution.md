It is also possible to change the datatype of a field if the schema changes, but this has some risks as values will lose precision or get truncated. If we change a 32-bit integer to a 64-bit integer, new code will be able to read and fill in 32-bit integers but old code will cut off 64-bit integers.

One thing about Protocol is that it does not have a list datatype but a repeated marker field (which is an alternative to required or optional) the encoding of repeated type simply appears multiple times in the record. Its ok to change a repeated type to an optional type as new code will look at each instance but old code will only look at the last element. 

Thrift has a dedicated list type which is parameterized with the datatype in the list, this doesn't allow the same evolution from single to multi valued as protocol buffers does, but does have the advantage of supporting nested lists. re