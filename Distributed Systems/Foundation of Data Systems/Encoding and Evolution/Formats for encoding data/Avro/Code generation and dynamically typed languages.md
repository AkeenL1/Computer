As stated previously, thrift and protocol buffers allow for code generation, this is good for statically typed languages because they allow efficient in-memory datastructured to be used and allow type checking and autocompletion in IDE's.

In dynamically typed languages this is less useful because the goal is to avoid a compilation step, thus code generation is an unnecessary step.

Avro provides optional code generation for statically typed programming languages but can be used w/o code generation just as well. If you have an object container file you can open it using the Avro library and look at the avro schema in the same way you'd look at json. This file is self-describing in this way.