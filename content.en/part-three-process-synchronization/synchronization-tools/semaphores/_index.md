---
title: 'Semaphores'
weight: 6
---

# Semaphores

Mutex locks, as we mentioned earlier, are generally considered the simplest of synchronization tools. In this section, we examine a more robust tool that can behave similarly to a mutex lock but can also providemore sophisticated ways for processes to synchronize their activities.

A **semaphore** S is an integer variable that, apart from initialization, is accessed only through two standard atomic operations: wait() and signal(). Semaphores were introduced by the Dutch computer scientist Edsger Dijk- stra, and such, the wait() operation was originally termed P (from the Dutch  

**_proberen,_** “to test”); signal()was originally called V (from **_verhogen,_** “to incre- ment”). The definition of wait() is as follows:
```
wait(S) { while (S <= 0)

;*/  busy wait S--;

}
```
The definition of signal() is as follows:
```
signal(S) { S++;

} 
```
All modifications to the integer value of the semaphore in the wait() and

signal() operations must be executed atomically. That is, when one process modifies the semaphore value, no other process can simultaneously modify that same semaphore value. In addition, in the case of wait(S), the testing of the integer value of S (S ≤ 0), as well as its possible modification (S--), must be executed without interruption. We shall see how these operations can be implemented in Section 6.6.2. First, let’s see how semaphores can be used.

## Semaphore Usage

Operating systems often distinguish between counting and binary semaphores. The value of a **counting semaphore** can range over an unrestricted domain. The value of a **binary semaphore** can range only between 0 and 1. Thus, binary semaphores behave similarly to mutex locks. In fact, on systems that do not provide mutex locks, binary semaphores can be used instead for providing mutual exclusion.

Counting semaphores can be used to control access to a given resource consisting of a finite number of instances. The semaphore is initialized to the number of resources available. Each process that wishes to use a resource performs a wait() operation on the semaphore (thereby decrementing the count). When a process releases a resource, it performs a signal() operation (incrementing the count). When the count for the semaphore goes to 0, all resources are being used. After that, processes that wish to use a resource will block until the count becomes greater than 0.

We can also use semaphores to solve various synchronization problems. For example, consider two concurrently running processes:_P_ 1 with a statement _S_ 1 and_P_ 2 with a statement _S_ 2. Supposewe require that _S_ 2 be executed only after _S_ 1 has completed. We can implement this scheme readily by letting _P_ 1 and _P_ 2 share a common semaphore synch, initialized to 0. In process _P_ 1, we insert the statements

_S_ 1; 
signal(synch);  


In process _P_ 2, we insert the statements

wait(synch); 
_S_ 2;

Because synch is initialized to 0, _P_ 2 will execute _S_ 2 only after _P_ 1 has invoked signal(synch), which is after statement _S_ 1 has been executed.

## Semaphore Implementation

Recall that the implementation of mutex locks discussed in Section 6.5 suffers from busy waiting. The definitions of the wait() and signal() semaphore operations just described present the same problem. To overcome this prob- lem, we can modify the definition of the wait() and signal() operations as follows: When a process executes the wait() operation and finds that the semaphore value is not positive, it must wait. However, rather than engaging in busy waiting, the process can suspend itself. The suspend operation places a process into a waiting queue associated with the semaphore, and the state of the process is switched to the waiting state. Then control is transferred to the CPU scheduler, which selects another process to execute.

Aprocess that is suspended,waiting on a semaphore S, should be restarted when some other process executes a signal() operation. The process is restarted by a wakeup() operation,which changes the process from thewaiting state to the ready state. The process is then placed in the ready queue. (The CPU may or may not be switched from the running process to the newly ready process, depending on the CPU-scheduling algorithm.)

To implement semaphores under this definition, we define a semaphore as follows:
```
typedef struct { int value; struct process *list;

} semaphore;
```
Each semaphore has an integer value and a list of processes list. When a process must wait on a semaphore, it is added to the list of processes. A signal() operation removes one process from the list of waiting processes and awakens that process.

Now, the wait() semaphore operation can be defined as
```
wait(semaphore *S) { S->value--; if (S->value < 0) {

add this process to S->list; sleep();

} }  



and the signal() semaphore operation can be defined as

signal(semaphore *S) { S->value++; if (S->value <= 0) {

remove a process _P_ from S->list; wakeup(P);

} }
```
The sleep() operation suspends the process that invokes it. The wakeup(P) operation resumes the execution of a suspended process P. These two opera- tions are provided by the operating system as basic system calls.

Note that in this implementation, semaphore values may be negative, whereas semaphore values are never negative under the classical definition of semaphoreswith busywaiting. If a semaphore value is negative, its magnitude is the number of processes waiting on that semaphore. This fact results from switching the order of the decrement and the test in the implementation of the wait() operation.

The list of waiting processes can be easily implemented by a link field in each process control block (PCB). Each semaphore contains an integer value and a pointer to a list of PCBs. One way to add and remove processes from the list so as to ensure bounded waiting is to use a FIFO queue, where the semaphore contains both head and tail pointers to the queue. In general, however, the list can use any queuing strategy. Correct usage of semaphores does not depend on a particular queuing strategy for the semaphore lists.

As mentioned, it is critical that semaphore operations be executed atomi- cally. We must guarantee that no two processes can execute wait() and sig- nal() operations on the same semaphore at the same time. This is a critical- section problem, and in a single-processor environment, we can solve it by sim- ply inhibiting interrupts during the time the wait() and signal() operations are executing. This scheme works in a single-processor environment because, once interrupts are inhibited, instructions from different processes cannot be interleaved. Only the currently running process executes until interrupts are reenabled and the scheduler can regain control.

In a multicore environment, interrupts must be disabled on every pro- cessing core. Otherwise, instructions from different processes (running on dif- ferent cores) may be interleaved in some arbitrary way. Disabling interrupts on every core can be a difficult task and can seriously diminish performance. Therefore, SMP systems must provide alternative techniques—such as com- pare and swap() or spinlocks—to ensure that wait() and signal() are per- formed atomically.

It is important to admit that we have not completely eliminated busy waiting with this definition of the wait() and signal() operations. Rather, we have moved busy waiting from the entry section to the critical sections of application programs. Furthermore, we have limited busy waiting to the critical sections of the wait() and signal() operations, and these sections are short (if properly coded, they should be no more than about ten instructions). Thus, the critical section is almost never occupied, and busy waiting occurs  



rarely, and then for only a short time. An entirely different situation exists with application programs whose critical sections may be long (minutes or even hours) or may almost always be occupied. In such cases, busy waiting is extremely inefficient.