The way avro reader's know what schema the records were written with comes down to the use case for the records
1. A large file with lots of records ( in the case of something like batch processing )
	1. In this case all the records are encoded w/ the same schema so we can simply put the schema at the beginning of the file and use that.
2. Database w/ individually written records
	1. In this case for each record we can include a version number that represents what version of the schema this is written with, the reader can extract the version number then fetch the writers schema
3. Sending records over a network connection
	1. Assuming the network connection is bidirectional, both programs can negotiate a schema version on connection setup and use that as the schema for the lifetime of the connection

In any case it's still useful to maintain schema in a dataase since it acts on documentation and allows you to check schema compatibility.