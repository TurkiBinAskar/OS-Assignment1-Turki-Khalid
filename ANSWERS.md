# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer: The CPU saves the process's current progress, takes it off the CPU, and moves it to the very back of the Ready Queue. The CPU then immediately switches to the next process at the front of the line.

 ? P1 executing quantum [3000ms] 

  ? Quantum progress: [???????????????] 20%
  ? Quantum progress: [???????????????] 40%
  ? Quantum progress: [???????????????] 60%
  ? Quantum progress: [???????????????] 80%
  ? Quantum progress: [???????????????] 100%
  ? P1 completed quantum 3000ms ? Overall progress: [????????????????????] 67%
     Remaining time: 1428ms
  ? P1 yields CPU for context switch

  ? P1 priority = 5 added to ready queue ? Burst time: 4428ms  Example of round robin

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**
New (Created): This happens inside your addProcessToQueue method with the line:
Thread thread = new Thread(process);
At this exact moment, the thread for P1 exists in memory, but the operating system doesn't know about it yet.

2. Runnable (Ready) : This happens in your main scheduling loop when it calls:
currentThread.start();
Calling start() does not instantly execute the code; it simply transitions the thread to the Runnable state, adding it to the JVM's internal ready queue.

3. Running : his occurs when the JVM internally invokes P1's @Override public void run() method. P1 starts calculating its runTime and begins printing the progress bar to the terminal.

4. Waiting (Timed Waiting / Blocked) : Inside its run() method, P1 needs to simulate taking up actual time. It calls Thread.sleep(stepTime);. While sleeping, P1 temporarily yields the CPU and enters a timed waiting state until the milliseconds run out.

5. Terminated (Dead) : After P1 finishes its for loop for the progress bar, subtracts its runTime from its remainingTime, and prints either the "yields CPU" or "finished execution!" message, it hits the final closing bracket } of the run() method. At this point, that specific thread dies.

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
