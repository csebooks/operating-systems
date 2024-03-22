---
title: 'Security and Protection'
weight: 6
references:
    videos:
        - youtube:fQlG5zzUNy8
        - youtube:Abta0j826Bk
    links:
        - https://www.geeksforgeeks.org/difference-between-security-and-protection/
        - https://www.javatpoint.com/security-vs-protection-in-operating-system
    books:
        - b1:
            title: Internet of Things Security and Data Protection 
            url: https://www.google.co.in/books/edition/Internet_of_Things_Security_and_Data_Pro/Ws2NDwAAQBAJ?hl=en&gbpv=0
        - b2:
            title: Quality Of Protection 
            url:  https://www.google.co.in/books/edition/Quality_Of_Protection/W09ZuB8hMW8C?hl=en&gbpv=0
---

# Security and Protection

If a computer system has multiple users and allows the concurrent execution of multiple processes, then access to data must be regulated. For that purpose, mechanisms ensure that files, memory segments, CPU, and other resources can be operated on by only those processes that have gained proper authoriza- tion from the operating system. For example, memory-addressing hardware ensures that a process can execute only within its own address space. The timer ensures that no process can gain control of the CPU without eventually relinquishing control. Device-control registers are not accessible to users, so the integrity of the various peripheral devices is protected.

**Protection**, then, is any mechanism for controlling the access of processes or users to the resources defined by a computer system. This mechanism must providemeans to specify the controls to be imposed and to enforce the controls.

Protection can improve reliability by detecting latent errors at the interfaces between component subsystems. Early detection of interface errors can often prevent contamination of a healthy subsystem by another subsystem that is malfunctioning. Furthermore, an unprotected resource cannot defend against use (or misuse) by an unauthorized or incompetent user. Aprotection-oriented system provides a means to distinguish between authorized and unauthorized usage, as we discuss in Chapter 17.

A system can have adequate protection but still be prone to failure and allow inappropriate access. Consider a user whose authentication information (her means of identifying herself to the system) is stolen. Her data could be copied or deleted, even though file and memory protection are working. It is the job of **security** to defend a system from external and internal attacks. Such attacks spread across a huge range and include viruses and worms, denial-of- service attacks (which use all of a system’s resources and so keep legitimate users out of the system), identity theft, and theft of service (unauthorized use of a system). Prevention of some of these attacks is considered an operating- system function on some systems, while other systems leave it to policy or additional software. Due to the alarming rise in security incidents, operating- system security features are a fast-growing area of research and implementa- tion. We discuss security in Chapter 16.

Protection and security require the system to be able to distinguish among all its users. Most operating systems maintain a list of user names and asso- ciated **user identifier** (**user IDs**). In Windows parlance, this is a **security ID** (**SID**). These numerical IDs are unique, one per user. When a user logs in to the system, the authentication stage determines the appropriate user ID for the user. That user ID is associated with all of the user’s processes and threads. When an ID needs to be readable by a user, it is translated back to the user name via the user name list.

In some circumstances, we wish to distinguish among sets of users rather than individual users. For example, the owner of a file on a UNIX systemmay be allowed to issue all operations on that file, whereas a selected set of users may be allowed only to read the file. To accomplish this, we need to define a group name and the set of users belonging to that group. Group functionality can be implemented as a system-wide list of group names and **group identifier** . A user can be in one or more groups, depending on operating-system design  
decisions. The user’s group IDs are also included in every associated process and thread.

In the course of normal system use, the user ID and group ID for a user are sufficient. However, a user sometimes needs to **escalate privileges** to gain extra permissions for an activity. The user may need access to a device that is restricted, for example. Operating systems provide various methods to allow privilege escalation. On UNIX, for instance, the _setuid_ attribute on a program causes that program to run with the user ID of the owner of the file, rather than the current user’s ID. The process runs with this **effective UID** until it turns off the extra privileges or terminates.