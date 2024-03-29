* Humans design & build systems so generally speaking they will be imperfect as humans *are imperfect*
---
### Preventing human error
* Designing systems so that opportunities for error are limited
	* I.E. well abstracted api's and admin interfaces that allow for proper execution of the system w/o being to restrictive and forcing users to find work arounds
* Decouple the areas where the most mistakes are made from where those mistakes can cause failure
	* I.E. provide sandbox environments using real data but in a way that won't affect real users
* Test thoroughly at all levels and utilizing all types
* Allow quick recovery and rollback from a bad state
* Setup clear monitoring & performance metrics and error rates
	* This is known as telemetry