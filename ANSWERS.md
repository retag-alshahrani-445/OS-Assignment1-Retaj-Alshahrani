# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A *Process* is a standalone program with its own memory space, resources, while a *Thread* is a basic unit of CPU utilization and it's associated with a process.
Each process has its own dedicated memory, and data cannot be exchanged directly between processes, whereas threads share the same memory within a single process.
Processes require more resources due to their isolation, while threads consume significantly fewer resources, making them lighter and faster.
Creation overhead of a process is slow and more cost, while a thread is faster and less cost.
In this project, we used threads together to simulate the execution of multiple processes within a single CPU and we need to context switching between them quickly and without high costs.


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round‑Robin scheduling, when a process does not finish within its allocated time quantum, it is preempted and placed back at the end of the ready queue so that it can receive CPU time again in the next round. This ensures fairness because every process gets a turn.  

Example from my output:
```
  ▶ P1 executing quantum [4000ms] 
  ⚡ Quantum progress: [███████████████] 100%
  ⏸ P1 completed quantum 4000ms │ Overall progress: [███████████░░░░░░░░░] 58%
     Remaining time: 2809ms
  ↻ P1 yields CPU for context switch

  ➕ P1 (Priority: 3) added to ready queue │ Burst time: 6809ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P3 → P4 → P5 → P6 → P7 → P8 → P9 → P10 → P1]
└───────────────────────────────────────────────────────────────────────────────
```
P1 was in last of Ready Queue 

after doing the other in Ready Queue and then come back to complate P1
```
  ▶ P1 executing quantum [2809ms]
  ⚡ Quantum progress: [███████████████] 100%
  ⏸ P1 completed quantum 2809ms │ Overall progress: [████████████████████] 100%
     Remaining time: 0ms
  ✓ P1 finished execution!

┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P3 → P4 → P5 → P6 → P7 → P8 → P9]
└───────────────────────────────────────────────────────────────────────────────

```

**Explanation of example:**
The frist part of this example, shown that P1 had an initial burst time of 6809ms, but the Time Quantum was only 4000ms, and after its first turn, P1 still needed 2809ms to finish. My output shows P1 "yielding the CPU" and being moved to the end of the Ready Queue (behind P10). P1 had to wait for all processes from P2 to P10 to finish their respective quanta before it could return to the CPU. In the end, P1 come back again to execute its remaining 2809ms and successfully finished as shown in second part of my output in the above.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. **New**: P1 is in the New state when it is first created in the program but before it is started, in the code that happened when statement `Thread thread = new Thread(process);` is executed in the `addProcessToQueue` function. At this time, the thread has not started execution yet and is not part of the ready queue.

2. **Runnable**:  When  P1  is added to ready queue, at execute `processQueue.add(thread);` at `processQueue` function.
     In output:
     ```
    ➕ P1 (Priority: 3) added to ready queue │ Burst time: 6809ms 
    ```

3. **Running**: P1 transitions to the Running state when the scheduler calls `currentThread.start();` in the `main` method. We can see that in the output:
     ```
    ▶ P1 executing quantum [4000ms]
    ```

4. **Waiting**: P1 enters the Waiting state when it finishes its time quantum but still has remaining burst time or at during the execution of `Thread.sleep(stepTime);` inside the `run()` method. we can see this in output:
     ```
    ↻ P1 yields CPU for context switch
    ```
    This happens to simulate the real-world time it takes for a process to execute

5. **Terminated**: P1 reaches the Terminated state once its Remaining Time = 0ms, this occurs because the condition `if(remainingTime > 0)` is not met. We can see this in the output:
     ```
    Remaining time: 0ms
    ✓ P1 finished execution!
    ```

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Chat Applications

**Description**: 
Chat applications like WhatsApp or Telegram handle messages from a large number of users simultaneously.

**Why Round-Robin works well here**: 
Because it ensures that every user has the opportunity to send and receive messages without significant delay, thus improving the user experience.

### Example 2: Online Multiplayer Games (PUBG)

**Description**: 
Online multiplayer games require players to continuously update their status (movement, attacks, scores, ..).

**Why Round-Robin works well here**: 
Because it ensures that every player receives an equal amount of time to update, maintaining game fairness and smooth performance.

---

## Summary

**Key concepts I understood through these questions:**
1. How thread states change during execution
2. The difference between threads and processes
3. Thread Lifecycle ( New, Runnable, Running, Waiting, and Terminated states) 

**Concepts I need to study more:**
1. predictability, I want to learn more abaut it.
2. Detailed behavior of context switching.
