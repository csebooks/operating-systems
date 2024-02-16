---
title: 'Hardware Support for Synchronization'
weight: 4
---

# Hardware Support for Synchronization

Wehave just described one software-based solution to the critical-section prob- lem. (We refer to it as a **_software-based_** solution because the algorithm involves no special support from the operating system or specific hardware instructions to ensure mutual exclusion.) However, as discussed, software-based solutions are not guaranteed to work on modern computer architectures. In this section, we present three hardware instructions that provide support for solving the critical-section problem. These primitive operations can be used directly as synchronization tools, or they can be used to form the foundation of more abstract synchronization mechanisms.

## Memory Barriers

In Section 6.3, we saw that a systemmay reorder instructions, a policy that can lead to unreliable data states. How a computer architecture determines what memory guarantees it will provide to an application program is known as its **memory model**. In general, a memory model falls into one of two categories:

**1. Strongly ordered**, where a memory modification on one processor is immediately visible to all other processors.

**2. Weakly ordered**, where modifications to memory on one processor may not be immediately visible to other processors.

Memorymodels vary by processor type, so kernel developers cannot make any assumptions regarding the visibility of modifications to memory on a shared-memory multiprocessor. To address this issue, computer architectures provide instructions that can _force_ any changes in memory to be propagated to all other processors, thereby ensuring that memorymodifications are visible to threads running on other processors. Such instructions are known as **memory barriers** or **memory fences**. When a memory barrier instruction is performed, the system ensures that all loads and stores are completed before any subse- quent load or store operations are performed. Therefore, even if instructions were reordered, the memory barrier ensures that the store operations are com- pleted in memory and visible to other processors before future load or store operations are performed.

Let’s return to ourmost recent example, inwhich reordering of instructions could have resulted in the wrong output, and use a memory barrier to ensure that we obtain the expected output.

If we add a memory barrier operation to Thread 1
```
while (!flag) memory barrier();

print x;
```
we guarantee that the value of flag is loaded before the value of x. Similarly, if we place a memory barrier between the assignments per-

formed by Thread 2
```
x = 100; memory barrier(); flag = true;
```
we ensure that the assignment to x occurs before the assignment to flag. With respect to Peterson’s solution, we could place a memory barrier

between the first two assignment statements in the entry section to avoid the reordering of operations shown in Figure 6.4. Note that memory barriers are considered very low-level operations and are typically only used by kernel developers when writing specialized code that ensures mutual exclusion.

## Hardware Instructions

Many modern computer systems provide special hardware instructions that allow us either to test andmodify the content of a word or to swap the contents of two words **atomically**—that is, as one uninterruptible unit. We can use these special instructions to solve the critical-section problem in a relatively simple manner. Rather than discussing one specific instruction for one specific machine, we abstract the main concepts behind these types of instructions by describing the test and set() and compare and swap() instructions.
```
boolean test and set(boolean *target) { boolean rv = *target; *target = true;

return rv; }
```
**Figure 6.5** The definition of the atomic test and set() instruction.  
```
do { while (test and set(&lock))

;*/ *do nothing */

/* critical section */

lock = false;

/* remainder section */ } while (true);
```
**Figure 6.6** Mutual-exclusion implementation with test and set().

The test and set() instruction can be defined as shown in Figure 6.5. The important characteristic of this instruction is that it is executed atomi- cally. Thus, if two test and set() instructions are executed simultaneously (each on a different core), they will be executed sequentially in some arbitrary order. If the machine supports the test and set() instruction, then we can implement mutual exclusion by declaring a boolean variable lock, initialized to false. The structure of process _Pi_ is shown in Figure 6.6.

The compare and swap() instruction (CAS), just like the test and set() instruction, operates on two words atomically, but uses a different mechanism that is based on swapping the content of two words.

The CAS instruction operates on three operands and is defined in Figure 6.7. The operand value is set to new value only if the expression (*value == expected) is true. Regardless, CAS always returns the original value of the variable value. The important characteristic of this instruction is that it is executed atomically. Thus, if two CAS instructions are executed simultaneously (each on a different core), they will be executed sequentially in some arbitrary order.

Mutual exclusion using CAS can be provided as follows: A global vari- able (lock) is declared and is initialized to 0. The first process that invokes compare and swap() will set lock to 1. It will then enter its critical section,
```
int compare and swap(int *value, int expected, int new value) { int temp = *value;

if (*value == expected) *value = new value;

return temp; }
```
**Figure 6.7** The definition of the atomic compare and swap() instruction.  
```
while (true) { while (compare and swap(&lock, 0, 1) != 0)

;*/ *do nothing */

/* critical section */

lock = 0;

/* remainder section */ }
```
**Figure 6.8** Mutual exclusion with the compare and swap() instruction.

