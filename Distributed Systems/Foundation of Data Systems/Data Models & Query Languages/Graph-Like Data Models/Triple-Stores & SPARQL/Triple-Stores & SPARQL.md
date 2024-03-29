The ***triple-store*** model is mostly similar to a property graph, but instead of defining a vertex then defining edges to and from the vertices, it uses a (subject, predicate, object) format to represent a graph. It does this in two ways
1. Defining properties: One can define properties on a vertex by making the object a datatype (string, int, bool) for example
	1. idaho, name, "Idaho"
	2. This creates a vertex - idaho - with the name property as "Idaho" this is equivalent to an idaho document with the key-value property `{name: Idaho}`
2. Defining edges ( defining relations ): We can use this same format do define the edges between two vertices by making the predicate a property ( basically a label as in property graphs)
	1. idaho, :within, united_states
	2. This creates a relation between the idaho and unites_states vertices with an edges from idaho to united_states labeled within

There are many types of formats to actually write these in such as *Turtle* but the core idea remains the same across formats.

[[The semantic web]]
[[The RDF data model]]
[[The SPARQL query language]]