## PROBLEMS

### PROB1

> In Fig. 2-2, three process states are shown. In theory, with three states, there could be six transitions, two out of each state. However, only four transitions are shown. Are there any circumstances in which either or both of the missing transitions might occur?

The remaining 2 states are: **Block-To-Running** and **Read-To-Block**. For the first case, because of the existence of scheduler, a blocking process cannot begin running immediately. As for the second, logically speaking, a process is not running cannot be blocked.

### PROB2

> Suppose that you were to design an advanced computer architecture that did process switching in hardware, instead of having interrupts. What information would the CPU need? Describe how the hardware process switching might work.

### PROB3

> On all current computers, at least part of the interrupt handlers are written in assembly language. Why?

Because some actions such as saving the registers and setting the stack pointer cannot be expressed in high-level language. These parts are implemented as a small assembly-language routine, usually the same one for all interrupts.

### PROB4

> When an interrupt or a system call transfers control to the operating system, a kernel stack area separate from the stack of the interrupted process is generally used. Why?

### PROB5

> A computer system has enough room to hold five programs in its main memory. These programs are idle waiting for I/O half the time. What fraction of the CPU time is wasted?

The probability that 5 processes are all waiting for IO are **0.5^5**, so the CPU utilization is **1-0.5^5**.

### PROB6

> A computer has 4 GB of RAM of which the operating system occupies 512 MB. The processes are all 256 MB (for simplicity) and have the same characteristics. If the goal is 99% CPU utilization, what is the maximum I/O wait that can be tolerated?

With simple calculation, we could know there are most 14 processes running in the main memory at the same time. Because these processes have the same characteristics, we should solve the equation:
$$1-x^{14}=0.99$$

### PROB7

> Multiple jobs can run in parallel and finish faster than if they had run sequentially. Suppose that two jobs, each needing 20 minutes of CPU time, start simultaneously. How long will the last one take to complete if they run sequentially? How long if they run in parallel? Assume 50% I/O wait.

Each process need 50% IO wait and 20 min of cpu time, so the total time for it is 40 min. If 2 processes run in sequentially, 80 min will be consumed. If they run in parallel, the cpu utilization is 0.75, and the total time this cpu need to work for to finish 2 jobs is 40 min, so the equation is:
$$0.75x=40$$

### PROB8

> Consider a multi-programmed system with degree of 6 (i.e., six programs in memory at the same time). Assume that each process spends 40% of its time waiting for I/O. What will be the CPU utilization?

The same strategy as the previous one.