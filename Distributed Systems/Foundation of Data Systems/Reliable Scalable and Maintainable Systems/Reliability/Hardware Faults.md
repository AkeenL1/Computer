* Hardware faults such as hard disk crashes and faulty ram are not uncommon, however 
---
### Hardware fault solutions
* The first response is to add physical redundancy, which until recently was enough and generally only required by a small number of applications. Now however as data has increased so has the need for more and larger machines which means there's an increase in the amount of hardware faults, as well as the increase in errors from increased usage of cloud based services (AWS)
* To handle these systems are being built w/ a focus on tolerating the loss of an entire machine by using software fault-tolerance techniques in addition to hardware redundancy
* A system that can handle these losses can fail and be patched one node at a time without downtime of the entire system.