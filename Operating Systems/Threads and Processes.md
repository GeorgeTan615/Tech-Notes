## Processes
Processes are programs that are scheduled in the CPU for execution.

## Thread
Thread is a segment of a process which means a process can have multiple threads.

## Context Switch
A context switch is the process of storing the state of the process of thread, so that it can be restored and resume execution at a later point and then restoring a different, previously saved, state.


## Processes VS Threads
| **Processes** | **Threads** |
|---------------|-------------|
| Process means any program that is executable.         | Thread means a segment of a process.         |
| Process takes more time to terminate         | Thread takes less time to terminate         |
| Takes more time for creation         | Takes less time for creation         |
| Process is less efficient in terms of communicatioh         | Thread is more efficent in terms of communication.         |
| Process is isolated         | Thread shares memory         |
| Process is heavyweight process         | Thread is lightweight as each thread in a process shares code, data and resources.         |
| Process can have states new, ready, running, waiting, terminated, and suspended         | Thread has states, running, ready and blocked         |
| Process switching uses an interface in an operating system.         | Thread switching does not require calling an OS and causes an interrupt to the kernel.         |
| If one process is blocked, it will not affec the execution of other processes         | If a user-level thread is blocked, then all other user-level threads are blocked.         |