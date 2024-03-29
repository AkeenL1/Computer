In avro when an applications wants to encode some data, it encodes the data using whatever schema it knows about, this is called writer's schema.

The same is true when reading encoded data where the application expects the data to be in some schema, which is known as the readers schema

The key idea with avro is these two schemas don't need to be the same, rather they just need to be compatible. Avro library resolves the differences by looking at both schemas side by side and translating from the writer schema to the reader schema the schema resolution matches fields by name. if the code reading the data encounters a fiele thats in the writer schema but not the reader schema its ignored. 