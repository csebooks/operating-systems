---
title: 'Virtual Memory'
weight: 2
---

# Virtual Memory

In Chapter 9, we discussed various memory-management strategies used in computer systems. All these strategies have the same goal: to keep many processes in memory simultaneously to allow multiprogramming. However, they tend to require that an entire process be in memory before it can execute.

Virtual memory is a technique that allows the execution of processes that are not completely inmemory. Onemajor advantage of this scheme is that pro- grams can be larger than physical memory. Further, virtual memory abstracts main memory into an extremely large, uniform array of storage, separating logical memory as viewed by the programmer from physical memory. This technique frees programmers from the concerns of memory-storage limita- tions. Virtual memory also allows processes to share files and libraries, and to implement shared memory. In addition, it provides an efficient mechanism for process creation. Virtual memory is not easy to implement, however, and may substantially decrease performance if it is used carelessly. In this chap- ter, we provide a detailed overview of virtual memory, examine how it is implemented, and explore its complexity and benefits.

**CHAPTER OBJECTIVES**

• Define virtual memory and describe its benefits.

• Illustrate how pages are loaded into memory using demand paging.

• Apply the FIFO, optimal, and LRU page-replacement algorithms.

• Describe the working set of a process, and explain how it is related to program locality.

• Describe how Linux, Windows 10, and Solaris manage virtual memory.

• Design a virtual memory manager simulation in the C programming lan- guage.