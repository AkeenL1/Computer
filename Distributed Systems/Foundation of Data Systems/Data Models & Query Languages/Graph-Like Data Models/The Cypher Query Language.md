Cypher is a declarative query language specifically made for Neo4js a graph database. In it each vertex is given a is given a name and those names are used in a query to created edges
Nodes can be created by doing
```
(Idaho:Location {name:'Idaho', type:'State'}) 
```
Edges can be created by doing
```
(Idaho) -[:WITHIN]-> (USA)
```
which creates an edge labeled "WITHIN" with Idaho as the tail and USA as the head.

The same arrow notation can be used to create a query, for example to find all the people born in the USA you could do
```
MATCH
	(person) -[:BORN_IN]-> () -[:WITHIN^*...0]->(us:Location {name:'USA'})
```
This would look for any *person* node that points to any other node through a 'BORN_IN' edge, from there we follow any number of outgoing "WITHIN" edges to find the location node whose name is 'USA'

This structure implies we start at each person node and traverse from the node to find matching people. But if we had an index on the name for Locations we could efficiently find the node representing USA and go backwards searching through WITHIN edges, afterwards we look for any people connected by BORN_IN edges.

The point being that since this language is *declaritive* the query optimizer handles this logic, deciding how to execute a query based on things such as the presence of said index. 