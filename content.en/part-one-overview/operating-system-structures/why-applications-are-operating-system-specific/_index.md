---
title: 'Why Applications Are Operating-System Specific'
weight: 6
references:
    videos:
        - youtube:t_McsJ1RGQg
        - youtube:acPvdGOYK4I
    links:
        - https://www.geeksforgeeks.org/design-and-implementation-in-operating-system/
        - https://www.tutorialspoint.com/operating-system-design-and-implementation
    books:
        - b1:
            title: Operating System  
            url: https://www.google.co.in/books/edition/Operating_Systems/dBQFXs5NPEYC?hl=en&gbpv=0&bsq=Why%20Applications%20Are%20Operating-System%20Specific
        - b2:
            title: Operating System
            url: https://www.google.co.in/books/edition/Operating_System/-p7C6ZbdwgUC?hl=en&gbpv=1&dq=Why+Applications+Are+Operating-System+Specific&printsec=frontcover
---

# Why Applications Are Operating-System Specific

Fundamentally, applications compiled on one operating system are not exe- cutable on other operating systems. If they were, the world would be a better place, and our choice of what operating system to use would depend on utility and features rather than which applications were available.

Based on our earlier discussion, we can now see part of the problem—each operating system provides a unique set of system calls. System calls are part of the set of services provided by operating systems for use by applications. Even if system calls were somehow uniform, other barriers would make it difficult for us to execute application programs on different operating systems. But if you have used multiple operating systems, you may have used some of the same applications on them. How is that possible?

An application can bemade available to run onmultiple operating systems in one of three ways:

**1\.** The application can bewritten in an interpreted language (such as Python or Ruby) that has an interpreter available for multiple operating systems. The interpreter reads each line of the source program, executes equivalent instructions on the native instruction set, and calls native operating sys- tem calls. Performance suffers relative to that for native applications, and the interpreter provides only a subset of each operating system’s features, possibly limiting the feature sets of the associated applications.

**2\.** The application can be written in a language that includes a virtual machine containing the running application. The virtual machine is part of the language’s full RTE. One example of thismethod is Java. Java has an RTE that includes a loader, byte-code verifier, and other components that load the Java application into the Java virtual machine. This RTE has been  



**ported**, or developed, for many operating systems, from mainframes to smartphones, and in theory any Java app can runwithin the RTEwherever it is available. Systems of this kind have disadvantages similar to those of interpreters, discussed above.

**3\.** The application developer can use a standard language or API in which the compiler generates binaries in a machine- and operating-system- specific language. The application must be ported to each operating sys- tem on which it will run. This porting can be quite time consuming and must be done for each new version of the application, with subsequent testing and debugging. Perhaps the best-known example is the POSIX API and its set of standards for maintaining source-code compatibility between different variants of UNIX-like operating systems.

In theory, these three approaches seemingly provide simple solutions for developing applications that can run across different operating systems. How- ever, the general lack of application mobility has several causes, all of which still make developing cross-platform applications a challenging task. At the application level, the libraries providedwith the operating system contain APIs to provide features like GUI interfaces, and an application designed to call one set of APIs (say, those available from iOS on the Apple iPhone) will not work on an operating system that does not provide those APIs (such as Android). Other challenges exist at lower levels in the system, including the following.

• Each operating system has a binary format for applications that dictates the layout of the header, instructions, and variables. Those components need to be at certain locations in specified structures within an executable file so the operating system can open the file and load the application for proper execution.

• CPUs have varying instruction sets, and only applications containing the appropriate instructions can execute correctly.

• Operating systems provide system calls that allow applications to request various activities, such as creating files and opening network connec- tions. Those system calls vary among operating systems in many respects, including the specific operands and operand ordering used, how an appli- cation invokes the system calls, their numbering and number, their mean- ings, and their return of results.

There are some approaches that have helped address, though not com- pletely solve, these architectural differences. For example, Linux—and almost every UNIX system—has adopted the ELF format for binary executable files. Although ELF provides a common standard across Linux and UNIX systems, the ELF format is not tied to any specific computer architecture, so it does not guarantee that an executable file will run across different hardware platforms.

APIs, as mentioned above, specify certain functions at the application level. At the architecture level, an **application binary interface** (ABI) is used to define how different components of binary code can interface for a given operating system on a given architecture. An ABI specifies low-level details, including addresswidth,methods of passing parameters to system calls, the organization of the run-time stack, the binary format of system libraries, and the size of data types, just to name a few. Typically, an ABI is specified for a given architecture (for example, there is an ABI for the ARMv8 processor). Thus, an ABI is the architecture-level equivalent of an API. If a binary executable file has been compiled and linked according to a particular ABI, it should be able to run on different systems that support that ABI. However, because a particular ABI is defined for a certain operating system running on a given architecture, ABIs do little to provide cross-platform compatibility.

In sum, all of these differences mean that unless an interpreter, RTE, or binary executable file iswritten for and compiled on a specific operating system on a specific CPU type (such as Intel x86 or ARMv8), the application will fail to run. Imagine the amount of work that is required for a program such as the Firefox browser to run on Windows, macOS, various Linux releases, iOS, and Android, sometimes on various CPU architectures.