because the original value of lockwas equal to the expected value of 0. Subse- quent calls to compare and swap()will not succeed, because lock now is not equal to the expected value of 0. When a process exits its critical section, it sets lock back to 0, which allows another process to enter its critical section. The structure of process _Pi_ is shown in Figure 6.8.

Although this algorithm satisfies the mutual-exclusion requirement, it does not satisfy the bounded-waiting requirement. In Figure 6.9, we present
```
while (true) { waiting[i] = true; key = 1; while (waiting[i] && key == 1)

key = compare and swap(&lock,0,1); waiting[i] = false;

/* critical section */

j = (i + 1) % n; while ((j != i) && !waiting[j])

j = (j + 1) % n;

if (j == i) lock = 0;

else waiting[j] = false;

/* remainder section */ }
```
**Figure 6.9** Bounded-waiting mutual exclusion with compare and swap().  

**_MAKING COMPARE-AND-SWAPATOMIC_**

On Intel x86 architectures, the assembly language statement cmpxchg is used to implement the compare and swap() instruction. To enforce atomic execution, the lock prefix is used to lock the bus while the destination operand is being updated. The general form of this instruction appears as:

lock cmpxchg <destination operand>, <source operand>

another algorithm using the compare and swap() instruction that satisfies all the critical-section requirements. The common data structures are
```
boolean waiting[n]; int lock;
```
The elements in the waiting array are initialized to false, and lock is initial- ized to 0. To prove that the mutual-exclusion requirement is met, we note that process _Pi_ can enter its critical section only if either waiting[i] == false or key == 0. The value of key can become 0 only if the compare and swap() is executed. The first process to execute the compare and swap() will find key == 0; all others must wait. The variable waiting[i] can become false only if another process leaves its critical section; only one waiting[i] is set to false, maintaining the mutual-exclusion requirement.

To prove that the progress requirement is met, we note that the arguments presented for mutual exclusion also apply here, since a process exiting the critical section either sets lock to 0 or sets waiting[j] to false. Both allow a process that is waiting to enter its critical section to proceed.

To prove that the bounded-waiting requirement is met, we note that, when a process leaves its critical section, it scans the array waiting in the cyclic ordering (_i_ + 1, _i_ + 2, ..., _n_ − 1, 0, ..., _i_ − 1). It designates the first process in this ordering that is in the entry section (waiting[j] == true) as the next one to enter the critical section. Any process waiting to enter its critical section will thus do so within _n_ − 1 turns.

Details describing the implementation of the atomic test and set() and compare and swap() instructions are discussed more fully in books on com- puter architecture.

## Atomic Variables

Typically, the compare and swap() instruction is not used directly to provide mutual exclusion. Rather, it is used as a basic building block for constructing other tools that solve the critical-section problem. One such tool is an **atomic variable**, which provides atomic operations on basic data types such as integers and booleans.We know from Section 6.1 that incrementing or decrementing an integer value may produce a race condition. Atomic variables can be used in to ensure mutual exclusion in situations where there may be a data race on a single variable while it is being updated, as when a counter is incremented.

Most systems that support atomic variables provide special atomic data types as well as functions for accessing and manipulating atomic variables.  

These functions are often implemented using compare and swap() opera- tions. As an example, the following increments the atomic integer sequence:

increment(&sequence);

where the increment() function is implemented using the CAS instruction:
```
void increment(atomic int *v) {

int temp;

do { temp = *v;

} while (temp != compare and swap(v, temp, temp+1));

}
```
It is important to note that although atomic variables provide atomic updates, they do not entirely solve race conditions in all circumstances. For example, in the bounded-buffer problemdescribed in Section 6.1, we could use an atomic integer for count. This would ensure that the updates to countwere atomic. However, the producer and consumer processes also have while loops whose condition depends on the value of count. Consider a situation in which the buffer is currently empty and two consumers are looping while waiting for count _>_ 0. If a producer entered one item in the buffer, both consumers could exit their while loops (as countwould no longer be equal to 0) and proceed to consume, even though the value of countwas only set to 1.

Atomic variables are commonly used in operating systems as well as con- current applications, although their use is often limited to single updates of shared data such as counters and sequence generators. In the following sec- tions, we explore more robust tools that address race conditions in more gen- eralized situations.