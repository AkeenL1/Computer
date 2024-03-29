Previously we discussed that there are multiple different ways for OLTP to structure their data, in analytics theres is much less diversity. Many data warehouses use a star schema, also known as dimension modeling.

At the center of this schema is a fact table, each row represents an event that occurred at a particular time. These events can be anything such as retail sales, website clicks, etc. These facts are usually captured individually, making the fact tables themselves very large. 

Some of the columns in fact tables are attributes but there are also foreign key references. These foreign keys reference dimension tables, which store the who what when where how and why of the event. For example you could have a sale of a product in the fact table, but reference the product and customer information by foreign key. Date and time are also represented using dimension tables because it allows us to have additional information on dates. 

This is called a *star schema* because when drawing the table relationships the fact table is in the middle with the dimension tables being the 'rays' of a star.

There is also a variation of this called the *snowflake* schema. In this dimensions are further broken down into subdimensions, this creates a more normalized data set by star schemas are generally preferred because they are simpler for analysts to work with. 

