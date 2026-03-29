# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A thread is a smaller component inside a process that shares memory with other threads, whereas a process is an active program with its own memory and resources. Threads are faster and lighter than processes, which are heavier and need more time to manufacture. Because they share memory, threads can communicate with each other more readily than processes, which need more sophisticated communication techniques.

Because threads are more effective for simulation, we employed them in this assignment rather than processes. More system resources would be used if several processes were created. With the help of threads, we may mimic several concurrent processes while maintaining a straightforward and quick software. As a result, threads are better suited for simulating CPU scheduling.**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:In Round-Robin scheduling, if a process does not finish within its time quantum, it is moved back to the end of the ready queue to wait for its next turn. This ensures fairness, as all processes get equal CPU time in cycles.

From my program output, we can clearly see this behavior with process P1. Initially, P1 starts executing for 3000ms, but it does not finish its total burst time. It still has remaining time, so it yields the CPU and gets re-added to the ready queue.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
? P1 executing quantum [3000ms]
? P1 completed quantum 3000ms │ Overall progress: 92%
Remaining time: 235ms
? P1 yields CPU for context switch

? P1 added to ready queue │ Burst time: 3235ms │ Priority : 5
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]

In this example, P1 runs for the full quantum (3000ms), but since its total burst time is 3235ms, it still has 235ms remaining. Because of that, it cannot finish in one turn. The scheduler forces it to stop (context switch), and then P1 is placed at the end of the ready queue. Later, we see that P1 runs again and completes its remaining time (235ms), which confirms how Round-Robin scheduling works in cycles.
---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:Every process (such as P1) in this simulation acts like a thread and changes states as it is running.**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [? P1 added to ready queue │ Burst time: 3235ms │ Priority : 5]

2. **Runnable**: [[... ? P20 ? P1]]

3. **Running**: [? P1 executing quantum [3000ms]]

4. **Waiting**: [? P1 yields CPU for context switch]

5. **Terminated**: [? P1 executing quantum [235ms]
? P1 completed quantum 235ms │ Overall progress: 100%
Remaining time: 0ms
? P1 finished execution!]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Server]

**Description**: 
[A web server handles multiple user requests at the same time, such as loading web pages or processing data from users. Each request can be treated as a separate thread that needs CPU time to be processed.]

**Why Round-Robin works well here**: 
[Round-Robin scheduling ensures that each request gets a fair share of CPU time. This prevents one request from blocking others and improves responsiveness. As a result, all users experience faster loading times and the system remains stable under heavy traffic.]

### Example 2: [Multiplayer Online Games]

**Description**: 
[In multiplayer online games, the server manages actions from multiple players, such as movement, attacks, and real-time updates. Each player’s actions can be handled as separate threads.

**Why Round-Robin works well here**: 
[Round-Robin allows each player’s actions to be processed in small time slices, ensuring fairness among all players. This helps maintain smooth gameplay and reduces lag, as no single player can dominate the CPU time.]

---

## Summary

**Key concepts I understood through these questions:**
1. Thread lifecycle
2. CPU scheduling
3. Context switching

**Concepts I need to study more:**
1. Advanced scheduling algorithms
2. Thread synchronization
