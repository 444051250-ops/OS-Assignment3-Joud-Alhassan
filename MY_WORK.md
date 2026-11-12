# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Joud Alhassan |
| **Student ID** | 444051250 |
| **University Email** | 444051250@std.psau.edu.sa |
| **GitHub Username** | 444051250-ops |
| **Repository Link** | https://github.com/444051250-ops/OS-Assignment3-Joud-Alhassan |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 8,2026, 7:45PM]
**What I did**:
Forked the repo, set my student ID, ran the starter, and did Feature 1

**Details**:
- Forked the starter repository and renamed it and checked it is public
- Changed the student ID on line 304 to 444051250 and committed it
- Ran the original code and all 3 CPUs crashed in snapshot() and all counters were 0
- Added a ReentrantLock queueLock in ReadyQueue and protected add(), poll(), processOf() and snapshot() with lock/try/finally
- Ran the code 5 times with no crash

**Challenges**:
The program crashed and I did not understand why
when I edited the code I deleted some import lines by mistake and got many red errors

**Solution**:
Understood that 3 CPUs were using the same list at the same time without any lock so the list broke
I added the missing imports back

**Time spent**:
1 hour

---

### Entry 2 - [November 10,2026, 9:20 AM]
**What I did**:
Feature 2 locks on the shared statistics

**Details**:
- Added three ReentrantLocks in SharedStats: switchLock and completedLock and serviceLock 
- Protected the 3 update methods and the 3 getters with lock/try/finally
- Busy-waiting polls was still not 0 (28), this is for Feature 3

**Challenges**:
Deciding between one lock for all counters or one lock for each counter

**Solution**:
Chose one lock per counter because the three counters are independent so a CPU updating one counter does not need to block another CPU updating a different one

**Time spent**:
40 minutes

---

### Entry 3 - [November 11, 2026, 10:15 PM]
**What I did**:
Feature 3 replaced busy waiting with a counting semaphore

**Details**:
- Added a Semaphore readyCount in ReadyQueue with initial value 0 because the queue is empty at the start
- Called release() in add() so the semaphore counts the processes waiting in the queue
- In CpuWorker the CPU now calls acquire() and sleeps until a process is available and I removed the Thread.sleep(20) polling code
- The CPU that finishes the last process calls release(totalCPUs) to wake up the other CPUs so they can stop
- Ran the code 5 times and all 4 lines are correct and busy-waiting polls is 0 and the program stops by itself

**Challenges**:
Understanding how the CPUs stop at the end because after the last process they stay blocked on acquire() forever

**Solution**:
The CPU that finishes the last process wakes up all the others and each CPU checks if all processes are completed after it wakes up then it stops

**Time spent**:
1 hour

---

### Entry 4 - [November 12, 2026, 5:30 PM]
**What I did**:
Wrote the 4 technical answers in Part C

**Details**:
- Pasted the verification block of my original starter (crash, all counters 0) and of my final version (all lines correct)
- Used my run after Feature 1 (22 instead of 24, 70232 instead of 78232) to explain a lost update step by step
- Filled the critical sections table and explained my lock granularity choice
- Explained the semaphore initial value (0, then 12 after the initial add calls) and the release(totalCPUs) shutdown
- Answered the producer-consumer and deadlock question

**Challenges**:
My original starter crashed before the counters were updated so I could not show a lost update from it directly

**Solution**:
Used the output of my run after Feature 1 where the queue was fixed but the counters were still not protected

**Time spent**:
1 hour 30 minutes

---

### Entry 5 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

My original starter run crashed right away and all 3 CPUs threw a NullPointerException inside ReadyQueue.snapshot() so every counter stayed at 0 (expected 24 context switches, 12 completed processes and 78232 ms) This happened because the 3 CPUs used the same LinkedList at the same time without a lock so one CPU was looping over the list while another CPU was removing from it
After I fixed only the queue (Feature 1) I could see the lost updates clearly the context switches were 22 instead of 24 and total service time was 70232 instead of 78232 so exactly 2 quanta of 4000 ms were lost
On a real machine the same bug can happen without RaceWindow because the OS can preempt a thread between the read and the write at any moment
It is hard to detect because this window is only a few nanoseconds so the bug appears rarely and randomly and the program can look correct in many runs

Verification block of the **original starter**:
```
Exception in thread "CPU-2" Exception in thread "CPU-1" Exception in thread "CPU-3" java.lang.NullPointerException: Cannot read field "next" because "this.next" is null
        at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 24       observed 0        ✘ MISMATCH
  Completed processes                    expected 12       observed 0        ✘ MISMATCH
  Total service time (ms)                expected 78232    observed 0        ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 24       observed 24       ✔
  Completed processes                    expected 12       observed 12       ✔
  Total service time (ms)                expected 78232    observed 78232    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
```

