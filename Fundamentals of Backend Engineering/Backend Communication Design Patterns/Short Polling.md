## What is short polling
- Normally when u have a request that takes a long time to process and we want to execute it asynchronously, we would get like a job ID or smth, and we can poll and keep checking "is the job done?"
- Client sends a request
- Server responds immediately with a handle (job id etc)
- Server continues to process the request (free to do whatever with it, put it into a queue, put it into disk, persist it into memory etc)
- Client will use the handle to check the status
- Multiple "short" request response as polls 

## Where request/response isn't ideal
- A request takes too long to process
	- Upload a youtube video
- The backend wants to send notification
	- User just logs in
- Polling is a good communication style


## Pros and Cons
- Pros
	- Simple
	- Good for long running requests
	- Clients can disconnect (persist the job id to disk)

- Cons
	- Too chatty (network can get digested if alot of people keep polling)
	- Network bandwidth 
	- Wasted backend resources (keep checking if the specific job is completed, and most of the time is just returning false)