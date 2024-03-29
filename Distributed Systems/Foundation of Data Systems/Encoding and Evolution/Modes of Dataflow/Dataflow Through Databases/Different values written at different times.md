A database will generally store records created and modified at different times, from different states.

When we deploy new versions of an application we may replace old versions with new versions in the span of a few minutes, however the contents of the database will remain there in its original encoding. This idea is summarized as "data outlives code"

Migrating this data to a new schema is an option, but can be slow on large data sets, most relaitional dbs allow simple schema changes such as adding a new column w. a null value without rewriting existing data, when an old row is read the database fills in nulls for any missing columns. 

Schema evolution allows the entire databse to appear as if it was encoded with a single schema