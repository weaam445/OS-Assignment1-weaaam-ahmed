# CS3701 Operating Systems - Assignment 1: Multithreading
## Round-Robin CPU Scheduler Simulation

### 📋 Assignment Overview

Welcome to Assignment 1! In this assignment, you will work with **Java threads** to simulate a **Round-Robin CPU scheduling algorithm**. This is your opportunity to:

- 🎯 Learn how threads work in practice
- 🔄 Understand CPU scheduling concepts
- 💻 Write, test, and document real concurrent code
- 📊 Analyze threading behavior

**Important**: This assignment is worth **5 marks** (5% of your final grade).

---

## 🚀 Getting Started

### Step 1: Fork This Repository

1. **Create a GitHub account** using your **university email** (@std.psau.edu.sa)
   - Go to https://github.com
   - Click "Sign up"
   - Use your university email: `yourname@std.psau.edu.sa`
   - Verify your email address

2. **Fork this repository**:
   - Click the **"Fork"** button at the top right of this page
   - This creates your own copy of the repository
   - Your repository will be at: `https://github.com/YOUR_USERNAME/OS-Assignment1-YOUR_NAME`

3. **Rename your forked repository**:
   - Go to your forked repository Settings
   - Change the repository name to: `OS-Assignment1-YourFirstName-YourLastName`
   - Example: `OS-Assignment1-Mohammed-Ahmed`

4. **Make sure your repository is PUBLIC**:
   - Go to Settings → scroll down to "Danger Zone"
   - Verify visibility is set to "Public"
   - If private, click "Change visibility" → "Make public"

### Step 2: Clone Your Repository to Your Computer

```bash
git clone https://github.com/YOUR_USERNAME/OS-Assignment1-YourFirstName-YourLastName.git
cd OS-Assignment1-YourFirstName-YourLastName
```

### Step 3: Set Up Your Student ID

**⚠️ CRITICAL FIRST STEP ⚠️**

Open `SchedulerSimulation.java` and **immediately** change line 92:

```java
// BEFORE (DO NOT SUBMIT THIS):
int studentID = 123456789;

// AFTER (Use YOUR real ID):
int studentID = 441234567;  // Replace with YOUR actual student ID
```

**Save this change and commit it right away**:

```bash
git add SchedulerSimulation.java
git commit -m "Set my student ID: 441234567"
git push origin main
```

✅ This personalizes your assignment and prevents identical outputs!

---

## 📂 Repository Structure

Your repository should have these files:

```
OS-Assignment1-YourName/
├── README.md                    # This file - project overview
├── SchedulerSimulation.java     # Main code file (YOU WILL MODIFY THIS)
├── DEVELOPMENT_LOG.md           # Your development timeline (FILL THIS)
├── REFLECTION.md                # Your learning reflections (FILL THIS)
├── ANSWERS.md                   # Answers to assignment questions (FILL THIS)
└── .gitignore                   # Git ignore file (already configured)
```

---

## 💡 Understanding the Code

### What is Round-Robin Scheduling?

Round-Robin is a CPU scheduling algorithm where:
- Each process gets a **fixed time slice** (time quantum) to run
- If a process doesn't finish, it goes to the **back of the queue**
- The next process gets its turn
- This continues until all processes finish

**Think of it like**: A teacher calling on students one by one. Each student gets 2 minutes to speak. If they're not done, they go to the back of the line.

### Key Components

#### 1. **Process Class** (lines 10-88)
Represents a process that will run on the CPU:
- `name`: Process identifier (P1, P2, etc.)
- `burstTime`: Total time needed to complete
- `timeQuantum`: Maximum time allowed per turn
- `remainingTime`: How much time is left
- `run()`: What the process does when scheduled

#### 2. **SchedulerSimulation Class** (lines 90-167)
The scheduler that manages all processes:
- Creates multiple processes with random burst times
- Maintains a **queue** of ready processes
- Runs each process for one time quantum
- Re-queues processes that aren't finished
- Continues until all processes complete

### Threading Concepts You'll Learn

1. **Thread Creation**: `Thread thread = new Thread(process);`
2. **Starting Threads**: `thread.start();`
3. **Waiting for Completion**: `thread.join();`
4. **Thread Sleeping**: `Thread.sleep(milliseconds);`

---

## ✅ Your Tasks (5 Parts - 5 Marks Total)

### **Part 1: Personalize & Run (1.5 marks)**

1. **Set your student ID** in line 92 (see Step 3 above)
2. **Compile and run** the program:
   ```bash
   javac SchedulerSimulation.java
   java SchedulerSimulation
   ```
3. **Take a screenshot** of the output showing:
   - Your student ID in the header
   - The simulation running
   - All processes finishing
4. **Save screenshot** as `output_screenshot.png` in your repository
5. **Commit your changes**:
   ```bash
   git add SchedulerSimulation.java output_screenshot.png
   git commit -m "Part 1 complete: Set student ID and captured output"
   git push origin main
   ```

### **Part 2: Code Implementation (1.5 marks)**

