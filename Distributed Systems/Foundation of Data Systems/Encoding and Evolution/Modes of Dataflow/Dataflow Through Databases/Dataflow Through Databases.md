In a database the process that writes to the database needs to encode the data, and the process that reads needs to decode it. If there is a single process accessing the database then it's effectively sending a message to your future self. Backwards compatibility is necessary in this case, otherwise your future self won't be able to understand what messages you sent.

However its common to have multiple processes accessing the database, in applications that consistently change, it's likely some these processes will be running newer code and some will be running older code, meaning a value written by newer version of the code must be able to be read by an older version of the code that is still running, so forwards compatibility is equally as important. 

Generally the encoding formats we've discussed can handle preservation of fields that may be in one but not another, but sometimes this logic needs to be in the application layer, this section discusses ways to solve this.

[[Different values written at different times]]
[[Archival Storage]]

