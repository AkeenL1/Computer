As schema's change overtime thrift and protocol buffers need to handle schema evolution accordingly, maintaing forwards and backwards compatibility.  

This is relatively simple because an encoded record is just a concatenation of its encoded fields, each field is identified by its tag number and annoted with a datatype. If the field value is not set it's omitted from the encoded record. So field tags are critical to the meaning of the encoded data, you can change the name of a field in the schema since the encoded record doesnt refernce the name, but you can't change the fields tag.

Using this fact we can maintain forwards compatibility by making sure when we add new fields to the schema we give each field a new tag number. If old code tries to reads the data with the new field number it will just ignore that field. The datatype annotation tells the parser how many bytes to skip. So old code can read records written by new code with no issue.

To maintain backwards compatibility, as long as each field has a unique tag number new code can always read old data. The only detail is any new fields added cannot be required and must be optional, this is because if you make it required any data written by old code will fail so all new data needs to either be optional or have a default value. 

To maintain compatibility when removing field is similar. You can only remove a field that is optional and you can never use the same tag number again as data might be written somewhere that includes that old tag and any new code needs to ignore it. 