## Synchronous I/O
- Caller sends a request and blocks
- Caller can't execute any code meanwhile
- Receiver responds, Caller unblocks
- Caller and receiver are in 'sync'

## Asynchronous I/O
- Caller sends a request 
- Caller can work until it receives a responds
- Caller either:
	- Checks if the response is ready (epoll, monitor if file descriptors to see if I/O is possible on any of them)
	- Receiver calls back when its done (io_uring, all completed responses will be in completion queue)
	- Spins up a new thread that blocks, while the current main thread remains in CPU and can proceed to other tasks
- Caller and receiver are not necessarily in "sync"

