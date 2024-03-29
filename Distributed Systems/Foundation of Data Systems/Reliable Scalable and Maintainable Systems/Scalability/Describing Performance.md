Once we've described the load parameters we care about in our system we want to look at what happens when that load increases, specifically
* When load increases and system resources are kept the same how does *performance* change
* When load increases how much of increase is needed in computer resources to keep the performance the same
Both questions require performance numbers, namely how does the *throughput* and *response time* of a system change when that load parameter is increased
---
### Throughput and Response Time
* In large data processing (I.E. batch processing) we care about *throughput* - the number of records we can process per second
* In online systems we care about *response times* - The time it takes from a client sending a request to receiving a response back
	* Note: Latency and Response Time are used similarly but are inherently different
	* Latency is the time it takes for a request to be handled, response time is the time it takes for a request to be picked up, processed, and returned
---
### Analyzing response time
* There are discrepancies in response time in each request so it's not useful to look at the average but rather look at the distribution of response times
	* The median is generally a good metric to track to know how long a user will generally wait for a request
* We can also look at outliers by looking at the 95th, 99th or 99.9th percentage of response times, these might be caused by large data processing etc.
	* These high percentiles - also known as *tail latencies* are important as they affect users' experience, I.E. the outliers are possibly the ones using the system the most, or a certain percentile is used in business agreements between companies using your service.
* At these high percentiles queuing delays often account for a large part
	* A server can only process a small amount of things in parallel (i.e. its limited by the amount of cpu cores it has)
	* This means a couple of large requests that take a large amount of time being processed holds up any smaller requests increasing the response time for all of them.
	* Therefore we must measure client response times on the client side and when creating artificial load queue requests on after another with no wait time to include simulation of these queueing delays