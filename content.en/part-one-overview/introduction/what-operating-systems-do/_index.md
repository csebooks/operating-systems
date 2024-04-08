---
title: 'What Operating Systems Do'
weight: 1
references:
    videos:
        - youtube:GjNp0bBrjmU
        - youtube:RozoeWzT7IM
    links:
        - https://www.geeksforgeeks.org/what-is-an-operating-system/
        - https://www.techtarget.com/whatis/definition/operating-system-OS
    books:
        - b1:
            title: Understanding Operating Systems
            url: https://www.google.co.in/books/edition/Understanding_Operating_Systems/bXMhAQAAIAAJ?hl=en&gbpv=0&bsq=What%20Operating%20Systems%20Do%20books
        - b2:
            title: Operating Systems
            url: https://www.google.co.in/books/edition/Operating_Systems_Principles_And_Design/fDZxNHyVcqIC?hl=en&gbpv=0
---

# What Operating Systems Do

We begin our discussion by looking at the operating system’s role in the overall computer system. A computer system can be divided roughly into four components: the **_hardware,_** the **_operating system,_** the **_application programs,_** and a **_user_** (Figure 1.1).

The **hardware**—the central processing unit (CPU), the memory, and the input/output (I/O) devices—provides the basic computing resources for the system. The **application programs**—such as word processors, spreadsheets, compilers, and web browsers—define the ways in which these resources are used to solve users’ computing problems. The operating system controls the hardware and coordinates its use among the various application programs for the various users.

We can also view a computer system as consisting of hardware, software, and data. The operating system provides the means for proper use of these resources in the operation of the computer system. An operating system is similar to a government. Like a government, it performs no useful function by itself. It simply provides an **_environment_** within which other programs can do useful work.

To understand more fully the operating system’s role, we next explore operating systems from two viewpoints: that of the user and that of the system.

### User View

The user’s view of the computer varies according to the interface being used. Many computer users sit with a laptop or in front of a PC consisting of a monitor, keyboard, and mouse. Such a system is designed for one user to monopolize its resources. The goal is to maximize the work (or play) that the user is performing. In this case, the operating system is designed mostly for **ease of use**, with some attention paid to performance and security and none paid to **resource utilization**—how various hardware and software resources are shared.

![Alt text](image-2.png)
**Figure 1.1** Abstract view of the components of a computer system.  
Increasingly, many users interact withmobile devices such as smartphones and tablets—devices that are replacing desktop and laptop computer systems for some users. These devices are typically connected to networks through cellular or other wireless technologies. The user interface formobile computers generally features a **touch screen**, where the user interacts with the system by pressing and swiping fingers across the screen rather than using a physical keyboard andmouse.Manymobile devices also allowusers to interact through a **voice recognition** interface, such as Apple’s **Siri**.

Some computers have little or no user view. For example, **embedded com- puters** in home devices and automobiles may have numeric keypads and may turn indicator lights on or off to show status, but they and their operating sys- tems and applications are designed primarily to runwithout user intervention.

### System View

From the computer’s point of view, the operating system is the program most intimately involved with the hardware. In this context, we can view an oper- ating system as a **resource allocator**. A computer system has many resources that may be required to solve a problem: CPU time, memory space, storage space, I/Odevices, and so on. The operating systemacts as themanager of these resources. Facing numerous and possibly conflicting requests for resources, the operating system must decide how to allocate them to specific programs and users so that it can operate the computer system efficiently and fairly.

A slightly different view of an operating system emphasizes the need to control the various I/O devices and user programs. An operating system is a control program. A **control program** manages the execution of user programs to prevent errors and improper use of the computer. It is especially concerned with the operation and control of I/O devices.

### Defining Operating Systems

By now, you can probably see that the term **_operating system_** covers many roles and functions. That is the case, at least in part, because of the myriad designs and uses of computers. Computers are present within toasters, cars, ships, spacecraft, homes, and businesses. They are the basis for gamemachines, cable TV tuners, and industrial control systems.

To explain this diversity, we can turn to the history of computers. Although computers have a relatively short history, they have evolved rapidly. Comput- ing started as an experiment to determine what could be done and quickly moved to fixed-purpose systems for military uses, such as code breaking and trajectory plotting, and governmental uses, such as census calculation. Those early computers evolved into general-purpose,multifunctionmainframes, and that’s when operating systemswere born. In the 1960s, **Moore’s Law** predicted that the number of transistors on an integrated circuit would double every 18 months, and that prediction has held true. Computers gained in functionality and shrank in size, leading to a vast number of uses and a vast number and variety of operating systems. (See Appendix A for more details on the history of operating systems.)

How, then, can we definewhat an operating system is? In general, we have no completely adequate definition of an operating system. Operating systems exist because they offer a reasonable way to solve the problem of creating a usable computing system. The fundamental goal of computer systems is to execute programs and to make solving user problems easier. Computer hardware is constructed toward this goal. Since bare hardware alone is not particularly easy to use, application programs are developed. These programs require certain common operations, such as those controlling the I/O devices. The common functions of controlling and allocating resources are then brought together into one piece of software: the operating system.

In addition, we have no universally accepted definition of what is part of the operating system. A simple viewpoint is that it includes everything a ven- dor ships when you order “the operating system.” The features included, how- ever, vary greatly across systems. Some systems take up less than a megabyte of space and lack even a full-screen editor, whereas others require gigabytes of space and are based entirely on graphical windowing systems. Amore com- mon definition, and the one that we usually follow, is that the operating system is the one program running at all times on the computer—usually called the **kernel**. Along with the kernel, there are two other types of programs: **system programs**, which are associated with the operating system but are not neces- sarily part of the kernel, and application programs, which include all programs not associated with the operation of the system.

The matter of what constitutes an operating system became increasingly important as personal computers becamemore widespread and operating sys- tems grew increasingly sophisticated. In 1998, the United States Department of Justice filed suit against Microsoft, in essence claiming that Microsoft included toomuch functionality in its operating systems and thus prevented application vendors from competing. (For example, a web browser was an integral part of Microsoft’s operating systems.)As a result,Microsoftwas found guilty of using its operating-system monopoly to limit competition.

Today, however, if we look at operating systems for mobile devices, we see that once again the number of features constituting the operating system is increasing. Mobile operating systems often include not only a core kernel but also **middleware**—a set of software frameworks that provide additional services to application developers. For example, each of the two most promi- nentmobile operating systems—Apple’s iOS andGoogle’s Android—features

**_WHY STUDY OPERATING SYSTEMS?_**

Although there are many practitioners of computer science, only a small per- centage of themwill be involved in the creation or modification of an operat- ing system. Why, then, study operating systems and how they work? Simply because, as almost all code runs on top of an operating system, knowledge of how operating systems work is crucial to proper, efficient, effective, and secure programming.Understanding the fundamentals of operating systems, how they drive computer hardware, andwhat they provide to applications is not only essential to those who program them but also highly useful to those who write programs on them and use them.  
a core kernel alongwithmiddleware that supports databases, multimedia, and graphics (to name only a few).
In summary, for our purposes, the operating system includes the always- running kernel, middleware frameworks that ease application development and provide features, and system programs that aid in managing the system while it is running. Most of this text is concerned with the kernel of general- purpose operating systems, but other components are discussed as needed to fully explain operating system design and operation.