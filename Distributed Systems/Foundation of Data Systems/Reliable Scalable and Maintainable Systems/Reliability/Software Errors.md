* With hardware faults there may be a weak correlation between two faults but generally speaking each fault is distinct and caused by some issue localized to the hardware
* With software however this is not the case as a systematic error across the system are usually correlated across nodes, because of this they are harder to anticipate and cause many more system failures than hardware faults
---
### Types of software faults
* Software bugs that cause exceptions and/or crashes
* Runaway processes using up shared resources
* A service the system depends on stops working as expected, such as slowing down or return corrupted responses
* Cascading failures,  a small fault in one component causes another failure in a larger one 
These faults are generally caused by the software of the system making an assumption during its process that is *usually* true but can be incorrect, b/c of this software faults can lie dormant for quite a while when compared to hardware faults
---
### Preventing software faults
* There is generally no quick solution for software faults many things can help such as thorough testing, careful though about the design, analysis of the system etc.
* These are all techniques and tools that can increase the prevention or tolerance of software faults