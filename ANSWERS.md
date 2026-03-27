# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A process is an independent program in execution with its own memory space, resources, and execution context. A thread is a smaller unit of execution within a process that shares the same memory and resources with other threads in the same process. Threads are lighter-weight compared to processes because they have less creation overhead and can communicate easily via shared memory. In this assignment, we used threads instead of separate processes because threads allow multiple tasks (simulated processes) to run concurrently without duplicating the entire process memory, making the simulation of a Round-Robin scheduler more efficient and easier to manage. Using threads also allows the ready queue and shared data structures to be accessed directly without inter-process communication.]
---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[In Round-Robin scheduling, if a process does not finish its execution within its assigned time quantum, it is placed back at the end of the ready queue to wait for its next turn. For example, if process P2 has 10ms of work and the quantum is 4ms, it will run for 4ms, then move to the end of the queue. It will then wait until the other processes have had their turn, at which point it will run again for the next quantum.

[P2 is running for 4ms
P2 did not finish. Remaining time: 6ms
P2 is moved to the end of the ready queue]

**Explanation of example:**
[Here, P2 used only part of its required CPU time and did not complete its task within the 4ms quantum. The scheduler moved it to the back of the ready queue, ensuring other processes get CPU time, and P2 will resume when it reaches the front again. This behavior ensures fair CPU sharing among all processes.]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[New: P1 is in the New state when it is created but not yet started by the scheduler. This is right after the thread object for P1 is instantiated in the code.
Runnable: P1 becomes Runnable when the scheduler adds it to the ready queue. It is now eligible to run but might wait its turn behind other threads.
Running: P1 enters the Running state when the scheduler assigns CPU time to it. For example, during its time quantum, it executes its instructions.
Waiting: P1 would enter Waiting if it needs to pause for I/O or synchronization, or when it has used up its time quantum and is waiting for its next turn in the ready queue.
Terminated: P1 reaches the Terminated state when it finishes all its execution, meaning it has completed its total required CPU burst and will no longer be scheduled.]
---

## Question 4: Real-World Applications

[Example 1: Web Server Handling Requests
Description:
A web server processes multiple client requests simultaneously. Each request can be treated as a thread that handles reading input, processing data, and sending a response.
Why Round-Robin works well here:
Round-Robin ensures that no single client request monopolizes the server. Each thread gets a fair slice of CPU time, improving responsiveness and making sure all clients are served in a predictable manner.
Example 2: Operating System Task Scheduling
Description:
Modern operating systems run multiple background tasks like file indexing, updates, or system monitoring alongside user applications. Each task can be implemented as a thread.
Why Round-Robin works well here:
Round-Robin gives each task a fair time slice, preventing long-running tasks from starving shorter or more urgent tasks. It provides balanced CPU utilization and smooth multitasking without noticeable delays.]---

## Summary

[Key concepts I understood through these questions:
Threads share memory and resources, while processes have separate memory spaces.
Round-Robin scheduling re-queues unfinished tasks to ensure fairness.
Thread lifecycle states are crucial for understanding concurrent execution.
Concepts I need to study more:
How Waiting state interacts with I/O in real multithreaded systems.
Advanced thread synchronization techniques.
Variations of CPU scheduling algorithms and their performance trade-offs.]
