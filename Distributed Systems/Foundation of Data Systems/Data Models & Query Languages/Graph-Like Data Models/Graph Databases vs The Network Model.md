While Graph Databases are similar to the network model (CODASYl) in that both were created to better handle many-to-many relationships, there are some stark differences that makes the graph model much more than just a simple rehash

1. Schema: The codasyl model required a defined schema, this made the evolvability of applications using it subpar, modern graph databases are schemaless and support heterogenous data by allowing any vertex of any type to connect to any other vertex of any type.
2. Traversal: The only way to find data in the codasyl model was to traverse through specific access paths, not only was this cumbersome if the access paths were deep, but it meant adjusting data meant needing to adjust the access paths. The graph model allows you to refer to any vertex by a unique ID, index on specific vertex data for the query optimizer, and there are many different graph traversal algorithms that can be used depending on context
3. Record Store: In CODASYL children are stored as an ordered set, meaning on insertions you needed to make sure the order was properly maintained, graph db's don't have this issue and allow for sorting as needed when performing query
4. Query Language: The network model only supported imperative querying, as previously discussed imperative languages have weaknesses in data querying as the end user needs to worry about performance and optimization at a granular level, modern day graph databases generally allow for imperative code, but also have declarative query languages such as Cypher and SPARQL that have similar bonuses to SQL.