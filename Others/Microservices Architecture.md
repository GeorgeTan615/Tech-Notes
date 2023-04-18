## What is microservices
In a monolithic system, all components of the system are designed and packed into one single unit. Microservice architecture is a software development style that breaks the system down into smaller independant components.
Big and complex monolithic systems are hard to maintain, any change to a single component would need the entire system to be redeployed.

## Pros
- Scaling up becomes easier
	- Each service designed, developed and deployed independantly. We do not have to tear down our entire system when for updates, allowing seamless updates
- Improved fault tolerance
	- Due to the nature of loose coupling, applications within microservices could continue working even if one service fails. When one microservice breaks down, it doesnt affect the whole system, unaffected microservices could still work and communicate with each other.
- Easier to understand codebase
	- Each microservice/module has a certain purpose and objective, thus easier to understand the codebase as the code revolves around that functionality

## Cons
- Increased communication complexity
	- Microservices have to talk to each other, thus increasing communication overhead.
- Need to be cautious in handling requests between the different modules.
	- The way different systems communicate may be different
- Requires more resources
	- Multiple databases and logs need to be maintained for the microservices
- Testing becomes even more difficult
	- Testing for monolithic applications are relatively easier
	- Each microservices has to be individually tested and also tested as a whole when all microservices are launched
- More complex deployment
	- Need configuration between mutliple services and not as simple as just dumping one entire codebase's code into a single container
- Not practical for smaller applications
	- Microservices can be more time consuming and challenging to implement for small apps. Cons outweight pros.