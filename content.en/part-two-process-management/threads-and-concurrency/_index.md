---
title: 'Threads & Concurrency'
weight: 2
---

# Threads & Concurrency

The process model introduced in Chapter 3 assumed that a process was an executing programwith a single thread of control. Virtually all modern operat- ing systems, however, provide features enabling a process to contain multiple threads of control. Identifying opportunities for parallelism through the use of threads is becoming increasingly important for modernmulticore systems that provide multiple CPUs.

In this chapter, we introduce many concepts, as well as challenges, associ- ated with multithreaded computer systems, including a discussion of the APIs for the Pthreads, Windows, and Java thread libraries. Additionally, we explore several new features that abstract the concept of creating threads, allowing developers to focus on identifying opportunities for parallelism and letting language features and API frameworks manage the details of thread creation and management. We look at a number of issues related to multithreaded pro- gramming and its effect on the design of operating systems. Finally, we explore how the Windows and Linux operating systems support threads at the kernel level.

**CHAPTER OBJECTIVES**

• Identify the basic components of a thread, and contrast threads and processes.

• Describe the major benefits and significant challenges of designing multi- threaded processes.

• Illustrate different approaches to implicit threading, including thread pools, fork-join, and Grand Central Dispatch.

• Describe how the Windows and Linux operating systems represent threads.

• Design multithreaded applications using the Pthreads, Java, and Windows threading APIs.