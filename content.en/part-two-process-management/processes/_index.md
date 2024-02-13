---
title: 'PROCESS'
weight: 1
---

# Processes

Early computers allowed only one program to be executed at a time. This pro- gram had complete control of the system and had access to all the system’s resources. In contrast, contemporary computer systems allow multiple pro- grams to be loaded into memory and executed concurrently. This evolution required firmer control and more compartmentalization of the various pro- grams; and these needs resulted in the notion of a **process**, which is a program in execution. A process is the unit of work in a modern computing system.

The more complex the operating system is, the more it is expected to do on behalf of its users. Although itsmain concern is the execution of user programs, it also needs to take care of various system tasks that are best done in user space, rather than within the kernel. A system therefore consists of a collection of processes, some executing user code, others executing operating system code. Potentially, all these processes can execute concurrently, with the CPU (or CPUs) multiplexed among them. In this chapter, you will read about what processes are, how they are represented in an operating system, and how they work.

**CHAPTER OBJECTIVES**

• Identify the separate components of a process and illustrate how they are represented and scheduled in an operating system.

• Describe how processes are created and terminated in an operating sys- tem, including developing programs using the appropriate system calls that perform these operations.

• Describe and contrast interprocess communication using shared memory and message passing.

• Design programs that use pipes and POSIX shared memory to perform interprocess communication.

• Describe client–server communication using sockets and remote proce- dure calls.

• Design kernel modules that interact with the Linux operating system.
