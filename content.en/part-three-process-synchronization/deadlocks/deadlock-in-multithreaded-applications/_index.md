---
title: 'Deadlock in Multithreaded Applications'
weight: 2
---

# Deadlock in Multithreaded Applications

Prior to examining how deadlock issues can be identified and man- aged, we first illustrate how deadlock can occur in a multithreaded Pthread program using POSIX mutex locks. The pthread mutex init() function initializes an unlocked mutex. Mutex locks are acquired and released using pthread mutex lock() and pthread mutex unlock(), respectively. If a thread attempts to acquire a locked mutex, the call to pthread mutex lock() blocks the thread until the owner of the mutex lock invokes pthread mutex unlock().

Two mutex locks are created and initialized in the following code example:
```
pthread mutex t first mutex; pthread mutex t second mutex;

pthread mutex init(&first mutex,NULL); pthread mutex init(&second mutex,NULL);
```
Next, two threads—thread one and thread two—are created, and both these threads have access to both mutex locks. thread one and thread two run in the functions do work one() and do work two(), respectively, as shown in Figure 8.1.

In this example, thread one attempts to acquire the mutex locks in the order (1) first mutex, (2) second mutex. At the same time, thread two attempts to acquire the mutex locks in the order (1) second mutex, (2) first mutex. Deadlock is possible if thread one acquires first mutex while thread two acquires second mutex.  


```
/* thread one runs in this function */ void *do work one(void *param) {

pthread mutex lock(&first mutex); pthread mutex lock(&second mutex);*/ ** * Do some work */

pthread mutex unlock(&second mutex); pthread mutex unlock(&first mutex);

pthread exit(0); }

/* thread two runs in this function */ void *do work two(void *param) {

pthread mutex lock(&second mutex); pthread mutex lock(&first mutex);*/ ** * Do some work */

pthread mutex unlock(&first mutex); pthread mutex unlock(&second mutex);

pthread exit(0); }
```
**Figure 8.1** Deadlock example.

Note that, even though deadlock is possible, it will not occur if thread one can acquire and release the mutex locks for first mutex and second mutex before thread two attempts to acquire the locks. And, of course, the order in which the threads run depends on how they are scheduled by the CPU scheduler. This example illustrates a problem with handling deadlocks: it is difficult to identify and test for deadlocks that may occur only under certain scheduling circumstances.

## Livelock

**Livelock** is another form of liveness failure. It is similar to deadlock; both prevent two or more threads from proceeding, but the threads are unable to proceed for different reasons. Whereas deadlock occurs when every thread in a set is blocked waiting for an event that can be caused only by another thread in the set, livelock occurswhen a thread continuously attempts an action that fails. Livelock is similar to what sometimes happens when two people attempt to pass in a hallway: One moves to his right, the other to her left, still obstructing each other’s progress. Then he moves to his left, and she moves to her right, and so forth. They aren’t blocked, but they aren’t making any progress.

Livelock can be illustrated with the Pthreads pthread mutex trylock() function, which attempts to acquire a mutex lock without blocking. The code example in Figure 8.2 rewrites the example from Figure 8.1 so that it now uses pthread mutex trylock(). This situation can lead to livelock if thread one acquires first mutex, followed by thread two acquiring second mutex. Each thread then invokes pthread mutex trylock(), which fails, releases their respective locks, and repeats the same actions indefinitely.

Livelock typically occurs when threads retry failing operations at the same time. It thus can generally be avoided by having each thread retry the failing operation at random times. This is precisely the approach taken by Ethernet networks when a network collision occurs. Rather than trying to retransmit a packet immediately after a collision occurs, a host involved in a collision will **_backoff_** a random period of time before attempting to transmit again.

Livelock is less common than deadlock but nonetheless is a challenging issue indesigning concurrent applications, and like deadlock, itmay only occur under specific scheduling circumstances.