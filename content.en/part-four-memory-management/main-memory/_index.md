---
title: 'Main Memory'
weight: 1
---

# Main Memory

In Chapter 5, we showed how the CPU can be shared by a set of processes. As a result of CPU scheduling, we can improve both the utilization of the CPU and the speed of the computer’s response to its users. To realize this increase in performance, however, we must keepmany processes in memory—that is, we must share memory.

In this chapter, we discuss various ways to manage memory. The memory- management algorithms vary from a primitive bare-machine approach to a strategy that uses paging. Each approach has its own advantages and disad- vantages. Selection of a memory-management method for a specific system depends on many factors, especially on the hardware design of the system. As we shall see, most algorithms require hardware support, leading many systems to have closely integrated hardware and operating-system memory management.

**CHAPTER OBJECTIVES**

• Explain the difference between a logical and a physical address and the role of the memory management unit (MMU) in translating addresses.

• Apply first-, best-, and worst-fit strategies for allocating memory contigu- ously.

• Explain the distinction between internal and external fragmentation.

• Translate logical to physical addresses in a paging system that includes a translation look-aside buffer (TLB).

• Describe hierarchical paging, hashed paging, and inverted page tables.

• Describe address translation for IA-32, x86-64, and ARMv8 architectures.