**Modify the code** to add these features:

#### 2.1: Add Process Priority (0.5 marks)
- Add a `priority` field to the Process class (1-5, where 5 is highest)
- Generate random priorities when creating processes
- Display priority when a process enters the ready queue

#### 2.2: Count Context Switches (0.5 marks)
- Add a counter for context switches (when CPU switches between processes)
- Display the total number of context switches at the end
- A context switch occurs every time a new process starts running

#### 2.3: Track Waiting Time (0.5 marks)
- Calculate and display each process's waiting time
- Waiting time = Time since creation - Time actually running
- Display waiting times in a summary table at the end

**Commit after EACH feature**:
```bash
git add SchedulerSimulation.java
git commit -m "Added [feature name]: [brief description]"
git push origin main
```

### **Part 3: Documentation (1 mark)**

Complete these three files:

#### 3.1: DEVELOPMENT_LOG.md (0.4 marks)
Document your development process with **at least 5 entries**:
- What you worked on
- What challenges you faced
- How you solved problems
- Timestamps for each entry

#### 3.2: REFLECTION.md (0.3 marks)
Answer the 4 reflection questions about your learning experience:
- What you learned about multithreading
- Challenges you faced
- How you overcame difficulties
- Real-world applications

#### 3.3: ANSWERS.md (0.3 marks)
Provide detailed answers to all 4 assignment questions:
- Each answer should be 3-5 sentences minimum
- Use proper terminology
- Reference your code where relevant

### **Part 4: Version Control (0.5 marks)**

Your repository must show:
- ✅ **At least 3 meaningful commits** spread over time
- ✅ Clear commit messages describing what changed
- ✅ Commits made on **different dates/times** (not all at once!)
- ✅ Incremental progress (not everything in one commit)

**Good commit examples**:
- ✅ "Part 1: Set student ID to 441234567"
- ✅ "Added priority field to Process class"
- ✅ "Implemented context switch counter"
- ✅ "Completed ANSWERS.md with all 4 questions"

**Bad commit examples**:
- ❌ "done"
- ❌ "update"
- ❌ "final version"

### **Part 5: Video Demonstration (0.5 marks)**

Create a **2-3 minute video** showing:

1. **Your GitHub repository** (show your account with university email)
2. **Navigate through your code** files
3. **Compile and run** your program in terminal/command prompt
4. **Explain** one threading concept you learned (choose from):
   - How `Thread.start()` works
   - What `Thread.join()` does
   - Why we use `Thread.sleep()`
   - How the ready queue works

**Video Requirements**:
- Length: 2-3 minutes (not shorter, not longer)
- Show your face OR use clear voice narration
- Screen recording of your code and execution
- Upload to **YouTube (unlisted)** or **Google Drive** (link-accessible)
- Add video link to your README.md

**Recording your video**:
- Mac: Use QuickTime Player (File → New Screen Recording)
- Windows: Use Xbox Game Bar (Win + G)
- Linux: Use SimpleScreenRecorder or OBS Studio

---

## 📝 Questions to Answer (in ANSWERS.md)

### Question 1: Thread vs Process
Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

### Question 2: Ready Queue Behavior
In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

### Question 3: Thread States
A thread can be in different states: New, Runnable, Running, Waiting, Terminated. Walk through these states for one process (P1) from your simulation.

### Question 4: Real-World Applications
Give TWO real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

---

## 🎥 Video Demonstration Guide

### What to Include:

1. **Introduction (30 seconds)**:
   - "Hello, I'm [Your Name], student ID [Your ID]"
   - "This is my submission for CS3701 Assignment 1"
   - Show your GitHub repository homepage

2. **Code Walkthrough (1 minute)**:
   - Open your repository files
   - Briefly explain the main components
   - Show your modifications (priority, context switches, waiting time)

3. **Compilation & Execution (30 seconds)**:
   - Open terminal/command prompt
   - Compile: `javac SchedulerSimulation.java`
   - Run: `java SchedulerSimulation`
   - Show the output with your student ID

4. **Concept Explanation (30 seconds)**:
   - Pick ONE threading concept
   - Explain it clearly using your code as example
   - Show where it appears in your implementation

5. **Closing (10 seconds)**:
   - Show your commit history
   - "Thank you for watching!"

### Tips for a Good Video:
- ✅ Test your screen recording software first
- ✅ Close unnecessary tabs/windows
- ✅ Use a clear microphone
- ✅ Speak slowly and clearly
- ✅ Zoom in on code if needed
- ✅ Keep it under 3 minutes

---

## ⚠️ Important Warnings

### ❌ What NOT to Do:

1. **Don't use ChatGPT/AI to write your code without understanding it**
   - You will be asked to explain your code in the video
   - If you can't explain it, you'll receive 0 marks

2. **Don't copy from classmates**
   - Each student has a unique student ID → unique output
   - Plagiarism results in 0 marks + academic misconduct report

3. **Don't make all commits at the last minute**
   - We can see your commit timestamps
   - Single-commit or last-hour submissions lose marks

