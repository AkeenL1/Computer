The network model was standardized at the Conference on Data Systems Language (CODASYL)
* b/c of this the network model is sometimes referenced to as the codasyl model

The network model was effectively a generalized version of the hierarchical model meaning it allowed for every record to have multiple parents as opposed to every record only being allowed one parent in the hierarchical model. This change meant the network model could be used to effectively model many-to-many data relationships.

The links between records in the CODASYl model was not done through foreign keys, but through pointers that were still stored on disk. To find a record one had to traverse pointers to records similarly to traversing a linked list. Meaning that application code had to keep track of the routes to records.

This worked at the time because manual access paths were able to make efficient use of the limited hardware at the time, but had a high amount of complexity as querying and updating the database was a difficult thing to do. If the access paths changed you had to rewrite query code to handle the new access path, and if that code didn't exist there was no easy way to find a record. Thus the network (CODASYL) model ( and by extension the hierarchical model) had relatively low operability, evolvability, and maintainability. 

