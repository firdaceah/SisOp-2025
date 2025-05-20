# CPU Scheduling

Nama: Firda Rahayu

NRP: 3124521002

Kelas: 1 TI A 

## Chapter 5 Exercises
5. 17. Consider the following set of processes, with the length of the CPU burst given in milliseconds:
    
    | Process    | Burst Time | Priority |
    |------------|------------|----------|
    |    P1      |     5      |     4    |
    |    P2      |     3      |     1    |
    |    P3      |     1      |     2    |
    |    P4      |     7      |     2    |
    |    P5      |     4      |     3    |

    The processes are assumed to have arrived in the order P_{v} P_{2}*r P3, P_{4r} all at time 0.

    a. Draw four Gantt charts that illustrate the execution of these pro-cesses using the following scheduling algorithms: FCFS, SJF, non-preemptive priority (a larger priority number implies a higher priority), and RR (quantum = 2).

    b. What is the turnaround time of each process for each of the scheduling algorithms in part a?

    c. What is the waiting time of each process for each of these schedul ing algorithms?

    d. Which of the algorithms results in the minimum average waiting time (over all processes)?

Answer:

a. Gantt Charts and Execution Order:

- First-Come, First-Served (FCFS): Following the arrival order (P1,P2,P3,P4,P5).

|   P1   |  P2  | P3 |      P4    |   P5   |
|--------|------|----|------------|--------|
0    5    8    9    16   20


- Shortest-Job-First (SJF) (Non-Preemptive): Processes with the shortest burst time are executed first (P3,P2,P5,P1,P4).

|--P3--|---P2---|----P5----|----P1----|-------P4-------|
0     1        4         8        13              20

- Priority (Non-Preemptive): Processes with the highest priority (smallest numerical value) are executed first (P2,P3,P4,P5,P1).

|---P2---|--P3--|-------P4-------|----P5----|----P1----|
0      3      4              11        15        20

Round Robin (Quantum = 2 ms): Each process is allocated a time quantum of 2 ms in a cyclic manner.

|--P1--|--P2--|--P3--|--P4--|--P5--|--P1--|--P4--|--P5--|--P1--|--P4--|
0     2     4     5     7     9    11    13    15    17    19
|--P4--|
19    20

b. Turnaround Time

    | Process    | FCFS (ms) | SJF (ms) | Priority (ms) | Round Robin (ms)  |
    |------------|-----------|----------|---------------|-------------------|
    |    P1      |     5     |     13   |       20      |        19         |
    |    P2      |     8     |     4    |        3      |         4         |
    |    P3      |     9     |     1    |        4      |         5         |
    |    P4      |     16    |     20   |       11      |        20         |
    |    P5      |     20    |     8    |       15      |        13         |

c. Waiting Time

    | Process    | FCFS (ms) | SJF (ms) | Priority (ms) | Round Robin (ms)  |
    |------------|-----------|----------|---------------|-------------------|
    |    P1      |     0     |     8    |       15      |        14         |
    |    P2      |     5     |     1    |        0      |         1         |
    |    P3      |     8     |     0    |        3      |         4         |
    |    P4      |     9     |     13   |        4      |        13         |
    |    P5      |     16    |     4    |       11      |         9         |
    |    Average |     7.6   |     5.2  |       6.6     |        8.2        |

d. Algorithm with minimum average waiting time:

Based on the calculated average waiting times, the Shortest-Job-First (SJF) algorithm yields the minimum average waiting time of 5.2 ms. This is attributed to SJF's strategy of prioritizing the execution of processes with the shortest burst times, thereby reducing the overall waiting time for other processes in the system.

However, it is important to note that the practical implementation of SJF can be challenging due to the requirement of knowing the burst time of processes in advance. Furthermore, non-preemptive SJF can potentially lead to starvation for processes with longer burst times if there is a continuous influx of shorter processes. 

