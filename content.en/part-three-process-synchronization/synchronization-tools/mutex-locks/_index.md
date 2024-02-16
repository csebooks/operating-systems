---
title: 'Mutex Locks'
weight: 5
---

# Mutex Locks

The hardware-based solutions to the critical-section problem presented in Sec- tion 6.4 are complicated as well as generally inaccessible to application pro- grammers. Instead, operating-system designers build higher-level software tools to solve the critical-section problem. The simplest of these tools is the **mutex lock**. (In fact, the term**_mutex_** is short for **_mut_**ual **_ex_**clusion.) We use the mutex lock to protect critical sections and thus prevent race conditions. That is, a process must acquire the lock before entering a critical section; it releases the lock when it exits the critical section. The acquire()function acquires the lock, and the release() function releases the lock, as illustrated in Figure 6.10.

A mutex lock has a boolean variable available whose value indicates if the lock is available or not. If the lock is available, a call to acquire() succeeds, and the lock is then considered unavailable. Aprocess that attempts to acquire an unavailable lock is blocked until the lock is released.  
```
while (true) {

_acquire lock_

critical section

_release lock_

remainder section

}
```
**Figure 6.10** Solution to the critical-section problem using mutex locks.

The definition of acquire() is as follows:
```
acquire() { while (!available)

;*/ *busy wait */ available = false;

}

The definition of release() is as follows:

release() { available = true;

}
```
Calls to either acquire() or release() must be performed atomically. Thus, mutex locks can be implemented using the CAS operation described in Section 6.4, and we leave the description of this technique as an exercise.

**_LOCK CONTENTION_**

Locks are either contended or uncontended. A lock is considered **contended** if a thread blocks while trying to acquire the lock. If a lock is available when a thread attempts to acquire it, the lock is considered **uncontended**. Con- tended locks can experience either **_high contention_** (a relatively large number of threads attempting to acquire the lock) or **_low contention_** (a relatively small number of threads attempting to acquire the lock.) Unsurprisingly, highly contended locks tend to decrease overall performance of concurrent applications.  

**_WHAT IS MEANT BY_** _“**SHORT DURATION**”**?**_

Spinlocks are often identified as the locking mechanism of choice on multi- processor systems when the lock is to be held for a short duration. But what exactly constitutes a _short duration_? Given that waiting on a lock requires two context switches—a context switch to move the thread to the waiting state and a second context switch to restore the waiting thread once the lock becomes available—the general rule is to use a spinlock if the lock will be held for a duration of less than two context switches.

The main disadvantage of the implementation given here is that it requires **busy waiting**. While a process is in its critical section, any other process that tries to enter its critical sectionmust loop continuously in the call to acquire(). This continual looping is clearly a problem in a realmultiprogramming system, where a single CPU core is shared among many processes. Busy waiting also wastes CPU cycles that some other process might be able to use productively. (In Section 6.6, we examine a strategy that avoids busy waiting by temporarily putting the waiting process to sleep and then awakening it once the lock becomes available.)

The type of mutex lock we have been describing is also called a **spin- lock** because the process “spins” while waiting for the lock to become avail- able. (We see the same issue with the code examples illustrating the com- pare and swap() instruction.) Spinlocks do have an advantage, however, in that no context switch is required when a process must wait on a lock, and a context switch may take considerable time. In certain circumstances on multi- core systems, spinlocks are in fact the preferable choice for locking. If a lock is to be held for a short duration, one thread can “spin” on one processing core while another thread performs its critical section on another core. On modern multicore computing systems, spinlocks are widely used in many operating systems.

In Chapter 7 we examine how mutex locks can be used to solve classical synchronization problems. We also discuss howmutex locks and spinlocks are used in several operating systems, as well as in Pthreads.