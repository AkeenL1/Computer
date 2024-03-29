Apache Thrift and Protocol Buffers (aka protobuf) are binary encoding libraries based on the principle of binary encoding. Both thrift and Protocol Buffers require a schema for any data that is encoded, once used each come with a code generation tool that takes the schema definition and produces classes that implement the schema in various languages. The application code can call the generated code to encode or decodes records of that schema. 

Thrift has two different binary encoding formats
* Binary Protocol
* Compact Protocol

Binary Protocol - similar to most binary encodings each field has a type annotation indicating the type of the field (int, string, list, etc. ) and a length indication, and the actual data is encoded using ASCII or UTF-8. The main difference is that the field name is not present (I.E. not userName: "akeen" encoded) instead the encoded data contains a field tag that appears in the schema definition. Field Tags are aliases for fields and a compact way of saying what field we're on without having to spell out the field name

Thrift Compact Protocol is semantically the same as BinaryProtocol however it can encode the data into much smaller bytes, it does this by packing the field type and tag number into a single byte and using variable-length integers. I.E. instead of use the full 8 bytes to enode 1337 its encoded in two bytes, iwth the top bit of each byte used to indicate whether there are more bytes to come

Protocol Buffers are similar to thrift compact protocol.

Note: there are required and optional keywords when defining the schema, but this makes no difference to how the field is encoded  it only enables a runtime check if the field is not set which can be useful for catching bugs. 

[[Field tags and schema evolution]]
[[Data Types and Schema Evolution]]