5. 18. The following processes are being scheduled using a preemptive, priority-based, round-robin scheduling algorithm..

    | Process    | Priority   | Burst    | Arrival  |
    |------------|------------|----------|----------|
    |    P1      |     8      |     15   |     0    |
    |    P2      |     3      |     20   |     0    |
    |    P3      |     4      |     20   |     20   |
    |    P4      |     4      |     20   |     25   |
    |    P5      |     5      |     5    |     45   |
    |    P6      |     5      |     15   |     55   |

    Each process is assigned a numerical priority, with a higher number indi-cating a higher relative priority. The scheduler will execute the highest-priority process. For processes with the same priority, a round-robin scheduler will be used with a time quantum of 10 units. If a process is preempted by a higher-priority process, the preempted process is placed at the end of the queue.

    a. Show the scheduling order of the processes using a Gantt chart.

    b. What is the turnaround time for each process?

    c. What is the waiting time for each process?

Answer:

a. Gantt Chart for Preemptive Priority-Based Round-Robin Scheduling:

We need to carefully simulate the execution based on arrival times, priorities, and the round-robin quantum for equal priorities.

- Time 0: P1 (priority 8) and P2 (priority 3) arrive. P2 has a higher priority, so it starts executing.

- Time 10: P2 has executed for its first quantum. No higher-priority process has arrived. P2 continues as it still has the highest priority.

- Time 20: P2 has executed for another quantum. P3 (priority 4) arrives. P2 (priority 3) still has a higher priority, so it continues.

- Time 25: P4 (priority 4) arrives. P2 (priority 3) still has a higher priority, so it continues.

- Time 30: P2 finishes its remaining burst (20). Now, the ready queue contains P1 (priority 8), P3 (priority 4), and P4 (priority 4). P3 and P4 have the same priority, so they will be scheduled using round robin with a quantum of 10. P3 starts.

- Time 40: P3 has executed for its first quantum. P4 gets its turn.

- Time 45: P5 (priority 5) arrives. P4 (priority 4) has a higher priority, so P4 continues.

- Time 50: P4 has executed for its first quantum. P3 gets its next turn.

- Time 55: P6 (priority 5) arrives. P3 (priority 4) has a higher priority, so P3 continues.

- Time 60: P3 finishes its remaining burst (20). Now, the ready queue contains P1 (priority 8), P4 (remaining burst 10, priority 4), P5 (priority 5), and P6 (priority 5). P4 has the highest priority among these. P4 resumes.

- Time 70: P4 finishes its remaining burst (10). Now, the ready queue contains P1 (priority 8), P5 (priority 5), and P6 (priority 5). P5 and P6 have the same priority, so they will be scheduled using round robin with a quantum of 10. P5 starts.

- Time 75: P5 finishes its burst (5). P6 gets its turn.

- Time 85: P6 executes for its first quantum. P_1 (priority 8) has been waiting. P1 has a higher priority than P6 (priority 5), so P6 is preempted, and P1 starts.

- Time 95: P1 executes for its first quantum. P1 continues as it still has the highest priority.

- Time 105: P1 finishes its remaining burst (15). P6 resumes its execution.

- Time 110: P6 finishes its remaining burst (5).


|----P2----|----P2----|----P3----|----P4----|----P3----|----P4----|--P5--|----P6----|----P1----|----P1----|--P6--|
0         10        20        30        40        50        60        70    75        85        95       105   110

b. Turnaround Time:

- P1: Finish Time - Arrival Time = 105 - 0 = 105

- P2: Finish Time - Arrival Time = 30 - 0 = 30

- P3: Finish Time - Arrival Time = 60 - 20 = 40

- P4: Finish Time - Arrival Time = 70 - 25 = 45

- P5: Finish Time - Arrival Time = 75 - 45 = 30

- P6: Finish Time - Arrival Time = 110 - 55 = 55

c. Waiting Time:

Waiting Time = Turnaround Time - Burst Time

- P1: 105 - 15 = 90

- P2: 30 - 20 = 10

- P3: 40 - 20 = 20

- P4: 45 - 20 = 25

- P5: 30 - 5 = 25

- P6: 55 - 15 = 40