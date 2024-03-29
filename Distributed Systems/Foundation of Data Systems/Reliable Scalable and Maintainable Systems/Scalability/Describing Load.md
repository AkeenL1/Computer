* To discuss questions about or system load we must be able to describe it, this where *load parameters* come into play
	* Load Parameters are simply the numbers we use to describe load
* The decision of what to use as a load parameter depends on the system
	* Requests per second to a server
	* Read and writes to a db
	* Simultaneously active users
	* Cache hit Rate
* Also how to focus on the numbers is dependent on use-case
	* I.E. it may be appropriate for some systems to worry about the average case of your load parameter, for others the bottleneck may be a focus
---
### Example using twitter
* The two main operations twitter supplies are
	* Posting a tweet - this has 4.6k request/sec w/ 12k at peak
	* Viewing home timeline - 300k requests/sec
* So for twitter the amount of write requests and amount of read requests in these specific cases are *load parameters*
* The scaling issues arise w/ the fact that each user follows many people and each user is followed *by* many people
* Twitter has two options for handling this load
	1. When a tweet is posted insert it into a global collection of tweets and when a user requests their home timeline look up all the people that person follow and find the appropriate tweets in the global collection
	2. Maintain a cache for each users home timeline and when a tweet is posted insert the tweet into each users timeline cache, the request to read the timeline is cheap b/c the result has been computed ahead of time
* Initially Twitter used solution 1 but switched to solution 2 as the amount of reads is almost 2^n higher than the amount of writes
* However now posting a tweet requires extra work ( as the tweet must be fanned out to all users that follow the poster) so for accounts with large follower counts they used a combined solution dependent on the amount of followers
* The amount of reads from a timeline and amount of writes were initial load parameters to take into account, however the distribution of followers per user also became an important parameter when discussing scalability