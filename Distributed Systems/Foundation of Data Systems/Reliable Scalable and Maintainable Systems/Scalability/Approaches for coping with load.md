When our load parameters increase by a certain amount there are two options we can take
1. Scaling Up - moving to a more powerful machine
2. Scaling out - Distributing the workload across multiple machines
Which method is better depends on the load parameters and changes those make on performance
---
### Scaling
* Good architectures usually involve both vertical and horizontal scaling dependent on the use case of the system
	* I.E even if two systems have the same *throughput* they may have different requirements
* Some systems are *elastic* meaning the add compute resources when they detect a load increase, others are manually scaled especially if the load is unpredictable
* While distributing stateless services across machines is fairly easy, doing so with stateful machines like databases is a bit trickier
	* Conventional wisdom is to keep your database on a single node and keep scaling *up* until cost or availability becomes to big of a requirement
* Architecture that scales well is built around educated guesses using the load parameters to decide which is common and focus on those
* While they are different by a case to case basis they usually do have some basic building blocks across architectures