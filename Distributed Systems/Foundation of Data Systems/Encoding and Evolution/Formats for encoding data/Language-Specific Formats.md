Many programming languages from with built in support for encoding objects, such as java serializeable. They're very convenient because they allow in-memory objects to be saved and restored w/ minimal additions to code. 

However there are also some problems.

1. The encoding is often tied to a particular language, which means reading data encoded in another language can be difficult, especially if trying to integrate w/ other systems.
2. The decoding process needs to be able to instantiate arbitrary classes, this can be a security risk if an attacker can get you're application to decode an arbitrary byte sequence they could be able to execute code. 
3. Versioning Data is not as important in these languages & there are some difficulties w/ forwards & backwards compatibility. 
4. Efficiency is often an after thought as well.

* For these reasons we generally don't want to the built-in encoding system.

