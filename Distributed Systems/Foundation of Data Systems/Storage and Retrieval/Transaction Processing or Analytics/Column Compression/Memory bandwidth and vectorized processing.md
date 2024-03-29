For data warehouses taking data from disk to memory is not the only bottleneck, the CPU is actually quite a large one with a few of the bottlenecks being
* Efficient usage of bandwidth from main memory into the CPU cache
* Avoiding branch mispredictions and bubbles in the CPU instruction processing pipeline
* Making use of single-instruction-multi-data instructions in modern CPUs

One way to handle this inefficiency is to reduce the volume of data being loaded from disk, another way is to make efficient usage of CPU cycles. This is done by the data warehouse query engine, it can take chunks of compressed column data that can fit in the CPU's L1 cache, and iterate it in a loop with few to no function calls and conditions. This also means more rows can fit in the L1 cache. We use bitwise operators to perform most of the operations. This technique is known as vectorized processing. 