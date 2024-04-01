In this section we discuss what happens if multiple machines are involved in data processing.

Theres a couple reasons why using multiple machines is
Scalability - If the data volume is larger than a single machine coan handle you can spread the load across multiple machines
Fault Tolerance/High Availability - if one a or multiple machines goes down you still have redundancy
Latency - You can server requests to users all over the world from specific datacenters close to them.

There are two types of vertical scaling architectures
Shared-Memory and Shared disk architecture
Shared-Memory architecture is effectively joining together many CPUs, Disks, and RAM under one operating system allowing the CPU to access any part of memory or disk, This has its bonuses but the problem is cost is not linear, I.E. with 2x as many cpus ram and disks the cost will likely be more than 2x higher, also we're still limited to a single geographic location and limited fault-tolerance ( we can swap parts of the machine should they go down, but if the machine goes down we go down )

Shared-Disk is multiple machines sharing the same disk but with independent CPU and RAM, this architecture is somewhat common in data warehousing but has some wweaknesses especially with the need to take great care in locking procedures that can limit its scalability.

Shared-Nothin architectures or horizontal scaling has gained a bit of popularity.

In it each machine is called a node ( a collection of nodes is a cluster ) and each node uses its CPU RAM and Disk independently. These have a lot of bonuses but require quite a bit more caution from the developer. as there are additional complexities that if handled incorrectly can result in a single machine still outperforming a cluster with 100s of CPU cores

There are two ways we keep data distributed across nodes
Replication  - keeping a copy of the data on several different nodes potentially in different locations, this provides redundancy
Partitioning ( aka sharding ) - splits the data up into different partitions assigned to different nodes

[[Replication]]
[[Partitioning]]
[[Transactions]]
[[Trouble with distributed Systems]]
[[Consistency and Consensus]]
