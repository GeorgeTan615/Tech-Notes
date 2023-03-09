## Where request/response & polling isn't ideal 
- A request takes long time to process
	- Upload a youtube video
- The backend wants to send notification
	- A user just logged in 
- Short polling is good but chatty
- Maybe can use long polling (Kafka uses it)

## What is Long Polling
- Client sends a request
- Server responds immediately with a handle
- Server continues to process the request
- Client uses the handle to check for status
- Server DOES NOT reply until it has the response (effectively blocking until it has a response)
- So we got a handle, we can disconnect and we are less chatty

## Pros and Cons
- Pros
	- Less chatty and backend friendly (don't have to keep making requests)
	- Client can still disconnect (we still have the job id)
- Cons
	- Not real-time (after we get a response, we have to poll again to get another response, but in between we might have missed out on a few other messages, thus not real time)