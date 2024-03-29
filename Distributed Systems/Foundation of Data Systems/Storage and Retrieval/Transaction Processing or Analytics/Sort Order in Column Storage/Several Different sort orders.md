Since different queries benefit from different sort orders, so we should store the data in different sorted ways, since data needs to be stored multiple times to avoid redundancy anyways we might as well store the data in multiple different sorted ways and use the most efficient ones to process the query. 

Having multiple sort orders is is like having multiple secondary indexes but rather keep the data in one place and have pointers, the data is replicated across sort orders. 

