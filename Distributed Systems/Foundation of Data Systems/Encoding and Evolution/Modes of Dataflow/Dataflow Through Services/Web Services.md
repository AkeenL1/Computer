When HTTP is used as a protocol for talking to a service it's called a web service, this is a slight misnomer because as stated previously client applications and other services can also make requests. Nonetheless there are two popular approaches to building web services REST and SOAP

Rest is not a protocol but a design philosophy building on HTTP, its focus is on simple data formats, using URLs for identifying resources and using HTTP features for cache control, authentication, and content type negotiation. An API based on these principles is known as RestFul.

SOAP *is* a protocol for making network API requests, although its commonly used using HTTP it aims to be independent from it and avoids using HTTP features. Instead it comes with a sprawling and complex multitude of standards, known as the web service framework or WS-* that adds features.

The API of a SOAP web service uses and XML based languages called the Web Services Description Language or WSDL. The WSDL enables code generation so that a client can access a remote service using local classes and method calls, which are encoded to xml and decoded by the framework, this is useful in statically typed languages but not dynamically typed ones. 

Since the WSDL is not designed to be human readable SOAP messages are too difficult to be constructed manually and usually generated with tools. This makes SOAP integration difficult with programming languages not supported by vendors.(I.E. if the don't provide an library to generate and utilize their SOAP messages). This causes problems and has caused REST to be much more common. As its a simpler approach and contains easy to use definition formats like OpenAPI (AKA Swagger) which can be used to describe Restful API's and produce documentation.

