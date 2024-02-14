---
title: 'PROCESS SYNCHRONIZATION'
weight: 3
---

  
*_Process Synchronization_*

A system typically consists of several (perhaps hundreds or even thou- sands) of threads running either concurrently or in parallel. Threads often share user data. Meanwhile, the operating system continuously updates various data structures to support multiple threads. A _race condition_ exists when access to shared data is not controlled, possibly resulting in corrupt data values.

_Process synchronization_ involves using tools that control access to shared data to avoid race conditions. These tools must be used carefully, as their incorrect use can result in poor system performance, including deadlock.  
