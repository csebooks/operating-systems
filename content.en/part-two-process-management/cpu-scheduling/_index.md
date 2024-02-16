---
title: 'CPU Scheduling'
weight: 3
---

# CPU Scheduling

CPU scheduling is the basis ofmultiprogrammedoperating systems. By switch- ing the CPU among processes, the operating system can make the computer more productive. In this chapter, we introduce basic CPU-scheduling concepts and present several CPU-scheduling algorithms, including real-time systems. We also consider the problem of selecting an algorithm for a particular system.

InChapter 4,we introduced threads to the processmodel.Onmodern oper- ating systems it is kernel-level threads—not processes—that are in fact being scheduled by the operating system. However, the terms "process scheduling" and "thread scheduling" are often used interchangeably. In this chapter, we use **_process scheduling_** when discussing general scheduling concepts and **_thread scheduling_** to refer to thread-specific ideas.

Similarly, in Chapter 1 we describe how a **_core_** is the basic computational unit of a CPU, and that a process executes on a CPU’s core. However, in many instances in this chapter, when we use the general terminology of scheduling a process to "run on a CPU", we are implying that the process is running on a CPU’s core.

**CHAPTER OBJECTIVES**

• Describe various CPU scheduling algorithms.

• Assess CPU scheduling algorithms based on scheduling criteria.

• Explain the issues related to multiprocessor and multicore scheduling.

• Describe various real-time scheduling algorithms.

• Describe the scheduling algorithms used in the Windows, Linux, and Solaris operating systems.

• Apply modeling and simulations to evaluate CPU scheduling algorithms.

• Design a program that implements several different CPU scheduling algo- rithms.