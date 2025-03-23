# LAPORAN SISTEM OPERASI  
## TUGAS PRACTICE EXERCISE  

**Nama**: Dino Ariel Ihsan Saputra  
**NRP**: 3124500031  
**Dosen Pengajar**: Dr Ferry Astika Saputra ST, M.Sc  

**PROGRAM STUDI D3 TEKNIK INFORMATIKA**  
**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)**  
**TAHUN 2025**  

---

### 1.1 What are the three main purposes of an operating system?

1. **Resource Management:** Manage and allocate hardware resources such as CPU, memory, and I/O devices.
2. **Abstraction and Simplification:** It provides a simplified interface for users and applications to interact with the hardware, hiding the complexities of the underlying system.
3. **Security and Protection:** The operating system ensures that different processes and users do not interfere with each other, providing a secure environment.
4. **User Interface:** Providing an interface that allows users to interact with the system.
5. **Program Execution:** Enabling the execution of applications and services by providing a stable and secure environment.

---

### 1.2 When is it appropriate for the operating system to forsake efficiency and "waste" resources? Why is such a system not really wasteful?

It is appropriate to "waste" resources when prioritizing user experience, system stability, or security. For example:

- **When security and stability are more important:** For example, allocating more memory for buffers or caches to enhance performance.
- **When user experience is more important:** For instance, using more resources for a more responsive user interface.
- **Such a system is not truly wasteful** because the "excessive" resource allocation can improve overall reliability, security, or user experience.

Such systems are not truly wasteful because the "wasted" resources serve critical purposes like reliability, performance, and security, which outweigh the cost of inefficiency.

---

### 1.3 What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?

- The main difficulty is ensuring **predictable and deterministic response times**. Real-time systems require tasks to be completed within strict deadlines, and the operating system must prioritize tasks accordingly. **Ensuring deterministic response times**: Real-time operating systems must guarantee that critical tasks are completed within strict time constraints.

This involves:

- Efficient scheduling algorithms.
- Minimizing latency and jitter.
- Handling interrupts and I/O operations without causing delays.

---

### 1.4 Should the operating system include applications such as web browsers and mail programs? Argue both sides.

1. **Should**: Including applications like web browsers and email programs can make the operating system more complete and ready to use.
2. **Should Not**: The operating system should focus on resource management and providing a platform for applications, rather than being the applications themselves.

---

### 1.5 How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security)?

1. **Kernel Mode**: Has full access to hardware and can execute privileged instructions.
2. **User Mode**: Restricts access to hardware and can only execute non-privileged instructions.
3. **Protection**: Prevents user applications from accessing or modifying critical system components.

---

### 1.6 Which of the following instructions should be privileged?

Privileged instructions are those that can only be executed in kernel mode to protect system integrity. The privileged instructions are:

- a. Set value of timer.
- c. Clear memory.
- e. Turn off interrupts.
- f. Modify entries in device-status table.
- g. Switch from user to kernel mode.
- h. Access I/O device.

Non-privileged instructions:

- b. Read the clock.
- d. Issue a trap instruction.

---

### 1.7 Describe two difficulties that could arise from placing the OS in a memory partition that cannot be modified.

1. **Limited Flexibility**: The operating system cannot easily modify its own memory partitions for optimization or fixes.
2. **Debugging Difficulties**: Immutable memory makes it hard to diagnose and fix bugs.

---

### 1.8 What are two possible uses of multiple modes of operation in CPUs?

1. **Enhanced Security**: Additional modes can provide finer-grained access control, isolating critical processes from less trusted ones.
2. **Specialized Operations**: Modes can be designed for specific tasks, such as virtualization or real-time processing, improving efficiency.
3. **Virtualization**: Additional modes can be used to run virtual machines with better isolation.
4. **Security**: Additional modes can enhance security by restricting access to certain resources.

---

### 1.9 How could timers be used to compute the current time?

Timers can be used to track elapsed time by counting clock ticks. For example:

- **Timer Interrupt**: A timer can be set to generate interrupts at regular intervals.
- **Time Calculation**: The operating system can calculate the current time by counting the number of interrupts since a specific time.

---

### 1.10 Give two reasons why caches are useful. What problems do they solve? What problems do they cause?

**Reasons caches are useful:**

1. **Speed:** Caches provide faster access to frequently used data, reducing latency.
2. **Efficiency:** They reduce the load on slower storage devices (e.g., disks) by serving data from faster memory.

**Problems they solve:**

- Slow access times for data stored in main memory or secondary storage.
- High latency in fetching data from remote or slow devices.

**Problems they cause:**

- **Cache Coherence:** Ensuring consistency between cache and main memory.
- **Cache Pollution:** Storing unnecessary data, reducing effective cache size.

**Why not make caches as large as the device they cache?**

- **Cost:** Larger caches are more expensive.
- **Diminishing Returns:** Beyond a certain size, the performance gains do not justify the cost.
