---
title: 'POSIX Synchronization'
weight: 3
---

# POSIX Synchronization

The synchronization methods discussed in the preceding section pertain to synchronization within the kernel and are therefore available only to kernel developers. In contrast, the POSIX API is available for programmers at the user level and is not part of any particular operating-system kernel. (Of course, it must ultimately be implemented using tools provided by the host operating system.)

In this section, we cover mutex locks, semaphores, and condition variables that are available in the Pthreads and POSIX APIs. These APIs are widely used for thread creation and synchronization by developers on UNIX, Linux, and macOS systems.

## POSIX Mutex Locks

Mutex locks represent the fundamental synchronization technique used with Pthreads. A mutex lock is used to protect critical sections of code—that is, a thread acquires the lock before entering a critical section and releases it upon exiting the critical section. Pthreads uses the pthread mutex t data type for mutex locks. A mutex is created with the pthread mutex init() function. The first parameter is a pointer to the mutex. By passing NULL as a second parameter, we initialize the mutex to its default attributes. This is illustrated below:  


```
#include <pthread.h_>_

pthread mutex t mutex;

/* create and initialize the mutex lock */ **pthread mutex init**(&mutex,NULL);
```
The mutex is acquired and released with the pthread mutex lock() and pthread mutex unlock() functions. If the mutex lock is unavailable when pthread mutex lock() is invoked, the calling thread is blocked until the owner invokes pthread mutex unlock(). The following code illustrates pro- tecting a critical section with mutex locks:
```
/* acquire the mutex lock */ **pthread mutex lock**(&mutex);

/* critical section */

/* release the mutex lock */ **pthread mutex unlock**(&mutex);
```
All mutex functions return a value of 0with correct operation; if an error occurs, these functions return a nonzero error code.

## POSIX Semaphores

Many systems that implement Pthreads also provide semaphores, although semaphores are not part of the POSIX standard and instead belong to the POSIX SEM extension. POSIX specifies two types of semaphores—**named** and **unnamed**. Fundamentally, the two are quite similar, but they differ in terms of how they are created and shared between processes. Because both techniques are common, we discuss both here. Beginning with Version 2.6 of the kernel, Linux systems provide support for both named and unnamed semaphores.

### POSIX Named Semaphores

The function sem open() is used to create and open a POSIX named sempahore:
```
#include <semaphore.h_>_ sem t *sem;

/* Create the semaphore and initialize it to 1 */ sem = **sem open**("SEM", O CREAT, 0666, 1);
```
In this instance, we are naming the semaphore SEM. The O CREAT flag indicates that the semaphore will be created if it does not already exist. Additionally, the semaphore has read and write access for other processes (via the parameter 0666) and is initialized to 1.

The advantage of named semaphores is that multiple unrelated processes can easily use a common semaphore as a synchronization mechanism by simply referring to the semaphore’s name. In the example above, once the semaphore SEM has been created, subsequent calls to sem open() (with the same parameters) by other processes return a descriptor to the existing semaphore.

In Section 6.6, we described the classic wait() and signal() semaphore operations. POSIX declares these operations sem wait() and sem post(), respectively. The following code sample illustrates protecting a critical section using the named semaphore created above:
```
/* acquire the semaphore */ **sem wait**(sem);

/* critical section */

/* release the semaphore */ **sem post**(sem);
```
Both Linux and macOS systems provide POSIX named semaphores.

### POSIX Unnamed Semaphores

An unnamed semaphore is created and initialized using the sem init() func- tion, which is passed three parameters:

**1.** Apointer to the semaphore

**2.** Aflag indicating the level of sharing

**3.** The semaphore’s initial value

and is illusrated in the following programming example:
```
#include <semaphore.h_>_ sem t sem;

/* Create the semaphore and initialize it to 1 */ **sem init**(&sem, 0, 1);
```
In this example, by passing the flag 0, we are indicating that this semaphore can be shared only by threads belonging to the process that created the semaphore. (If we supplied a nonzero value, we could allow the semaphore to be shared between separate processes by placing it in a region of shared memory.) In addition, we initialize the semaphore to the value 1.

POSIX unnamed semaphores use the same sem wait() and sem post() operations as named semaphores. The following code sample illustrates pro- tecting a critical section using the unnamed semaphore created above:  


```
/* acquire the semaphore */ sem wait(&sem);

/* critical section */

/* release the semaphore */ sem post(&sem);
```
Just like mutex locks, all semaphore functions return 0 when successful and nonzero when an error condition occurs.

## POSIX Condition Variables

Condition variables in Pthreads behave similarly to those described in Section 6.7. However, in that section, condition variables are used within the context of a monitor, which provides a locking mechanism to ensure data integrity. Since Pthreads is typically used in C programs—and since C does not have a monitor— we accomplish locking by associating a condition variable with a mutex lock.

Condition variables in Pthreads use the pthread cond t data type and are initialized using the pthread cond init() function. The following code creates and initializes a condition variable as well as its associated mutex lock:
```
pthread mutex t mutex; pthread cond t cond var;

pthread mutex init(&mutex,NULL); **pthread cond init**(&cond var,NULL);
```
The pthread cond wait() function is used for waiting on a condition variable. The following code illustrates how a thread canwait for the condition a == b to become true using a Pthread condition variable:
```
pthread mutex lock(&mutex); while (a != b)

**pthread cond wait**(&cond var, &mutex);

pthread mutex unlock(&mutex);
```
The mutex lock associated with the condition variable must be locked before the pthread cond wait() function is called, since it is used to protect the data in the conditional clause from a possible race condition. Once this lock is acquired, the thread can check the condition. If the condition is not true, the thread then invokes pthread cond wait(), passing the mutex lock and the condition variable as parameters. Calling pthread cond wait() releases the mutex lock, thereby allowing another thread to access the shared data and possibly update its value so that the condition clause evaluates to true. (To protect against program errors, it is important to place the conditional clause within a loop so that the condition is rechecked after being signaled.)  

A thread that modifies the shared data can invoke the pthread cond signal() function, thereby signaling one thread waiting on the condition variable. This is illustrated below:
```
pthread mutex lock(&mutex); a = b; **pthread cond signal**(&cond var); pthread mutex unlock(&mutex);
```
It is important to note that the call to pthread cond signal() does not release the mutex lock. It is the subsequent call to pthread mutex unlock() that releases the mutex. Once the mutex lock is released, the signaled thread becomes the owner of the mutex lock and returns control from the call to pthread cond wait().

We provide several programming problems and projects at the end of this chapter that use Pthreadsmutex locks and condition variables, as well as POSIX semaphores.