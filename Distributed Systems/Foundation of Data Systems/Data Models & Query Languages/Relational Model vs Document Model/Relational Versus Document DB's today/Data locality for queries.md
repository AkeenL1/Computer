In the document model data is stored as one continuous string encoded as JSON or XML ( or some binary version). This *storage locality* ( I.E. way of storing the data) means that if your application needs to access the entire document there is a performance advantage or the relational way of splitting the data and doing multiple queries or joins.

This advantage though only applies if you need the *entire* document as if you only need small portions the database will *still* load the entire document. Also when a record is rewritten the entire document is updated, only changes that don't change the documents encoded size can be done in place, b/c of this it's recommended that you keep the documents generally as small as possible.

However this storage locality is not only specific to the document model, and many different relational db's offer solutions that also allow for a continuous storage locality.
