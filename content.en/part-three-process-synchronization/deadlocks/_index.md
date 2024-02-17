---
title: 'Deadlocks'
weight: 3
---

# Deadlocks

In a multiprogramming environment, several threads may compete for a finite number of resources. A thread requests resources; if the resources are not available at that time, the thread enters a waiting state. Sometimes, a waiting thread can never again change state, because the resources it has requested are held by otherwaiting threads. This situation is called a **deadlock**.We discussed this issue briefly in Chapter 6 as a form of liveness failure. There, we defined deadlock as a situation in which _every process in a set of processes is waiting for an event that can be caused only by another process in the set_.

Perhaps the best illustration of a deadlock can be drawn from a law passed by the Kansas legislature early in the 20th century. It said, in part: “When two trains approach each other at a crossing, both shall come to a full stop and neither shall start up again until the other has gone.”

In this chapter, we describe methods that application developers as well as operating-system programmers can use to prevent or deal with dead- locks. Although some applications can identify programs that may dead- lock, operating systems typically do not provide deadlock-prevention facil- ities, and it remains the responsibility of programmers to ensure that they design deadlock-free programs. Deadlock problems—aswell as other liveness failures—are becoming more challenging as demand continues for increased concurrency and parallelism on multicore systems.

**CHAPTER OBJECTIVES**

• Illustrate how deadlock can occur when mutex locks are used.

• Define the four necessary conditions that characterize deadlock.

• Identify a deadlock situation in a resource allocation graph.

• Evaluate the four different approaches for preventing deadlocks.

• Apply the banker’s algorithm for deadlock avoidance.

• Apply the deadlock detection algorithm.

• Evaluate approaches for recovering from deadlock.