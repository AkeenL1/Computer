Using document NoSQl db's for one to many makes sense when we don't need much or any queries and joins and can contain important data on the document, creating a denormalized document w/ one-to-many relations with its entities.

Denormalizing this data (storing the 'many' entities as their raw data in the document) can be a bad choice for a number of reasons however and rather storing the data as a reference w/ an ID ( I.e. having a table and referencing that table through a foreign key) can provide some advantages
* Consistent style & spelling across data
* Avoiding ambiguity ( different entities w/ the same name)
* Ease of updating
* Localization
* Better search

Storing text directly means you're duplicating the information humans care about across records while using an ID means you have one source of truth. When something needs to be changed having duplicated everything means you need to change everything that was duplicated which risks inconsistencies and incurs write overhead. This idea of avoiding and removing duplication is the core idea in *normalization*.

However when you normalize data many-to-one ( and many-to-many ) relationships arise which don't work very well in a document oriented model because joins are not needed for one-to-many structured and support for them is generally weak in implementations of document DB's.

If the database itself doesn't support joins they must be emulated using the application layer by making multiple queries to the database, and if the data becomes more interconnected as time goes on a one-to-many relationship can quickly turn into a many-to-many. I.E. you could hold some information local to each user, but as discussed above there are plenty of good reasons *not* to do this.