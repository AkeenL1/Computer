With binary encoding formats, their schema languages are much simpler than text based encoding formats like json that support more detailed validation. Because of this the different encoding formats have grown to support a wide variety of programming languages.

However these ideas arent new and not unique, many proprietary binary encodings exist for specific databses created by the database vendors.

So we can see that binary encoding formats are quite the viable option for a number of reasons
1. They can be much more compact than binary variants of text based encodings
2. The schema is a valuable consistent form of documentation
3. Keeping a database of schema allows you to check forward and backward compatibility
4. If using a statically typed language, the schema can provide type checking at compile time.

This schema evolution provides the same flexibility that nosql/schemaless(schema-on-read)databases provide, while providing good tooling and guarantees about data