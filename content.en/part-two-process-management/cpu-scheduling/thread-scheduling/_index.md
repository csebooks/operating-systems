---
title: 'Thread Scheduling'
weight: 4
references:
    videos:
        - youtube:7q22vVYKpnQ
        - youtube:VbQwCEYtWZM
    links:
        - https://www.geeksforgeeks.org/thread-scheduling/
        - https://www.javatpoint.com/thread-scheduler-in-java
    books:
        - b1:
            title: Java Threads 
            url: https://www.google.co.in/books/edition/Java_Threads/r8hhO7oGKrEC?hl=en&gbpv=0
        - b2:
            title: Thread Time
            url: https://www.google.co.in/books/edition/Thread_Time/YJtQAAAAMAAJ?hl=en&gbpv=0&bsq=Thread%20Scheduling%20book 
---

# Thread Scheduling

In Chapter 4, we introduced threads to the process model, distinguishing between **_user-level_** and **_kernel-level_** threads. On most modern operating sys- tems it is kernel-level threads—not processes—that are being scheduled by the operating system. User-level threads are managed by a thread library, and the kernel is unaware of them. To run on a CPU, user-level threads must ulti- mately be mapped to an associated kernel-level thread, although this mapping may be indirect and may use a lightweight process (LWP). In this section, we explore scheduling issues involving user-level and kernel-level threads and offer specific examples of scheduling for Pthreads.

## Contention Scope

One distinction between user-level and kernel-level threads lies in how they are scheduled. On systems implementing the many-to-one (Section 4.3.1) and many-to-many (Section 4.3.3) models, the thread library schedules user- level threads to run on an available LWP. This scheme is known as **process- contention scope** (**PCS**), since competition for the CPU takes place among threads belonging to the same process. (When we say the thread library _sched- ules_ user threads onto available LWPs, we do not mean that the threads are actually _running_ on a CPU as that further requires the operating system to schedule the LWP’s kernel thread onto a physical CPU core.) To decide which kernel-level thread to schedule onto a CPU, the kernel uses **system-contention scope** (**SCS**). Competition for the CPU with SCS scheduling takes place among all threads in the system. Systems using the one-to-one model (Section 4.3.2), such as Windows and Linux schedule threads using only SCS.

Typically, PCS is done according to priority—the scheduler selects the runnable thread with the highest priority to run. User-level thread priorities are set by the programmer and are not adjusted by the thread library, although some thread libraries may allow the programmer to change the priority of a thread. It is important to note that PCS will typically preempt the thread currently running in favor of a higher-priority thread; however, there is no guarantee of time slicing (Section 5.3.3) among threads of equal priority.

## Pthread Scheduling

We provided a sample POSIX Pthread program in Section 4.4.1, along with an introduction to thread creation with Pthreads. Now, we highlight the POSIX Pthread API that allows specifying PCS or SCS during thread creation. Pthreads identifies the following contention scope values:

• PTHREAD SCOPE PROCESS schedules threads using PCS scheduling.

• PTHREAD SCOPE SYSTEM schedules threads using SCS scheduling.

On systems implementing the many-to-many model, the PTHREAD SCOPE PROCESS policy schedules user-level threads onto available LWPs. The number of LWPs is maintained by the thread library, perhaps using scheduler activations (Section 4.6.5). The PTHREAD SCOPE SYSTEM scheduling policy will create and bind an LWP for each user-level thread onmany-to-many systems, effectively mapping threads using the one-to-one policy.

The Pthread IPC (Interprocess Communication) provides two functions for setting—and getting—the contention scope policy:

• pthread attr setscope(pthread attr t \*attr, int scope)

• pthread attr getscope(pthread attr t \*attr, int \*scope)

The first parameter for both functions contains a pointer to the attribute set for the thread. The second parameter for the pthread attr setscope() function is passed either the PTHREAD SCOPE SYSTEM or the PTHREAD SCOPE PROCESS value, indicating how the contention scope is to be set. In the case of pthread attr getscope(), this second parameter contains a pointer to an int value that is set to the current value of the contention scope. If an error occurs, each of these functions returns a nonzero value.

In Figure 5.10, we illustrate a Pthread scheduling API. The pro- gram first determines the existing contention scope and sets it to PTHREAD SCOPE SYSTEM. It then creates five separate threads that will run using the SCS scheduling policy. Note that on some systems, only certain contention scope values are allowed. For example, Linux and macOS systems allow only PTHREAD SCOPE SYSTEM.  

```
#include _<_pthread.h_\>_ #include _<_stdio.h_\>_ #define NUM THREADS 5

int main(int argc, char \*argv\[\]) _{_

int i, scope; pthread t tid\[NUM THREADS\]; pthread attr t attr;

/\* get the default attributes \*/ pthread attr init(&attr);

/\* first inquire on the current scope \*/ if (**pthread attr getscope**(&attr, &scope) != 0)

fprintf(stderr, "Unable to get scheduling scope∖n"); else _{_

if (scope == PTHREAD SCOPE PROCESS) printf("PTHREAD SCOPE PROCESS");

else if (scope == PTHREAD SCOPE SYSTEM) printf("PTHREAD SCOPE SYSTEM");

else fprintf(stderr, "Illegal scope value.∖n");

_}_

/\* set the scheduling algorithm to PCS or SCS \*/ **pthread attr setscope**(&attr, PTHREAD SCOPE SYSTEM);

/\* create the threads \*/ for (i = 0; i < NUM THREADS; i++)

pthread create(&tid\[i\],&attr,runner,NULL);

/\* now join on each thread \*/ for (i = 0; i < NUM THREADS; i++)

pthread join(tid\[i\], NULL); _}_

/\* Each thread will begin control in this function \*/ void \*runner(void \*param) _{_

/\* do some work ... \*/

pthread exit(0); _}_
```
**Figure 5.10** Pthread scheduling API.  
