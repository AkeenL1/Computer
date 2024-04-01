In this section we look at asynchronous message-passing systems, in these they're similar to RPC in that the clients request is delivered to a process w/ low latency, they're similar to databases in that the message is not dent via direct network connection but goes through an intermediary called a message broker

Message brokers do a couple things
* Act as a buffer if the receipient can receive the message immediatly
* Automatically redeliver messages
* Avoids the sender neediing to know the IP addresss and port number of the recepient
* Allows one message to be sent to several recepients
* Decouples the sender from the resident

There are many different types of message brokers, RabbitMQ and ApacheKafka being two open source popular ones, the core idea is that one process sends a message to be sent to a named queue or a topic, the broker ensures the message is delivered to that queue or topic that is subscribed to by a consumer. As long as the encoding format is forwards and backwards compatible you can use any encoding format.

Another way of passing messages is using distributed actor frameworks, that allow us to use the actor model. The actor model is a programming model for concurrency in a single process, the logic is encapsulated in actors and each actor sends and receives asynchronous messages, since each actor processes one message at a time it doesn't need to worry about threads and each actor can be scheduled independenlty

These frameworks can be used to scale an application across multiple nodes, a distributed actor framework essentially integrates a message broker and the actor programming model into a single framework., as long s the encoding format is forwards and backwards compatible to support upgrades you can use it.