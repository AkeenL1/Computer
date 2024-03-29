The relational model introduced a new way of querying data *SQL*, with the main difference being that it was a *declarative language* similar to relational algebra, instead of imperative code that was used by IMS and CODASYL. The language being declarative mean users just needed to specify the data they wanted and the db's query optimizer would use the correct indexes and proper joins to find it in whatever order the query optimizer thought to be appropriate.

A declarative language is in general simpler to work with because the finer details are abstracted away, so performance improvements could be made to the database and queries would not need to change, however there is more limited functionality that is lost from the switch from an imperative language. This isn't necessarily a bad thing, more-so a tradeoff as now the database has more capability of performance optimizations than it might've had previously. 

Declarative languages also lend themselves to parallel execution quite nicely, since the implementation details are hidden and unlike imperative languages there is no step-by-step functionality that needs to be followed, declarative languages are able to use parallel implementations when appropriate.

[[Declarative Queries on the Web]]
[[MapReduce Querying]]
