JSON XML and to a lesser extent CSV are the most popular data encoding formats. Each as a text format meaning they're all human readable, although there are arguments on which one has the best syntax. However there are some issues amongst the formats as well

1. There's ambiguity around encoding numbers, in XML and CSV there's no difference between an integer and a string with numbers, in JSON there is a distinction, but it doesnt differ between ints and floating point numbers, and struggles to handle large values & percision. 
2. JSON and XML have support for unicode character strngs but not binary strings, binary strings are useful so to get around this the strings are usually Base64 encoded and the schema dictates that the value should be Base64 decoded, this works but is hacky and increases data size.
3. There is optional schema support for JSON and XML and if you don't use the schema the logic to decode the text needs to be hardcoded in the application
4. CSV doesn't have any schema and always has to be handled by application logic

Despite these flaws, the majority of organizations have agreed on how to use each these text formats and that fact alone means they're likely to continue being the most widely used. 

[[Binary Encodings]]