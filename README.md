# CPU Scheduling Simulator (C)

Operating Systems course project at Birzeit University.

An interactive console program in **C** that simulates four classic CPU scheduling algorithms.
The user adds processes, picks an algorithm, and the program shows the execution timeline (Gantt chart) and the performance metrics of each process.

## Algorithms

| Algorithm | Type |
|---|---|
| **FCFS** (First Come, First Served) | Non-preemptive |
| **SJF** (Shortest Job First) | Preemptive, also known as Shortest Remaining Time First |
| **Round Robin** | Preemptive, with a time quantum chosen by the user |
| **Priority scheduling** | Preemptive (a lower number means a higher priority) |

## Features

- Menu to **add and remove processes** at any time, each with a name, arrival time, burst time and priority
- Input checks: no duplicate process names, arrival time of 0 or more, and burst time greater than 0
- Handles **idle CPU time** when no process has arrived yet
- For every run, the program prints:
  - A **Gantt chart** showing which process runs in each time slot
  - A process table (arrival time, burst time, priority)
  - A **metrics table** with completion time, turnaround time, waiting time and response time for each process
- The original process list is kept, so several algorithms can be run on the same processes and compared

## Example output (priority scheduling)

```
Metrics Table:
---------------------------------------------------------------------------------
| Process Id | Completion Time | Turnaround Time | Waiting Time | Response Time |
---------------------------------------------------------------------------------
|          P1 |               8 |               8 |            3 |             0 |
|          P2 |               4 |               3 |            0 |             0 |
---------------------------------------------------------------------------------
```

## Implementation

- Written in C, with `structs` for processes, the task queue and Gantt chart entries
- Each algorithm is its own function; the process list is saved before each run and restored after it

## How to run

```
gcc CPU_Scheduling.c -o CPU_Scheduling
./CPU_Scheduling
```
