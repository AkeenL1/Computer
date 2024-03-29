The discussion between document & relational databases is similar to the argument in the 1970s revolving around network and relational databsaes.

In the 70s IBM had a database for business processing called IMS (information management system) that used a *hierarchichal model*. This model represented data as a tree of records nested within records, somewhat like the structure of JSON. Like document databases this model was very good for one-to-many relationships but when other models began being referenced and many-to-many relationships were required it was difficult, as well as not supporting joins.

So developers using IMS had either two options
1. Denormalize (duplicate) data across records
2. Manually resolve references to each other ( bring data handling into the application layer)

So other options were researched and to solve this problem two solutions were created to solve the limitations against the heirarchichal model
1. [[The network model]]
2. [[The relational model]]
3. [[Comparison to document databases]]


