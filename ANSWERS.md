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

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?]

2. **Runnable**: [When does P1 become Runnable?]

3. **Running**: [When is P1 Running?]

4. **Waiting**: [When/why would P1 be Waiting?]

5. **Terminated**: [When is P1 Terminated?]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

### Example 2: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