4. **Don't forget the university email**
   - GitHub account MUST use @std.psau.edu.sa
   - Other emails will result in -0.25 marks

### ✅ What TO Do:

1. **Start early** - Don't wait until the deadline
2. **Commit frequently** - After each small change
3. **Test your code** - Make sure it compiles and runs
4. **Ask questions** - Use Blackboard discussion or office hours
5. **Keep it simple** - Don't over-complicate your modifications

---

## 📅 Submission Instructions

### What to Submit on Blackboard:

Submit **ONE text file** named: `YourName_StudentID_Assignment1.txt`

**Content of the text file**:
```
Student Name: Mohammed Ahmed Abdullah
Student ID: 441234567
GitHub Username: mohammed-ahmed
Repository Link: https://github.com/mohammed-ahmed/OS-Assignment1-Mohammed-Ahmed
Video Link: https://youtu.be/aBcDeFgHiJk
Date Submitted: April 14, 2026
```

### Submission Checklist:

Before submitting, verify:
- ✅ Repository is PUBLIC
- ✅ Repository contains ALL required files
- ✅ Student ID is set correctly in code
- ✅ At least 3 commits with good messages
- ✅ All 3 documentation files completed
- ✅ Video is accessible (unlisted YouTube or public Google Drive)
- ✅ Code compiles without errors
- ✅ Screenshot shows your execution with your student ID

---

## 🏆 Grading Breakdown (5 Marks Total)

| Component | Marks | Criteria |
|-----------|-------|----------|
| **Part 1: Personalization & Execution** | 1.5 | Student ID set, program runs, screenshot provided |
| **Part 2: Code Implementation** | 1.5 | All 3 features implemented correctly |
| **Part 3: Documentation** | 1.0 | All files completed with good detail |
| **Part 4: Version Control** | 0.5 | Meaningful commits showing progression |
| **Part 5: Video Demonstration** | 0.5 | Clear video showing all requirements |
| **Total** | **5.0** | |

### Penalties:
- Late submission: **-1 mark per day**
- Missing video: **-0.5 marks**
- Single commit or all commits in last hour: **-0.5 marks**
- Private repository: **-0.5 marks**
- Not using university email: **-0.25 marks**
- AI-generated without understanding: **0 marks**
- Plagiarism: **0 marks + academic misconduct report**

---

## 🆘 Getting Help

### If you have issues:

1. **Check the FAQ** in Blackboard
2. **Use the discussion forum** - other students may have similar questions
3. **Attend office hours**
4. **Email your instructor** with specific questions

### Common Issues & Solutions:

**Problem**: "javac is not recognized"
→ **Solution**: Install JDK and set PATH variable

**Problem**: "My repository is not accessible"
→ **Solution**: Go to Settings → ensure it's set to Public

**Problem**: "I can't fork the repository"
→ **Solution**: Make sure you're logged into GitHub with your university email

**Problem**: "Git push is rejected"
→ **Solution**: Make sure you're pushing to YOUR forked repository, not the original

---

## 📚 Learning Resources

### Java Threading Basics:
- Oracle Java Tutorials: [Concurrency](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- Your textbook: Chapter 4 - Threads & Concurrency

### Git & GitHub:
- [GitHub Guides](https://guides.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Round-Robin Scheduling:
- Your textbook: Chapter 5 - CPU Scheduling
- Wikipedia: [Round-robin scheduling](https://en.wikipedia.org/wiki/Round-robin_scheduling)

---

## 🎯 Success Tips

1. **Read the entire README** before starting
2. **Set your student ID first** - this is critical!
3. **Make small changes** and commit often
4. **Test after every change** - don't wait until the end
5. **Start the video early** - you might need multiple takes
6. **Explain concepts in your own words** - this shows understanding
7. **Keep backups** - copy your repository regularly
8. **Submit early** - don't wait for the last minute

---

## 📝 Final Checklist Before Submission

- [ ] Student ID set in code (line 92)
- [ ] Code compiles without errors
- [ ] Code runs and produces expected output
- [ ] All 3 features implemented (priority, context switches, waiting time)
- [ ] DEVELOPMENT_LOG.md completed (5+ entries)
- [ ] REFLECTION.md completed (4 questions answered)
- [ ] ANSWERS.md completed (4 questions answered)
- [ ] At least 3 meaningful commits
- [ ] Commits spread over different times/dates
- [ ] Repository is PUBLIC
- [ ] GitHub account uses university email
- [ ] Video recorded (2-3 minutes)
- [ ] Video uploaded to YouTube/Google Drive
- [ ] Video link added to README or submission file
- [ ] Screenshot of output included
- [ ] Text file prepared with all submission info
- [ ] Text file submitted on Blackboard

---

## 🎓 Deadline

**Due Date**: April 15, 2026, 11:59 PM

**Late Policy**: -1 mark per day late

---

Good luck with your assignment! Remember, the goal is to **learn about multithreading**, not just to complete the assignment. Take your time to understand each concept.

If you learn something new, you've succeeded! 🎉
