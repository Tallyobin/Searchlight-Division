**Question 1**<br>
Performance and abilities of disk input/output (I/O) operation depends on several factors; computer system architecture, operating system and disk control hardware.

(a) In disk scheduling, performances among various scheduling policies varies due to difference of value for seek time. What does seek time means? **[1 mark]** <br>

The time it takes to position the head at the track

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

| Types of Scheduling        | Explanation                                                                                         |
|----------------------------|-----------------------------------------------------------------------------------------------------|
| Long-Term Scheduling       | The decision to add to the pool of processes to be executed.                                        |
| Medium-Term Scheduling     | The decision to add to the number of processes that are partially or fully in main memory.          |
| Short-Term Scheduling      | The decision as to which available process will be executed by the processor.                       |
| I/O Scheduling             | The decision as to which process’s pending I/O request shall be handled by an available I/O device. |

Table 1 – Scheduling type

<br>

(c) There are several scheduling policies that are commonly employed by the operating system in order to determine which processes will be chosen for execution.

i. There are **TWO (2)** decision modes commonly used on uniprocessors’ scheduling. Name both of them. **[2 marks]** <br>

   1. **Nonpreemptive**
   2. **Preemptive**

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

| J | K | L | M | N |
|---|---|---|---|---|

1   5   7   10  16  20


at T5 = K & L have arrived

```
RRK = ((5 - 2) + 2) / 2
    = (3 + 2) / 2
    = 5 / 2
    = 2.5

RRL = ((5 - 5) + 3) / 3
    = 3 / 3
    = 1
```
    
at T10 = M & N have arrived

```
RRM = ((10 - 8) + 6) / 6
    = (2 + 6) / 6
    = 8 / 6
    = 1.33

RRN = ((10 - 9) + 4) / 4
    = (1 + 4) / 4
    = 5 / 4
    = 1.25
```

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

The Need Matrix is calculated as the difference between the Max Matrix and the Allocation Matrix.<br>

Need = Max - Allocation<br>

```
| 1 | 2 | 3 | 4 |   | 1 | 1 | 1 | 1 |
|---|---|---|---|   |---|---|---|---|
| 2 | 2 | 5 | 1 | - | 1 | 2 | 3 | 1 |
| 2 | 1 | 2 | 1 |   | 2 | 0 | 2 | 1 |
| 4 | 3 | 1 | 2 |   | 3 | 2 | 1 | 1 |
```

<br>

```
| 0 | 1 | 2 | 3 |
|---|---|---|---|
| 1 | 0 | 2 | 0 |
| 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 1 |
```

<br>

(ii) Is the system state is in currently safe or unsafe state? Show your working steps / calculation and justify your answer. **[3 marks]** <br>

| 0 | 1 | 0 | 1 |
|---|---|---|---|

Available Vector

<br>

| 0 | 1 | 2 | 3 |
|---|---|---|---|
| 1 | 0 | 2 | 0 |
| 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 1 |

Need Matrix

<br>

For process P0, Need = (0, 1, 2, 3) and Available = (0, 1, 0, 1)<br>
Need <= Available = False

<br><br>

**Question 4**

(a) State **ONE (1)** example of human readable and **ONE (1)** example of machine readable I/O device. **[3 marks]** <br>

- **Human Readable I/O Device Example:** Keyboard
- **Machine Readable I/O Device Example:** Controllers

<br>

(b) There are **THREE (3)** main techniques for performing I/O process. List all of them. **[3 marks]** <br>

1. **Programmed I/O**
2. **Interrupt-driven I/O**
3. **Direct memory access (DMA)**

<br><br>

**Question 5**<br>
Deadlocks occur generally because processes deny each other’s’ resources and none can proceed to completion. It is a permanent occurrence that cannot be solved efficiently. In general, there are several ways or strategies to be dealing with deadlock. One of the ways to show a deadlock representation is by using resource allocation graphs.<br>

Processes: PA, PB, PC, PD<br>
Resources: R1 (3units), R2 (2 units), R3 (2 units), R4 (3 units)<br>
Requirements: Processes needs to have 3 different resources before it can be executed / completed.<br>

Draw a Resource Allocation Graph that represents information shown above. **[10 marks]** <br>

![Screenshot_170](https://github.com/Tallyobin/Searchlight-Division/assets/156051265/678b1105-ede9-4bf1-bead-d12a62f975e8)

<br><br>

**Question 6**

(a) The prime purpose of memory management is to ready programs into memory for execution by the processor. Without using virtual memory, there are a few main techniques could be used; partitioning, simple paging and simple segmentation.

(i) What do you understand on the concept of partitioning? **[1 mark]** <br>

**Partitioning is an early method of managing memory.**

<br>

(ii) There are two types of fragmentation that could happen when partitioning technique is being carried out. Name both of the fragmentations, and list down **TWO (2)** differences between both types of fragmentations. **[6 marks]** <br>

1. **Internal Fragmentation:**
   - Occurs when memory allocated to a process is larger than the actual memory required.
   - The unused memory within a partition is wasted.
   - More common in Fixed Partitioning.

2. **External Fragmentation:**
   - Occurs when free memory blocks are scattered throughout the memory, but the total free space is sufficient to satisfy a request.
   - Leads to inefficient use of memory.
   - More common in Dynamic Partitioning.

Differences:
   - Internal fragmentation is caused by the allocated memory being larger than needed, while external fragmentation is caused by scattered free memory blocks.
   - Internal fragmentation is inherent to Fixed Partitioning, while external fragmentation is more prominent in Dynamic Partitioning.

<br>

(b) Page Replacement Policy is used to decide on the selection of page in main memory to be replaced when a newer page is brought in.

(i) Name **TWO (2)** algorithms that are commonly used in page replacement policy. **[2 marks]** <br>

1. **Optimal**
2. **Least recently used (LRU)**

<br>

(ii) Given the following information:-<br>
Resident Set = 3 frames, Page address stream: - | 2 | 3 | 4 | 2 | 1 | 3 | 7 | 5 | 4 | 3 |<br>
By using any **ONE (1)** of the algorithms mentioned in Question (b) (i), draw a table that shows the page placement correctly. **[5 marks]** <br>



<br><br>

**Question 7**<br>
Process is a combination of program code and a distinct set of associated data. There are a lot unique and specific trait or elements that characterized data. x is a special
program that switches the processor from one process to another.<br>

(a) Define what is x. **[1 mark]** <br>

**x is a Dispatcher**

<br>

(b) For all processes, there are **TWO (2)** main model that explains the states of processes. Name both models accordingly. **[2 marks]** <br>

   1. **TWO-STATE PROCESS MODEL**
   2. **FIVE-STATE PROCESS MODEL**

<br>

(c) Process termination stops and halts processes from executing properly. Provide **THREE (3)** reasons that leads to process termination. **[3 marks]** <br>

   1. **Normal completion**
   2. **Arithmetic error**
   3. **Parent termination**

<br>

(d) Label the following Five-State Process Model accordingly. Figure 4 **[5 marks]** <br>

![Untitled329_20240128021651](https://github.com/Tallyobin/Searchlight-Division/assets/156051265/9d36705c-91cb-4df2-8e68-d87dade3b0cc)

<br><br>

**Question 8**<br>

(a) Input / output (I/O) buffering possesses two main problems; user may hung up waiting for completion of I/O process, and the buffer itself may interfere with operating system swapping decision. In order to fix this, there are **THREE (3)** types of I/O buffering could be attempted by operating system. Name all of them. **[3 marks]** <br>

   1. **Single Buffer**
   2. **Double Buffer**
   3. **Circular Buffer**

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
