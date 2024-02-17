---
title: 'Deadlock Prevention'
weight: 5
---

# Deadlock Prevention

As we noted in Section 8.3.1, for a deadlock to occur, each of the four neces- sary conditions must hold. By ensuring that at least one of these conditions cannot hold, we can **_prevent_** the occurrence of a deadlock. We elaborate on this approach by examining each of the four necessary conditions separately.

## Mutual Exclusion

The mutual-exclusion condition must hold. That is, at least one resource must be nonsharable. Sharable resources do not require mutually exclusive access and thus cannot be involved in a deadlock. Read-only files are a good example of a sharable resource. If several threads attempt to open a read-only file at the same time, they can be granted simultaneous access to the file. A thread never needs to wait for a sharable resource. In general, however, we cannot prevent deadlocks by denying the mutual-exclusion condition, because some resources are intrinsically nonsharable. For example, a mutex lock cannot be simultaneously shared by several threads.

## Hold and Wait

To ensure that the hold-and-wait condition never occurs in the system,wemust guarantee that, whenever a thread requests a resource, it does not hold any other resources. One protocol that we can use requires each thread to request and be allocated all its resources before it begins execution. This is, of course,impractical for most applications due to the dynamic nature of requesting resources.

An alternative protocol allows a thread to request resources only when it has none. A thread may request some resources and use them. Before it can request any additional resources, it must release all the resources that it is currently allocated.

Both these protocols have two main disadvantages. First, resource utiliza- tionmay be low, since resourcesmay be allocated but unused for a long period. For example, a thread may be allocated a mutex lock for its entire execution, yet only require it for a short duration. Second, starvation is possible. A thread that needs several popular resources may have to wait indefinitely, because at least one of the resources that it needs is always allocated to some other thread.

## No Preemption

The third necessary condition for deadlocks is that there be no preemption of resources that have already been allocated. To ensure that this condition does not hold, we can use the following protocol. If a thread is holding some resources and requests another resource that cannot be immediately allocated to it (that is, the thread must wait), then all resources the thread is currently holding are preempted. In other words, these resources are implicitly released. The preempted resources are added to the list of resources for which the thread iswaiting. The threadwill be restarted onlywhen it can regain its old resources, as well as the new ones that it is requesting.

Alternatively, if a thread requests some resources, we first check whether they are available. If they are, we allocate them. If they are not, we check whether they are allocated to some other thread that is waiting for additional resources. If so, we preempt the desired resources from the waiting thread and allocate them to the requesting thread. If the resources are neither available nor held by a waiting thread, the requesting thread must wait. While it is waiting, some of its resources may be preempted, but only if another thread requests them. A thread can be restarted only when it is allocated the new resources it is requesting and recovers any resources that were preempted while it was waiting.

This protocol is often applied to resources whose state can be easily saved and restored later, such as CPU registers and database transactions. It can- not generally be applied to such resources as mutex locks and semaphores, precisely the type of resources where deadlock occurs most commonly.

## Circular Wait

The three options presented thus far for deadlock prevention are generally impractical in most situations. However, the fourth and final condition for deadlocks — the circular-wait condition — presents an opportunity for a practical solution by invalidating one of the necessary conditions. One way to ensure that this condition never holds is to impose a total ordering of all resource types and to require that each thread requests resources in an increasing order of enumeration.

To illustrate, we let _R_ = _{R_ 1, _R_ 2, ..., _Rm}_ be the set of resource types. We assign to each resource type a unique integer number, which allows us to compare two resources and to determine whether one precedes another in our ordering. Formally,we define a one-to-one function _F_:_R_→_N,_where_N_ is the set of natural numbers. We can accomplish this scheme in an application program by developing an ordering among all synchronization objects in the system. For example, the lock ordering in the Pthread program shown in Figure 8.1 could be _F_(first mutex) = 1 _F_(second mutex) = 5

We can now consider the following protocol to prevent deadlocks: Each thread can request resources only in an increasing order of enumeration. That is, a thread can initially request an instance of a resource—say, _Ri_. After that, the thread can request an instance of resource _Rj_ if and only if _F_(_Rj_) _> F_(_Ri_). For example, using the function defined above, a thread that wants to use both first mutex and second mutex at the same time must first request first mutex and then second mutex. Alternatively, we can require that a thread requesting an instance of resource _Rj_ must have released any resources _Ri_ such that _F_(_Ri_)≥ _F_(_Rj_). Note also that if several instances of the same resource type are needed, a **_single_** request for all of them must be issued.

If these two protocols are used, then the circular-wait condition cannot hold. We can demonstrate this fact by assuming that a circular wait exists (proof by contradiction). Let the set of threads involved in the circular wait be _{T_ 0, _T_ 1, ..., _Tn}_, where _Ti_ is waiting for a resource _Ri_, which is held by thread _Ti_+1. (Modulo arithmetic is used on the indexes, so that _Tn_ is waiting for a resource _Rn_ held by _T_ 0.) Then, since thread _Ti_+1 is holding resource _Ri_ while requesting resource _Ri_+1, we must have _F_(_Ri_) _< F_(_Ri_+1) for all _i._ But this condi- tionmeans that _F_(_R_ 0)_< F_(_R_ 1)< ..._< F_(_Rn_)_< F_(_R_ 0). By transitivity, _F_(_R_ 0) _< F_(_R_ 0), which is impossible. Therefore, there can be no circular wait.

Keep in mind that developing an ordering, or hierarchy, does not in itself prevent deadlock. It is up to application developers to write programs that follow the ordering. However, establishing a lock ordering can be difficult, especially on a system with hundreds—or thousands—of locks. To address this challenge, many Java developers have adopted the strategy of using the method System.identityHashCode(Object) (which returns the default hash code value of the Object parameter it has been passed) as the function for ordering lock acquisition.

It is also important to note that imposing a lock ordering does not guar- antee deadlock prevention if locks can be acquired dynamically. For exam- ple, assume we have a function that transfers funds between two accounts. To prevent a race condition, each account has an associated mutex lock that is obtained from a get lock() function such as that shown in Figure 8.7. Deadlock is possible if two threads simultaneously invoke the transaction() function, transposing different accounts. That is, one thread might invoke

transaction(checking account, savings account, 25.0)

and another might invoke

transaction(savings account, checking account, 50.0)  


```
void transaction(Account from, Account to, double amount) {

mutex lock1, lock2; lock1 = get lock(from); lock2 = get lock(to);

acquire(lock1); acquire(lock2);

withdraw(from, amount); deposit(to, amount);

release(lock2); release(lock1);

}
```
**Figure 8.7** Deadlock example with lock ordering.