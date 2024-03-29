We discussed previously how the main issue with document databases (especially those of olden day such as hierarchical and network models) struggle with many-to-many relationships. The relational model is good for handling simple many-to-many relationships but can struggle as complexity increases. The last model we'll discuss is the **graph** model, that is DB's that use a graph ( a collection of nodes and edges) to model data.

Many kinds of data can be modeled this way and there are many popular algorithms to search graphs with specific parameters. Graphs are also not limited to the *type* of data they store, I.E. they can be heterogenous (as opposed to homogenous ) meaning different types of objects can be stored together in a single datastore. Facebook for example stores a single graph with many different types of nodes and edges pointing people to posts, events to locations. etc.

There are several different ways of structuring data in a graph-like way, in this section we discuss two ways of doing so, along with 3 declarative query languages for graphs
1. [[Property Graphs]]
2. [[The Cypher Query Language]]
3. [[Graph Queries in SQL]]
4. [[Triple-Stores & SPARQL]]
5. [[Graph Databases vs The Network Model]]
6. [[The Foundation - Datalog]]