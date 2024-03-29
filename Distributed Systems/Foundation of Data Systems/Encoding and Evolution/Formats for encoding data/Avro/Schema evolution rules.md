In avro forward compatibility means you can have a new version of the schema as a writer and an old version as the reader, backwards compatibility is reversed with the new version of the schema as the reader and the old version as the writer.

To maintain this compatibility we can only add or remove fields that have default values, otherwise a reader using a new schema will not be able to read data written by old writer schemas and thus would not be backwards compatible. 

Is some languages null can be used as a default value, this is the case in avro but you have to use a union type that indicates all of the options a field can be, meaning that fields can only ever default to null if you also specify at least one other datatype they can be. This means that there is no optional and required keywords in Avro

You can change the name of a field by having the reader schema contain aliases for field names so it can match an old writer's schema against the aliases, this means changing the name is backwards compatible (works with old writers schemas) but not forwards compatible.