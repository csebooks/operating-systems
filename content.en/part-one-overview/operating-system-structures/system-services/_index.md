---
title: 'System Services'
weight: 4
references:
    videos:
        - youtube:q7SqTVrdmUM
        - youtube:TQWERtMoKbI
    links:
        - https://www.geeksforgeeks.org/operating-system-services/
        - https://www.javatpoint.com/operating-system-services
    books:
        - b1:
            title: Win32 System Services
            url: https://www.google.co.in/books/edition/Win32_System_Services/JCG5aNnGlYsC?hl=en&authuser=2&gbpv=0
        - b2:
            title: Fundamentals of Service Systems
            url: https://www.google.co.in/books/edition/Fundamentals_of_Service_Systems/v6cvCwAAQBAJ?hl=en&authuser=2&gbpv=0
---

# System Services

Another aspect of a modern system is its collection of system services. Recall Figure 1.1, which depicted the logical computer hierarchy. At the lowest level is hardware. Next is the operating system, then the system services, and finally the application programs. **System services**, also known as **system utilities**, provide a convenient environment for program development and execution. Some of them are simply user interfaces to system calls. Others are consider- ably more complex. They can be divided into these categories:

• **File management**. These programs create, delete, copy, rename, print, list, and generally access and manipulate files and directories.

• **Status information**. Some programs simply ask the system for the date, time, amount of available memory or disk space, number of users, or similar status information. Others are more complex, providing detailed performance, logging, and debugging information. Typically, these pro- grams format and print the output to the terminal or other output devices or files or display it in a window of the GUI. Some systems also support a **registry**, which is used to store and retrieve configuration information.

• **File modificatio** . Several text editorsmay be available to create andmod- ify the content of files stored on disk or other storage devices. There may also be special commands to search contents of files or perform transfor- mations of the text.

• **Programming-language support**. Compilers, assemblers, debuggers, and interpreters for common programming languages (such as C, C++, Java, and Python) are often provided with the operating system or available as a separate download.

• **Program loading and execution**. Once a program is assembled or com- piled, it must be loaded into memory to be executed. The system may provide absolute loaders, relocatable loaders, linkage editors, and overlay loaders. Debugging systems for either higher-level languages or machine language are needed as well.

• **Communications**. These programs provide the mechanism for creating virtual connections among processes, users, and computer systems. They allow users to send messages to one another’s screens, to browse web pages, to send e-mail messages, to log in remotely, or to transfer files from one machine to another.

• **Background services**. All general-purpose systems have methods for launching certain system-program processes at boot time. Some of these processes terminate after completing their tasks, while others continue to run until the system is halted. Constantly running system-program pro- cesses are known as **services**, **subsystems**, or daemons. One example is the network daemon discussed in Section 2.3.3.5. In that example, a sys- tem needed a service to listen for network connections in order to connect those requests to the correct processes. Other examples include process schedulers that start processes according to a specified schedule, system error monitoring services, and print servers. Typical systems have dozens of daemons. In addition, operating systems that run important activities in user context rather than in kernel context may use daemons to run these activities.

Along with system programs, most operating systems are supplied with programs that are useful in solving common problems or performing common operations. Such **application programs** include web browsers, word proces- sors and text formatters, spreadsheets, database systems, compilers, plotting and statistical-analysis packages, and games.

The view of the operating system seen by most users is defined by the application and system programs, rather than by the actual system calls. Con- sider a user’s PC. When a user’s computer is running the macOS operating system, the user might see the GUI, featuring a mouse-and-windows interface. Alternatively, or even in one of the windows, the user might have a command- line UNIX shell. Both use the same set of system calls, but the system calls look different and act in different ways. Further confusing the user view, consider the user dual-booting from macOS into Windows. Now the same user on the same hardware has two entirely different interfaces and two sets of applica- tions using the same physical resources. On the same hardware, then, a user can be exposed to multiple user interfaces sequentially or concurrently.