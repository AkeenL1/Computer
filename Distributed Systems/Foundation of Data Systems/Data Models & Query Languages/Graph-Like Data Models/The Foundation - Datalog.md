Datalog is another query language for graph databases that actually predates both cypher and sparql. It's similar to the triple store model but moves the predicate outside of the parentheses

`namerica, name, "USA"`
becomes
`name(namerica, "USA")`

Datalog also differs as the syntax for performing queries is a bit different, rather than query for specific relations you can define rules that return new triples

`within_recursive(Location, Name) :- name(Location, Name)`

The rule above applies if a match is found for all predicates on the right side of the `:-` , when a rule applies Datalog effectively creates a new predicate and saves it, dictated by the left hand side of the `:-`, using the capatilized values (the way datalog dictates variables)

Meaning that if `name(namerica, "USA")` was inside the database, a new predicate `within_recursive(namerica, "USA")` would be created

Datalog allows rules inside rules and rules to be recursive, this way of thinking about querying graphs is different than previously discussed, but uses the same idea of relationships between vertices and edges.