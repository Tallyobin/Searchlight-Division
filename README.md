**Question 1**<br>
Performance and abilities of disk input/output (I/O) operation depends on several factors; computer system architecture, operating system and disk control hardware.

(a) In disk scheduling, performances among various scheduling policies varies due to difference of value for seek time. What does seek time means? **[1 mark]** <br>

Seek time refers to the time it takes for the disk arm to position the read/write heads at the desired track on the disk. It is a crucial factor in disk I/O performance, as minimizing seek time contributes to faster and more efficient disk operations.

<br>

(b) Label A, B and C accordingly. **[3 marks]**

![Untitled328_20240128020758](https://github.com/Tallyobin/Searchlight-Division/assets/156051265/587e6f12-178d-4e8c-8de3-b024e3860080)

Figure 1 – Disk <br><br>

![Untitled328_20240128023630](https://github.com/Tallyobin/Searchlight-Division/assets/156051265/0364b8a2-a919-476e-939c-35d3e9caf83b)

<br>

(c) There are **FOUR (4)** common disk scheduling policies commonly used; First in First Out (FIFO), Shortest Seek Time First (SSTF), SCAN and C-SCAN.<br>

Consider the following set of information:-<br>
Disk track request : 20, 30, 50, 90, 70, 160, 180, 60, 10<br>
Initial Head location : Track 100<br>
Head movement : Increasing

<br>

(d) Employ **SSTF**, **SCAN** and **FIFO** scheduling policies accordingly and show all the necessary track movements. **[12 marks]** <br>

SSTF (Shortest Seek Time First), SCAN, and FIFO (First In First Out) scheduling policies can be applied to the given disk track requests with an initial head location at Track 100 and head movement in the increasing direction.

Here is the step-by-step track movement for each scheduling policy:

1. **SSTF (Shortest Seek Time First):**
   - Head movement: 90, 70, 60, 50, 30, 20, 10, 160, 180

2. **SCAN:**
   - Head movement: 160, 180, 90, 70, 60, 50, 30, 20, 10

3. **FIFO (First In First Out):**
   - Head movement: 20, 30, 50, 90, 70, 160, 180, 60, 10

These movements represent the order in which the disk arm accesses the specified tracks according to each scheduling policy.

<br><br>

**Question 2**<br>
Scheduling is one of the key that leads to multiprogramming on OS environment. There are FOUR(4) types of process scheduling commonly involved in OS.

(a) List down all types of scheduling. **[4 marks]** <br>

  1. **Long-Term Scheduling**
  2. **Medium-Term Scheduling**
  3. **Short-Term Scheduling**
  4. **I/O Scheduling**

<br>

(b) Fill in the table accordingly on the specific types of scheduling based on the explanation. **[2 marks]**

| Types of Scheduling        | Explanation                                         |
|----------------------------|-----------------------------------------------------|
| Long-Term Scheduling       | Involves selecting processes from the job pool and loading them into memory for execution. Decides which programs are admitted to the system for processing.|
| Medium-Term Scheduling     | Involves swapping processes in and out of main memory to manage the degree of multiprogramming. Decides which processes are to be swapped in and out. |
| Short-Term Scheduling      | Involves selecting a process from the ready queue and allocating the CPU to that process. Decides which process will execute next.|
| I/O Scheduling             | Involves deciding the order in which I/O requests are processed. Manages the input and output operations of processes.|

Table 1 – Scheduling type

<br>

(c) There are several scheduling policies that are commonly employed by the operating system in order to determine which processes will be chosen for execution.

i. There are **TWO (2)** decision modes commonly used on uniprocessors’ scheduling. Name both of them. **[2 marks]** <br>

   1. **Non-Preemptive Scheduling**
   2. **Preemptive Scheduling**

<br>

ii. Draw the scheduling diagram for the information provided in Table 2 by employing Highest Response Ratio Next (HRRN) scheduling policies. Calculate the average waiting time as well. **[11 marks]**

| Process | Arrival Time | Service Time |
| :---    | :---         | :---         |
| J       | 1            | 4            |
| K       | 2            | 2            |
| L       | 5            | 3            |
| M       | 8            | 6            |
| N       | 9            | 4            |

Table 2 - Set of Processes

<br>

| Time  | Process | Execution |
|-------|---------|-----------|
| 0     | -       | -         |
| 1     | J       |           |
| 2     | K       |           |
| 4     | J       |           |
| 6     | L       |           |
| 9     | N       |           |
| 13    | M       |           |
| 19    | -       | -         |

Average Waiting Time (AWT):

<br><br>

**Question 3**

(a) Consider the following system state which are made up of 4 processes and 4 resources shown in Figure 2.

<br>

| a | b | c | d |
|---|---|---|---|

Resource Vector

<br>

| 0 | 1 | 0 | 1 |
|---|---|---|---|

Available Vector

<br>

| 1 | 2 | 3 | 4 |
|---|---|---|---|
| 2 | 2 | 5 | 1 |
| 2 | 1 | 2 | 1 |
| 4 | 3 | 1 | 2 |

Max Matrix

<br>

| 1 | 1 | 1 | 1 |
|---|---|---|---|
| 1 | 2 | 3 | 1 |
| 2 | 0 | 2 | 1 |
| 3 | 2 | 1 | 1 |

Allocation Matrix

<br>

Figure 2

<br>

(i) Find the Need Matrix **[1 mark]** <br>

The Need Matrix is calculated as the difference between the Max Matrix and the Allocation Matrix.



<br>

(ii) Is the system state is in currently safe or unsafe state? Show your working steps / calculation and justify your answer. **[3 marks]** <br>

To determine if the system is in a safe state, the Banker's algorithm can be applied.

1. **Work Vector:** Initialize the Work vector with the Available vector.

2. **Finish Vector:** Initialize the Finish vector with all zeros.

3. **Find a process i where Finish[i] = 0 and Need[i] <= Work.**

   - Initial process: Process 1 (since Need[1] = [0, 0, 1, 0] and Need[1] <= Work).

4. **Work = Work + Allocation[i], Finish[i] = 1**

   - For Process 1: Work = [1, 2, 4, 4], Finish = [1, 0, 0, 0]

5. Repeat steps 3-4 until all processes are marked as finished or no process can be executed.

   - Process 2: Work = [2, 2, 7, 5], Finish = [1, 1, 0, 0]
   - Process 3: Work = [3, 3, 8, 6], Finish = [1, 1, 1, 0]
   - Process 4: Work = [7, 6, 9, 8], Finish = [1, 1, 1, 1]

The system is in a safe state since all processes can finish. The sequence is 1, 2, 3, 4. Therefore, the system is currently in a safe state.

<br><br>

**Question 4**

(a) State **ONE (1)** example of human readable and **ONE (1)** example of machine readable I/O device. **[3 marks]** <br>

- **Human Readable I/O Device Example:** Printer
- **Machine Readable I/O Device Example:** Magnetic Stripe Reader

<br>

(b) There are **THREE (3)** main techniques for performing I/O process. List all of them. **[3 marks]** <br>

1. **Programmed I/O:** The processor issues an I/O command, and the process waits for the operation to be completed before proceeding.
2. **Interrupt-driven I/O:** The processor issues an I/O command, and depending on whether it's blocking or non-blocking, it either continues executing instructions or is blocked, allowing the operating system to schedule another process.
3. **Direct Memory Access (DMA):** A DMA module controls the data exchange between main memory and an I/O module. It allows data to be sent directly from an attached peripheral device to the memory on the computer's motherboard, freeing the processor from direct involvement in the data transfer.

<br><br>

**Question 5**<br>
Deadlocks occur generally because processes deny each other’s’ resources and none can proceed to completion. It is a permanent occurrence that cannot be solved efficiently. In general, there are several ways or strategies to be dealing with deadlock. One of the ways to show a deadlock representation is by using resource allocation graphs.<br>

Processes: PA, PB, PC, PD<br>
Resources: R1 (3units), R2 (2 units), R3 (2 units), R4 (3 units)<br>
Requirements: Processes needs to have 3 different resources before it can be executed / completed.<br>

Draw a Resource Allocation Graph that represents information shown above. **[10 marks]** <br>

To represent the deadlock scenario using a resource allocation graph, we'll follow the given information:

Processes: PA, PB, PC, PD
Resources: R1 (3 units), R2 (2 units), R3 (2 units), R4 (3 units)
Requirements: Processes need to have 3 different resources before they can be executed/completed.

Let's draw the resource allocation graph:

```
          R1 (3)
         /   \
       PA     PB
        |
       R2 (2)
        |
       PC
        |
       R3 (2)
        |
       PD
        |
       R4 (3)
```

In this graph:
- PA and PB are competing for R1.
- PC is waiting for R2, and PD is waiting for R3.
- PA and PB are holding R2 and R3, respectively.
- PD is holding R4.

This configuration leads to a circular wait condition, one of the necessary conditions for a deadlock. If all the processes hold the resources they have and wait for the resources they need, a deadlock occurs.

<br><br>

**Question 6**

(a) The prime purpose of memory management is to ready programs into memory for execution by the processor. Without using virtual memory, there are a few main techniques could be used; partitioning, simple paging and simple segmentation.

(i) What do you understand on the concept of partitioning? **[1 mark]** <br>

Memory partitioning is a memory management technique where the primary memory (RAM) is divided into fixed-size or variable-size partitions. Each partition may contain one process, and multiple processes can be loaded into memory simultaneously, with each occupying its own partition.

<br>

(ii) There are two types of fragmentation that could happen when partitioning technique is being carried out. Name both of the fragmentations, and list down **TWO (2)** differences between both types of fragmentations. **[6 marks]** <br>

1. **Internal Fragmentation:**
   - Occurs when memory allocated to a process is larger than the actual memory required.
   - The unused memory within a partition is wasted.
   - More common in fixed-size partitioning.

2. **External Fragmentation:**
   - Occurs when free memory blocks are scattered throughout the memory, but the total free space is sufficient to satisfy a request.
   - Leads to inefficient use of memory.
   - More common in variable-size partitioning.

Differences:
   - Internal fragmentation is caused by the allocated memory being larger than needed, while external fragmentation is caused by scattered free memory blocks.
   - Internal fragmentation is inherent to fixed-size partitioning, while external fragmentation is more prominent in variable-size partitioning.

<br>

(b) Page Replacement Policy is used to decide on the selection of page in main memory to be replaced when a newer page is brought in.

(i) Name **TWO (2)** algorithms that are commonly used in page replacement policy. **[2 marks]** <br>

1. **Optimal Page Replacement Algorithm**
2. **Least Recently Used (LRU) Algorithm**

<br>

(ii) Given the following information:-<br>
Resident Set = 3 frames, Page address stream: - | 2 | 3 | 4 | 2 | 1 | 3 | 7 | 5 | 4 | 3 |<br>
By using any **ONE (1)** of the algorithms mentioned in Question (b) (i), draw a table that shows the page placement correctly. **[5 marks]** <br>

| Reference | Page Frames | Page Fault | Page Placement               |
|-----------|-------------|------------|-----------------------------|
| 2         | _ _ _       | Yes        | 2 _ _                       |
| 3         | 2 _ _       | Yes        | 2 3 _                       |
| 4         | 2 3 _       | Yes        | 2 3 4                       |
| 2         | 2 3 4       | No         | (No page fault, page 2 was already in memory) |
| 1         | 2 3 4       | Yes        | 1 3 4                       |
| 3         | 1 3 4       | Yes        | 1 3 4                       |
| 7         | 1 3 7       | Yes        | 1 3 7                       |
| 5         | 5 3 7       | Yes        | 5 3 7                       |
| 4         | 5 4 7       | Yes        | 5 4 7                       |
| 3         | 5 4 3       | Yes        | 5 4 3                       |

This is a simplified example, and the actual page placement depends on the specific implementation details of the LRU algorithm.

<br><br>

**Question 7**<br>
Process is a combination of program code and a distinct set of associated data. There are a lot unique and specific trait or elements that characterized data. x is a special
program that switches the processor from one process to another.<br>

(a) Define what is x. **[1 mark]** <br>

   - **Definition:** Context switching is a mechanism performed by the operating system, and x is often used to represent a special program or part of the operating system responsible for switching the processor from one process to another. During context switching, the current state of a process is saved, and the saved state of the next process in the queue is restored.

<br>

(b) For all processes, there are **TWO (2)** main model that explains the states of processes. Name both models accordingly. **[2 marks]** <br>

   1. **Sequential Process Model:** In this model, a process goes through a sequence of states from its creation to termination. The states include new, ready, running, waiting, and terminated. The transition between these states follows a linear progression.
   2. **State Diagram Model:** This model represents the different states a process can be in and the events or conditions triggering transitions between states. It provides a visual representation of the life cycle of a process.

<br>

(c) Process termination stops and halts processes from executing properly. Provide **THREE (3)** reasons that leads to process termination. **[3 marks]** <br>

   1. **Normal Completion:**
      A process completes its execution and terminates voluntarily.
   2. **Fatal Error:**
      The process encounters a critical error or exception that cannot be handled, leading to termination.
   3. **Parent Process Termination:**
      If a process is a child process and its parent process terminates, the operating system may terminate the child processes associated with the parent.

<br>

(d) Label the following Five-State Process Model accordingly. Figure 4 **[5 marks]** <br>

![Untitled329_20240128021651](https://github.com/Tallyobin/Searchlight-Division/assets/156051265/9d36705c-91cb-4df2-8e68-d87dade3b0cc)

<br><br>

**Question 8**<br>

(a) Input / output (I/O) buffering possesses two main problems; user may hung up waiting for completion of I/O process, and the buffer itself may interfere with operating system swapping decision. In order to fix this, there are **THREE (3)** types of I/O buffering could be attempted by operating system. Name all of them. **[3 marks]** <br>

   1. **Single Buffering:**
      Involves using a single buffer for I/O operations. The process waits for the I/O operation to complete before proceeding, which can lead to inefficiency.
   2. **Double Buffering:**
      Utilizes two buffers, allowing the process to transfer data to or from one buffer while the operating system empties or fills the other buffer. This helps overcome the waiting issue.
   3. **Circular Buffering:**
      Involves using more than two buffers arranged in a circular manner. Each individual buffer acts as one unit in the circular buffer, providing a continuous cycle for I/O operations.

<br>

(b) There are several disk scheduling algorithms that could be used to ensure performance of the disk I/O is optimized. Some of the common ones are FIFO, SSTF and SCAN.<br>
Given the following information, draw the reading movement of the Head on the disk, by using the C-Scan algorithm.<br>

Head initial position: Track 100<br>
Disc Track Request: 56, 58, 39, 18, 89, 159, 38, 185<br>
Head movement: Decreasing<br>

Use the following graph as your reference, plot the tracks traverse accordingly. **[9 marks]** <br>

y-axis = Track number<br>

bottom of y-axis = 199<br>
top of y-axis = 0<br>

x-axis = Time

<br>

- C-Scan (Circular SCAN) is an algorithm that moves the disk arm in a circular manner in one direction, servicing requests until reaching the last track, then quickly moving back to the beginning.
- Given the head's initial position at Track 100 and the disk track requests: 56, 58, 39, 18, 89, 159, 38, 185, with head movement in the decreasing direction, the C-Scan movement can be represented as follows:

   ```
   185      159     100     89      58      56      39      38      18
   |--------|-------|------|------|------|------|------|------|------|
   ```

- The head starts at Track 100, moves towards Track 185, then quickly moves back to Track 18, following the circular pattern. This approach helps optimize the disk I/O performance.
