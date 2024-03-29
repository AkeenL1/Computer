Avro is a binary encoding format that also uses a schema to specify the structure of data being encoded, there are 2 languages however, one intended for human editing and one thats more easily machine readable.

The thing that makes avro unique is there are no tag numbers in the schema and when encoded the encoded values are just concatenated together with no identifier.

To parse the binary data you go through the fields in order that they appearin the schema and use the schema to tell you the datatype of each field. Thus means data can only be decoded if the code reading the data has the same schema as the code that wrote the data. 

[[The writer's schema and the reader's schema]]
[[Schema evolution rules]]
[[But what is the writer's schema]]
[[Dynamically generated schemas]]
[[Code generation and dynamically typed languages]]
