## What is a serverless function cold start?
Cold start refers to the state of our function when serving a particular invocation request. A serverless function is served by one or multiple micro-containers. When a request comes in, our function will check whether there is already a  container running to serve the invocation. When an idle container is available, we call it a "warm" container. If there isn't a container readily available, the function will spin up a new one and this is what we call a "cold start".

When a function is in cold state, the request will take additional time to complete, due to the latency in starting up a new container.

## Process of container starting from cold state
1. Get the package containing code from external persistent storage.
2. Spin up the container.
3. Load your package code in memory.
4. Run your function's handler method/function. (if in warm state, container jumps right to this step 4).

## Main factors driving cold start latency
- Memory Size
	- The more memory allocated to function, the faster it will start up.
- Runtime
	- Usually scripting languages like Python, Javascript perform better in startup time comparison (although they might be slower in execution time, the saved startup time can offset the slow execution time) to compiled runtime languages like Java, C#
- VPC
	- functions running inside a virtual private cloud will suffer additional latency, taking usually an extra second or two to startup
	- try to design your functions to run outside a VPC
- Code package size
	- The larger the package size, the more time it takes to spin up the new container

## How to solve cold start latency
- Increase memory allocation
	- If cost is not issue, allocate more memory to the functions needed for better startup performance
- Choose faster runtime for workloads that are sensitive to startup time
	- For example Python gives the best startup time for AWS Lambda
- Keep shared data in memory by loading it outside the main event handler method
	- For example loading third party libraries, if we do this loading the handler method, on every request we are calling it, instead we could do it outside of the handler method, so that these libraries are only loaded once and stored in the container
	- This does not speed up cold starts, but reduce startup time for subsequent requests
- Shrink package size
	- Remove unncessary files/codes in the codebase, for example README files/ unused third party libraries 
	- Ultimate goal is to let function fetch a smaller package file
- Keep a pool of pre-warmed functions
	- Set up regular jobs to keep functions warmed
	- Like for AWS Lambda, typical container stays alive for about 30-45 minutes
- Fancy, use time series forecasting to predict how many containers we need to keep warm at certain times
