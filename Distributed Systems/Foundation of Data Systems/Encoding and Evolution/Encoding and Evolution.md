In the beginning we discussed the importance of evolvability, one aspect of change that we need to focus on is change in data format. When new features get added to an application its likely new data will be stored. Relational DB's always have a single schema active at any point in time but this can be changed and schemaless databases don't enforce any schema so the database can contain a mixture of old a new data. 

When schema or the reading of schema changes, the application code must change, but this has to be done sequentially, in a rolling upgrade where we can slowly update different nodes and monitor changes. This means old and new data will be accessed on the application code, so we need to have both backwards and forwards compatibility. So the way we store the data and manipulate it in our code is extremely important. 

In this chapter we look at different formats for encoding data and how they handle schema changes, we also discuss how those formats are used for data storage and in communications like rest apis and rpc systems, as well as message brokers. 

[[Formats for encoding data]]
