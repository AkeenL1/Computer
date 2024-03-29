The simple answer is "it depends" a few factors that can affect the answer include
1. Structure of the application
	1. If the application has a document like structure (I.E. a tree of one-to-many relationships that are loaded in at once), the document model makes sense
		1. The relational model has a technique called *shredding* where you combine all of the records that effectively converts a record as a document into its respective relational counterparts, but this can create cumbersome schema and complicated application code
2. Accessing data
	1. In the document model nested data is accessed similarly to an access path in the network/hierarchical, this *can* become complex in the same way that access paths did, but are generally much easier and not as complex especially if the nesting is not to deep
3. Poor support for joins
	1. The importance of the document database not having support for joins is dependent on the applications functionality. If your application doesn't have many-to-many relationships then joins are not required
	2. If the application code *does* use joins this can be a large issue, as stated previously it's possible to move joins to application code by doing multiple requests to a database, but then your application code becomes more complex and can cause worse performance

Generally speaking which data model is best depends on use case, if your data is highly interconnected the document model is not very good, the relational model is likely to be good and the graph model can be very good.