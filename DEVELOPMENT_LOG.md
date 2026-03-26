# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 21, 2026, 6:00 PM]
**What I did**: Set up development environment and installed required tools

**Details**: 
- Installed VS Code on my computer
- Installed Java Extension Pack for Java support
- Installed GitLens for Git management
- Installed Markdown All in One for documentation files
- Verified that Java is working correctly

**Challenges**: I was not sure which extensions were required and how to install them properly

**Solution**: I was following the instructions in the assignment and watch some videos in YouTub, and installed all required extensions successfully

**Time spent**: 2 hours

---

### Entry 2 - [March 22, 2026, 11:30 PM]
**What I did**: Created GitHub account and forked the repository

**Details**: 
- Created a GitHub account using my university email [445052009@std.psau.edu.sa]
- Chose a professional username [retag-alshahrani-445]
- Forked the starter repository
- Rename the repository to [OS-Assignment1-Retag-Alshahrani]
- Verified that the repository is public

**Challenges**: I was not familiar with the GitHub interface and had difficulty understanding how to fork and rename the repository

**Solution**: Followed the assignment instructions step by step and ask Chatgpt to learn more, then I did it.

**Time spent**: 1.5 hours  

---

### Entry 3 - [March 23, 2026, 2:00 AM]
**What I did**: Updated my student ID on GitHub and cloned the repository 

**Details**: 
- Navigated to SchedulerSimulation.java file in my repository on GitHub
- Changed student ID on line 150 to my actual ID (445052009)
- Added commit message
- Cloned the repository to my local machine using VS Code
- Ran the program successfully to verify the changes

**Challenges**: 
- I was not sure where to find the correct line for the student ID in the code
- Faced difficulty linking GitHub account with VS Code

**Solution**: Searched within the file and found the student ID in line 150, for the second challenge; I used the sign-in option in VS Code and followed a tutorial to complete the connection

**Time spent**: 2 hours

---

### Entry 4 - [March 24, 2026, 2:30 AM]
**What I did**: Implemented Feature 1: Process Priority

**Details**: 
- Added a new field priority to the Process class with values from 1 to 5
- Modified the constructor to include the priority parameter
- Generated random priority values for each process when creating them
- Updated the addProcessToQueue method to display the priority when a process enters the ready queue
- Added clear comments in the code to explain the new changes
- Created a commit with message: "Added process priority"
- Pushed the changes to my GitHub repository

**Challenges**: I was not sure how to properly add a new attribute to the Process class and pass it through the constructor

**Solution**: I reviewed the class structure, added the new variable, and updated the constructor and print statements step by step

**Time spent**: 2 hours

---

### Entry 5 - [March 25, 2026, 12:20 AM]
**What I did**: Implemented Feature 2: Context Switch Counter

**Details**: 
- Added a static variable private static int contextSwitchCount = 0; in SchedulerSimulation
- Introduced a boolean flag isFirstProcess = true; before the scheduling loop
- Incremented the counter only when a new process starts and it is not the first process
- Printed the total at the end: " Total context switches: 20"
- Created a commit with message: "Feature 2: Implemented context switch counter"
- Pushed the changes to my GitHub repository

**Challenges**: 
- Initially the counter was displayed many times because I printed it inside the ready‑queue message
- I also counted the first process as a switch, which would be incorrect

**Solution**: I moved the increment logic to the scheduling loop just before currentThread.start(), I used isFirstProcess to skip counting the first process, also ensured the final count is printed only once after the simulation ends

**Time spent**: 4.5 hours

---

### Entry 6 - [March 26, 2026, 3:20 PM]
**What I did**: Added feature 3 "Track Waiting Time"

**Details**: 
- Added new fields in the `Process` class to track timing: `creationTime`, `lastEnqueueTime`, and `totalWaitingTime`
- Initialized timing variables using `System.currentTimeMillis()` 
- calculated the waiting time as:
  `waiting time = currentTime - lastEnqueueTime`, then added it to `totalWaitingTime`
- Created a list allProcesses to store all process objects for later summary
- Implemented `printSummaryTable()` to display a formatted table with Process Name, Burst Time, and Waiting Time
- Created a commit with message: "Feature 3: Track Waiting Time"
- Pushed the changes to my GitHub repository
  
**Challenges**: At begin, I calculated the waiting time after thread.join(), which resulted in incorrect values because it included execution time
I also mistakenly calculated waiting time multiple times for the same process cycle, also the final table presentatio presented some difficulty in formatting it neatly.

**Solution**: I removed duplicate calculations to avoid double counting
Carefully tested the output to verify that waiting times increase only when the process is in the ready queue.

**Time spent**: 6 hours

---

## Summary

**Total time spent on assignment**: [18 hours]

**Most challenging part**: feature 3: waiting time was the most challenging. It required a deep understanding of how a round-robin loop works and determining when a process is "waiting and when it is executing. Understanding the difference between the time a time stamp is recorded and the time a wait time is calculated took several attempts.

**Most interesting learning**: For me, the most interesting part was concept of CPU Scheduling much clearer than just reading about it in a textbook.

**What I would do differently next time**: I would plan the features more carefully before coding and test each feature step by step to avoid logical mistakes