**Explanation of the timeline:**
In my run after Feature 1 P3 on CPU-3 and P1 on CPU-1 finished a 4000 ms quantum at the same time, and totalServiceTime was 3185 (only P2 was done):
1. CPU-3 reads totalServiceTime = 3185
2. CPU-3 calls RaceWindow.pause() so it stops before writing
3. CPU-1 reads totalServiceTime = 3185 (the same old value)
4. CPU-3 writes 3185 + 4000 = 7185
5. CPU-1 writes 3185 + 4000 = 7185
The correct value is 11185 so 4000 ms were lost and This is why my run showed 70232 instead of 78232.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected the ready queue (list and map) with one lock queueLock in add(), poll(), processOf() and snapshot(). For the statistics I used one lock per variable: switchLock for contextSwitchCount, completedLock for completedProcessCount and serviceLock for totalServiceTime, in the 3 update methods and the 3 getters. I chose one lock per variable because the three counters are independent, so a CPU adding service time should not block another CPU counting a context switch; the trade-off is more code, and if I ever needed to read the three values together as one consistent snapshot I would have to take the three locks in the same order every time to avoid deadlock. The queue has a different lock because it is a different shared resource: if they shared one lock, a CPU updating a counter would block another CPU taking a process from the queue for no reason. Mutual exclusion is guaranteed because only the thread that owns the lock can enter the critical section, and the others wait in lock(); progress is guaranteed because the lock is always released in finally, so a free lock is never kept. A default ReentrantLock is not fair, so it does not promise first-come first-served order, and a thread could be overtaken many times; in my program the critical sections are very short, so the waiting stays small, but new ReentrantLock(true) would give fair order with a small performance cost

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` (list, map) | `queueLock` | Two CPUs can re-enqueue at the same time and corrupt the list |
| `ReadyQueue.poll()` (list) | `queueLock` | Reading the head and removing it must be one step, or two CPUs take the same process |
| `ReadyQueue.processOf()` (map) | `queueLock` | Reading the map while another CPU changes it is not safe |
| `ReadyQueue.snapshot()` (list, map) | `queueLock` | Looping over the list while it changes crashed my starter (NullPointerException) |
| `contextSwitchCount` (increment + getter) | `switchLock` | Read-modify-write lost updates (22 instead of 24) |
| `completedProcessCount` (increment + getter) | `completedLock` | A lost update means the CPUs never see 12 completed |
| `totalServiceTime` (add + getter) | `serviceLock` | Read-modify-write lost updates (70232 instead of 78232) |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the starter when a CPU found the ready queue empty it slept 20 ms and checked the queue again in a loop and it only stopped when completedProcessCount reached the total. My original starter run crashed before this code was reached, so it showed 0 polls, but after Feature 1 the same polling code gave 44, 55 and 28 busy-waiting polls in my runs, which is CPU time wasted on checking an empty queue. In my final version, the value of the semaphore readyCount is the number of processes waiting in the ready queue. Its initial value is 0 because the queue is empty when it is created (with 1, a CPU could take a process from an empty queue), and right after the 12 initial add() calls its value is 12. A CPU now calls acquire() and is blocked (not running) until add() calls release(), so the busy-waiting polls are 0. At the end no process will ever be added again, so the CPUs blocked in acquire() would wait forever; the CPU that finishes the last process calls release(totalCPUs) (3 in my run) to wake them up, they see that all processes are completed and stop. Without this, the program would hang and the watchdog would stop it.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
This is the producer-consumer (bounded-buffer) problem
The producers are the main thread, which adds the 12 initial processes and also the CPUs when they put an unfinished process back in the queue
The consumers are the CPUs that take processes from the queue so in my program each CPU is both a consumer and a producer

**Semaphores for a bounded queue (name and initial value)**:
- mutex = 1: mutual exclusion on the queue (my queueLock plays this role)
- empty = K: number of free slots in the queue
- full = 0: number of processes in the queue (my readyCount plays this role)

**Deadlock scenario and prevention**:
Suppose the queue is full and a CPU wants to re-enqueue a process if it calls wait(mutex) first and then wait(empty), it blocks on empty while holding the mutex. The only thread that can free a slot is a consumer, but the consumer needs the mutex to remove a process, so it blocks too, and both wait forever: deadlock. This is a hold-and-wait situation (holding the mutex while waiting for another resource), so I would break the hold-and-wait condition by always calling wait(empty) or wait(full) before wait(mutex). This is also why in my code I never call acquire() while holding queueLock. If two locks were used together, I would also prevent circular wait by always taking them in the same order.

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
