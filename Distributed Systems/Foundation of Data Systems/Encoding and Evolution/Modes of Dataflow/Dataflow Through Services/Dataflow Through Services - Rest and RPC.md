The most common way to arrange processes communicating over a network is client, server with servers exposing API over the network that clients can request to, the API is known as the service

The web works by web browsers acting as clients and making requests to web servers, I.E. GET, POST, etc. The API consists of protocols and data formats, I.E. HTML, SSL/TLS etc. Since everyone agrees on how to use these standards the web should work no matter what client you use. 

Web browsers aren't the only type of client, a native app running on a mobile device or computer can make network requests, so can client-side java applications running inside web browsers, this is what ajax is, the response in these cases are generally in formats like json that can be easily parsed by the client. The main thing to note is that the API implemented on the top is application-specific and the client and server need to agree on its details. 

A server itself can also be a client to another service, this is effectively what SOA's(service oriented architecture)/Microservices are. In some ways services are similar to databases in that they allow clients to submit and query data. While databases allow arbitrary queries using the query languages, services expose an application specific API.  These API encapsulate and restrict what the client can and can't do.

The goak of using microservices is to make the application easier to change and manage, by building each service independently. If each service is owned by a single team, we can iterate frequently without having to coordinate. This means we should expect old and new versions of servers and clients to be running at the same, and data encoding used by servers and clients must be compatible across versions of the service API.

[[Web Services]]
[[The problems with remote procedure calls]]
[[Current directions for RPC]]
[[Data Encoding and evolution for RPC]]