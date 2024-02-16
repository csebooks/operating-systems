---
title: 'Liveness'
weight: 8
---

# Liveness

One consequence of using synchronization tools to coordinate access to critical sections is the possibility that a process attempting to enter its critical section will wait indefinitely. Recall that in Section 6.2, we outlined three criteria that solutions to the critical-sectionproblemmust satisfy. Indefinitewaiting violates two of these—the progress and bounded-waiting criteria.

**Liveness** refers to a set of properties that a system must satisfy to ensure that processes make progress during their execution life cycle. A process wait- ing indefinitely under the circumstances just described is an example of a “liveness failure.”

There are many different forms of liveness failure; however, all are gen- erally characterized by poor performance and responsiveness. A very simple example of a liveness failure is an infinite loop. A busy wait loop presents the _possibility_ of a liveness failure, especially if a process may loop an arbitrarily long period of time. Efforts at providing mutual exclusion using tools such as mutex locks and semaphores can often lead to such failures in concurrent pro- gramming. In this section, we explore two situations that can lead to liveness failures.

## Deadlock

The implementation of a semaphore with a waiting queue may result in a situation where two or more processes are waiting indefinitely for an event that can be caused only by one of the waiting processes. The event in question is the execution of a signal() operation. When such a state is reached, these processes are said to be **deadlocked**.

To illustrate this, consider a system consisting of two processes, _P_0 and _P_1, each accessing two semaphores, S and Q, set to the value 1:

_P_ 0         _P_ 1

wait(S);     wait(Q);
wait(Q);     wait(S);

.              .

.              .

.              . 
signal(S);   signal(Q); signal(Q);   signal(S);

Suppose that _P_ 0 executes wait(S) and then _P_ 1 executes wait(Q). When _P_ 0 executes wait(Q), it must wait until _P_1 executes signal(Q). Similarly, when _P_ 1 executes wait(S), it must wait until _P_ 0 executes signal(S). Since these signal() operations cannot be executed, _P_ 0 and _P_ 1 are deadlocked.

We say that a set of processes is in a deadlocked state when _every process in the set is waiting for an event that can be caused only by another process in the set_. The “events” with which we are mainly concerned here are the acquisition and release of resources such as mutex locks and semaphores. Other types of events may result in deadlocks, as we show in more detail in Chapter 8. In that chapter, we describe various mechanisms for dealing with the deadlock problem, as well as other forms of liveness failures.

## Priority Inversion

A scheduling challenge arises when a higher-priority process needs to read or modify kernel data that are currently being accessed by a lower-priority process—or a chain of lower-priority processes. Since kernel data are typi- cally protected with a lock, the higher-priority process will have to wait for a lower-priority one to finish with the resource. The situation becomes more complicated if the lower-priority process is preempted in favor of another process with a higher priority.

As an example, assume we have three processes—_L_, _M_, and _H_—whose priorities follow the order _L < M < H_. Assume that process _H_ requires a semaphore _S_, which is currently being accessed by process _L_. Ordinarily, process _H_ would wait for _L_ to finish using resource _S_. However, now suppose that process _M_ becomes runnable, thereby preempting process _L_. Indirectly, a process with a lower priority—process _M_—has affected how long process _H_ must wait for _L_ to relinquish resource _S_.

This liveness problem is known as **priority inversion**, and it can occur only in systems with more than two priorities. Typically, priority inversion is avoided by implementing a **priority-inheritance protocol**. According to this protocol, all processes that are accessing resources needed by a higher-priority process inherit the higher priority until they are finished with the resources in question.When they are finished, their priorities revert to their original values. In the example above, a priority-inheritance protocol would allow process _L_ to temporarily inherit the priority of process _H_, thereby preventing process _M_  frompreempting its execution.Whenprocess _Lhadfinished_ using resource _S_, it would relinquish its inherited priority from _H_ and assume its original priority. Because resource _S_ would now be available, process _H_—not _M_—would run next.