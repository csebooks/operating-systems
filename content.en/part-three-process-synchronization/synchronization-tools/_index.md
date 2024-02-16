---
title: 'Synchronization Tools'
weight: 1
---

# Synchronization Tools

A **cooperating process** is one that can affect or be affected by other processes executing in the system. Cooperating processes can either directly share a logical address space (that is, both code and data) or be allowed to share data only through sharedmemory or message passing. Concurrent access to shared data may result in data inconsistency, however. In this chapter, we discuss various mechanisms to ensure the orderly execution of cooperating processes that share a logical address space, so that data consistency is maintained.

**CHAPTER OBJECTIVES**

• Describe the critical-section problem and illustrate a race condition.

• Illustrate hardware solutions to the critical-section problem using memory barriers, compare-and-swap operations, and atomic variables.

• Demonstrate how mutex locks, semaphores, monitors, and condition vari- ables can be used to solve the critical-section problem.

• Evaluate tools that solve the critical-section problem in low-, moderate-, and high-contention scenarios.