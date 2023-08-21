---
title: 'PART TEN APPENDICES'
weight: 15
---

  

_AAppendixInfluential Operating Systems_

Now that you understand the fundamental concepts of operating systems (CPU scheduling, memory management, processes, and so on), we are in a position to examine how these concepts have been applied in several older and highly influential operating systems. Some of them (such as the XDS-940 and the THE system) were one-of-a-kind systems; others (such as OS/360) are widely used. The order of presentation highlights the similarities and differences of the systems; it is not strictly chronological or ordered by importance. The serious student of operating systems should be familiar with all these systems.

In the bibliographical notes at the end of the chapter, we include references to further reading about these early systems. The papers, written by the design- ers of the systems, are important both for their technical content and for their style and flavor.

**CHAPTER OBJECTIVES**

• Explain how operating-system features migrate over time from large com- puter systems to smaller ones.

• Discuss the features of several historically important operating systems.

**A.1 Feature Migration**

One reason to study early architectures and operating systems is that a feature that once ran only on huge systems may eventually make its way into very small systems. Indeed, an examination of operating systems for mainframes and microcomputers shows that many features once available only on main- frames have been adopted for microcomputers. The same operating-system concepts are thus appropriate for various classes of computers: mainframes, minicomputers,microcomputers, andhandhelds. Tounderstandmodern oper- ating systems, then, you need to recognize the theme of feature migration and the long history of many operating-system features, as shown in Figure A.1.

Agood example of featuremigration startedwith theMultiplexed Informa- tion and Computing Services (MULTICS) operating system. MULTICSwas devel-

**1**  

**2 Appendix A Influentia Operating Systems**

mainframes

1950

no software

no software

multiprocessorbatch

compilers time shared

distributed systems

resident monitors

fault tolerantnetworked

multiuser

no software

compilers

no software interactive

compilers

compilers

interactive

networked

time sharedresident

monitors fault tolerant

multiuser

networked clustered

multiuser

multiprocessor

multiprocessor

1960 1970 MULTICS

1980 1990 2000

minicomputers

desktop computers

handheld computers

UNIX

UNIX

networked UNIX

smart phones

2010

LINUX

multiprocessor

networked interactive

LINUX

**Figure A.1** Migration of operating-system concepts and features.

oped from 1965 to 1970 at the Massachusetts Institute of Technology (MIT) as a computing **utility**. It ran on a large, complexmainframe computer (the GE-645). Many of the ideas that were developed for MULTICS were subsequently used at Bell Laboratories (one of the original partners in the development of MULTICS) in the design of UNIX. The UNIX operating system was designed around 1970 for a PDP-11 minicomputer. Around 1980, the features of UNIX became the basis for UNIX-like operating systems on microcomputers, and these features are included in several more recent operating systems for microcomputers, such as Microsoft Windows, Windows XP, and the macOS operating system. Linux includes some of these same features, and they can now be found on PDAs.

**A.2 Early Systems**

We turn our attention now to a historical overview of early computer systems. We should note that the history of computing starts far before “computers” with looms and calculators. We begin our discussion, however, with the com- puters of the twentieth century.

Before the 1940s, computing devices were designed and implemented to perform specific, fixed tasks.Modifying one of those tasks required a great deal of effort andmanual labor. All that changed in the 1940s whenAlan Turing and John von Neumann (and colleagues), both separately and together, worked on the idea of a more general-purpose **stored program** computer. Such a machine  

**A.2 Early Systems 3**

has both a program store and a data store, where the program store provides instructions about what to do to the data.

This fundamental computer concept quickly generated a number of general-purpose computers, but much of the history of these machines is blurred by time and the secrecy of their development during World War II. It is likely that the first working stored-program general-purpose computer was the Manchester Mark 1, which ran successfully in 1949. The first commercial computer—the Ferranti Mark 1, which went on sale in 1951—was its offspring.

Early computers were physically enormous machines run from consoles. The programmer, who was also the operator of the computer system, would write a programand thenwould operate it directly from the operator’s console. First, the programwould be loadedmanually intomemory from the front panel switches (one instruction at a time), from paper tape, or from punched cards. Then the appropriate buttons would be pushed to set the starting address and to start the execution of the program. As the program ran, the program- mer/operator could monitor its execution by the display lights on the console. If errors were discovered, the programmer could halt the program, examine the contents of memory and registers, and debug the program directly from the console. Output was printed or was punched onto paper tape or cards for later printing.

**A.2.1 Dedicated Computer Systems**

As time went on, additional software and hardware were developed. Card readers, line printers, and magnetic tape became commonplace. Assemblers, loaders, and linkers were designed to ease the programming task. Libraries of common functions were created. Common functions could then be copied into a new program without having to be written again, providing software reusability.

The routines that performed I/O were especially important. Each new I/O device had its own characteristics, requiring careful programming. A special subroutine called a device driver—was written for each I/O device. A device driver knows how the buffers, flags, registers, control bits, and status bits for a particular device should be used. Each type of device has its own driver. A simple task, such as reading a character from a paper-tape reader, might involve complex sequences of device-specific operations. Rather than writing the necessary code every time, the device driver was simply used from the library.

Later, compilers for FORTRAN, COBOL, and other languages appeared,mak- ing the programming taskmuch easier but the operation of the computer more complex. To prepare a FORTRAN program for execution, for example, the pro- grammer would first need to load the FORTRAN compiler into the computer. The compiler was normally kept on magnetic tape, so the proper tape would need to be mounted on a tape drive. The program would be read through the card reader and written onto another tape. The FORTRAN compiler produced assembly-language output, which then had to be assembled. This procedure required mounting another tape with the assembler. The output of the assem- bler would need to be linked to supporting library routines. Finally, the binary object form of the program would be ready to execute. It could be loaded into memory and debugged from the console, as before.  

**4 Appendix A Influentia Operating Systems**

A significant amount of **setup time** could be involved in the running of a job. Each job consisted of many separate steps:

**1\.** Loading the FORTRAN compiler tape

**2\.** Running the compiler

**3\.** Unloading the compiler tape

**4\.** Loading the assembler tape

**5\.** Running the assembler

**6\.** Unloading the assembler tape

**7\.** Loading the object program

**8\.** Running the object program

If an error occurred during any step, the programmer/operator might have to start over at the beginning. Each job step might involve the loading and unloading of magnetic tapes, paper tapes, and punch cards.

The job setup timewas a real problem.While tapes were beingmounted or the programmer was operating the console, the CPU sat idle. Remember that, in the early days, few computers were available, and they were expensive. A computer might have cost millions of dollars, not including the operational costs of power, cooling, programmers, and so on. Thus, computer time was extremely valuable, and owners wanted their computers to be used as much as possible. They needed high **utilization** to get as much as they could from their investments.

**A.2.2 Shared Computer Systems**

The solution was twofold. First, a professional computer operator was hired. The programmer no longer operated the machine. As soon as one job was finished, the operator could start the next. Since the operator had more experi- ence with mounting tapes than a programmer, setup time was reduced. The programmer provided whatever cards or tapes were needed, as well as a short description of how the job was to be run. Of course, the operator could not debug an incorrect program at the console, since the operator would not understand the program. Therefore, in the case of program error, a dump of memory and registers was taken, and the programmer had to debug from the dump. Dumping the memory and registers allowed the operator to continue immediately with the next job but left the programmer with the more difficult debugging problem.

Second, jobs with similar needswere batched together and run through the computer as a group to reduce setup time. For instance, suppose the operator received one FORTRAN job, one COBOL job, and another FORTRAN job. If she ran them in that order, she would have to set up for FORTRAN (load the compiler tapes and so on), then set up for COBOL, and then set up for FORTRAN again. If she ran the two FORTRAN programs as a batch, however, she could setup only once for FORTRAN, saving operator time.  

**A.2 Early Systems 5**

loader

job sequencing

control card interpreter

user program

area

monitor

**Figure A.2** Memory layout for a resident monitor.

But there were still problems. For example, when a job stopped, the oper- ator would have to notice that it had stopped (by observing the console), determine _why_ it stopped (normal or abnormal termination), dump memory and register (if necessary), load the appropriate device with the next job, and restart the computer. During this transition from one job to the next, the CPU sat idle.

To overcome this idle time, people developed **automatic job sequencing**. With this technique, the first rudimentary operating systems were created. A small program, called a **resident monitor**, was created to transfer control automatically from one job to the next (Figure A.2). The resident monitor is always in memory (or **_resident_**).

When the computer was turned on, the resident monitor was invoked, and it would transfer control to a program.When the program terminated, it would return control to the resident monitor, which would then go on to the next program. Thus, the resident monitor would automatically sequence from one program to another and from one job to another.

But how would the resident monitor know which program to execute? Previously, the operator had been given a short description of what programs were to be run on what data. **Control cards** were introduced to provide this information directly to the monitor. The idea is simple. In addition to the program or data for a job, the programmer supplied control cards, which contained directives to the resident monitor indicating what program to run. For example, a normal user program might require one of three programs to run: the FORTRAN compiler (FTN), the assembler (ASM), or the user’s program (RUN). We could use a separate control card for each of these:

$FTN—Execute the FORTRAN compiler. $ASM—Execute the assembler. $RUN—Execute the user program.

These cards tell the resident monitor which program to run.  

**6 Appendix A Influentia Operating Systems**

We can use two additional control cards to define the boundaries of each job:

$JOB—First card of a job $END—Final card of a job

These two cards might be useful in accounting for the machine resources used by the programmer. Parameters can be used to define the job name, account number to be charged, and so on. Other control cards can be defined for other functions, such as asking the operator to load or unload a tape.

One problem with control cards is how to distinguish them from data or program cards. The usual solution is to identify them by a special character or pattern on the card. Several systems used the dollar-sign character ($) in the first column to identify a control card. Others used a different code. IBM’s Job Control Language (JCL) used slash marks (//) in the first two columns. Figure A.3 shows a sample card-deck setup for a simple batch system.

A resident monitor thus has several identifiable parts:

• The **control-card interpreter** is responsible for reading and carrying out the instructions on the cards at the point of execution.

• The **loader** is invoked by the control-card interpreter to load system pro- grams and application programs into memory at intervals.

• The **device drivers** are used by both the control-card interpreter and the loader for the system’s I/O devices. Often, the system and application programs are linked to these same device drivers, providing continuity in their operation, as well as saving memory space and programming time.

These batch systems work fairly well. The resident monitor provides auto- matic job sequencing as indicated by the control cards. When a control card indicates that a program is to be run, the monitor loads the program intomem- ory and transfers control to it.When the program completes, it transfers control

$END

$RUN

data for program

$LOAD

$FTN

$JOB

program to be compiled

**Figure A.3** Card deck for a simple batch system.  

**A.2 Early Systems 7**

back to the monitor, which reads the next control card, loads the appropriate program, and so on. This cycle is repeated until all control cards are interpreted for the job. Then the monitor automatically continues with the next job.

The switch to batch systems with automatic job sequencing was made to improve performance. The problem, quite simply, is that humans are consid- erably slower than computers. Consequently, it is desirable to replace human operation with operating-system software. Automatic job sequencing elimi- nates the need for human setup time and job sequencing.

Even with this arrangement, however, the CPU is often idle. The problem is the speed of the mechanical I/O devices, which are intrinsically slower than electronic devices. Even a slow CPU works in the microsecond range, with thousands of instructions executed per second. A fast card reader, in contrast, might read 1,200 cards per minute (or 20 cards per second). Thus, the difference in speed between the CPU and its I/O devices may be three orders of magnitude ormore.Over time, of course, improvements in technology resulted in faster I/O devices. Unfortunately, CPU speeds increased even faster, so that the problem was not only unresolved but also exacerbated.

**A.2.3 Overlapped I/O**

One common solution to the I/O problem was to replace slow card readers (input devices) and line printers (output devices) with magnetic-tape units. Most computer systems in the late 1950s and early 1960s were batch systems reading from card readers andwriting to line printers or card punches. The CPU did not read directly from cards, however; instead, the cards were first copied onto a magnetic tape via a separate device. When the tape was sufficiently full, it was taken down and carried over to the computer. When a card was needed for input to a program, the equivalent recordwas read from the tape. Similarly, output was written to the tape, and the contents of the tape were printed later. The card readers and line printers were operated **_off-line_**, rather than by the main computer (Figure A.4).

An obvious advantage of off-line operation was that the main computer was no longer constrained by the speed of the card readers and line printers but was limited only by the speed of the much faster magnetic tape units. The technique of using magnetic tape for all I/O could be applied with any

(b)

(a)

CPU

card reader

card reader

line printer

tape drives tape drives line printer

CPU

on-line

on-line

**Figure A.4** Operation of I/O devices (a) on-line and (b) off-line.  

**8 Appendix A Influentia Operating Systems**

similar equipment (such as card readers, card punches, plotters, paper tape, and printers).

The real gain in off-line operation comes from the possibility of using multiple reader-to-tape and tape-to-printer systems for one CPU. If the CPU can process input twice as fast as the reader can read cards, then two readers working simultaneously can produce enough tape to keep the CPU busy. There is a disadvantage, too, however—a longer delay in getting a particular job run. The job must first be read onto tape. Then it must wait until enough additional jobs are readonto the tape to “fill” it. The tapemust then be rewound, unloaded, hand-carried to the CPU, and mounted on a free tape drive. This process is not unreasonable for batch systems, of course. Many similar jobs can be batched onto a tape before it is taken to the computer.

Although off-line preparation of jobs continued for some time, it was quickly replaced in most systems. Disk systems became widely available and greatly improved on off-line operation. One problem with tape systems was that the card reader could not write onto one end of the tape while the CPU read from the other. The entire tape had to be written before it was rewound and read, because tapes are by nature **sequential-access devices**. Disk systems eliminated this problem by being **random-access devices**. Because the head is moved from one area of the disk to another, it can switch rapidly from the area on the disk being used by the card reader to store new cards to the position needed by the CPU to read the “next” card.

In a disk system, cards are read directly from the card reader onto the disk. The location of card images is recorded in a table kept by the operating system. When a job is executed, the operating system satisfies its requests for card- reader input by reading from the disk. Similarly, when the job requests the printer to output a line, that line is copied into a system buffer and is written to the disk. When the job is completed, the output is actually printed. This form of processing is called **spooling** (Figure A.5); the name is an acronym for **s**imultaneous **p**eripheral **o**peration **o**n-**l**ine. Spooling, in essence, uses the disk as a huge buffer for reading as far ahead as possible on input devices and for storing output files until the output devices are able to accept them.

CPU

card reader line printer

disk

I/O

on-line

**Figure A.5** Spooling.  

**A.3 Atlas 9**

Spooling is also used for processing data at remote sites. The CPU sends the data via communication paths to a remote printer (or accepts an entire input job from a remote card reader). The remote processing is done at its own speed, with no CPU intervention. The CPU just needs to be notified when the processing is completed, so that it can spool the next batch of data.

Spooling overlaps the I/O of one job with the computation of other jobs. Even in a simple system, the spooler may be reading the input of one job while printing the output of a different job. During this time, still another job (or other jobs) may be executed, reading its “cards” from disk and “printing” its output lines onto the disk.

Spooling has a direct beneficial effect on the performance of the system. For the cost of some disk space and a few tables, the computation of one job and the I/O of other jobs can take place at the same time. Thus, spooling can keep both the CPU and the I/O devices working at much higher rates. Spooling leads naturally to multiprogramming, which is the foundation of all modern operating systems.

**A.3 Atlas**

The Atlas operating system was designed at the University of Manchester in England in the late 1950s and early 1960s. Many of its basic features that were novel at the time have become standard parts of modern operating systems. Device drivers were a major part of the system. In addition, system calls were added by a set of special instructions called **_extra codes_**.

Atlas was a batch operating system with spooling. Spooling allowed the system to schedule jobs according to the availability of peripheral devices, such as magnetic tape units, paper tape readers, paper tape punches, line printers, card readers, and card punches.

The most remarkable feature of Atlas, however, was its memory manage- ment. **Core memory** was new and expensive at the time. Many computers, like the IBM 650, used a drum for primary memory. The Atlas system used a drum for its main memory, but it had a small amount of core memory that was used as a cache for the drum. Demand pagingwas used to transfer information between core memory and the drum automatically.

The Atlas system used a British computer with 48-bit words. Addresses were 24 bits but were encoded in decimal, which allowed 1 million words to be addressed. At that time, this was an extremely large address space. The physical memory for Atlas was a 98-KB-word drum and 16-KB words of core. Memory was divided into 512-word pages, providing 32 frames in physical memory. An associative memory of 32 registers implemented the mapping from a virtual address to a physical address.

If a page fault occurred, a page-replacement algorithm was invoked. One memory frame was always kept empty, so that a drum transfer could start immediately. The page-replacement algorithm attempted to predict future memory-accessing behavior based on past behavior. A reference bit for each frame was set whenever the frame was accessed. The reference bits were read into memory every 1,024 instructions, and the last 32 values of these bits were retained. This history was used to define the time since the most recent ref-  

**10 Appendix A Influentia Operating Systems**

erence (_t_1) and the interval between the last two references (_t_2). Pages were chosen for replacement in the following order:

**1\.** Any page with _t_1 _\> t_2 + 1 is considered to be no longer in use and is replaced.

**2\.** If _t_1 ≤ _t_2 for all pages, then replace the page with the largest value for _t_2 − _t_1.

The page-replacement algorithm assumes that programs access memory in loops. If the time between the last two references is _t_2, then another reference is expected _t_2 time units later. If a reference does not occur (_t_1 _\> t_2), it is assumed that the page is no longer being used, and the page is replaced. If all pages are still in use, then the page that will not be needed for the longest time is replaced. The time to the next reference is expected to be _t_2 − _t_1.

**A.4 XDS-940**

The XDS-940 operating system was designed at the University of California at Berkeley in the early 1960s. Like the Atlas system, it used paging for memory management. Unlike theAtlas system, it was a time-shared system. The paging was used only for relocation; it was not used for demand paging. The virtual memory of any user processwasmade up of 16-KBwords,whereas the physical memory was made up of 64-KB words. Each page was made up of 2-KB words. The page table was kept in registers. Since physical memory was larger than virtual memory, several user processes could be in memory at the same time. The number of users could be increased by page sharing when the pages contained read-only reentrant code. Processes were kept on a drum and were swapped in and out of memory as necessary.

The XDS-940 system was constructed from a modified XDS-930. The mod- ifications were typical of the changes made to a basic computer to allow an operating system to be written properly. A user-monitor mode was added. Certain instructions, such as I/O and halt, were defined to be privileged. An attempt to execute a privileged instruction in user mode would trap to the operating system.

A system-call instruction was added to the user-mode instruction set. This instructionwas used to create new resources, such as files, allowing the operat- ing system tomanage the physical resources. Files, for example, were allocated in 256-word blocks on the drum. A bitmap was used to manage free drum blocks. Each file had an index block with pointers to the actual data blocks. Index blocks were chained together.

The XDS-940 system also provided system calls to allow processes to cre- ate, start, suspend, and destroy subprocesses. A programmer could construct a system of processes. Separate processes could share memory for communi- cation and synchronization. Process creation defined a tree structure, where a process is the root and its subprocesses are nodes below it in the tree. Each of the subprocesses could, in turn, create more subprocesses.  

**A.6 RC 4000 11**

**A.5 THE**

The THE operating system was designed at the Technische Hogeschool in Eindhoven in the Netherlands in the mid-1960s. It was a batch system running on a Dutch computer, the EL X8, with 32-KB of 27-bit words. The system was mainly noted for its clean design, particularly its layer structure, and its use of a set of concurrent processes employing semaphores for synchronization.

Unlike the processes in the XDS-940 system, the set of processes in the THE system was static. The operating system itself was designed as a set of cooperating processes. In addition, five user processeswere created that served as the active agents to compile, execute, and print user programs. When one job was finished, the process would return to the input queue to select another job.

Apriority CPU-scheduling algorithmwas used. The priorities were recom- puted every 2 seconds and were inversely proportional to the amount of CPU timeused recently (in the last 8 to 10 seconds). This scheme gave higher priority to I/O-bound processes and to new processes.

Memory management was limited by the lack of hardware support. How- ever, since the system was limited and user programs could be written only in Algol, a software paging scheme was used. The Algol compiler automatically generated calls to system routines, which made sure the requested information was in memory, swapping if necessary. The backing store was a 512-KB-word drum. A 512-word page was used, with an LRU page-replacement strategy.

Another major concern of the THE system was deadlock control. The banker’s algorithm was used to provide deadlock avoidance.

Closely related to the THE system is the Venus system. The Venus system was also a layer-structureddesign, using semaphores to synchronize processes. The lower levels of the design were implemented in microcode, however, pro- viding amuch faster system. Paged-segmentedmemorywas used for memory management. In addition, the system was designed as a time-sharing system rather than a batch system.

**A.6 RC 4000**

The RC 4000 system, like the THE system, was notable primarily for its design concepts. It was designed in the late 1960s for the Danish 4000 computer by Regnecentralen, particularly by Brinch-Hansen. The objective was not to design a batch system, or a time-sharing system, or any other specific system. Rather, the goal was to create an operating-system nucleus, or kernel, onwhich a complete operating system could be built. Thus, the system structure was layered, and only the lower levels—comprising the kernel—were provided.

The kernel supported a collection of concurrent processes. A round-robin CPU schedulerwas used. Although processes could sharememory, the primary communication and synchronizationmechanismwas the**message system** pro- vided by the kernel. Processes could communicate with each other by exchang- ing fixed-sized messages of eight words in length. All messages were stored in buffers from a common buffer pool. When a message buffer was no longer required, it was returned to the common pool.  

**12 Appendix A Influentia Operating Systems**

A **message queue** was associated with each process. It contained all the messages that had been sent to that process but had not yet been received. Messages were removed from the queue in FIFO order. The system supported four primitive operations, which were executed atomically:

• send-message (in _receiver,_ in _message,_ out _buffer_)

• wait-message (out _sender,_ out _message,_ out _buffer_)

• send-answer (out _result,_ in _message,_ in _buffer_)

• wait-answer (out _result,_ out _message,_ in _buffer_)

The last two operations allowed processes to exchange several messages at a time.

These primitives required that a process service its message queue in FIFO order and that it block itself while other processes were handling its messages. To remove these restrictions, the developers provided two additional commu- nication primitives that allowed a process to wait for the arrival of the next message or to answer and service its queue in any order:

• wait-event (in _previous-buffer,_ out _next-buffer,_ out _result_)

• get-event (out _buffer_)

I/O devices were also treated as processes. The device drivers were code that converted the device interrupts and registers into messages. Thus, a pro- cess would write to a terminal by sending that terminal a message. The device driver would receive the message and output the character to the terminal. An input character would interrupt the system and transfer to a device driver. The device driver would create a message from the input character and send it to a waiting process.

**A.7 CTSS**

The Compatible Time-Sharing System (CTSS) was designed at MIT as an exper- imental time-sharing system and first appeared in 1961. It was implemented on an IBM 7090 and eventually supported up to 32 interactive users. The users were providedwith a set of interactive commands that allowed them tomanip- ulate files and to compile and run programs through a terminal.

The 7090 had a 32-KB memory made up of 36-bit words. The monitor used 5-KB words, leaving 27 KB for the users. User memory images were swapped between memory and a fast drum. CPU scheduling employed a multilevel- feedback-queue algorithm. The time quantum for level _i_ was 2 ∗ _i_ time units. If a program did not finish its CPU burst in one time quantum, it was moved down to the next level of the queue, giving it twice as much time. The program at the highest level (with the shortest quantum) was run first. The initial level of a programwas determined by its size, so that the time quantumwas at least as long as the swap time.

CTSS was extremely successful and was in use as late as 1972. Although it was limited, it succeeded in demonstrating that time sharing was a con-  

**A.9 IBM OS/360 13**

venient and practical mode of computing. One result of CTSS was increased development of time-sharing systems. Another result was the development of MULTICS.

**A.8 MULTICS**

The MULTICS operating system was designed from 1965 to 1970 at MIT as a natural extension of CTSS. CTSS and other early time-sharing systems were so successful that they created an immediate desire to proceed quickly to bigger and better systems. As larger computers became available, the designers of CTSS set out to create a time-sharing utility. Computing service would be provided like electrical power. Large computer systems would be connected by telephone wires to terminals in offices and homes throughout a city. The operating systemwould be a time-shared system running continuously with a vast file system of shared programs and data.

MULTICS was designed by a team from MIT, GE (which later sold its com- puter department to Honeywell), and Bell Laboratories (which dropped out of the project in 1969). The basic GE 635 computer was modified to a new com- puter system called the GE 645, mainly by the addition of paged-segmentation memory hardware.

In MULTICS, a virtual address was composed of an 18-bit segment number and a 16-bit word offset. The segments were then paged in 1-KB-word pages. The second-chance page-replacement algorithm was used.

The segmented virtual address space wasmerged into the file system; each segment was a file. Segments were addressed by the name of the file. The file system itself was a multilevel tree structure, allowing users to create their own subdirectory structures.

Like CTSS, MULTICS used a multilevel feedback queue for CPU scheduling. Protection was accomplished through an access list associated with each file and a set of protection rings for executing processes. The system, which was written almost entirely in PL/1, comprised about 300,000 lines of code. It was extended to a multiprocessor system, allowing a CPU to be taken out of service for maintenance while the system continued running.

**A.9 IBM OS/360**

The longest line of operating-system development is undoubtedly that of IBM computers. The early IBM computers, such as the IBM 7090 and the IBM 7094, are prime examples of the development of common I/O subroutines, followed by development of a residentmonitor, privileged instructions, memory protec- tion, and simple batch processing. These systems were developed separately, often at independent sites. As a result, IBM was faced with many different computers, with different languages and different system software.

The IBM/360—which first appeared in the mid 1960s—was designed to alter this situation. The IBM/360 was designed as a family of computers span- ning the complete range from small business machines to large scientific machines. Only one set of software would be needed for these systems, which all used the same operating system: OS/360. This arrangement was intended to  

**14 Appendix A Influentia Operating Systems**

reduce maintenance problems for IBM and to allow users to move programs and applications freely from one IBM system to another.

Unfortunately, OS/360 tried to be all things to all people. As a result, it did none of its tasks especially well. The file system included a type field that defined the type of each file, and different file types were defined for fixed-length and variable-length records and for blocked and unblocked files. Contiguous allocationwas used, so the user had to guess the size of each output file. The Job Control Language (JCL) added parameters for every possible option, making it incomprehensible to the average user.

The memory-management routines were hampered by the architecture. Although a base-register addressingmodewas used, the program could access and modify the base register, so that absolute addresses were generated by the CPU. This arrangement prevented dynamic relocation; the programwas bound to physicalmemory at load time. Two separate versions of the operating system were produced: OS/MFT used fixed regions and OS/MVT used variable regions.

The system was written in assembly language by thousands of program- mers, resulting inmillions of lines of code. The operating system itself required large amounts of memory for its code and tables. Operating-system overhead often consumed one-half of the total CPU cycles. Over the years, new versions were released to add new features and to fix errors. However, fixing one error often caused another in some remote part of the system, so that the number of known errors in the system remained fairly constant.

Virtual memory was added to OS/360 with the change to the IBM/370 architecture. The underlying hardware provided a segmented-paged virtual memory. New versions of OS used this hardware in different ways. OS/VS1 created one large virtual address space and ran OS/MFT in that virtualmemory. Thus, the operating system itself was paged, as well as user programs. OS/VS2 Release 1 ran OS/MVT in virtual memory. Finally, OS/VS2 Release 2, which is now called MVS, provided each user with his own virtual memory.

MVS is still basically a batch operating system. The CTSS systemwas run on an IBM 7094, but the developers at MIT decided that the address space of the 360, IBM’s successor to the 7094, was too small for MULTICS, so they switched vendors. IBM then decided to create its own time-sharing system, TSS/360. Like MULTICS, TSS/360 was supposed to be a large, time-shared utility. The basic 360 architecture was modified in the model 67 to provide virtual memory. Several sites purchased the 360/67 in anticipation of TSS/360.

TSS/360 was delayed, however, so other time-sharing systems were devel- oped as temporary systems until TSS/360 was available. A time-sharing option (TSO) was added to OS/360. IBM’s Cambridge Scientific Center developed CMS as a single-user system and CP/67 to provide a virtual machine to run it on.

When TSS/360 was eventually delivered, it was a failure. It was too large and too slow. As a result, no site would switch from its temporary system to TSS/360. Today, time sharing on IBM systems is largely provided either by TSO under MVS or by CMS under CP/67 (renamed VM).

Neither TSS/360 nor MULTICS achieved commercial success. What went wrong? Part of the problem was that these advanced systems were too large and too complex to be understood. Another problem was the assumption that computing power would be available from a large, remote source. Minicom-  

**A.11 CP/M and MS/DOS 15**

puters came along and decreased the need for large monolithic systems. They were followed by workstations and then personal computers, which put com- puting power closer and closer to the end users.

**A.10 TOPS-20**

DEC created many influential computer systems during its history. Probably the most famous operating system associated with DEC is VMS, a popular business-oriented system that is still in use today as OpenVMS, a product of Hewlett-Packard. But perhaps the most influential of DEC’s operating systems was TOPS-20.

TOPS-20 started life as a research project at Bolt, Beranek, and Newman (BBN) around 1970. BBN took the business-oriented DEC PDP-10 computer run- ning TOPS-10, added a hardware memory-paging system to implement virtual memory, and wrote a new operating system for that computer to take advan- tage of the new hardware features. The result was TENEX, a general-purpose time-sharing system. DEC then purchased the rights to TENEX and created a new computer with a built-in hardware pager. The resulting system was the DECSYSTEM-20 and the TOPS-20 operating system.

TOPS-20 had an advanced command-line interpreter that provided help as needed to users. That, in combination with the power of the computer and its reasonable price, made the DECSYSTEM-20 the most popular time-sharing system of its time. In 1984, DEC stopped work on its line of 36-bit PDP-10 computers to concentrate on 32-bit VAX systems running VMS.

**A.11 CP/M and MS/DOS**

Early hobbyist computers were typically built from kits and ran a single pro- gram at a time. The systems evolved into more advanced systems as computer components improved. An early “standard” operating system for these com- puters of the 1970s was **CP/M**, short for Control Program/Monitor, written by Gary Kindall of Digital Research, Inc. CP/M ran primarily on the first “personal computer” CPU, the 8-bit Intel 8080. CP/M originally supported only 64 KB of memory and ran only one program at a time. Of course, it was text-based, with a command interpreter. The command interpreter resembled those in other operating systems of the time, such as the TOPS-10 from DEC.

When IBM entered the personal computer business, it decided to have Bill Gates and company write a new operating system for its 16-bit CPU of choice —the Intel 8086. This operating system, **MS-DOS**, was similar to CP/M but had a richer set of built-in commands, again mostly modeled after TOPS-10. MS-DOS became the most popular personal-computer operating system of its time, starting in 1981 and continuing development until 2000. It supported 640 KB of memory,with the ability to address “extended” and “expanded”memory to get somewhat beyond that limit. It lacked fundamental current operating-system features, however, especially protected memory.  

**16 Appendix A Influentia Operating Systems**

**A.12 Macintosh Operating System and Windows**

With the advent of 16-bit CPUs, operating systems for personal computers could become more advanced, feature rich, and usable. The **Apple Macintosh** computer was arguably the first computer with a GUI designed for home users. It was certainly the most successful for a while, starting at its launch in 1984. It used a mouse for screen pointing and selecting and came with many utility programs that took advantage of the newuser interface. Hard-disk driveswere relatively expensive in 1984, so it came only with a 400-KB-capacity floppy drive by default.

The original Mac OS ran only onApple computers and slowlywas eclipsed by Microsoft Windows (starting with Version 1.0 in 1985), which was licensed to run on many different computers from a multitude of companies. As micro- processor CPUs evolved to 32-bit chips with advanced features, such as pro- tected memory and context switching, these operating systems added features that had previously been found only onmainframes andminicomputers. Over time, personal computers became as powerful as those systems and more use- ful for many purposes. Minicomputers died out, replaced by general- and special-purpose “servers.” Although personal computers continue to increase in capacity and performance, servers tend to stay ahead of them in amount of memory, disk space, and number and speed of available CPUs. Today, servers typically run in data centers or machine rooms, while personal computers sit on or next to desks and talk to each other and servers across a network.

The desktop rivalry between Apple and Microsoft continues today, with new versions of Windows and Mac OS trying to outdo each other in fea- tures, usability, and application functionality. Other operating systems, such as AmigaOS and OS/2, have appeared over time but have not been long-term competitors to the two leading desktop operating systems. Meanwhile, Linux in its many forms continues to gain in popularity among more technical users —and evenwith nontechnical users on systems like the **One Laptop per Child** (**OLPC**) children’s connected computer network (http://laptop.org/).

**A.13 Mach**

The Mach operating system traces its ancestry to the Accent operating sys- tem developed at Carnegie Mellon University (CMU). Mach’s communication system and philosophy are derived from Accent, but many other significant portions of the system (for example, the virtual memory system and task and thread management) were developed from scratch.

Work on Mach began in the mid 1980. The operating system was designed with the following three critical goals in mind:

**1\.** Emulate 4.3 BSD UNIX so that the executable files from a UNIX system can run correctly under Mach.

**2\.** Be a modern operating system that supports many memory models, as well as parallel and distributed computing.

**3\.** Have a kernel that is simpler and easier to modify than 4.3 BSD.  

**A.13 Mach 17**

Mach’s development followed an evolutionary path from BSD UNIX sys- tems.Mach codewas initially developed inside the 4.2 BSD kernel, with BSD ker- nel components replaced by Mach components as the Mach components were completed. The BSD components were updated to 4.3 BSD when that became available. By 1986, the virtual memory and communication subsystems were running on the DEC VAX computer family, including multiprocessor versions of the VAX. Versions for the IBM RT/PC and for SUN 3 workstations followed shortly. Then, 1987 saw the completion of the Encore Multimax and Sequent Balance multiprocessor versions, including task and thread support, as well as the first official releases of the system, Release 0 and Release 1.

Through Release 2, Mach provided compatibility with the corresponding BSD systems by including much of BSD’s code in the kernel. The new features and capabilities of Mach made the kernels in these releases larger than the cor- responding BSD kernels.Mach 3moved the BSD code outside the kernel, leaving a much smaller microkernel. This system implements only basic Mach fea- tures in the kernel; all UNIX-specific code has been evicted to run in user-mode servers. Excluding UNIX-specific code from the kernel allows the replacement of BSD with another operating system or the simultaneous execution of multi- ple operating-system interfaces on top of the microkernel. In addition to BSD, user-mode implementations have beendeveloped forDOS, theMacintosh oper- ating system, and OSF/1. This approach has similarities to the virtual machine concept, but here the virtual machine is defined by software (the Mach kernel interface), rather than by hardware. With Release 3.0, Mach became available on a wide variety of systems, including single-processor SUN, Intel, IBM, and DEC machines and multiprocessor DEC, Sequent, and Encore systems.

Mach was propelled to the forefront of industry attention when the Open Software Foundation (OSF) announced in 1989 that it would use Mach 2.5 as the basis for its new operating system, OSF/1. (Mach 2.5 was also the basis for the operating system on the NeXT workstation, the brainchild of Steve Jobs of Apple Computer fame.) The initial release of OSF/1 occurred a year later, and this system competed with UNIX System V, Release 4, the operating system of choice at that time among UNIX International (UI) members. OSF members included key technological companies such as IBM, DEC, and HP. OSF has since changed its direction, and only DEC UNIX is based on the Mach kernel.

Unlike UNIX, which was developed without regard for multiprocessing, Mach incorporates multiprocessing support throughout. This support is also exceedingly flexible, ranging from shared-memory systems to systemswith no memory shared between processors. Mach uses lightweight processes, in the form of multiple threads of execution within one task (or address space), to support multiprocessing and parallel computation. Its extensive use of mes- sages as the only communication method ensures that protection mechanisms are complete and efficient. By integrating messages with the virtual memory system,Mach also ensures that messages can be handled efficiently. Finally, by having the virtualmemory system usemessages to communicate with the dae- monsmanaging the backing store,Mach provides great flexibility in the design and implementation of these memory-object-managing tasks. By providing low-level, or primitive, system calls from which more complex functions can be built,Mach reduces the size of the kernelwhile permitting operating-system emulation at the user level, much like IBM’s virtual machine systems.  

**18 Appendix A Influentia Operating Systems**

Today, the only remaining pure Mach implementation is in GNU HURD, a little-used operating system. Mach still lives on, however, in XNU—the kernel driving macOSand the iOSvariants. XNU—whose codebase Apple obtained with the acquisition of NeXT and its NeXTSTEP operating system—is a Mach core with a top layer of BSD APIs. Apple continues to support and maintain the Mach APIs (still accessible through specialized system calls known as traps, and via Mach Messages), and the kernel continues evolving with new features to this day.

Some previous editions of **_Operating System Concepts_** included an entire chapter on Mach. This chapter, as it appeared in the fourth edition, is available on the web (http://www.os-book.com).

**A.14 Capability-based Systems—Hydra and CAP**

In this section, we survey two capability-based protection systems. These sys- tems differ in their complexity and in the types of policies that can be imple- mented on them. Neither system is widely used, but both provide interesting proving grounds for protection theories.

**A.14.1 Hydra**

Hydra is a capability-based protection system that provides considerable flex- ibility. The system implements a fixed set of possible access rights, including such basic forms of access as the right to read, write, or execute a memory seg- ment. In addition, a user (of the protection system) can declare other rights. The interpretation of user-defined rights is performed solely by the user’s program, but the system provides access protection for the use of these rights, as well as for the use of system-defined rights. These facilities constitute a significant development in protection technology.

Operations on objects are defined procedurally. The procedures that imple- ment such operations are themselves a form of object, and they are accessed indirectly by capabilities. The names of user-defined procedures must be iden- tified to the protection system if it is to deal with objects of the user-defined type. When the definition of an object is made known to Hydra, the names of operations on the type become **auxiliary rights**. Auxiliary rights can be described in a capability for an instance of the type. For a process to perform an operation on a typed object, the capability it holds for that object must con- tain the name of the operation being invoked among its auxiliary rights. This restriction enables discrimination of access rights to be made on an instance- by-instance and process-by-process basis.

Hydra also provides **rights amplificatio** . This scheme allows a procedure to be certified as **_trustworthy_** to act on a formal parameter of a specified type on behalf of any process that holds a right to execute the procedure. The rights held by a trustworthy procedure are independent of, and may exceed, the rights held by the calling process. However, such a procedure must not be regarded as universally trustworthy (the procedure is not allowed to act on other types, for instance), and the trustworthiness must not be extended to any other procedures or program segments that might be executed by a process.  

**A.14 Capability-based Systems—Hydra and CAP 19**

Amplification allows implementation procedures access to the representa- tion variables of an abstract data type. If a process holds a capability to a typed object _A,_ for instance, this capability may include an auxiliary right to invoke some operation _P_ but does not include any of the so-called kernel rights, such as read, write, or execute, on the segment that represents _A._ Such a capability gives a process a means of indirect access (through the operation _P_) to the representation of _A,_ but only for specific purposes.

When a process invokes the operation _P_ on an object _A,_ however, the capability for access to _A_may be amplified as control passes to the code body of _P._ This amplification may be necessary to allow _P_ the right to access the storage segment representing_A_ so as to implement the operation that _P_ defines on the abstract data type. The code body of _P_ may be allowed to read or to write to the segment of _A_ directly, even though the calling process cannot. On return from _P,_ the capability for _A_ is restored to its original, unamplified state. This case is a typical one in which the rights held by a process for access to a protected segment must change dynamically, depending on the task to be performed. The dynamic adjustment of rights is performed to guarantee consistency of a programmer-defined abstraction. Amplification of rights can be stated explicitly in the declaration of an abstract type to theHydra operating system.

When a user passes an object as an argument to a procedure, we may need to ensure that the procedure cannot modify the object. We can implement this restriction readily by passing an access right that does not have the modifi- cation (write) right. However, if amplification may occur, the right to modify may be reinstated. Thus, the user-protection requirement can be circumvented. In general, of course, a user may trust that a procedure performs its task cor- rectly. This assumption is not always correct, however, because of hardware or software errors. Hydra solves this problem by restricting amplifications.

The procedure-call mechanism of Hydra was designed as a direct solution to the **_problem of mutually suspicious subsystems_**. This problem is defined as follows. Suppose that a program can be invoked as a service by a number of different users (for example, a sort routine, a compiler, a game). When users invoke this service program, they take the risk that the program will malfunc- tion and will either damage the given data or retain some access right to the data to be used (without authority) later. Similarly, the service program may have some private files (for accounting purposes, for example) that should not be accessed directly by the calling user program. Hydra provides mechanisms for directly dealing with this problem.

AHydra subsystem is built on top of its protection kernel and may require protection of its own components. A subsystem interacts with the kernel through calls on a set of kernel-defined primitives that define access rights to resources defined by the subsystem. The subsystem designer can define poli- cies for use of these resources by user processes, but the policies are enforced by use of the standard access protection provided by the capability system.

Programmers can make direct use of the protection system after acquaint- ing themselves with its features in the appropriate reference manual. Hydra provides a large library of system-defined procedures that can be called by user programs. Programmers can explicitly incorporate calls on these system procedures into their program code or can use a program translator that has been interfaced to Hydra.  

**20 Appendix A Influentia Operating Systems**

**A.14.2 Cambridge CAP System**

A different approach to capability-based protection has been taken in the design of the Cambridge CAP system. CAP’s capability system is simpler and superficially less powerful than that of Hydra. However, closer examination shows that it, too, can be used to provide secure protection of user-defined objects. CAP has two kinds of capabilities. The ordinary kind is called a **data capability**. It can be used to provide access to objects, but the only rights pro- vided are the standard read, write, and execute of the individual storage seg- ments associatedwith the object. Data capabilities are interpretedbymicrocode in the CAP machine.

The second kind of capability is the so-called **software capability**, which is protected, but not interpreted, by the CAPmicrocode. It is interpreted by a **_pro- tected_** (that is, privileged) procedure, which may be written by an application programmer as part of a subsystem. A particular kind of rights amplification is associated with a protected procedure. When executing the code body of such a procedure, a process temporarily acquires the right to read or write the contents of a software capability itself. This specific kind of rights amplifica- tion corresponds to an implementation of the seal and unseal primitives on capabilities. Of course, this privilege is still subject to type verification to ensure that only software capabilities for a specified abstract type are passed to any such procedure. Universal trust is not placed in any code other than the CAP machine’s microcode. (See the bibliographical notes at the end of the chapter for references.)

The interpretation of a software capability is left completely to the sub- system, through the protected procedures it contains. This scheme allows a variety of protection policies to be implemented. Although programmers can define their own protected procedures (any of which might be incorrect), the security of the overall system cannot be compromised. The basic protection system will not allow an unverified, user-defined, protected procedure access to any storage segments (or capabilities) that do not belong to the protection environment in which it resides. The most serious consequence of an insecure protected procedure is a protection breakdown of the subsystem for which that procedure has responsibility.

The designers of the CAP system have noted that the use of software capabilities allowed them to realize considerable economies in formulating and implementing protection policies commensurate with the requirements of abstract resources. However, subsystem designers who want to make use of this facility cannot simply study a reference manual, as is the case with Hydra. Instead, they must learn the principles and techniques of protection, since the system provides them with no library of procedures.

**A.15 Other Systems**

There are, of course, other operating systems, and most of them have interest- ing properties. The MCP operating system for the Burroughs computer family was the first to be written in a system programming language. It supported segmentation and multiple CPUs. The SCOPE operating system for the CDC 6600 was also a multi-CPU system. The coordination and synchronization of the multiple processes were surprisingly well designed.  

**Bibliography 21**

History is littered with operating systems that suited a purpose for a time (be it a long or a short time) and then, when faded, were replaced by operating systems that hadmore features, supported newer hardware, were easier to use, or were better marketed. We are sure this trend will continue in the future.

**Further Reading**

Looms and calculators are described in \[Frah (2001)\] and shown graphically in \[Frauenfelder (2005)\].

The Manchester Mark 1 is discussed by \[Rojas and Hashagen (2000)\], and its offspring, the Ferranti Mark 1, is described by \[Ceruzzi (1998)\].

\[Kilburn et al. (1961)\] and \[Howarth et al. (1961)\] examine the Atlas oper- ating system.

The XDS-940 operating system is described by \[Lichtenberger and Pirtle (1965)\].

The THE operating system is covered by \[Dijkstra (1968)\] and by \[McKeag and Wilson (1976)\].

The Venus system is described by \[Liskov (1972)\]. \[Brinch-Hansen (1970)\] and \[Brinch-Hansen (1973)\] discuss the RC 4000

system. The Compatible Time-Sharing System (CTSS) is presented by \[Corbato et al.

(1962)\]. The MULTICS operating system is described by \[Corbato and Vyssotsky

(1965)\] and \[Organick (1972)\]. \[Mealy et al. (1966)\] presented the IBM/360. \[Lett and Konigsford (1968)\]

cover TSS/360. CP/67 is described by \[Meyer and Seawright (1970)\] and \[Parmelee et al.

(1972)\]. DEC VMS is discussed by \[Kenah et al. (1988)\], and TENEX is described by

\[Bobrow et al. (1972)\]. A description of the Apple Macintosh appears in \[Apple (1987)\]. For more

information on these operating systems and their history, see \[Freiberger and Swaine (2000)\].

The Mach operating system and its ancestor, the Accent operating system, are described by \[Rashid and Robertson (1981)\]. Mach’s communication system is covered by \[Rashid (1986)\], \[Tevanian et al. (1989)\], and \[Accetta et al. (1986)\]. The Mach scheduler is described in detail by \[Tevanian et al. (1987a)\] and \[Black (1990)\]. An early version of the Mach shared- memory and memory-mapping system is presented by \[Tevanian et al. (1987b)\]. A good resource describing the Mach project can be found at http://www.cs.cmu.edu/afs/cs/project/mach/public/www/mach.html.

\[McKeag and Wilson (1976)\] discuss the MCP operating system for the Burroughs computer family as well as the SCOPE operating system for the CDC 6600.

The Hydra system was described by \[Wulf et al. (1981)\]. The CAP system was described by \[Needham and Walker (1977)\]. \[Organick (1972)\] discussed the MULTICS ring-protection system.  

**22 Appendix A Influentia Operating Systems**

**Bibliography**

**\[Accetta et al. (1986)\]** M. Accetta, R. Baron, W. Bolosky, D. B. Golub, R. Rashid, A. Tevanian, and M. Young, “Mach: ANew Kernel Foundation for UNIX Devel- opment”, _Proceedings of the Summer USENIX Conference_ (1986), pages 93–112.

**\[Apple (1987)\]** _Apple Technical Introduction to the Macintosh Family_. Addison- Wesley (1987).

**\[Black (1990)\]** D. L. Black, “Scheduling Support for Concurrency and Paral- lelism in the Mach Operating System”, _IEEE Computer_, Volume 23, Number 5 (1990), pages 35–43.

**\[Bobrow et al. (1972)\]** D.G. Bobrow, J. D. Burchfiel, D. L.Murphy, andR. S. Tom- linson, “TENEX, a Paged Time Sharing System for the PDP-10”, _Communications of the ACM_, Volume 15, Number 3 (1972).

**\[Brinch-Hansen (1970)\]** P. Brinch-Hansen, “The Nucleus of a Multiprogram- ming System”, _Communications of the ACM_, Volume 13, Number 4 (1970), pages 238–241 and 250.

**\[Brinch-Hansen (1973)\]** P. Brinch-Hansen, _Operating System Principles_, Prentice Hall (1973).

**\[Ceruzzi (1998)\]** P. E. Ceruzzi, _AHistory of Modern Computing_, MIT Press (1998).

**\[Corbato and Vyssotsky (1965)\]** F. J. Corbato and V. A. Vyssotsky, “Introduction and Overview of the MULTICS System”, _Proceedings of the AFIPS Fall Joint Computer Conference_ (1965), pages 185–196.

**\[Corbato et al. (1962)\]** F. J. Corbato, M. Merwin-Daggett, and R. C. Daley, “An Experimental Time-Sharing System”, _Proceedings of the AFIPS Fall Joint Computer Conference_ (1962), pages 335–344.

**\[Dijkstra (1968)\]** E. W. Dijkstra, “The Structure of the THE Multiprogramming System”, _Communications of the ACM_, Volume 11, Number 5 (1968), pages 341– 346.

**\[Frah (2001)\]** G. Frah, _The Universal History of Computing_, John Wiley and Sons (2001).

**\[Frauenfelder (2005)\]** M. Frauenfelder, _The Computer—An Illustrated History_, Carlton Books (2005).

**\[Freiberger and Swaine (2000)\]** P. Freiberger andM. Swaine, _Fire in the Valley— The Making of the Personal Computer_, McGraw-Hill (2000).

**\[Howarth et al. (1961)\]** D. J. Howarth, R. B. Payne, and F. H. Sumner, “The Manchester University Atlas Operating System, Part II: User’s Description”, _Computer Journal_, Volume 4, Number 3 (1961), pages 226–229.

**\[Kenah et al. (1988)\]** L. J. Kenah, R. E. Goldenberg, and S. F. Bate, _VAX/VMS Internals and Data Structures_, Digital Press (1988).

**\[Kilburn et al. (1961)\]** T. Kilburn, D. J. Howarth, R. B. Payne, and F. H. Sumner, “The Manchester University Atlas Operating System, Part I: Internal Organiza- tion”, _Computer Journal_, Volume 4, Number 3 (1961), pages 222–225.  

**Bibliography 23**

**\[Lett and Konigsford (1968)\]** A. L. Lett and W. L. Konigsford, “TSS/360: A Time-Shared Operating System”, _Proceedings of the AFIPS Fall Joint Computer Conference_ (1968), pages 15–28.

**\[Lichtenberger and Pirtle (1965)\]** W. W. Lichtenberger and M. W. Pirtle, “A Facility for Experimentation in Man-Machine Interaction”, _Proceedings of the AFIPS Fall Joint Computer Conference_ (1965), pages 589–598.

**\[Liskov (1972)\]** B. H. Liskov, “TheDesign of the VenusOperating System”,_Com- munications of the ACM_, Volume 15, Number 3 (1972), pages 144–149.

**\[McKeag and Wilson (1976)\]** R. M. McKeag and R. Wilson, _Studies in Operating Systems_, Academic Press (1976).

**\[Mealy et al. (1966)\]** G. H. Mealy, B. I. Witt, and W. A. Clark, “The Functional Structure of OS/360”, _IBM Systems Journal_, Volume 5, Number 1 (1966), pages 3–11.

**\[Meyer and Seawright (1970)\]** R. A. Meyer and L. H. Seawright, “A Virtual Machine Time-Sharing System”, _IBM Systems Journal_, Volume 9, Number 3 (1970), pages 199–218.

**\[Needham and Walker (1977)\]** R. M. Needham and R. D. H. Walker, “The Cam- bridge CAP Computer and Its Protection System”, _Proceedings of the Sixth Sym- posium on Operating System Principles_ (1977), pages 1–10.

**\[Organick (1972)\]** E. I. Organick, _The Multics System: An Examination of Its Struc- ture_, MIT Press (1972).

**\[Parmelee et al. (1972)\]** R. P. Parmelee, T. I. Peterson, C. C. Tillman, and D. Hat- field, “Virtual Storage and Virtual Machine Concepts”, _IBM Systems Journal_, Volume 11, Number 2 (1972), pages 99–130.

**\[Rashid (1986)\]** R. F. Rashid, “From RIG to Accent to Mach: The Evolution of a Network Operating System”, _Proceedings of the ACM/IEEE Computer Society, Fall Joint Computer Conference_ (1986), pages 1128–1137.

**\[Rashid and Robertson (1981)\]** R. Rashid and G. Robertson, “Accent: A Com- munication-Oriented Network Operating System Kernel”, _Proceedings of the ACM Symposium on Operating System Principles_ (1981), pages 64–75.

**\[Rojas and Hashagen (2000)\]** R. Rojas and U. Hashagen, _The First Computers— History and Architectures_, MIT Press (2000).

**\[Tevanian et al. (1987a)\]** A. Tevanian, Jr., R. F. Rashid, D. B. Golub, D. L. Black, E. Cooper, andM.W. Young, “Mach Threads and the Unix Kernel: The Battle for Control”, _Proceedings of the Summer USENIX Conference_ (1987).

**\[Tevanian et al. (1987b)\]** A. Tevanian, Jr., R. F. Rashid,M.W. Young, D. B. Golub, M. R. Thompson, W. Bolosky, and R. Sanzi, “A UNIX Interface for Shared Memory and Memory Mapped Files Under Mach”, Technical report, Carnegie- Mellon University (1987).

**\[Tevanian et al. (1989)\]** A. Tevanian, Jr., and B. Smith, “Mach: The Model for Future Unix”, _Byte_ (1989).  

**24 Appendix A Influentia Operating Systems**

**\[Wulf et al. (1981)\]** W. A. Wulf, R. Levin, and S. P. Harbison, _Hydra/C.mmp: An Experimental Computer System_, McGraw-Hill (1981).  

_B_**Appendix**

_Windows 7_

**Updated by Dave Probert**

The Microsoft Windows 7 operating system is a 32-/64-bit preemptive mul- titasking client operating system for microprocessors implementing the Intel IA-32 and AMD64 instruction set architectures (ISAs).Microsoft’s corresponding server operating system, Windows Server 2008 R2, is based on the same code as Windows 7 but supports only the 64-bit AMD64 and IA64 (Itanium) ISAs. Windows 7 is the latest in a series of Microsoft operating systems based on its NT code, which replaced the earlier systems based on Windows 95/98. In this appendix, we discuss the key goals of Windows 7, the layered architecture of the system that has made it so easy to use, the file system, the networking features, and the programming interface.

**CHAPTER OBJECTIVES**

• Explore the principles underlying Windows 7’s design and the specific components of the system.

• Provide a detailed discussion of the Windows 7 file system.

• Illustrate the networking protocols supported in Windows 7.

• Describe the interface available in Windows 7 to system and application programmers.

• Describe the important algorithms implemented with Windows 7.

**B.1 History**

In the mid-1980s, Microsoft and IBM cooperated to develop the **OS/2 operating system**, which was written in assembly language for single-processor Intel 80286 systems. In 1988, Microsoft decided to end the joint effort with IBM and develop its own “new technology” (or NT) portable operating system to support both the OS/2 and POSIX application-programming interfaces (APIs). In

**1**  

**2 Appendix B Windows 7**

October 1988, Dave Cutler, the architect of the DEC VAX/VMS operating system, was hired and given the charter of buildingMicrosoft’s new operating system.

Originally, the team planned to use the OS/2 API as NT’s native environ- ment, but during development, NT was changed to use a new 32-bit Windows API (called Win32), based on the popular 16-bit API used in Windows 3.0. The first versions of NT were Windows NT 3.1 and Windows NT 3.1 Advanced Server. (At that time, 16-bit Windows was at Version 3.1.) Windows NT Ver- sion 4.0 adopted the Windows 95 user interface and incorporated Internet web-server andweb-browser software. In addition, user-interface routines and all graphics code were moved into the kernel to improve performance, with the side effect of decreased system reliability. Although previous versions of NT had been ported to other microprocessor architectures, the Windows 2000 version, released in February 2000, supported only Intel (and compatible) processors due to marketplace factors. Windows 2000 incorporated signifi- cant changes. It added Active Directory (an X.500-based directory service), better networking and laptop support, support for plug-and-play devices, a distributed file system, and support for more processors and more memory.

In October 2001, Windows XP was released as both an update to the Win- dows 2000 desktop operating system and a replacement for Windows 95/98. In 2002, the server edition of Windows XP became available (called Windows .Net Server). Windows XP updated the graphical user interface (GUI) with a visual design that took advantage of more recent hardware advances and many new **_ease-of-use features_**. Numerous features were added to automat- ically repair problems in applications and the operating system itself. As a result of these changes, Windows XP provided better networking and device experience (including zero-configuration wireless, instant messaging, stream- ing media, and digital photography/video), dramatic performance improve- ments for both the desktop and largemultiprocessors, and better reliability and security than earlier Windows operating systems.

The long-awaited update to Windows XP, called Windows Vista, was released in November 2006, but it was not well received. Although Win- dows Vista included many improvements that later showed up in Windows 7, these improvements were overshadowed by Windows Vista’s perceived sluggishness and compatibility problems. Microsoft responded to criticisms of Windows Vista by improving its engineering processes and working more closelywith themakers ofWindows hardware and applications. The resultwas **Windows 7**, which was released in October 2009, along with corresponding server editions of Windows. Among the significant engineering changes is the increased use of **execution tracing** rather than counters or profiling to analyze system behavior. Tracing runs constantly in the system, watching hundreds of scenarios execute. When one of these scenarios fails, or when it succeeds but does not perform well, the traces can be analyzed to determine the cause.

Windows 7 uses a client–server architecture (like Mach) to implement two operating-system personalities, Win32 and POSIX, with user-level processes called subsystems. (At one time, Windows also supported an OS/2 subsystem, but it was removed in Windows XP due to the demise of OS/2.) The subsystem architecture allows enhancements to be made to one operating-system person- ality without affecting the application compatibility of the other. Although the POSIX subsystem continues to be available for Windows 7, the Win32 API has become very popular, and the POSIX APIs are used by only a few sites. The sub- system approach continues to be interesting to study from an operating-system  

**B.2 Design Principles 3**

perspective, but machine-virtualization technologies are now becoming the dominant way of running multiple operating systems on a single machine.

Windows 7 is a multiuser operating system, supporting simultaneous access through distributed services or through multiple instances of the GUI via the Windows terminal services. The server editions of Windows 7 support simultaneous terminal server sessions from Windows desktop systems. The desktop editions of terminal server multiplex the keyboard, mouse, and mon- itor between virtual terminal sessions for each logged-on user. This feature, called **_fast user switching_**, allows users to preempt each other at the console of a PC without having to log off and log on.

We noted earlier that some GUI implementation moved into kernel mode in Windows NT 4.0. It started to move into user mode again with Windows Vista, which included the **desktop window manager** (**DWM**) as a user-mode process. DWM implements the desktop compositing ofWindows, providing the Windows**_Aero_** interface look on top of theWindows DirectX graphic software. DirectX continues to run in the kernel, as does the code implementing Win- dows’ previouswindowing and graphicsmodels (Win32k and GDI).Windows 7 made substantial changes to the DWM, significantly reducing its memory footprint and improving its performance.

**Windows XP** was the first version of Windows to ship a 64-bit version (for the IA64 in 2001 and the AMD64 in 2005). Internally, the native NT file system (NTFS) and many of the Win32 APIs have always used 64-bit integers where appropriate—so the major extension to 64-bit in Windows XP was support for large virtual addresses. However, 64-bit editions of Windows also support much larger physical memories. By the time Windows 7 shipped, the AMD64 ISAhad become available on almost all CPUs from both Intel andAMD. In addi- tion, by that time, physical memories on client systems frequently exceeded the 4-GB limit of the IA-32. As a result, the 64-bit version of Windows 7 is now commonly installed on larger client systems. Because the AMD64 architecture supports high-fidelity IA-32 compatibility at the level of individual processes, 32- and 64-bit applications can be freely mixed in a single system.

In the rest of our description ofWindows 7,wewill not distinguish between the client editions of Windows 7 and the corresponding server editions. They are based on the same core components and run the same binary files for the kernel and most drivers. Similarly, although Microsoft ships a variety of different editions of each release to address different market price points, few of the differences between editions are reflected in the core of the system. In this chapter, we focus primarily on the core components of Windows 7.

**B.2 Design Principles**

Microsoft’s design goals for Windows included security, reliability, Windows and POSIX application compatibility, high performance, extensibility, portabil- ity, and international support. Some additional goals, energy efficiency and dynamic device support, have recently been added to this list. Next, we discuss each of these goals and how it is achieved in Windows 7.

**B.2.1 Security**

Windows 7 security goals requiredmore than just adherence to the design stan- dards that had enabled Windows NT 4.0 to receive a C2 security classification  

**4 Appendix B Windows 7**

from the U.S. government. (A C2 classification signifies a moderate level of protection from defective software and malicious attacks. Classifications were defined by the Department of Defense Trusted Computer System Evaluation Criteria, also known as the **Orange Book**.) Extensive code review and testing were combined with sophisticated automatic analysis tools to identify and investigate potential defects that might represent security vulnerabilities.

Windows bases security on discretionary access controls. System objects, including files, registry settings, and kernel objects, are protected by **access- control lists** (**ACLs**) (see Section 13.4.2). ACLs are vulnerable to user and pro- grammer errors, however, as well as to the most common attacks on consumer systems, in which the user is tricked into running code, often while browsing the web. Windows 7 includes a mechanism called **integrity levels** that acts as a rudimentary **_capability_** system for controlling access. Objects and processes are marked as having low, medium, or high integrity. Windows does not allow a process to modify an object with a higher integrity level, no matter what the setting of the ACL.

Other security measures include **address-space layout randomization** (**ASLR**), nonexecutable stacks and heaps, and encryption and **digital signature** facilities. ASLR thwarts many forms of attack by preventing small amounts of injected code from jumping easily to code that is already loaded in a process as part of normal operation. This safeguard makes it likely that a system under attack will fail or crash rather than let the attacking code take control.

Recent chips from both Intel and AMD are based on the AMD64 architec- ture, which allows memory pages to be marked so that they cannot contain executable instruction code. Windows tries to mark stacks and memory heaps so that they cannot be used to execute code, thus preventing attacks in which a program bug allows a buffer to overflow and then is tricked into executing the contents of the buffer. This technique cannot be applied to all programs, because some rely on modifying data and executing it. A column labeled “data execution prevention” in the Windows task manager shows which processes are marked to prevent these attacks.

Windows uses encryption as part of common protocols, such as those used to communicate securely with websites. Encryption is also used to protect user files stored on disk from prying eyes. Windows 7 allows users to easily encrypt virtually awhole disk, aswell as removable storagedevices such as USB flash drives, with a feature called BitLocker. If a computer with an encrypted disk is stolen, the thieves will need very sophisticated technology (such as an electron microscope) to gain access to any of the computer’s files. Windows uses digital signatures to **_sign_** operating system binaries so it can verify that the files were produced byMicrosoft or another known company. In some editions of Windows, a **code integrity** module is activated at boot to ensure that all the loaded modules in the kernel have valid signatures, assuring that they have not been tampered with by an off-line attack.

**B.2.2 Reliability**

Windows matured greatly as an operating system in its first ten years, leading toWindows 2000. At the same time, its reliability increased due to such factors as maturity in the source code, extensive stress testing of the system, improved CPU architectures, and automatic detection of many serious errors in drivers from both Microsoft and third parties. Windows has subsequently extended  

**B.2 Design Principles 5**

the tools for achieving reliability to include automatic analysis of source code for errors, tests that include providing invalid or unexpected input parameters (known as **fuzzing**) to detect validation failures, and an application version of the driver verifier that applies dynamic checking for an extensive set of com- mon user-mode programming errors. Other improvements in reliability have resulted frommovingmore code out of the kernel and into user-mode services. Windows provides extensive support for writing drivers in user mode. System facilities that were once in the kernel and are now in user mode include the Desktop Window Manager and much of the software stack for audio.

One of themost significant improvements in theWindows experience came from adding memory diagnostics as an option at boot time. This addition is especially valuable because so few consumer PCs have error-correcting mem- ory. When bad RAM starts to drop bits here and there, the result is frustratingly erratic behavior in the system. The availability of memory diagnostics has greatly reduced the stress levels of users with bad RAM.

Windows 7 introduced a fault-tolerantmemory heap. The heap learns from application crashes and automatically inserts mitigations into future execution of an application that has crashed. This makes the application more reliable even if it contains common bugs such as using memory after freeing it or accessing past the end of the allocation.

Achieving high reliability in Windows is particularly challenging because almost one billion computers run Windows. Even reliability problems that affect only a small percentage of users still impact tremendous numbers of human beings. The complexity of the Windows ecosystem also adds to the challenges.Millions of instances of applications, drivers, and other software are being constantly downloaded and run on Windows systems. Of course, there is also a constant stream of malware attacks. As Windows itself has become harder to attack directly, exploits increasingly target popular applications.

To copewith these challenges,Microsoft is increasingly relying on commu- nications from customer machines to collect large amounts of data from the ecosystem. Machines can be sampled to see how they are performing, what software they are running, and what problems they are encountering. Cus- tomers can send data to Microsoft when systems or software crashes or hangs. This constant stream of data from customer machines is collected very care- fully, with the users’ consent and without invading privacy. The result is that Microsoft is building an ever-improving picture of what is happening in the Windows ecosystem that allows continuous improvements through software updates, as well as providing data to guide future releases of Windows.

**B.2.3 Windows and POSIX Application Compatibility**

As mentioned, Windows XP was both an update of Windows 2000 and a replacement forWindows 95/98.Windows 2000 focused primarily on compat- ibility for business applications. The requirements for Windows XP included a much greater compatibility with the consumer applications that ran on Win- dows 95/98. Application compatibility is difficult to achieve because many applications check for a particular version of Windows, may depend to some extent on the quirks of the implementation of APIs, may have latent application bugs that were masked in the previous system, and so forth. Applications may  

**6 Appendix B Windows 7**

also have been compiled for a different instruction set. Windows 7 implements several strategies to run applications despite incompatibilities.

Like Windows XP, Windows 7 has a compatibility layer that sits between applications and the Win32 APIs. This layer makes Windows 7 look (almost) bug-for-bug compatible with previous versions of Windows. Windows 7, like earlier NT releases, maintains support for running many 16-bit applications using a **_thunking_**, or conversion, layer that translates 16-bit API calls into equivalent 32-bit calls. Similarly, the 64-bit version of Windows 7 provides a thunking layer that translates 32-bit API calls into native 64-bit calls.

TheWindows subsystemmodel allows multiple operating-system person- alities to be supported.As noted earlier, although theAPImost commonly used with Windows is the Win32 API, some editions of Windows 7 support a POSIX subsystem. POSIX is a standard specification for UNIX that allowsmost available UNIX-compatible software to compile and run without modification.

As a final compatibility measure, several editions of Windows 7 provide a virtual machine that runs Windows XP insideWindows 7. This allows applica- tions to get bug-for-bug compatibility with Windows XP.

**B.2.4 High Performance**

Windows was designed to provide high performance on desktop systems (which are largely constrained by I/O performance), server systems (where the CPU is often the bottleneck), and large multithreaded andmultiprocessor envi- ronments (where locking performance and cache-line management are keys to scalability). To satisfy performance requirements, NT used a variety of tech- niques, such as asynchronous I/O, optimized protocols for networks, kernel- based graphics rendering, and sophisticated caching of file-system data. The memory-management and synchronization algorithms were designed with an awareness of the performance considerations related to cache lines and multi- processors.

Windows NT was designed for symmetrical multiprocessing (SMP); on a multiprocessor computer, several threads can run at the same time, even in the kernel. On each CPU, Windows NT uses priority-based preemptive scheduling of threads. Except while executing in the kernel dispatcher or at interrupt level, threads in any process running inWindows can be preempted by higher- priority threads. Thus, the system responds quickly (see Chapter 5).

The subsystems that constitute Windows NT communicate with one another efficiently through a **local procedure call** (**LPC**) facility that provides high-performance message passing. When a thread requests a synchronous service from another process through an LPC, the servicing thread is marked **_ready_**, and its priority is temporarily boosted to avoid the scheduling delays that would occur if it had to wait for threads already in the queue.

Windows XP further improved performance by reducing the code-path length in critical functions, using better algorithms and per-processor data structures, using memory coloring for **non-uniform memory access** (**NUMA**) machines, and implementing more scalable locking protocols, such as queued spinlocks. The new locking protocols helped reduce system bus cycles and included lock-free lists and queues, atomic read–modify–write operations (like interlocked increment), and other advanced synchronization techniques.  

**B.2 Design Principles 7**

By the time Windows 7 was developed, several major changes had come to computing. Client/server computing had increased in importance, so an advanced local procedure call (ALPC) facility was introduced to provide higher performance and more reliability than LPC. The number of CPUs and the amount of physical memory available in the largest multiprocessors had increased substantially, so quite a lot of effort was put into improving operating-system scalability.

The implementation of SMP in Windows NT used bitmasks to represent collections of processors and to identify, for example, which set of processors a particular thread could be scheduled on. These bitmaskswere defined as fitting within a single word of memory, limiting the number of processors supported within a system to 64. Windows 7 added the concept of **processor groups** to represent arbitrary numbers of CPUs, thus accommodating more CPU cores. The number of CPU cores within single systems has continued to increase not only because of more cores but also because of cores that support more than one logical thread of execution at a time.

All these additional CPUs created a great deal of contention for the locks used for scheduling CPUs andmemory.Windows 7 broke these locks apart. For example, before Windows 7, a single lock was used by theWindows scheduler to synchronize access to the queues containing threads waiting for events. In Windows 7, each object has its own lock, allowing the queues to be accessed concurrently. Also, many execution paths in the scheduler were rewritten to be lock-free. This change resulted in good scalability performance for Windows even on systems with 256 hardware threads.

Other changes are due to the increasing importance of support for par- allel computing. For years, the computer industry has been dominated by Moore’s Law, leading to higher densities of transistors that manifest them- selves as faster clock rates for each CPU. Moore’s Law continues to hold true, but limits have been reached that prevent CPU clock rates from increasing further. Instead, transistors are being used to build more and more CPUs into each chip. New programmingmodels for achieving parallel execution, such as Microsoft’s Concurrency RunTime (ConcRT) and Intel’s Threading Building Blocks (TBB), are being used to express parallelism in C++ programs. Where Moore’s Law has governed computing for forty years, it now seems that Amdahl’s Law, which governs parallel computing, will rule the future.

To support task-based parallelism, Windows 7 provides a new form of **user-mode scheduling** (**UMS**). UMS allows programs to be decomposed into tasks, and the tasks are then scheduled on the available CPUs by a scheduler that operates in user mode rather than in the kernel.

The advent of multiple CPUs on the smallest computers is only part of the shift taking place to parallel computing. Graphics processing units (GPUs) accelerate the computational algorithms needed for graphics by using **SIMD** architectures to execute a single instruction for multiple data at the same time. This has given rise to the use of GPUs for general computing, not just graphics. Operating-system support for software like OpenCL and CUDA is allowing programs to take advantage of the GPUs. Windows supports use of GPUs through software in its DirectX graphics support. This software, called DirectCompute, allows programs to specify **computational kernels** using the same HLSL (high-level shader language) programmingmodel used to program the SIMD hardware for **graphics shaders**. The computational kernels run very  

**8 Appendix B Windows 7**

quickly on the GPU and return their results to the main computation running on the CPU.

**B.2.5 Extensibility**

**Extensibility** refers to the capacity of an operating system to keep up with advances in computing technology. To facilitate change over time, the devel- opers implementedWindows using a layered architecture. TheWindows exec- utive runs in kernel mode and provides the basic system services and abstrac- tions that support shared use of the system. On top of the executive, several server subsystems operate in usermode. Among them are **environmental sub- systems** that emulate different operating systems. Thus, programs written for the Win32 APIs and POSIX all run onWindows in the appropriate environment. Because of the modular structure, additional environmental subsystems can be added without affecting the executive. In addition, Windows uses loadable drivers in the I/O system, so new file systems, new kinds of I/O devices, and new kinds of networking can be added while the system is running. Windows uses a client–server model like the Mach operating system and supports dis- tributed processing by **remote procedure calls** (**RPCs**) as defined by the Open Software Foundation.

**B.2.6 Portability**

An operating system is **portable** if it can be moved from one CPU architec- ture to another with few changes. Windows was designed to be portable. Like the UNIX operating system, Windows is written primarily in C and C++. The architecture-specific source code is relatively small, and there is very little use of assembly code. Porting Windows to a new architecture mostly affects the Windows kernel, since the user-mode code in Windows is almost exclu- sively written to be architecture independent. To port Windows, the kernel’s architecture-specific code must be ported, and sometimes conditional compi- lation is needed in other parts of the kernel because of changes in major data structures, such as the page-table format. The entire Windows system must then be recompiled for the new CPU instruction set.

Operating systems are sensitive not only to CPU architecture but also to CPU support chips and hardware boot programs. The CPU and support chips are collectively known as a **chipset**. These chipsets and the associated boot code determine how interrupts are delivered, describe the physical characteristics of each system, and provide interfaces to deeper aspects of the CPU architecture, such as error recovery and power management. It would be burdensome to have to port Windows to each type of support chip as well as to each CPU architecture. Instead, Windows isolates most of the chipset-dependent code in a dynamic link library (DLL), called the **hardware-abstraction layer** (**HAL**), that is loaded with the kernel. The Windows kernel depends on the HAL interfaces rather than on the underlying chipset details. This allows the single set of kernel anddriver binaries for a particular CPU to be usedwith different chipsets simply by loading a different version of the HAL.

Over the years, Windows has been ported to a number of different CPU architectures: Intel IA-32-compatible 32-bit CPUs, AMD64-compatible and IA64 64-bit CPUs, the DEC Alpha, and the MIPS and PowerPC CPUs. Most of these CPU architectures failed in the market. When Windows 7 shipped, only the IA-  

**B.2 Design Principles 9**

32 and AMD64 architectures were supported on client computers, along with AMD64 and IA64 on servers.

**B.2.7 International Support**

Windows was designed for international and multinational use. It provides support for different locales via the **national-language-support** (**NLS**) API. The NLS API provides specialized routines to format dates, time, and money in accordance with national customs. String comparisons are specialized to account for varying character sets. UNICODE is Windows’s native character code. Windows supports ANSI characters by converting them to UNICODE characters before manipulating them (8-bit to 16-bit conversion). System text strings are kept in resource files that can be replaced to localize the system for different languages. Multiple locales can be used concurrently, which is important to multilingual individuals and businesses.

**B.2.8 Energy Efficiency**

Increasing energy efficiency for computers causes batteries to last longer for laptops and netbooks, saves significant operating costs for power and cooling of data centers, and contributes to green initiatives aimed at lowering energy consumption by businesses and consumers. For some time, Windows has implemented several strategies for decreasing energy use. The CPUs aremoved to lower power states—for example, by lowering clock frequency—whenever possible. In addition, when a computer is not being actively used, Windows may put the entire computer into a low-power state (sleep) or may even save all of memory to disk and shut the computer off (hibernation). When the user returns, the computer powers up and continues from its previous state, so the user does not need to reboot and restart applications.

Windows 7 added some new strategies for saving energy. The longer a CPU can stay unused, themore energy can be saved. Because computers are somuch faster than human beings, a lot of energy can be saved just while humans are thinking. The problem is that too many programs are constantly polling to see what is happening in the system. A swarm of software timers are firing, keeping the CPU from staying idle long enough to savemuch energy.Windows 7 extends CPU idle time by skipping clock ticks, coalescing software timers into smaller numbers of events, and “parking” entire CPUs when systems are not heavily loaded.

**B.2.9 Dynamic Device Support**

Early in the history of the PC industry, computer configurations were fairly static. Occasionally, new devices might be plugged into the serial, printer, or game ports on the back of a computer, but that was it. The next steps toward dynamic configuration of PCs were laptop docks and PCMIA cards. A PC could suddenly be connected to or disconnected from a whole set of peripherals. In a contemporary PC, the situation has completely changed. PCs are designed to let users to plug and unplug a huge host of peripherals all the time; external disks, thumb drives, cameras, and the like are constantly coming and going.

Support for dynamic configuration of devices is continually evolving in Windows. The system can automatically recognize devices when they are  

**10 Appendix B Windows 7**

OS/2 applications

OS/2 subsystem

Win16 applications

MS-DOS applications

Win18 VDM

window manager

user mode

file system

I/O manager

MS-DOS VDM

Win32 subsystem

POSIX subsystem

logon process

security subsystem

authentication package

security account manager database

Win32 applications

POSIX applications

graphic device drivers

kernel

executive

hardware abstraction layer

hardware

cache manager

device drivers

network drivers

object manager

security reference monitor

process manager

plug and play

manager

virtual memory manager

local procedure

call facility

**Figure B.1** Windows block diagram.

plugged in and can find, install, and load the appropriate drivers—oftenwith- out user intervention. When devices are unplugged, the drivers automatically unload, and system execution continues without disrupting other software.

**B.3 System Components**

The architecture of Windows is a layered system of modules, as shown in Fig- ure B.1. The main layers are the HAL, the kernel, and the executive, all of which run in kernelmode, and a collection of subsystems and services that run in user mode. The user-mode subsystems fall into two categories: the environmental subsystems, which emulate different operating systems, and the **protection subsystems**, which provide security functions. One of the chief advantages of this type of architecture is that interactions between modules are kept simple. The remainder of this section describes these layers and subsystems.

**B.3.1 Hardware-Abstraction Layer**

The HAL is the layer of software that hides hardware chipset differences from upper levels of the operating system. The HAL exports a virtual hard- ware interface that is used by the kernel dispatcher, the executive, and the device drivers. Only a single version of each device driver is required for  

**B.3 System Components 11**

each CPU architecture, no matter what support chips might be present. Device drivers map devices and access them directly, but the chipset-specific details of mapping memory, configuring I/O buses, setting up DMA, and coping with motherboard-specific facilities are all provided by the HAL interfaces.

**B.3.2 Kernel**

The kernel layer ofWindows has fourmain responsibilities: thread scheduling, low-level processor synchronization, interrupt and exception handling, and switching between user mode and kernel mode. The kernel is implemented in the C language, using assembly language only where absolutely necessary to interface with the lowest level of the hardware architecture.

The kernel is organized according to object-oriented design principles. An **object type** inWindows is a system-defineddata type that has a set of attributes (data values) and a set of methods (for example, functions or operations). An **object** is an instance of an object type. The kernel performs its job by using a set of kernel objects whose attributes store the kernel data and whose methods perform the kernel activities.

**B.3.2.1 Kernel Dispatcher**

The kernel dispatcher provides the foundation for the executive and the sub- systems. Most of the dispatcher is never paged out of memory, and its execu- tion is never preempted. Its main responsibilities are thread scheduling and context switching, implementation of synchronization primitives, timer man- agement, software interrupts (asynchronous and deferred procedure calls), and exception dispatching.

**B.3.2.2 Threads and Scheduling**

Like many other modern operating systems, Windows uses processes and threads for executable code. Each process has one or more threads, and each threadhas its own scheduling state, including actual priority, processor affinity, and CPU usage information.

There are six possible thread states: ready, standby, running, waiting, transition, and terminated. Ready indicates that the thread is waiting to run. The highest-priority ready thread is moved to the standby state, which means it is the next thread to run. In a multiprocessor system, each processor keeps one thread in a standby state. A thread is running when it is executing on a processor. It runs until it is preempted by a higher-priority thread, until it terminates, until its allotted execution time (quantum) ends, or until it waits on a dispatcher object, such as an event signaling I/O completion. A thread is in the waiting state when it is waiting for a dispatcher object to be signaled. A thread is in the transition state while it waits for resources necessary for execution; for example, it may be waiting for its kernel stack to be swapped in from disk. A thread enters the terminated state when it finishes execution.

The dispatcher uses a 32-level priority scheme to determine the order of thread execution. Priorities are divided into two classes: variable class and real- time class. The variable class contains threads having priorities from 1 to 15, and the real-time class contains threads with priorities ranging from 16 to 31.  

**12 Appendix B Windows 7**

The dispatcher uses a queue for each scheduling priority and traverses the set of queues from highest to lowest until it finds a thread that is ready to run. If a thread has a particular processor affinity but that processor is not available, the dispatcher skips past it and continues looking for a ready thread that is willing to run on the available processor. If no ready thread is found, the dispatcher executes a special thread called the **_idle thread_**. Priority class 0 is reserved for the idle thread.

When a thread’s time quantum runs out, the clock interrupt queues a quantum-end **deferred procedure call** (**DPC**) to the processor. Queuing the DPC results in a software interrupt when the processor returns to normal interrupt priority. The software interrupt causes the dispatcher to reschedule the processor to execute the next available thread at the preempted thread’s priority level.

The priority of the preempted thread may be modified before it is placed back on the dispatcher queues. If the preempted thread is in the variable- priority class, its priority is lowered. The priority is never lowered below the base priority. Lowering the thread’s priority tends to limit the CPU consump- tion of compute-bound threads versus I/O-bound threads. When a variable- priority thread is released from a wait operation, the dispatcher boosts the priority. The amount of the boost depends on the device for which the thread was waiting. For example, a thread waiting for keyboard I/O would get a large priority increase, whereas a thread waiting for a disk operation would get a moderate one. This strategy tends to give good response times to interactive threads using amouse andwindows. It also enables I/O-bound threads to keep the I/O devices busy while permitting compute-bound threads to use spare CPU cycles in the background. In addition, the thread associatedwith the user’s active GUI window receives a priority boost to enhance its response time.

Scheduling occurs when a thread enters the ready or wait state, when a thread terminates, or when an application changes a thread’s priority or pro- cessor affinity. If a higher-priority thread becomes readywhile a lower-priority thread is running, the lower-priority thread is preempted. This preemption gives the higher-priority thread preferential access to the CPU. Windows is not a hard real-time operating system, however, because it does not guarantee that a real-time thread will start to execute within a particular time limit; threads are blocked indefinitely while DPCs and **interrupt service routines** (**ISRs**) are running (as discussed further below).

Traditionally, operating-system schedulers used sampling to measure CPU utilization by threads. The system timer would fire periodically, and the timer interrupt handler would take note of what threadwas currently scheduled and whether it was executing in user or kernel mode when the interrupt occurred. This sampling technique was necessary because either the CPU did not have a high-resolution clock or the clock was too expensive or unreliable to access frequently. Although efficient, sampling was inaccurate and led to anomalies such as incorporating interrupt servicing time as thread time and dispatching threads that had run for only a fraction of the quantum. StartingwithWindows Vista, CPU time in Windows has been tracked using the hardware **timestamp counter** (**TSC**) included in recent processors. Using the TSC results in more accurate accounting of CPU usage, and the scheduler will not preempt threads before they have run for a full quantum.  

**B.3 System Components 13**

**B.3.2.3 Implementation of Synchronization Primitives**

Key operating-system data structures are managed as objects using common facilities for allocation, reference counting, and security. **Dispatcher objects** control dispatching and synchronization in the system. Examples of these objects include the following:

• The **event object** is used to record an event occurrence and to synchronize this occurrence with some action. Notification events signal all waiting threads, and synchronization events signal a single waiting thread.

• The **mutant** provides kernel-mode or user-mode mutual exclusion associ- ated with the notion of ownership.

• The **mutex**, available only in kernel mode, provides deadlock-free mutual exclusion.

• The **semaphore object** acts as a counter or gate to control the number of threads that access a resource.

• The **thread object** is the entity that is scheduled by the kernel dispatcher. It is associated with a **process object**, which encapsulates a virtual address space. The thread object is signaled when the thread exits, and the process object, when the process exits.

• The **timer object** is used to keep track of time and to signal timeouts when operations take too long and need to be interrupted or when a periodic activity needs to be scheduled.

Many of the dispatcher objects are accessed from user mode via an open operation that returns a handle. The user-mode code polls or waits on handles to synchronize with other threads as well as with the operating system (see Section B.7.1).

**B.3.2.4 Software Interrupts: Asynchronous and Deferred Procedure Calls**

The dispatcher implements two types of software interrupts: **asynchronous procedure calls** (**APCs**) and deferred procedure calls (DPCs, mentioned earlier). An asynchronous procedure call breaks into an executing thread and calls a procedure. APCs are used to begin execution of new threads, suspend or resume existing threads, terminate threads or processes, deliver notification that an asynchronous I/O has completed, and extract the contents of the CPU registers from a running thread. APCs are queued to specific threads and allow the system to execute both system and user code within a process’s context. User-mode execution of an APC cannot occur at arbitrary times, but only when the thread is waiting in the kernel and marked **_alertable_**.

DPCsare used to postpone interrupt processing. After handling all urgent device-interrupt processing, the ISR schedules the remaining processing by queuing a DPC. The associated software interruptwill not occur until the CPU is next at a priority lower than the priority of all I/O device interrupts but higher than the priority at which threads run. Thus, DPCs do not block other device ISRs. In addition to deferring device-interrupt processing, the dispatcher uses  

**14 Appendix B Windows 7**

DPCs to process timer expirations and to preempt thread execution at the end of the scheduling quantum.

Execution of DPCs prevents threads from being scheduled on the current processor and also keeps APCs from signaling the completion of I/O. This is done so that completion of DPC routines does not take an extended amount of time. As an alternative, the dispatcher maintains a pool of worker threads. ISRs and DPCs may queue work items to the worker threads where they will be executed using normal thread scheduling. DPC routines are restricted so that they cannot take page faults (be paged out of memory), call system services, or take any other action that might result in an attempt to wait for a dispatcher object to be signaled. Unlike APCs, DPC routines make no assumptions about what process context the processor is executing.

**B.3.2.5 Exceptions and Interrupts**

The kernel dispatcher also provides trap handling for exceptions and interrupts generated by hardware or software. Windows defines several architecture-independent exceptions, including:

• Memory-access violation

• Integer overflow

• Floating-point overflow or underflow

• Integer divide by zero

• Floating-point divide by zero

• Illegal instruction

• Data misalignment

• Privileged instruction

• Page-read error

• Access violation

• Paging file quota exceeded

• Debugger breakpoint

• Debugger single step

The trap handlers deal with simple exceptions. Elaborate exception handling is performed by the kernel’s exception dispatcher. The **exception dispatcher** creates an exception record containing the reason for the exception and finds an exception handler to deal with it.

When an exception occurs in kernelmode, the exception dispatcher simply calls a routine to locate the exception handler. If no handler is found, a fatal system error occurs, and the user is left with the infamous “blue screen of death” that signifies system failure.

Exception handling is more complex for user-mode processes, because an environmental subsystem (such as the POSIX system) sets up a debugger port and an exception port for every process it creates. (For details on ports,  

**B.3 System Components 15**

see Section B.3.3.4.) If a debugger port is registered, the exception handler sends the exception to the port. If the debugger port is not found or does not handle that exception, the dispatcher attempts to find an appropriate exception handler. If no handler is found, the debugger is called again to catch the error for debugging. If no debugger is running, a message is sent to the process’s exception port to give the environmental subsystem a chance to translate the exception. For example, the POSIX environment translates Windows exception messages into POSIX signals before sending them to the thread that caused the exception. Finally, if nothing else works, the kernel simply terminates the process containing the thread that caused the exception.

WhenWindows fails to handle an exception, it may construct a description of the error that occurred and request permission from the user to send the information back to Microsoft for further analysis. In some cases, Microsoft’s automated analysis may be able to recognize the error immediately and sug- gest a fix or workaround.

The interrupt dispatcher in the kernel handles interrupts by calling either an interrupt service routine (ISR) supplied by a device driver or a kernel trap- handler routine. The interrupt is represented by an **interrupt object** that con- tains all the information needed to handle the interrupt. Using an interrupt object makes it easy to associate interrupt-service routines with an interrupt without having to access the interrupt hardware directly.

Different processor architectures have different types and numbers of inter- rupts. For portability, the interrupt dispatcher maps the hardware interrupts into a standard set. The interrupts are prioritized and are serviced in prior- ity order. There are 32 interrupt request levels (IRQLs) in Windows. Eight are reserved for use by the kernel; the remaining 24 represent hardware interrupts via theHAL(althoughmost IA-32 systemsuse only 16). TheWindows interrupts are defined in Figure B.2.

The kernel uses an **interrupt-dispatch table** to bind each interrupt level to a service routine. In a multiprocessor computer, Windows keeps a separate interrupt-dispatch table (IDT) for each processor, and each processor’s IRQL can be set independently to mask out interrupts. All interrupts that occur at a level equal to or less than the IRQLof a processor are blocked until the IRQL is lowered

interrupt levels types of interrupts

31

30

29

machine check or bus error

power fail

clock (used to keep track of time)

profile

traditional PC IRQ hardware interrupts

dispatch and deferred procedure call (DPC) (kernel)

asynchronous procedure call (APC)

passive

28

27

3–26

2

1

0

interprocessor notification (request another processor to act; e.g., dispatch a process or update the TLB)

**Figure B.2** Windows interrupt-request levels.  

**16 Appendix B Windows 7**

by a kernel-level thread or by an ISR returning from interrupt processing. Windows takes advantage of this property and uses software interrupts to deliver APCs and DPCs, to perform system functions such as synchronizing threads with I/O completion, to start thread execution, and to handle timers.

**B.3.2.6 Switching between User-Mode and Kernel-Mode Threads**

What the programmer thinks of as a thread in traditional Windows is actually two threads: a **user-mode thread** (**UT**) and a **kernel-mode thread** (**KT**). Each has its own stack, register values, and execution context. A UT requests a system service by executing an instruction that causes a trap to kernel mode. The kernel layer runs a trap handler that switches between the UT and the corresponding KT. When a KT has completed its kernel execution and is ready to switch back to the corresponding UT, the kernel layer is called to make the switch to the UT, which continues its execution in user mode.

Windows 7 modifies the behavior of the kernel layer to support user- mode scheduling of the UTs. User-mode schedulers in Windows 7 support cooperative scheduling. A UT can explicitly yield to another UT by calling the user-mode scheduler; it is not necessary to enter the kernel. User-mode scheduling is explained in more detail in Section B.7.3.7.

**B.3.3 Executive**

The Windows executive provides a set of services that all environmental sub- systems use. The services are grouped as follows: object manager, virtual memory manager, process manager, advanced local procedure call facility, I/O manager, cachemanager, security referencemonitor, plug-and-play and power managers, registry, and booting.

**B.3.3.1 Object Manager**

For managing kernel-mode entities, Windows uses a generic set of interfaces that are manipulated by user-mode programs. Windows calls these entities **_objects_**, and the executive component that manipulates them is the **object manager**. Examples of objects are semaphores, mutexes, events, processes, and threads; all these are **_dispatcher objects_**. Threads can block in the ker- nel dispatcher waiting for any of these objects to be signaled. The process, thread, and virtual memory APIs use process and thread handles to identify the process or thread to be operated on. Other examples of objects include files, sections, ports, and various internal I/O objects. File objects are used to maintain the open state of files and devices. Sections are used to map files. Local-communication endpoints are implemented as port objects.

User-mode code accesses these objects using an opaque value called a **handle**, which is returned by many APIs. Each process has a **handle table** containing entries that track the objects used by the process. The **system pro- cess**, which contains the kernel, has its own handle table, which is protected from user code. The handle tables in Windows are represented by a tree struc- ture, which can expand from holding 1,024 handles to holding over 16 million. Kernel-mode code can access an object by using either a handle or a **referenced pointer**.  

**B.3 System Components 17**

Aprocess gets a handle by creating an object, by opening an existing object, by receiving a duplicated handle from another process, or by inheriting a handle from the parent process. When a process exits, all its open handles are implicitly closed. Since the object manager is the only entity that generates object handles, it is the natural place to check security. The object manager checks whether a process has the right to access an object when the process tries to open the object. The object manager also enforces quotas, such as the maximum amount of memory a process may use, by charging a process for the memory occupied by all its referenced objects and refusing to allocate more memory when the accumulated charges exceed the process’s quota.

The object manager keeps track of two counts for each object: the number of handles for the object and the number of referenced pointers. The handle count is the number of handles that refer to the object in the handle tables of all processes, including the system process that contains the kernel. The referenced pointer count is incremented whenever a new pointer is needed by the kernel and decremented when the kernel is done with the pointer. The purpose of these reference counts is to ensure that an object is not freed while it is still referenced by either a handle or an internal kernel pointer.

The object manager maintains the Windows internal name space. In con- trast to UNIX, which roots the system name space in the file system, Windows uses an abstract name space and connects the file systems as devices. Whether a Windows object has a name is up to its creator. Processes and threads are created without names and referenced either by handle or through a separate numerical identifier. Synchronization events usually have names, so that they can be opened by unrelated processes. A name can be either permanent or temporary. A permanent name represents an entity, such as a disk drive, that remains even if no process is accessing it. A temporary name exists only while a process holds a handle to the object. The object manager supports directories and symbolic links in the name space. As an example, MS-DOS drive letters are implemented using symbolic links; ∖Global??∖C: is a symbolic link to the device object ∖Device∖HarddiskVolume2, representing a mounted file-system volume in the ∖Device directory.

Each object, asmentioned earlier, is an instance of an **_object type_**. The object type specifies how instances are to be allocated, how the data fields are to be defined, and how the standard set of virtual functions used for all objects are to be implemented. The standard functions implement operations such as mapping names to objects, closing and deleting, and applying security checks. Functions that are specific to a particular type of object are implemented by system services designed to operate on that particular object type, not by the methods specified in the object type.

The parse() function is the most interesting of the standard object func- tions. It allows the implementation of an object. The file systems, the registry configuration store, and GUI objects are the most notable users of parse func- tions to extend the Windows name space.

Returning to our Windows naming example, device objects used to rep- resent file-system volumes provide a parse function. This allows a name like ∖Global??∖C:∖foo∖bar.doc to be interpreted as the file ∖foo∖bar.doc on the volume represented by the device object HarddiskVolume2. We can illustrate how naming, parse functions, objects, and handles work together by looking at the steps to open the file in Windows:  

**18 Appendix B Windows 7**

**1\.** An application requests that a file named C:∖foo∖bar.doc be opened.

**2\.** The object manager finds the device object HarddiskVolume2, looks up the parse procedure IopParseDevice from the object’s type, and invokes it with the file’s name relative to the root of the file system.

**3\.** IopParseDevice() allocates a file object and passes it to the file system, which fills in the details of how to access C:∖foo∖bar.doc on the volume.

**4\.** When the file system returns, IopParseDevice() allocates an entry for the file object in the handle table for the current process and returns the handle to the application.

If the file cannot successfully be opened, IopParseDevice() deletes the file object it allocated and returns an error indication to the application.

**B.3.3.2 Virtual Memory Manager**

The executive component that manages the virtual address space, physi- cal memory allocation, and paging is the **virtual memory** (**VM**) **manager**. The design of the VM manager assumes that the underlying hardware sup- ports virtual-to-physicalmapping, a pagingmechanism, and transparent cache coherence on multiprocessor systems, as well as allowing multiple page-table entries to map to the same physical page frame. The VM manager in Windows uses a page-based management scheme with page sizes of 4 KB and 2 MB on AMD64 and IA-32-compatible processors and 8 KB on the IA64. Pages of data allocated to a process that are not in physical memory are either stored in the **paging file** on disk or mapped directly to a regular file on a local or remote file system. A page can also be marked zero-fill-on-demand, which initializes the page with zeros before it is allocated, thus erasing the previous contents.

On IA-32 processors, each process has a 4-GB virtual address space. The upper 2 GB are mostly identical for all processes and are used by Windows in kernel mode to access the operating-system code and data structures. For the AMD64 architecture, Windows provides a 8-TB virtual address space for user mode out of the 16 EB supported by existing hardware for each process.

Key areas of the kernel-mode region that are not identical for all processes are the self-map, hyperspace, and session space. The hardware references a process’s page table using physical page-frame numbers, and the **page table self-map** makes the contents of the process’s page table accessible using virtual addresses. **Hyperspace** maps the current process’s working-set information into the kernel-mode address space. **Session space** is used to share an instance of the Win32 and other session-specific drivers among all the processes in the same terminal-server (TS) session. Different TS sessions share different instances of these drivers, yet they are mapped at the same virtual addresses. The lower, user-mode region of virtual address space is specific to each process and accessible by both user- and kernel-mode threads.

The Windows VM manager uses a two-step process to allocate virtual memory. The first step **_reserves_** one or more pages of virtual addresses in the process’s virtual address space. The second step **_commits_** the allocation by assigning virtualmemory space (physicalmemory or space in the paging files). Windows limits the amount of virtual memory space a process consumes by enforcing a quota on committedmemory. Aprocess decommits memory that it  

**B.3 System Components 19**

is no longer using to free up virtual memory space for use by other processes. The APIs used to reserve virtual addresses and commit virtual memory take a handle on a process object as a parameter. This allows one process to control the virtual memory of another. Environmental subsystemsmanage the memory of their client processes in this way.

Windows implements shared memory by defining a **section object**. After getting a handle to a section object, a processmaps thememory of the section to a range of addresses, called a **view**. A process can establish a view of the entire section or only the portion it needs. Windows allows sections to be mapped not just into the current process but into any process for which the caller has a handle.

Sections can be used in many ways. A section can be backed by disk space either in the system-paging file or in a regular file (a **memory-mapped file).** A section can be **_based_**, meaning that it appears at the same virtual address for all processes attempting to access it. Sections can also represent physical memory, allowing a 32-bit process to access more physical memory than can fit in its virtual address space. Finally, the memory protection of pages in the section can be set to read-only, read-write, read-write-execute, execute-only, no access, or copy-on-write.

Let’s look more closely at the last two of these protection settings:

• A **_no-access page_** raises an exception if accessed. The exception can be used, for example, to check whether a faulty program iterates beyond the end of an array or simply to detect that the program attempted to access virtual addresses that are not committed to memory. User- and kernel-mode stacks use no-access pages as **guard pages** to detect stack overflows. Another use is to look for heap buffer overruns. Both the user- modememory allocator and the special kernel allocator used by the device verifier can be configured to map each allocation onto the end of a page, followed by a no-access page to detect programming errors that access beyond the end of an allocation.

• The **_copy-on-write mechanism_** enables the VM manager to use physical memorymore efficiently.When two processes want independent copies of data from the same section object, the VM manager places a single shared copy into virtualmemory and activates the copy-on-write property for that region of memory. If one of the processes tries to modify data in a copy- on-write page, the VM manager makes a private copy of the page for the process.

The virtual address translation in Windows uses a multilevel page table. For IA-32 and AMD64 processors, each process has a **page directory** that con- tains 512 **page-directory entries** (**PDEs**) 8 bytes in size. Each PDE points to a **PTE table** that contains 512**page-table entries** (**PTEs**) 8 bytes in size. Each PTE points to a 4-KB **page frame** in physicalmemory. For a variety of reasons, the hardware requires that the page directories or PTE tables at each level of amultilevel page table occupy a single page. Thus, the number of PDEs or PTEs that fit in a page determine how many virtual addresses are translated by that page. See Figure B.3 for a diagram of this structure.

The structure described so far can be used to represent only 1 GB of virtual address translation. For IA-32, a second page-directory level is needed, con-  

**20 Appendix B Windows 7**

page table entry 0

page table 0

page table entry 0

4-KB page

4-KB page

4-KB page

4-KB page

page table 511

page table entry 511

page table entry 511

page directory entry 0

page directory

0

page directory entry 0

page directory

3

page directory entry 511

page directory entry 511

pointer 0 pointer 1 pointer 2 pointer 3

page directory pointer table

**Figure B.3** Page-table layout.

taining only four entries, as shown in the diagram. On 64-bit processors, more levels are needed. For AMD64, Windows uses a total of four full levels. The total size of all page-table pages needed to fully represent even a 32-bit virtual address space for a process is 8 MB. The VM manager allocates pages of PDEs and PTEs as needed and moves page-table pages to disk when not in use. The page-table pages are faulted back into memory when referenced.

We next consider how virtual addresses are translated into physical addresses on IA-32-compatible processors. A 2-bit value can represent the values 0, 1, 2, 3. A 9-bit value can represent values from 0 to 511; a 12-bit value, values from 0 to 4,095. Thus, a 12-bit value can select any byte within a 4-KB page of memory. A 9-bit value can represent any of the 512 PDEs or PTEs in a page directory or PTE-table page. As shown in Figure B.4, translating a virtual address pointer to a byte address in physical memory involves breaking the 32-bit pointer into four values, starting from the most significant bits:

• Two bits are used to index into the four PDEs at the top level of the page table. The selected PDE will contain the physical page number for each of the four page-directory pages that map 1 GB of the address space.

PTR PTE indexPDE index page offset

31 0

**Figure B.4** Virtual-to-physical address translation on IA-32.  

**B.3 System Components 21**

• Nine bits are used to select another PDE, this time from a second-level page directory. This PDE will contain the physical page numbers of up to 512 PTE-table pages.

• Nine bits are used to select one of 512 PTEs from the selected PTE-table page. The selected PTE will contain the physical page number for the byte we are accessing.

• Twelve bits are used as the byte offset into the page. The physical address of the byte we are accessing is constructed by appending the lowest 12 bits of the virtual address to the end of the physical page number we found in the selected PTE.

The number of bits in a physical addressmay be different from the number of bits in a virtual address. In the original IA-32 architecture, the PTE and PDE were 32-bit structures that had room for only 20 bits of physical page number, so the physical address size and the virtual address size were the same. Such systems could address only 4 GB of physical memory. Later, the IA-32 was extended to the larger 64-bit PTE size used today, and the hardware supported 24-bit physical addresses. These systems could support 64 GB and were used on server systems. Today, all Windows servers are based on either the AMD64 or the IA64 and support very, very large physical addresses—more thanwe can possibly use. (Of course, once upon a time 4 GB seemed optimistically large for physical memory.)

To improve performance, the VM manager maps the page-directory and PTE-table pages into the same contiguous region of virtual addresses in every process. This self-map allows the VMmanager to use the same pointer to access the current PDE or PTE corresponding to a particular virtual address no matter what process is running. The self-map for the IA-32 takes a contiguous 8-MB region of kernel virtual address space; the AMD64 self-map occupies 512 GB. Although the self-map occupies significant address space, it does not require any additional virtual memory pages. It also allows the page table’s pages to be automatically paged in and out of physical memory.

In the creation of a self-map, one of the PDEs in the top-level page directory refers to the page-directory page itself, forming a “loop” in the page-table translations. The virtual pages are accessed if the loop is not taken, the PTE-table pages are accessed if the loop is taken once, the lowest-level page-directory pages are accessed if the loop is taken twice, and so forth.

The additional levels of page directories used for 64-bit virtual memory are translated in the same way except that the virtual address pointer is broken up into even more values. For the AMD64, Windows uses four full levels, each of which maps 512 pages, or 9+9+9+9+12 = 48 bits of virtual address.

To avoid the overhead of translating every virtual address by looking up the PDE and PTE, processors use **translation look-aside buffer** (**TLB**) hardware, which contains an associativememory cache formapping virtual pages to PTEs. The TLB is part of the**memory-management unit** (**MMU**) within each processor. The MMU needs to “walk” (navigate the data structures of) the page table in memory only when a needed translation is missing from the TLB.

The PDEs and PTEs contain more than just physical page numbers. They also have bits reserved for operating-system use and bits that control how the hardware uses memory, such as whether hardware caching should be used for  

**22 Appendix B Windows 7**

each page. In addition, the entries specify what kinds of access are allowed for both user and kernel modes.

APDE can also be marked to say that it should function as a PTE rather than a PDE. On a IA-32, the first 11 bits of the virtual address pointer select a PDE in the first two levels of translation. If the selected PDE is marked to act as a PTE, then the remaining 21 bits of the pointer are used as the offset of the byte. This results in a 2-MB size for the page. Mixing and matching 4-KB and 2-MB page sizeswithin the page table is easy for the operating systemand can significantly improve the performance of some programs by reducing how often the MMU needs to reload entries in the TLB, since one PDE mapping 2 MB replaces 512 PTEs each mapping 4 KB.

Managing physical memory so that 2-MB pages are available when needed is difficult, however, as they may continually be broken up into 4-KB pages, causing external fragmentation of memory. Also, the large pages can result in very significant internal fragmentation. Because of these problems, it is typically only Windows itself, along with large server applications, that use large pages to improve the performance of the TLB. They are better suited to do so because operating-system and server applications start running when the system boots, before memory has become fragmented.

Windows manages physical memory by associating each physical page with one of seven states: free, zeroed, modified, standby, bad, transition, or valid.

• A **_free_** page is a page that has no particular content.

• A **_zeroed_** page is a free page that has been zeroed out and is ready for immediate use to satisfy zero-on-demand faults.

• Amodified page has beenwritten by a process andmust be sent to the disk before it is allocated for another process.

• A **_standby_** page is a copy of information already stored on disk. Standby pages may be pages that were not modified, modified pages that have already been written to the disk, or pages that were prefetched because they are expected to be used soon.

• A **_bad_** page is unusable because a hardware error has been detected.

• A **_transition_** page is on its way in from disk to a page frame allocated in physical memory.

• A **_valid_** page is part of the working set of one or more processes and is contained within these processes’ page tables.

While valid pages are contained in processes’ page tables, pages in other states are kept in separate lists according to state type. The lists are constructed by linking the corresponding entries in the **page frame number** (**PFN**) database, which includes an entry for each physical memory page. The PFN entries also include information such as reference counts, locks, and NUMA information. Note that the PFN database represents pages of physical memory, whereas the PTEs represent pages of virtual memory.

When the valid bit in a PTE is zero, hardware ignores all the other bits, and the VMmanager can define them for its own use. Invalid pages can have a number of states represented by bits in the PTE. Page-file pages that have never  

**B.3 System Components 23**

63

V

32

protT P page file

31 0

page file offset

**Figure B.5** Page-file page-table entry. The valid bit is zero.

been faulted in are marked zero-on-demand. Pages mapped through section objects encode a pointer to the appropriate section object. PTEs for pages that have beenwritten to the page file contain enough information to locate the page on disk, and so forth. The structure of the page-file PTE is shown in Figure B.5. The T, P, and V bits are all zero for this type of PTE. The PTE includes 5 bits for page protection, 32 bits for page-file offset, and 4 bits to select the paging file. There are also 20 bits reserved for additional bookkeeping.

Windows uses a per-working-set, least-recently-used (LRU) replacement policy to take pages from processes as appropriate. When a process is started, it is assigned a default minimum working-set size. The working set of each process is allowed to grow until the amount of remaining physical memory starts to run low, at which point the VM manager starts to track the age of the pages in each working set. Eventually, when the available memory runs critically low, the VM manager trims the working set to remove older pages.

How old a page is depends not on how long it has been in memory but on when it was last referenced. This is determined by periodically making a pass through the working set of each process and incrementing the age for pages that have not been marked in the PTE as referenced since the last pass. When it becomes necessary to trim the working sets, the VMmanager uses heuristics to decide howmuch to trim from each process and then removes the oldest pages first.

A process can have its working set trimmed even when plenty of memory is available, if it was given a **_hard limit_** on howmuch physical memory it could use. In Windows 7, the VM manager will also trim processes that are growing rapidly, even if memory is plentiful. This policy change significantly improves the responsiveness of the system for other processes.

Windows tracks working sets not only for user-mode processes but also for the system process, which includes all the pageable data structures and code that run in kernel mode. Windows 7 created additional working sets for the system process and associated them with particular categories of kernel memory; the file cache, kernel heap, and kernel code now have their own working sets. The distinct working sets allow the VM manager to use different policies to trim the different categories of kernel memory.  

**24 Appendix B Windows 7**

The VM manager does not fault in only the page immediately needed. Research shows that the memory referencing of a thread tends to have a **locality** property. That is, when a page is used, it is likely that adjacent pages will be referenced in the near future. (Think of iterating over an array or fetching sequential instructions that form the executable code for a thread.) Because of locality, when the VM manager faults in a page, it also faults in a few adjacent pages. This prefetching tends to reduce the total number of page faults and allows reads to be clustered to improve I/O performance.

In addition to managing committed memory, the VM manager manages each process’s reserved memory, or virtual address space. Each process has an associated tree that describes the ranges of virtual addresses in use and what the uses are. This allows the VMmanager to fault in page-table pages as needed. If the PTE for a faulting address is uninitialized, the VM manager searches for the address in the process’s tree of **virtual address descriptors** (**VADs**) and uses this information to fill in the PTE and retrieve the page. In some cases, a PTE- table page itself may not exist; such a pagemust be transparently allocated and initialized by the VM manager. In other cases, the page may be shared as part of a section object, and the VADwill contain a pointer to that section object. The section object contains information on how to find the shared virtual page so that the PTE can be initialized to point at it directly.

**B.3.3.3 Process Manager**

The Windows process manager provides services for creating, deleting, and using processes, threads, and jobs. It has no knowledge about parent–child relationships or process hierarchies; those refinements are left to the particular environmental subsystem that owns the process. The process manager is also not involved in the scheduling of processes, other than setting the priorities and affinities in processes and threads when they are created. Thread scheduling takes place in the kernel dispatcher.

Each process contains one or more threads. Processes themselves can be collected into larger units called **job objects**. The use of job objects allows limits to be placed on CPU usage, working-set size, and processor affinities that control multiple processes at once. Job objects are used to manage large data-center machines.

An example of process creation in the Win32 environment is as follows:

**1\.** AWin32 application calls CreateProcess().

**2\.** Amessage is sent to the Win32 subsystem to notify it that the process is being created.

**3\.** CreateProcess() in the original process then calls an API in the process manager of the NT executive to actually create the process.

**4\.** The process manager calls the object manager to create a process object and returns the object handle to Win32.

**5\.** Win32 calls the process manager again to create a thread for the process and returns handles to the new process and thread.

The Windows APIs for manipulating virtual memory and threads and for duplicating handles take a process handle, so subsystems can perform  

**B.3 System Components 25**

operations on behalf of a new process without having to execute directly in the new process’s context. Once a new process is created, the initial thread is created, and an asynchronous procedure call is delivered to the thread to prompt the start of execution at the user-mode image loader. The loader is in ntdll.dll, which is a link library automatically mapped into every newly created process. Windows also supports a UNIX fork() style of process creation in order to support the POSIX environmental subsystem. Although the Win32 environment calls the process manager directly from the client process, POSIX uses the cross-process nature of the Windows APIs to create the new process from within the subsystem process.

The process manager relies on the asynchronous procedure calls (APCs) implemented by the kernel layer. APCs are used to initiate thread execution, suspend and resume threads, access thread registers, terminate threads and processes, and support debuggers.

The debugger support in the processmanager includes the APIs to suspend and resume threads and to create threads that begin in suspendedmode. There are also process-manager APIs that get and set a thread’s register context and access another process’s virtual memory. Threads can be created in the current process; they can also be injected into another process. The debugger makes use of thread injection to execute code within a process being debugged.

While running in the executive, a thread can temporarily attach to a dif- ferent process. **Thread attach** is used by kernel worker threads that need to execute in the context of the process originating a work request. For example, the VM manager might use thread attach when it needs access to a process’s working set or page tables, and the I/O manager might use it in updating the status variable in a process for asynchronous I/O operations.

The process manager also supports **impersonation**. Each thread has an associated **security token**. When the login process authenticates a user, the security token is attached to the user’s process and inherited by its child pro- cesses. The token contains the **security identity** (**SID**) of the user, the SIDs of the groups the user belongs to, the privileges the user has, and the integrity level of the process. By default, all threads within a process share a common token, representing the user and the application that started the process. However, a thread running in a process with a security token belonging to one user can set a thread-specific token belonging to another user to impersonate that user.

The impersonation facility is fundamental to the client–server RPC model, where services must act on behalf of a variety of clients with different security IDs. The right to impersonate a user is most often delivered as part of an RPC connection from a client process to a server process. Impersonation allows the server to access system services as if itwere the client in order to access or create objects and files on behalf of the client. The server process must be trustworthy andmust be carefullywritten to be robust against attacks. Otherwise, one client could take over a server process and then impersonate any user who made a subsequent client request.

**B.3.3.4 Facilities for Client–Server Computing**

The implementation of Windows uses a client–server model throughout. The environmental subsystems are servers that implement particular operating- system personalities. Many other services, such as user authentication, net-  

**26 Appendix B Windows 7**

work facilities, printer spooling, web services, network file systems, and plug- and-play, are also implemented using this model. To reduce the memory foot- print, multiple services are often collected into a few processes running the svchost.exe program. Each service is loaded as a dynamic-link library (DLL), which implements the service by relying on the user-mode thread-pool facili- ties to share threads and wait for messages (see Section B.3.3.3).

The normal implementation paradigm for client–server computing is to use RPCs to communicate requests. TheWin32API supports a standard RPC pro- tocol, as described in Section B.6.2.7. RPC usesmultiple transports (for example, namedpipes and TCP/IP) and can be used to implement RPCs between systems. When an RPC always occurs between a client and server on the local system, the advanced local procedure call facility (ALPC) can be used as the transport. At the lowest level of the system, in the implementation of the environmental systems, and for services that must be available in the early stages of booting, RPC is not available. Instead, native Windows services use ALPC directly.

ALPC is a message-passing mechanism. The server process publishes a globally visible connection-port object. When a client wants services from a subsystem or service, it opens a handle to the server’s connection-port object and sends a connection request to the port. The server creates a channel and returns a handle to the client. The channel consists of a pair of private com- munication ports: one for client-to-server messages and the other for server- to-client messages. Communication channels support a callback mechanism, so the client and server can accept requests when they would normally be expecting a reply.

When an ALPC channel is created, one of threemessage-passing techniques is chosen.

**1\.** The first technique is suitable for small tomediummessages (up to 63 KB). In this case, the port’s message queue is used as intermediate storage, and the messages are copied from one process to the other.

**2\.** The second technique is for larger messages. In this case, a shared- memory section object is created for the channel. Messages sent through the port’s message queue contain a pointer and size information referring to the section object. This avoids the need to copy large messages. The sender places data into the shared section, and the receiver views them directly.

**3\.** The third technique uses APIs that read and write directly into a process’s address space. ALPC provides functions and synchronization so that a server can access the data in a client. This technique is normally used by RPC to achieve higher performance for specific scenarios.

The Win32 windowmanager uses its own form of message passing, which is independent of the executive ALPC facilities.When a client asks for a connec- tion that uses window-manager messaging, the server sets up three objects: (1) a dedicated server thread to handle requests, (2) a 64-KB shared section object, and (3) an event-pair object. An **_event-pair object_** is a synchronization object used by theWin32 subsystem to provide notificationwhen the client thread has copied a message to the Win32 server, or vice versa. The section object is used to pass the messages, and the event-pair object provides synchronization.  

**B.3 System Components 27**

Window-manager messaging has several advantages:

• The section object eliminates message copying, since it represents a region of shared memory.

• The event-pair object eliminates the overhead of using the port object to pass messages containing pointers and lengths.

• The dedicated server thread eliminates the overhead of determiningwhich client thread is calling the server, since there is one server thread per client thread.

• The kernel gives scheduling preference to these dedicated server threads to improve performance.

**B.3.3.5 I/O Manager**

The **I/O manager** is responsible for managing file systems, device drivers, and network drivers. It keeps track of which device drivers, filter drivers, and file systems are loaded, and it also manages buffers for I/O requests. It works with the VM manager to provide memory-mapped file I/O and controls the Windows cache manager, which handles caching for the entire I/O system. The I/O manager is fundamentally asynchronous, providing synchronous I/O by explicitly waiting for an I/O operation to complete. The I/O manager provides several models of asynchronous I/O completion, including setting of events, updating of a status variable in the calling process, deliveryof APCs to initiating threads, and use of I/O completion ports,which allow a single thread to process I/O completions from many other threads.

Device drivers are arranged in a list for each device (called a driver or I/O stack). A driver is represented in the system as a **driver object**. Because a single driver can operate on multiple devices, the drivers are represented in the I/O stack by a **device object**, which contains a link to the driver object. The I/O manager converts the requests it receives into a standard form called an **I/O request packet** (**IRP**). It then forwards the IRP to the first driver in the targeted I/O stack for processing. After a driver processes the IRP, it calls the I/O manager either to forward the IRP to the next driver in the stack or, if all processing is finished, to complete the operation represented by the IRP.

The I/O request may be completed in a context different from the one in which it was made. For example, if a driver is performing its part of an I/O operation and is forced to block for an extended time, it may queue the IRP to a worker thread to continue processing in the system context. In the original thread, the driver returns a status indicating that the I/O request is pending so that the thread can continue executing in parallel with the I/O operation. An IRP may also be processed in interrupt-service routines and completed in an arbitrary process context. Because some final processing may need to take place in the context that initiated the I/O, the I/O manager uses an APC to do final I/O-completion processing in the process context of the originating thread.

The I/O stack model is very flexible. As a driver stack is built, vari- ous drivers have the opportunity to insert themselves into the stack as **filte drivers**. Filter drivers can examine and potentially modify each I/O operation. Mount management, partition management, and disk striping and mirroring are all examples of functionality implemented using filter drivers that execute  

**28 Appendix B Windows 7**

beneath the file system in the stack. File-system filter drivers execute above the file system and have been used to implement functionalities such as hier- archical storage management, single instancing of files for remote boot, and dynamic format conversion. Third parties also use file-system filter drivers to implement virus detection.

Device drivers for Windows are written to the Windows Driver Model (WDM) specification. This model lays out all the requirements for device drivers, including how to layer filter drivers, share common code for han- dling power and plug-and-play requests, build correct cancellation logic, and so forth.

Because of the richness of the WDM, writing a full WDM device driver for each new hardware device can involve a great deal of work. Fortunately, the port/miniport model makes it unnecessary to do this. Within a class of similar devices, such as audio drivers, SATA devices, or Ethernet controllers, each instance of a device shares a common driver for that class, called a **port driver**. The port driver implements the standard operations for the class and then calls device-specific routines in the device’s **miniport driver** to imple- ment device-specific functionality. The TCP/IP network stack is implemented in this way, with the ndis.sys class driver implementingmuch of the network driver functionality and calling out to the networkminiport drivers for specific hardware.

Recent versions of Windows, including Windows 7, provide additional simplifications for writing device drivers for hardware devices. Kernel-mode drivers can now be written using the **Kernel-Mode Driver Framework** (**KMDF**), which provides a simplified programming model for drivers on top of WDM. Another option is the **User-Mode Driver Framework** (**UMDF**). Many drivers do not need to operate in kernel mode, and it is easier to develop and deploy drivers in user mode. It also makes the system more reliable, because a failure in a user-mode driver does not cause a kernel-mode crash.

**B.3.3.6 Cache Manager**

In many operating systems, caching is done by the file system. Instead, Win- dows provides a centralized caching facility. The **cache manager** works closely with the VM manager to provide cache services for all components under the control of the I/O manager. Caching in Windows is based on files rather than raw blocks. The size of the cache changes dynamically according to howmuch free memory is available in the system. The cache manager maintains a pri- vate working set rather than sharing the system process’s working set. The cache manager memory-maps files into kernel memory and then uses special interfaces to the VMmanager to fault pages into or trim them from this private working set.

The cache is divided into blocks of 256 KB. Each cache block can hold a view (that is, a memory-mapped region) of a file. Each cache block is described by a **virtual address control block** (**VACB**) that stores the virtual address and file offset for the view, aswell as the number of processes using the view. The VACBs reside in a single array maintained by the cache manager.

When the I/O manager receives a file’s user-level read request, the I/O manager sends an IRP to the I/O stack for the volume on which the file resides. For files that are marked as cacheable, the file system calls the cache manager  

**B.3 System Components 29**

cache manager

VM manager

process

file system

disk driver

noncached I/O

I/O manager

data copy

cached I/O

page fault

I/O

**Figure B.6** File I/O.

to look up the requested data in its cached file views. The cache manager calculates which entry of that file’s VACB index array corresponds to the byte offset of the request. The entry either points to the view in the cache or is invalid. If it is invalid, the cache manager allocates a cache block (and the corresponding entry in the VACB array) andmaps the view into the cache block. The cache manager then attempts to copy data from the mapped file to the caller’s buffer. If the copy succeeds, the operation is completed.

If the copy fails, it does so because of a page fault, which causes the VM manager to send a noncached read request to the I/O manager. The I/O manager sends another request down the driver stack, this time requesting a paging operation, which bypasses the cache manager and reads the data from the file directly into the page allocated for the cache manager. Upon completion, the VACB is set to point at the page. The data, now in the cache, are copied to the caller’s buffer, and the original I/O request is completed. Figure B.6 shows an overview of these operations.

Akernel-level read operation is similar, except that the data can be accessed directly from the cache rather than being copied to a buffer in user space. To use file-system metadata (data structures that describe the file system), the kernel uses the cache manager’s mapping interface to read the metadata. To modify the metadata, the file system uses the cache manager’s pinning interface. **Pinning** a page locks the page into a physical-memory page frame so that the VM manager cannot move the page or page it out. After updating the metadata, the file system asks the cachemanager to unpin the page. Amodified page is marked dirty, and so the VM manager flushes the page to disk.

To improve performance, the cache manager keeps a small history of read requests and from this history attempts to predict future requests. If the cache manager finds a pattern in the previous three requests, such as sequential access forward or backward, it prefetches data into the cache before the next request is submitted by the application. In this way, the application may find its data already cached and not need to wait for disk I/O.

The cache manager is also responsible for telling the VM manager to flush the contents of the cache. The cache manager’s default behavior is write-back  

**30 Appendix B Windows 7**

caching: it accumulates writes for 4 to 5 seconds and then wakes up the cache- writer thread. When write-through caching is needed, a process can set a flag when opening the file, or the process can call an explicit cache-flush function.

A fast-writing process could potentially fill all the free cache pages before the cache-writer thread had a chance to wake up and flush the pages to disk. The cache writer prevents a process from flooding the system in the following way. When the amount of free cache memory becomes low, the cache manager temporarily blocks processes attempting to write data and wakes the cache- writer thread to flush pages to disk. If the fast-writing process is actually a network redirector for a network file system, blocking it for too long could cause network transfers to time out and be retransmitted. This retransmission would waste network bandwidth. To prevent such waste, network redirectors can instruct the cache manager to limit the backlog of writes in the cache.

Because a network file system needs to move data between a disk and the network interface, the cache manager also provides a DMA interface to move the data directly. Moving data directly avoids the need to copy data through an intermediate buffer.

**B.3.3.7 Security Reference Monitor**

Centralizing management of system entities in the object manager enables Windows to use a uniform mechanism to perform run-time access validation and audit checks for every user-accessible entity in the system. Whenever a process opens a handle to an object, the **security reference monitor** (**SRM**) checks the process’s security token and the object’s access-control list to see whether the process has the necessary access rights.

The SRM is also responsible for manipulating the privileges in security tokens. Special privileges are required for users to perform backup or restore operations on file systems, debug processes, and so forth. Tokens can also be marked as being restricted in their privileges so that they cannot access objects that are available to most users. Restricted tokens are used primarily to limit the damage that can be done by execution of untrusted code.

The integrity level of the code executing in a process is also representedby a token. Integrity levels are a type of capabilitymechanism, asmentioned earlier. Aprocess cannotmodify an object with an integrity level higher than that of the code executing in the process, whatever other permissions have been granted. Integrity levels were introduced to make it harder for code that successfully attacks outward-facing software, like Internet Explorer, to take over a system.

Another responsibility of the SRM is logging security audit events. The Department of Defense’s **Common Criteria** (the 2005 successor to the Orange Book) requires that a secure system have the ability to detect and log all attempts to access system resources so that it can more easily trace attempts at unauthorized access. Because the SRM is responsible for making access checks, it generates most of the audit records in the security-event log.

**B.3.3.8 Plug-and-Play Manager**

The operating system uses the **plug-and-play** (**PnP**) manager to recognize and adapt to changes in the hardware configuration. PnP devices use standard protocols to identify themselves to the system. The PnPmanager automatically recognizes installed devices and detects changes in devices as the system  

**B.3 System Components 31**

operates. Themanager also keeps track of hardware resources used by a device, as well as potential resources that could be used, and takes care of loading the appropriate drivers. This management of hardware resources—primarily interrupts and I/O memory ranges—has the goal of determining a hardware configuration in which all devices are able to operate successfully.

The PnP manager handles dynamic reconfiguration as follows. First, it gets a list of devices from each bus driver (for example, PCI or USB). It loads the installed driver (after finding one, if necessary) and sends an add-device request to the appropriate driver for each device. The PnPmanager thenfigures out the optimal resource assignments and sends a start-device request to each driver specifying the resource assignments for the device. If a device needs to be reconfigured, the PnPmanager sends a query-stop request, which asks the driver whether the device can be temporarily disabled. If the driver can disable the device, then all pending operations are completed, and new operations are prevented from starting. Finally, the PnPmanager sends a stop request and can then reconfigure the devicewith a new start-device request.

The PnP manager also supports other requests. For example, query- remove, which operates similarly to query-stop, is employed when a user is getting ready to eject a removable device, such as a USB storage device. The surprise-remove request is used when a device fails or, more likely, when a user removes a device without telling the system to stop it first. Finally, the remove request tells the driver to stop using a device permanently.

Many programs in the system are interested in the addition or removal of devices, so the PnP manager supports notifications. Such a notification, for example, gives GUI file menus the information they need to update their list of disk volumes when a new storage device is attached or removed. Installing devices often results in adding new services to the svchost.exe processes in the system. These services frequently set themselves up to run whenever the system boots and continue to run even if the original device is never plugged into the system. Windows 7 introduced a **service-trigger** mechanism in the **service control manager** (**SCM**), which manages the system services. With this mechanism, services can register themselves to start only when SCM receives a notification from the PnP manager that the device of interest has been added to the system.

**B.3.3.9 Power Manager**

Windows works with the hardware to implement sophisticated strategies for energy efficiency, as described in Section B.2.8. The policies that drive these strategies are implementedby the**power manager**. The powermanager detects current system conditions, such as the load on CPUs or I/O devices, and improves energy efficiency by reducing the performance and responsiveness of the systemwhenneed is low. The powermanager can also put the entire system into a very efficient **_sleep_**mode and can even write all the contents of memory to disk and turn off the power to allow the system to go into **_hibernation_**.

The primary advantage of sleep is that the system can enter fairly quickly, perhaps just a few seconds after the lid closes on a laptop. The return from sleep is also fairly quick. The power is turned down low on the CPUs and I/O devices, but the memory continues to be powered enough that its contents are not lost.  

**32 Appendix B Windows 7**

Hibernation takes considerably longer because the entire contents of mem- ory must be transferred to disk before the system is turned off. However, the fact that the system is, in fact, turned off is a significant advantage. If there is a loss of power to the system, as when the battery is swapped on a lap- top or a desktop system is unplugged, the saved system data will not be lost. Unlike shutdown, hibernation saves the currently running system so a user can resume where she left off, and because hibernation does not require power, a system can remain in hibernation indefinitely.

Like the PnP manager, the power manager provides notifications to the rest of the system about changes in the power state. Some applications want to know when the system is about to be shut down so they can start saving their states to disk.

**B.3.3.10 Registry**

Windows keeps much of its configuration information in internal databases, called **hives**, that are managed by the Windows configuration manager, which is commonly known as the **registry**. There are separate hives for system information, default user preferences, software installation, security, and boot options. Because the information in the **system hive** is required to boot the system, the registry manager is implemented as a component of the executive.

The registry represents the configuration state in each hive as a hierarchical namespace of keys (directories), each ofwhich can contain a set of typedvalues, such as UNICODE string, ANSI string, integer, or untyped binary data. In theory, new keys and values are created and initialized as new software is installed; then they are modified to reflect changes in the configuration of that software. In practice, the registry is often used as a general-purpose database, as an interprocess-communication mechanism, and for many other such inventive purposes.

Restarting applications, or even the system, every time a configuration change was made would be a nuisance. Instead, programs rely on various kinds of notifications, such as those provided by the PnP and powermanagers, to learn about changes in the system configuration. The registry also supplies notifications; it allows threads to register to be notified when changes are made to some part of the registry. The threads can thus detect and adapt to configuration changes recorded in the registry itself.

Whenever significant changes are made to the system, such as when updates to the operating system or drivers are installed, there is a danger that the configuration data may be corrupted (for example, if a working driver is replaced by a nonworking driver or an application fails to install correctly and leaves partial information in the registry). Windows creates a **system restore point** before making such changes. The restore point contains a copy of the hives before the change and can be used to return to this version of the hives and thereby get a corrupted system working again.

To improve the stability of the registry configuration, Windows added a transaction mechanism beginning with Windows Vista that can be used to prevent the registry from being partially updated with a collection of related configuration changes. Registry transactions can be part of more general trans- actions administered by the **kernel transaction manager** (**KTM**), which can also  

**B.3 System Components 33**

include file-system transactions. KTM transactions do not have the full seman- tics found in normal database transactions, and they have not supplanted the system restore facility for recovering fromdamage to the registry configuration caused by software installation.

**B.3.3.11 Booting**

The booting of a Windows PC begins when the hardware powers on and firmware begins executing from ROM. In older machines, this firmware was known as the BIOS, but more modern systems use UEFI (the Unified Extensible Firmware Interface), which is faster and more general and makes better use of the facilities in contemporary processors. The firmware runs **power-on self- test** (**POST**) diagnostics; identifies many of the devices attached to the system and initializes them to a clean, power-up state; and then builds the description used by the **advanced configuratio and power interface** (**ACPI**). Next, the firmware finds the system disk, loads the Windows bootmgr program, and begins executing it.

In a machine that has been hibernating, the winresume program is loaded next. It restores the running system from disk, and the system continues execu- tion at the point it had reached right before hibernating. In a machine that has been shut down, the bootmgr performs further initialization of the system and then loads winload. This program loads hal.dll, the kernel (ntoskrnl.exe), any drivers needed in booting, and the system hive. winload then transfers execution to the kernel.

The kernel initializes itself and creates two processes. The **system pro- cess** contains all the internal kernel worker threads and never executes in user mode. The first user-mode process created is SMSS, for **_session manager subsystem_**, which is similar to the INIT (initialization) process in UNIX. SMSS performs further initialization of the system, including establishing the paging files, loading more device drivers, and managing the Windows sessions. Each session is used to represent a logged-on user, except for **_session 0_**, which is used to run system-wide background services, such as LSASS and SERVICES. A session is anchored by an instance of the CSRSS process. Each session other than 0 initially runs the WINLOGON process. This process logs on a user and then launches the EXPLORER process, which implements the Windows GUI experience. The following list itemizes some of these aspects of booting:

• SMSS completes system initialization and then starts up session 0 and the first login session.

• WININIT runs in session 0 to initialize usermode and start LSASS, SERVICES, and the local session manager, LSM.

• LSASS, the security subsystem, implements facilities such as authentication of users.

• SERVICES contains the service control manager, or SCM, which supervises all background activities in the system, including user-mode services. A number of services will have registered to start when the system boots. Others will be started only on demand or when triggered by an event such as the arrival of a device.  

**34 Appendix B Windows 7**

• CSRSS is the Win32 environmental subsystem process. It is started in every session—unlike the POSIX subsystem, which is started only on demand when a POSIX process is created.

• WINLOGON is run in each Windows session other than session 0 to log on a user.

The system optimizes the boot process by prepaging from files on disk based on previous boots of the system. Disk access patterns at boot are also used to lay out system files on disk to reduce the number of I/O operations required. The processes necessary to start the system are reduced by grouping services into fewer processes. All of these approaches contribute to a dramatic reduction in system boot time. Of course, system boot time is less important than it once was because of the sleep and hibernation capabilities of Windows.

**B.4 Terminal Services and Fast User Switching**

Windows supports a GUI-based console that interfaces with the user via key- board, mouse, and display. Most systems also support audio and video. Audio input is used byWindows voice-recognition software; voice recognitionmakes the system more convenient and increases its accessibility for users with dis- abilities. Windows 7 added support for **multi-touch hardware**, allowing users to input data by touching the screen and making gestures with one or more fingers. Eventually, the video-input capability, which is currently used for com- munication applications, is likely to be used for visually interpreting gestures, as Microsoft has demonstrated for its Xbox 360 Kinect product. Other future input experiences may evolve from Microsoft’s **surface computer**. Most often installed at public venues, such as hotels and conference centers, the surface computer is a table surface with special cameras underneath. It can track the actions of multiple users at once and recognize objects that are placed on top.

The PC was, of course, envisioned as a **_personal computer_**—an inherently single-user machine. ModernWindows, however, supports the sharing of a PC among multiple users. Each user that is logged on using the GUI has a **session** created to represent the GUI environment he will be using and to contain all the processes created to run his applications. Windows allows multiple sessions to exist at the same time on a single machine. However, Windows only supports a single console, consisting of all the monitors, keyboards, and mice connected to the PC. Only one session can be connected to the console at a time. From the logon screen displayed on the console, users can create new sessions or attach to an existing session that was previously created. This allows multiple users to share a single PC without having to log off and on between users. Microsoft calls this use of sessions **_fast user switching_**.

Users can also create new sessions, or connect to existing sessions, on one PC from a session running on another Windows PC. The terminal server (TS) connects one of the GUI windows in a user’s local session to the new or existing session, called a **remote desktop**, on the remote computer. The most common use of remote desktops is for users to connect to a session on their work PC from their home PC.

Many corporations use corporate terminal-server systems maintained in data centers to run all user sessions that access corporate resources, rather than  

**B.5 File System 35**

allowing users to access those resources from the PCs in each user’s office. Each server computer may handle many dozens of remote-desktop sessions. This is a form of **thin-client** computing, in which individual computers rely on a server for many functions. Relying on data-center terminal servers improves reliability, manageability, and security of the corporate computing resources.

The TS is also used byWindows to implement **remote assistance**. A remote user can be invited to share a session with the user logged on to the session on the console. The remote user can watch the user’s actions and even be given control of the desktop to help resolve computing problems.

**B.5 File System**

The native file system in Windows is NTFS. It is used for all local volumes. However, associatedUSB thumbdrives, flashmemory on cameras, and external disks may be formatted with the 32-bit FAT file system for portability. FAT is a much older file-system format that is understood by many systems besides Windows, such as the software running on cameras. A disadvantage is that the FAT file system does not restrict file access to authorized users. The only solution for securing data with FAT is to run an application to encrypt the data before storing it on the file system.

In contrast, NTFS uses ACLs to control access to individual files and sup- ports implicit encryption of individual files or entire volumes (usingWindows BitLocker feature). NTFS implements many other features as well, including data recovery, fault tolerance, very large files and file systems, multiple data streams, UNICODE names, sparse files, journaling, volume shadow copies, and file compression.

**B.5.1 NTFS Internal Layout**

The fundamental entity in NTFS is a volume. A volume is created by the Win- dows logical disk management utility and is based on a logical disk partition. Avolumemay occupy a portion of a disk or an entire disk, or may span several disks.

NTFS does not deal with individual sectors of a disk but instead uses clus- ters as the units of disk allocation. A **cluster** is a number of disk sectors that is a power of 2. The cluster size is configured when an NTFS file system is format- ted. The default cluster size is based on the volume size—4 KB for volumes larger than 2 GB. Given the size of today’s disks, it may make sense to use cluster sizes larger than the Windows defaults to achieve better performance, although these performance gains will come at the expense of more internal fragmentation.

NTFS uses **logical cluster numbers** (**LCNs**) as disk addresses. It assigns them by numbering clusters from the beginning of the disk to the end. Using this scheme, the system can calculate a physical disk offset (in bytes) bymultiplying the LCN by the cluster size.

A file in NTFS is not a simple byte stream as it is in UNIX; rather, it is a structured object consisting of typed **attributes**. Each attribute of a file is an independent byte stream that can be created, deleted, read, and written. Some attribute types are standard for all files, including the file name (or names, if the file has aliases, such as an MS-DOS short name), the creation time, and the  

**36 Appendix B Windows 7**

security descriptor that specifies the access control list. User data are stored in **_data attributes_**.

Most traditional data files have an **_unnamed_** data attribute that contains all the file’s data. However, additional data streams can be created with explicit names. For instance, inMacintosh files stored on aWindows server, the resource fork is a named data stream. The IProp interfaces of the Component Object Model (COM) use a named data stream to store properties on ordinary files, including thumbnails of images. In general, attributes may be added as necessary and are accessed using a **_file-name:attribute_** syntax. NTFS returns only the size of the unnamed attribute in response to file-query operations, such as when running the dir command.

Every file inNTFS is described by one ormore records in an array stored in a special file called the master file table (MFT). The size of a record is determined when the file system is created; it ranges from 1 to 4 KB. Small attributes are stored in the MFT record itself and are called **_resident attributes_**. Large attributes, such as the unnamed bulk data, are called **_nonresident attributes_** and are stored in one or more contiguous **extents** on the disk. A pointer to each extent is stored in the MFT record. For a small file, even the data attribute may fit inside the MFT record. If a file has many attributes—or if it is highly fragmented, so that many pointers are needed to point to all the fragments —one record in the MFT might not be large enough. In this case, the file is described by a record called the **base fil record**, which contains pointers to overflow records that hold the additional pointers and attributes.

Each file in an NTFS volume has a unique ID called a **fil reference**. The file reference is a 64-bit quantity that consists of a 48-bit file number and a 16-bit sequence number. The file number is the record number (that is, the array slot) in the MFT that describes the file. The sequence number is incremented every time an MFT entry is reused. The sequence number enables NTFS to perform internal consistency checks, such as catching a stale reference to a deleted file after the MFT entry has been reused for a new file.

**B.5.1.1 NTFS B+ Tree**

As in UNIX, the NTFS namespace is organized as a hierarchy of directories. Each directoryuses a data structure called a**B+ tree** to store an index of the file names in that directory. In a B+ tree, the length of every path from the root of the tree to a leaf is the same, and the cost of reorganizing the tree is eliminated. The **index root** of a directory contains the top level of the B+ tree. For a large directory, this top level contains pointers to disk extents that hold the remainder of the tree. Each entry in the directory contains the name and file reference of the file, as well as a copy of the update timestamp and file size taken from the file’s resident attributes in the MFT. Copies of this information are stored in the directory so that a directory listing can be efficiently generated. Because all the file names, sizes, and update times are available from the directory itself, there is no need to gather these attributes from the MFT entries for each of the files.

**B.5.1.2 NTFS Metadata**

The NTFS volume’s metadata are all stored in files. The first file is the MFT. The second file, which is used during recovery if the MFT is damaged, contains a  

**B.5 File System 37**

copy of the first 16 entries of the MFT. The next few files are also special in purpose. They include the files described below.

• The **log file** records all metadata updates to the file system.

• The **volume file** contains the name of the volume, the version of NTFS that formatted the volume, and a bit that tells whether the volume may have been corrupted and needs to be checked for consistency using the chkdsk program.

• The **attribute-definitio table** indicates which attribute types are used in the volume and what operations can be performed on each of them.

• The **root directory** is the top-level directory in the file-system hierarchy.

• The **bitmap fil** indicates which clusters on a volume are allocated to files and which are free.

• The **boot fil** contains the startup code for Windows and must be located at a particular disk address so that it can be found easily by a simple ROM bootstrap loader. The boot file also contains the physical address of the MFT.

• The **bad-cluster file** keeps track of any bad areas on the volume; NTFS uses this record for error recovery.

Keeping all the NTFS metadata in actual files has a useful property. As dis- cussed in Section B.3.3.6, the cache manager caches file data. Since all the NTFS metadata reside in files, these data can be cached using the same mechanisms used for ordinary data.

**B.5.2 Recovery**

In many simple file systems, a power failure at the wrong time can damage the file-system data structures so severely that the entire volume is scrambled. Many UNIX file systems, including UFS but not ZFS, store redundant metadata on the disk, and they recover from crashes by using the fsck program to check all the file-system data structures and restore them forcibly to a consistent state. Restoring them often involves deleting damaged files and freeing data clusters that had been written with user data but not properly recorded in the file system’s metadata structures. This checking can be a slow process and can cause the loss of significant amounts of data.

NTFS takes a different approach to file-system robustness. In NTFS, all file- system data-structure updates are performed inside transactions. Before a data structure is altered, the transaction writes a log record that contains redo and undo information. After the data structure has been changed, the transaction writes a commit record to the log to signify that the transaction succeeded.

After a crash, the system can restore the file-system data structures to a consistent state by processing the log records, first redoing the operations for committed transactions and then undoing the operations for transactions that did not commit successfully before the crash. Periodically (usually every 5 seconds), a checkpoint record is written to the log. The system does not need log records prior to the checkpoint to recover from a crash. They can be  

**38 Appendix B Windows 7**

discarded, so the log file does not grow without bounds. The first time after system startup that an NTFS volume is accessed, NTFS automatically performs file-system recovery.

This scheme does not guarantee that all the user-file contents are correct after a crash. It ensures only that the file-system data structures (the metadata files) are undamaged and reflect some consistent state that existed prior to the crash. It would be possible to extend the transaction scheme to cover user files, and Microsoft took some steps to do this in Windows Vista.

The log is stored in the third metadata file at the beginning of the volume. It is created with a fixed maximum size when the file system is formatted. It has two sections: the **_logging area_**, which is a circular queue of log records, and the **_restart area_**, which holds context information, such as the position in the logging area where NTFS should start reading during a recovery. In fact, the restart area holds two copies of its information, so recovery is still possible if one copy is damaged during the crash.

The logging functionality is provided by the **_log-file service_**. In addition to writing the log records and performing recovery actions, the log-file service keeps track of the free space in the log file. If the free space gets too low, the log- file service queues pending transactions, andNTFS halts all new I/O operations. After the in-progress operations complete, NTFS calls the cache manager to flush all data and then resets the log file and performs the queued transactions.

**B.5.3 Security**

The security of an NTFS volume is derived from the Windows object model. Each NTFS file references a security descriptor, which specifies the owner of the file, and an access-control list, which contains the access permissions granted or denied to each user or group listed. Early versions of NTFS used a separate security descriptor as an attribute of each file. Beginning with Windows 2000, the security-descriptors attribute points to a shared copy, with a significant savings in disk and caching space; many, many files have identical security descriptors.

In normal operation, NTFS does not enforce permissions on traversal of directories in file path names. However, for compatibility with POSIX, these checks can be enabled. Traversal checks are inherently more expensive, since modern parsing of file path names uses prefix matching rather than directory- by-directory parsing of path names. Prefix matching is an algorithm that looks up strings in a cache and finds the entry with the longest match—for example, an entry for ∖foo∖bar∖dirwould be a match for ∖foo∖bar∖dir2∖dir3∖myfile. The prefix-matching cache allows path-name traversal to begin much deeper in the tree, savingmany steps. Enforcing traversal checksmeans that the user’s access must be checked at each directory level. For instance, a user might lack permission to traverse ∖foo∖bar, so starting at the access for ∖foo∖bar∖dir would be an error.

**B.5.4 Volume Management and Fault Tolerance**

FtDisk is the fault-tolerant disk driver for Windows. When installed, it pro- vides several ways to combine multiple disk drives into one logical volume so as to improve performance, capacity, or reliability.  

**B.5 File System 39**

LCNs 0–128000

LCNs 128001–783361

disk 1 (2.5 GB) disk 2 (2.5 GB)

disk C: (FAT) 2 GB

logical drive D: (NTFS) 3 GB

**Figure B.7** Volume set on two drives.

**B.5.4.1 Volume Sets and RAID Sets**

One way to combine multiple disks is to concatenate them logically to form a large logical volume, as shown in Figure B.7. In Windows, this logical volume, called a **volume set**, can consist of up to 32 physical partitions. A volume set that contains an NTFS volume can be extended without disturbance of the data already stored in the file system. The bitmap metadata on the NTFS volume are simply extended to cover the newly added space. NTFS continues to use the same LCN mechanism that it uses for a single physical disk, and the FtDisk driver supplies the mapping from a logical-volume offset to the offset on one particular disk.

Another way to combine multiple physical partitions is to interleave their blocks in round-robin fashion to form a **stripe set**. This scheme is also called RAID level 0, or **disk striping**. (Formore on RAID (redundant arrays of inexpen- sive disks), see Section 11.8.) FtDisk uses a stripe size of 64 KB. The first 64 KB of the logical volume are stored in the first physical partition, the second 64 KB in the second physical partition, and so on, until each partition has contributed 64 KB of space. Then, the allocation wraps around to the first disk, allocating the second 64-KB block. A stripe set forms one large logical volume, but the physical layout can improve the I/O bandwidth, because for a large I/O, all the disks can transfer data in parallel. Windows also supports RAID level 5, stripe set with parity, and RAID level 1, mirroring.

**B.5.4.2 Sector Sparing and Cluster Remapping**

To deal with disk sectors that go bad, FtDisk uses a hardware technique called sector sparing, and NTFS uses a software technique called cluster remapping. **Sector sparing** is a hardware capability provided by many disk drives. When a disk drive is formatted, it creates a map from logical block numbers to good sectors on the disk. It also leaves extra sectors unmapped, as spares. If a sector fails, FtDisk instructs the disk drive to substitute a spare. **Cluster remapping**  

**40 Appendix B Windows 7**

is a software technique performed by the file system. If a disk block goes bad, NTFS substitutes a different, unallocated block by changing any affected pointers in the MFT. NTFS also makes a note that the bad block should never be allocated to any file.

When a disk block goes bad, the usual outcome is a data loss. But sector sparing or cluster remapping can be combined with fault-tolerant volumes to mask the failure of a disk block. If a read fails, the system reconstructs the missing data by reading the mirror or by calculating the exclusive or parity in a stripe set with parity. The reconstructed data are stored in a new location that is obtained by sector sparing or cluster remapping.

**B.5.5 Compression**

NTFS can perform data compression on individual files or on all data files in a directory. To compress a file, NTFS divides the file’s data into **compres- sion units**, which are blocks of 16 contiguous clusters. When a compression unit is written, a data-compression algorithm is applied. If the result fits into fewer than 16 clusters, the compressed version is stored. When reading, NTFS can determine whether data have been compressed: if they have been, the length of the stored compression unit is less than 16 clusters. To improve per- formance when reading contiguous compression units, NTFS prefetches and decompresses ahead of the application requests.

For sparse files or files that contain mostly zeros, NTFS uses another tech- nique to save space. Clusters that contain only zeros because they have never been written are not actually allocated or stored on disk. Instead, gaps are left in the sequence of virtual-cluster numbers stored in the MFT entry for the file. When reading a file, if NTFS finds a gap in the virtual-cluster numbers, it just zero-fills that portion of the caller’s buffer. This technique is also used by UNIX.

**B.5.6 Mount Points, Symbolic Links, and Hard Links**

Mount points are a form of symbolic link specific to directories on NTFS that were introduced in Windows 2000. They provide a mechanism for organizing disk volumes that is more flexible than the use of global names (like drive letters). A mount point is implemented as a symbolic link with associated data that contains the true volume name. Ultimately, mount points will sup- plant drive letters completely, but there will be a long transition due to the dependence of many applications on the drive-letter scheme.

Windows Vista introduced support for a more general form of symbolic links, similar to those found in UNIX. The links can be absolute or relative, can point to objects that do not exist, and can point to both files and directories even across volumes. NTFS also supports **hard links**, where a single file has an entry in more than one directory of the same volume.

**B.5.7 Change Journal**

NTFS keeps a journal describing all changes that have been made to the file system. User-mode services can receive notifications of changes to the journal and then identify what files have changed by reading from the journal. The search indexer service uses the change journal to identify files that need to be  

**B.6 Networking 41**

re-indexed. The file-replication service uses it to identify files that need to be replicated across the network.

**B.5.8 Volume Shadow Copies**

Windows implements the capability of bringing a volume to a known state and then creating a shadow copy that can be used to back up a consistent view of the volume. This technique is known as **_snapshots_** in some other file systems.Making a shadow copy of a volume is a form of copy-on-write, where blocks modified after the shadow copy is created are stored in their original form in the copy. To achieve a consistent state for the volume requires the cooperation of applications, since the system cannot knowwhen the data used by the application are in a stable state from which the application could be safely restarted.

The server version of Windows uses shadow copies to efficiently maintain old versions of files stored on file servers. This allows users to see documents stored on file servers as they existed at earlier points in time. The user can use this feature to recover files that were accidentally deleted or simply to look at a previous version of the file, all without pulling out backup media.

**B.6 Networking**

Windows supports both peer-to-peer and client–server networking. It also has facilities for network management. The networking components in Win- dows provide data transport, interprocess communication, file sharing across a network, and the ability to send print jobs to remote printers.

**B.6.1 Network Interfaces**

To describe networking inWindows, we must first mention two of the internal networking interfaces: the **network device interface specificatio** (**NDIS**) and the **transport driver interface** (**TDI**). The NDIS interface was developed in 1989 byMicrosoft and 3Com to separate network adapters from transport protocols so that either could be changed without affecting the other. NDIS resides at the interface between the data-link and network layers in the ISO model and enables many protocols to operate over many different network adapters. In terms of the ISO model, the TDI is the interface between the transport layer (layer 4) and the session layer (layer 5). This interface enables any session-layer component to use any available transport mechanism. (Similar reasoning led to the streams mechanism in UNIX.) The TDI supports both connection-based and connectionless transport and has functions to send any type of data.

**B.6.2 Protocols**

Windows implements transport protocols as drivers. These drivers can be loaded and unloaded from the system dynamically, although in practice the system typically has to be rebooted after a change. Windows comes with several networking protocols. Next, we discuss a number of these protocols.  

**42 Appendix B Windows 7**

**B.6.2.1 Server-Message Block**

The **server-message-block** (**SMB**) protocol was first introduced in MS-DOS 3.1. The system uses the protocol to send I/O requests over the network. The SMB protocol has four message types. Session control messages are commands that start and end a redirector connection to a shared resource at the server. A redirector uses File messages to access files at the server. Printer messages are used to send data to a remote print queue and to receive status information from the queue, and Messagemessages are used to communicate with another workstation. A version of the SMB protocol was published as the **common Internet fil system** (**CIFS**) and is supported on a number of operating systems.

**B.6.2.2 Transmission Control Protocol/Internet Protocol**

The transmission control protocol/Internet protocol (TCP/IP) suite that is used on the Internet has become the de facto standard networking infrastructure. Windows uses TCP/IP to connect to a wide variety of operating systems and hardware platforms. The Windows TCP/IP package includes the simple network-management protocol (SNM), the dynamic host-configuration proto- col (DHCP), and the older Windows Internet name service (WINS). Windows Vista introduced a new implementation of TCP/IP that supports both IPv4 and IPv6 in the same network stack. This new implementation also supports offloading of the network stack onto advanced hardware, to achieve very high performance for servers.

Windows provides a software firewall that limits the TCP ports that can be used by programs for network communication. Network firewalls are com- monly implemented in routers and are a very important security measure. Having a firewall built into the operating system makes a hardware router unnecessary, and it also providesmore integratedmanagement and easier use.

**B.6.2.3 Point-to-Point Tunneling Protocol**

The **point-to-point tunneling protocol** (**PPTP**) is a protocol provided by Win- dows to communicate between remote-access servermodules running onWin- dows server machines and other client systems that are connected over the Internet. The remote-access servers can encrypt data sent over the connec- tion, and they support multiprotocol **virtual private networks** (**VPNs**) over the Internet.

**B.6.2.4 HTTP Protocol**

The HTTP protocol is used to get/put information using the World WideWeb. Windows implements HTTP using a kernel-mode driver, so web servers can operate with a low-overhead connection to the networking stack. HTTP is a fairly general protocol that Windows makes available as a transport option for implementing RPC.

**B.6.2.5 Web-Distributed Authoring and Versioning Protocol**

Web-distributed authoring and versioning (WebDAV) is an HTTP-based proto- col for collaborative authoring across a network. Windows builds a WebDAV  

**B.6 Networking 43**

redirector into the file system. Being built directly into the file system enables WebDAV to work with other file-system features, such as encryption. Personal files can then be stored securely in a public place. Because WebDAV uses HTTP, which is a get/put protocol, Windows has to cache the files locally so pro- grams can use read and write operations on parts of the files.

**B.6.2.6 Named Pipes**

**Named pipes** are a connection-oriented messaging mechanism. A process can use named pipes to communicate with other processes on the same machine. Since named pipes are accessed through the file-system interface, the security mechanisms used for file objects also apply to named pipes. The SMB protocol supports named pipes, so they can also be used for communication between processes on different systems.

The format of pipe names follows the **uniform naming convention** (**UNC**). A UNC name looks like a typical remote file name. The format is ∖∖server name∖share name∖x∖y∖z, where server name identifies a server on the network; share name identifies any resource that is made available to network users, such as directories, files, named pipes, and printers; and ∖x∖y∖z is a normal file path name.

**B.6.2.7 Remote Procedure Calls**

A remote procedure call (RPC) is a client–server mechanism that enables an application on one machine to make a procedure call to code on another machine. The client calls a local procedure—a stub routine—that packs its arguments into a message and sends them across the network to a particular server process. The client-side stub routine then blocks. Meanwhile, the server unpacks the message, calls the procedure, packs the return results into a mes- sage, and sends them back to the client stub. The client stub unblocks, receives themessage, unpacks the results of the RPC, and returns them to the caller. This packing of arguments is sometimes called**marshaling**. The client stub code and the descriptors necessary to pack and unpack the arguments for an RPC are compiled from a specification written in the **Microsoft Interface Definitio Language**.

The Windows RPC mechanism follows the widely used distributed- computing-environment standard for RPC messages, so programs written to use Windows RPCs are highly portable. The RPC standard is detailed. It hides many of the architectural differences among computers, such as the sizes of binary numbers and the order of bytes and bits in computer words, by specifying standard data formats for RPC messages.

**B.6.2.8 Component Object Model**

The **component object model** (**COM**) is a mechanism for interprocess commu- nication that was developed for Windows. COM objects provide a well-defined interface to manipulate the data in the object. For instance, COM is the infras- tructure used by Microsoft’s **object linking and embedding** (**OLE**) technology for inserting spreadsheets into Microsoft Word documents. Many Windows services provide COM interfaces. Windows has a distributed extension called  

**44 Appendix B Windows 7**

**DCOM** that can be used over a network utilizing RPC to provide a transparent method of developing distributed applications.

**B.6.3 Redirectors and Servers**

In Windows, an application can use the Windows I/O API to access files from a remote computer as though they were local, provided that the remote com- puter is running a CIFS server such as those provided byWindows. A **redirector** is the client-side object that forwards I/O requests to a remote system, where they are satisfied by a server. For performance and security, the redirectors and servers run in kernel mode.

In more detail, access to a remote file occurs as follows:

**1\.** The application calls the I/Omanager to request that a file be openedwith a file name in the standard UNC format.

**2\.** The I/O manager builds an I/O request packet, as described in Section B.3.3.5.

**3\.** The I/O manager recognizes that the access is for a remote file and calls a driver called a **multiple universal-naming-convention provider** (**MUP**).

**4\.** The MUP sends the I/O request packet asynchronously to all registered redirectors.

**5\.** A redirector that can satisfy the request responds to the MUP. To avoid asking all the redirectors the same question in the future, the MUP uses a cache to remember which redirector can handle this file.

**6\.** The redirector sends the network request to the remote system.

**7\.** The remote-system network drivers receive the request and pass it to the server driver.

**8\.** The server driver hands the request to the proper local file-system driver.

**9\.** The proper device driver is called to access the data.

**10\.** The results are returned to the server driver, which sends the data back to the requesting redirector. The redirector then returns the data to the calling application via the I/O manager.

Asimilar process occurs for applications that use theWin32 network API, rather than the UNC services, except that a module called a **_multi-provider router_** is used instead of a MUP.

For portability, redirectors and servers use the TDI API for network trans- port. The requests themselves are expressed in a higher-level protocol, which by default is the SMB protocol described in Section B.6.2. The list of redirectors is maintained in the system hive of the registry.

**B.6.3.1 Distributed File System**

UNC names are not always convenient, because multiple file servers may be available to serve the same content and UNC names explicitly include the name  

**B.6 Networking 45**

of the server. Windows supports a **distributed file-syste** (**DFS**) protocol that allows a network administrator to serve up files from multiple servers using a single distributed name space.

**B.6.3.2 Folder Redirection and Client-Side Caching**

To improve the PC experience for users who frequently switch among com- puters, Windows allows administrators to give users **roaming profile** , which keepusers’ preferences and other settings on servers.**Folder redirection** is then used to automatically store a user’s documents and other files on a server.

This works well until one of the computers is no longer attached to the network, as when a user takes a laptop onto an airplane. To give users off-line access to their redirected files, Windows uses **client-side caching** (**CSC**). CSC is also used when the computer is on-line to keep copies of the server files on the local machine for better performance. The files are pushed up to the server as they are changed. If the computer becomes disconnected, the files are still available, and the update of the server is deferred until the next time the computer is online.

**B.6.4 Domains**

Many networked environments have natural groups of users, such as students in a computer laboratory at school or employees in one department in a busi- ness. Frequently, we want all the members of the group to be able to access shared resources on their various computers in the group. Tomanage the global access rights within such groups, Windows uses the concept of a domain. Pre- viously, these domains had no relationship whatsoever to the domain-name system (DNS) that maps Internet host names to IP addresses. Now, however, they are closely related.

Specifically, a Windows domain is a group of Windows workstations and servers that share a common security policy and user database. SinceWindows uses the Kerberos protocol for trust and authentication, a Windows domain is the same thing as a Kerberos realm. Windows uses a hierarchical approach for establishing trust relationships between related domains. The trust rela- tionships are based on DNS and allow transitive trusts that can flow up and down the hierarchy. This approach reduces the number of trusts required for _n_ domains from _n_ ∗ (_n_ − 1) to _O_(_n_). The workstations in the domain trust the domain controller to give correct information about the access rights of each user (loaded into the user’s access token by LSASS). All users retain the ability to restrict access to their ownworkstations, however, nomatter what any domain controller may say.

**B.6.5 Active Directory**

**Active Directory** is the Windows implementation of **lightweight directory- access protocol** (**LDAP**) services. Active Directory stores the topology infor- mation about the domain, keeps the domain-based user and group accounts and passwords, and provides a domain-based store for Windows features that need it, such as **Windows group policy**. Administrators use group policies to establish uniform standards for desktop preferences and software. For many  

**46 Appendix B Windows 7**

corporate information-technology groups, this uniformity drastically reduces the cost of computing.

**B.7 Programmer Interface**

The**Win32 API** is the fundamental interface to the capabilities ofWindows. This section describes five main aspects of the Win32 API: access to kernel objects, sharing of objects between processes, process management, interprocess com- munication, and memory management.

**B.7.1 Access to Kernel Objects**

The Windows kernel provides many services that application programs can use. Application programs obtain these services by manipulating kernel objects. A process gains access to a kernel object named XXX by calling the CreateXXX function to open a handle to an instance of XXX. This handle is unique to the process. Depending on which object is being opened, if the Create() function fails, it may return 0, or it may return a special constant named INVALID HANDLE VALUE. A process can close any handle by calling the CloseHandle() function, and the system may delete the object if the count of handles referencing the object in all processes drops to zero.

**B.7.2 Sharing Objects between Processes**

Windows provides three ways to share objects between processes. The first way is for a child process to inherit a handle to the object. When the parent calls the CreateXXX function, the parent supplies a SECURITIES ATTRIBUTES structure with the bInheritHandle field set to TRUE. This field creates an inheritable handle. Next, the child process is created, passing a value of TRUE to the CreateProcess() function’s bInheritHandle argument. Figure B.8 shows a code sample that creates a semaphore handle inherited by a child process.

SECURITY ATTRIBUTES sa; sa.nlength = sizeof(sa); sa.lpSecurityDescriptor = NULL; sa.bInheritHandle = TRUE; Handle a semaphore = CreateSemaphore(&sa, 1, 1, NULL); char comand line\[132\]; ostrstream ostring(command line, sizeof(command line)); ostring << a semaphore << ends; CreateProcess("another process.exe", command line,

NULL, NULL, TRUE, . . .);

**Figure B.8** Code enabling a child to share an object by inheriting a handle.  

**B.7 Programmer Interface 47**

// Process A . . . HANDLE a semaphore = CreateSemaphore(NULL, 1, 1, "MySEM1"); . . .

// Process B . . . HANDLE b semaphore = OpenSemaphore(SEMAPHORE ALL ACCESS,

FALSE, "MySEM1"); . . .

**Figure B.9** Code for sharing an object by name lookup.

Assuming the child process knows which handles are shared, the parent and child can achieve interprocess communication through the shared objects. In the example in Figure B.8, the child process gets the value of the handle from the first command-line argument and then shares the semaphore with the parent process.

The second way to share objects is for one process to give the object a name when the object is created and for the second process to open the name. This method has two drawbacks: Windows does not provide a way to check whether an object with the chosen name already exists, and the object name space is global, without regard to the object type. For instance, two applications may create and share a single object named “foo” when two distinct objects— possibly of different types—were desired.

Named objects have the advantage that unrelated processes can readily share them. The first process calls one of the CreateXXX functions and supplies a name as a parameter. The second process gets a handle to share the object by calling OpenXXX() (or CreateXXX) with the same name, as shown in the example in Figure B.9.

The thirdway to share objects is via the DuplicateHandle() function. This method requires some other method of interprocess communication to pass the duplicated handle. Given a handle to a process and the value of a handle within that process, a second process can get a handle to the same object and thus share it. An example of this method is shown in Figure B.10.

**B.7.3 Process Management**

InWindows, a **process** is a loaded instance of an application and a **thread** is an executable unit of code that can be scheduled by the kernel dispatcher. Thus, a process contains one or more threads. A process is created when a thread in some other process calls the CreateProcess() API. This routine loads any dynamic link libraries used by the process and creates an initial thread in the process. Additional threads can be created by the CreateThread() function. Each thread is created with its own stack, which defaults to 1 MB unless otherwise specified in an argument to CreateThread().  

**48 Appendix B Windows 7**

// Process A wants to give Process B access to a semaphore

// Process A HANDLE a semaphore = CreateSemaphore(NULL, 1, 1, NULL); // send the value of the semaphore to Process B // using a message or shared memory object . . .

// Process B HANDLE process a = OpenProcess(PROCESS ALL ACCESS, FALSE,

process id of A); HANDLE b semaphore; DuplicateHandle(process a, a semaphore,

GetCurrentProcess(), &b semaphore, 0, FALSE, DUPLICATE SAME ACCESS);

// use b semaphore to access the semaphore . . .

**Figure B.10** Code for sharing an object by passing a handle.

**B.7.3.1 Scheduling Rule**

Priorities in the Win32 environment are based on the native kernel (NT) scheduling model, but not all priority values may be chosen. The Win32 API uses four priority classes:

**1\.** IDLE PRIORITY CLASS (NT priority level 4)

**2\.** NORMAL PRIORITY CLASS (NT priority level 8)

**3\.** HIGH PRIORITY CLASS (NT priority level 13)

**4\.** REALTIME PRIORITY CLASS (NT priority level 24)

Processes are typically members of the NORMAL PRIORITY CLASS unless the parent of the process was of the IDLE PRIORITY CLASS or another class was specified when CreateProcess was called. The priority class of a process is the default for all threads that execute in the process. It can be changed with the SetPriorityClass() function or by passing an argument to the START command. Only userswith the **_increase scheduling priority_** privilege canmove a process into the REALTIME PRIORITY CLASS. Administrators and power users have this privilege by default.

When a user is running an interactive process, the system needs to schedule the process’s threads to provide good responsiveness. For this reason, Windows has a special scheduling rule for processes in the NOR- MAL PRIORITY CLASS. Windows distinguishes between the process associated with the foreground window on the screen and the other (background) processes. When a process moves into the foreground, Windows increases the scheduling quantum for all its threads by a factor of 3; CPU-bound threads  

**B.7 Programmer Interface 49**

in the foreground process will run three times longer than similar threads in background processes.

**B.7.3.2 Thread Priorities**

A thread starts with an initial priority determined by its class. The priority can be altered by the SetThreadPriority() function. This function takes an argument that specifies a priority relative to the base priority of its class:

• THREAD PRIORITY LOWEST: base − 2

• THREAD PRIORITY BELOW NORMAL: base − 1

• THREAD PRIORITY NORMAL: base + 0

• THREAD PRIORITY ABOVE NORMAL: base + 1

• THREAD PRIORITY HIGHEST: base + 2

Two other designations are also used to adjust the priority. Recall from Section B.3.2.2 that the kernel has two priority classes: 16–31 for the real- time class and 1–15 for the variable class. THREAD PRIORITY IDLE sets the priority to 16 for real-time threads and to 1 for variable-priority threads. THREAD PRIORITY TIME CRITICAL sets the priority to 31 for real-time threads and to 15 for variable-priority threads.

As discussed in Section B.3.2.2, the kernel adjusts the priority of a variable class thread dynamically depending on whether the thread is I/O bound or CPU bound. The Win32 API provides a method to disable this adjustment via SetProcessPriorityBoost() and SetThreadPriorityBoost() functions.

**B.7.3.3 Thread Suspend and Resume**

A thread can be created in a **_suspended state_** or can be placed in a suspended state later by use of the SuspendThread() function. Before a suspended thread can be scheduled by the kernel dispatcher, it must be moved out of the sus- pended state by use of the ResumeThread() function. Both functions set a counter so that if a thread is suspended twice, it must be resumed twice before it can run.

**B.7.3.4 Thread Synchronization**

To synchronize concurrent access to shared objects by threads, the kernel pro- vides synchronization objects, such as semaphores and mutexes. These are dispatcher objects, as discussed in Section B.3.2.2. Threads can also synchronize with kernel services operating on kernel objects—such as threads, processes, and files—because these are also dispatcher objects. Synchronization with ker- nel dispatcher objects can be achieved by use of the WaitForSingleObject() and WaitForMultipleObjects() functions; these functions wait for one or more dispatcher objects to be signaled.

Another method of synchronization is available to threadswithin the same process that want to execute code exclusively. TheWin32 **critical section object** is a user-mode mutex object that can often be acquired and released without entering the kernel. On a multiprocessor, a Win32 critical section will attempt to spinwhile waiting for a critical section held by another thread to be released.  

**50 Appendix B Windows 7**

If the spinning takes too long, the acquiring thread will allocate a kernel mutex and yield its CPU. Critical sections are particularly efficient because the kernel mutex is allocated only when there is contention and then used only after attempting to spin. Most mutexes in programs are never actually contended, so the savings are significant.

Before using a critical section, some thread in the process must call InitializeCriticalSection(). Each thread that wants to acquire the mutex calls EnterCriticalSection() and then later calls LeaveCritical- Section() to release themutex. There is also a TryEnterCriticalSection() function, which attempts to acquire the mutex without blocking.

For programs that want user-mode reader–writer locks rather than a mutex, Win32 supports **slim reader–writer** (**SRW**) **locks**. SRW locks have APIs similar to those for critical sections, such as InitializeSRWLock, AcquireSRWLockXXX, and ReleaseSRWLockXXX, where XXX is either Exclusive or Shared, depending on whether the thread wants write access or just read access to the object protected by the lock. TheWin32 API also supports **condition variables**, which can be used with either critical sections or SRW locks.

**B.7.3.5 Thread Pool**

Repeatedly creating and deleting threads can be expensive for applications and services that perform small amounts of work in each instantiation. The Win32 thread pool provides user-mode programs with three services: a queue to which work requests may be submitted (via the SubmitThreadpoolWork() function), an API that can be used to bind callbacks towaitable handles (Regis- terWaitForSingleObject()), and APIs to workwith timers (CreateThread- poolTimer() and WaitForThreadpoolTimerCallbacks()) and to bind call- backs to I/O completion queues (BindIoCompletionCallback()).

The goal of using a threadpool is to increase performance and reducemem- ory footprint. Threads are relatively expensive, and each processor can only be executing one thread at a time no matter how many threads are available. The thread pool attempts to reduce the number of runnable threads by slightly delaying work requests (reusing each thread for many requests) while provid- ing enough threads to effectively utilize the machine’s CPUs. The wait and I/O- and timer-callback APIs allow the thread pool to further reduce the number of threads in a process, using far fewer threads than would be necessary if a process were to devote separate threads to servicing each waitable handle, timer, or completion port.

**B.7.3.6 Fibers**

A **fibe** is user-mode code that is scheduled according to a user-defined scheduling algorithm. Fibers are completely a user-mode facility; the kernel is not aware that they exist. The fibermechanism usesWindows threads as if they were CPUs to execute the fibers. Fibers are cooperatively scheduled, meaning that they are never preempted but must explicitly yield the thread on which they are running. When a fiber yields a thread, another fiber can be scheduled on it by the run-time system (the programming language run-time code).

The system creates a fiber by calling either ConvertThreadToFiber() or CreateFiber(). The primary difference between these functions is that  

**B.7 Programmer Interface 51**

CreateFiber() does not begin executing the fiber that was created. To begin execution, the application must call SwitchToFiber(). The application can terminate a fiber by calling DeleteFiber().

Fibers are not recommended for threads that use Win32 APIs rather than standardC-library functions because of potential incompatibilities.Win32 user- mode threads have a **thread-environment block** (**TEB**) that contains numerous per-threadfields used by theWin32APIs. Fibersmust share the TEB of the thread on which they are running. This can lead to problems when a Win32 interface puts state information into the TEB for one fiber and then the information is overwritten by a different fiber. Fibers are included in theWin32API to facilitate the porting of legacy UNIX applications that were written for a user-mode thread model such as Pthreads.

**B.7.3.7 User-Mode Scheduling (UMS) and ConcRT**

A new mechanism in Windows 7, user-mode scheduling (UMS), addresses several limitations of fibers. First, recall that fibers are unreliable for executing Win32 APIs because they do not have their own TEBs. When a thread running a fiber blocks in the kernel, the user scheduler loses control of the CPU for a time as the kernel dispatcher takes over scheduling. Problemsmay result when fibers change the kernel state of a thread, such as the priority or impersonation token, or when they start asynchronous I/O.

UMS provides an alternative model by recognizing that each Windows thread is actually two threads: a kernel thread (KT) and a user thread (UT). Each type of thread has its own stack and its own set of saved registers. The KT and UT appear as a single thread to the programmer because UTs can never block but must always enter the kernel, where an implicit switch to the corresponding KT takes place. UMS uses each UT’s TEB to uniquely identify the UT. When a UT enters the kernel, an explicit switch is made to the KT that corresponds to the UT identified by the current TEB. The reason the kernel does not know which UT is running is that UTs can invoke a user-mode scheduler, as fibers do. But in UMS, the scheduler switches UTs, including switching the TEBs.

When a UT enters the kernel, its KT may block. When this happens, the kernel switches to a scheduling thread, which UMS calls a **_primary_**, and uses this thread to reenter the user-mode scheduler so that it can pick another UT to run. Eventually, a blocked KT will complete its operation and be ready to return to user mode. Since UMS has already reentered the user-mode scheduler to run a different UT, UMS queues the UT corresponding to the completed KT to a completion list in user mode. When the user-mode scheduler is choosing a new UT to switch to, it can examine the completion list and treat any UT on the list as a candidate for scheduling.

Unlike fibers, UMS is not intended to be used directly by the program- mer. The details of writing user-mode schedulers can be very challenging, and UMS does not include such a scheduler. Rather, the schedulers come from pro- gramming language libraries that build on top of UMS. Microsoft Visual Studio 2010 shippedwith Concurrency Runtime (ConcRT), a concurrent programming framework for C++. ConcRT provides a user-mode scheduler together with facilities for decomposing programs into tasks, which can then be scheduled on the available CPUs. ConcRT provides support for par for styles of con-  

**52 Appendix B Windows 7**

NTOS executive

Only primary thread runs in user-mode Trap code switches to parked KT KT blocks = primary returns to user-mode KT unblocks & parks = queue UT completion

thread parking

UT completion list

kernel user

user-mode scheduler

trap code primary thread

KT0

UT0

UT1 UT0

KT1 KT2

KT0 blocks

\> >

**Figure B.11** User-mode scheduling.

structs, aswell as rudimentary resourcemanagement and task synchronization primitives. The key features of UMS are depicted in Figure B.11.

**B.7.3.8 Winsock**

**Winsock** is the Windows sockets API. Winsock is a session-layer interface that is largely compatible with UNIX sockets but has some added Windows extensions. It provides a standardized interface to many transport protocols that may have different addressing schemes, so that any Winsock application can run on anyWinsock-compliant protocol stack.Winsock underwent amajor update in Windows Vista to add tracing, IPv6 support, impersonation, new security APIs and many other features.

Winsock follows the Windows Open System Architecture (WOSA) model, which provides a standard service provider interface (SPI) between applica- tions and networking protocols. Applications can load and unload **_layered protocols_** that build additional functionality, such as additional security, on top of the transport protocol layers. Winsock supports asynchronous opera- tions and notifications, reliable multicasting, secure sockets, and kernel mode sockets. There is also support for simpler usage models, like the WSAConnect- ByName() function, which accepts the target as strings specifying the name or IP address of the server and the service or port number of the destination port.

**B.7.4 IPC Using Windows Messaging**

Win32 applications handle interprocess communication in several ways. One way is by using shared kernel objects. Another is by using the Windows messaging facility, an approach that is particularly popular for Win32 GUI applications. One thread can send a message to another thread or to a window by calling PostMessage(), PostThreadMessage(), SendMessage(), SendThreadMessage(), or SendMessageCallback(). **_Posting_** a message and **_sending_** a message differ in this way: the post routines are asynchronous, they return immediately, and the calling thread does not know when the message  

**B.7 Programmer Interface 53**

// allocate 16 MB at the top of our address space void \*buf = VirtualAlloc(0, 0x1000000, MEM RESERVE | MEM TOP DOWN,

PAGE READWRITE); // commit the upper 8 MB of the allocated space VirtualAlloc(buf + 0x800000, 0x800000, MEM COMMIT, PAGE READWRITE); // do something with the memory . . . // now decommit the memory VirtualFree(buf + 0x800000, 0x800000, MEM DECOMMIT); // release all of the allocated address space VirtualFree(buf, 0, MEM RELEASE);

**Figure B.12** Code fragments for allocating virtual memory.

is actually delivered. The send routines are synchronous: they block the caller until the message has been delivered and processed.

In addition to sending a message, a thread can send data with the mes- sage. Since processes have separate address spaces, the data must be copied. The system copies data by calling SendMessage() to send a message of type WM COPYDATA with a COPYDATASTRUCT data structure that contains the length and address of the data to be transferred. When the message is sent, Windows copies the data to a new block of memory and gives the virtual address of the new block to the receiving process.

Every Win32 thread has its own input queue from which it receives mes- sages. If a Win32 application does not call GetMessage() to handle events on its input queue, the queue fills up, and after about five seconds, the system marks the application as “Not Responding”.

**B.7.5 Memory Management**

TheWin32 API provides several ways for an application to usememory: virtual memory, memory-mapped files, heaps, and thread-local storage.

**B.7.5.1 Virtual Memory**

An application calls VirtualAlloc() to reserve or commit virtual memory and VirtualFree() to decommit or release the memory. These functions enable the application to specify the virtual address at which the memory is allocated. They operate on multiples of the memory page size. Examples of these functions appear in Figure B.12.

A process may lock some of its committed pages into physical memory by calling VirtualLock(). The maximum number of pages a process can lock is 30, unless the process first calls SetProcessWorkingSetSize() to increase the maximum working-set size.

**B.7.5.2 Memory-Mapping Files**

Another way for an application to use memory is by memory-mapping a file into its address space. Memory mapping is also a convenient way for two  

**54 Appendix B Windows 7**

// open the file or create it if it does not exist HANDLE hfile = CreateFile("somefile", GENERIC READ | GENERIC WRITE,

FILE SHARE READ | FILE SHARE WRITE, NULL, OPEN ALWAYS, FILE ATTRIBUTE NORMAL, NULL);

// create the file mapping 8 MB in size HANDLE hmap = CreateFileMapping(hfile, PAGE READWRITE,

SEC COMMIT, 0, 0x800000, "SHM 1"); // now get a view of the space mapped void \*buf = MapViewOfFile(hmap, FILE MAP ALL ACCESS,

0, 0, 0, 0x800000); // do something with the mapped file . . . // now unmap the file UnMapViewOfFile(buf); CloseHandle(hmap); CloseHandle(hfile);

**Figure B.13** Code fragments for memory mapping of a file.

processes to share memory: both processes map the same file into their virtual memory. Memory mapping is a multistage process, as you can see in the example in Figure B.13.

If a processwants tomap some address space just to share amemory region with another process, no file is needed. The process calls CreateFileMap- ping() with a file handle of 0xffffffff and a particular size. The resulting file-mapping object can be shared by inheritance, by name lookup, or by handle duplication.

**B.7.5.3 Heaps**

Heaps provide a third way for applications to use memory, just as with mal- loc() and free() in standard C. A heap in the Win32 environment is a region of reserved address space. When a Win32 process is initialized, it is created with a**default heap**. SincemostWin32 applications aremultithreaded, access to the heap is synchronized to protect the heap’s space-allocation data structures from being damaged by concurrent updates by multiple threads.

Win32 provides several heap-management functions so that a process can allocate and manage a private heap. These functions are HeapCreate(), Hea- pAlloc(), HeapRealloc(), HeapSize(), HeapFree(), and HeapDestroy(). The Win32 API also provides the HeapLock() and HeapUnlock() functions to enable a thread to gain exclusive access to a heap. Unlike VirtualLock(), these functions perform only synchronization; they do not lock pages into physical memory.

The original Win32 heap was optimized for efficient use of space. This led to significant problems with fragmentation of the address space for larger server programs that ran for long periods of time. A new **low-fragmentation heap** (**LFH**) design introduced in Windows XP greatly reduced the fragmen-  

**Summary 55**

// reserve a slot for a variable DWORD var index = T1sAlloc(); // set it to the value 10 T1sSetValue(var index, 10); // get the value int var T1sGetValue(var index); // release the index T1sFree(var index);

**Figure B.14** Code for dynamic thread-local storage.

tation problem. The Windows 7 heap manager automatically turns on LFH as appropriate.

**B.7.5.4 Thread-Local Storage**

Afourth way for applications to use memory is through a **thread-local storage** (**TLS**) mechanism. Functions that rely on global or static data typically fail to work properly in a multithreaded environment. For instance, the C run-time function strtok() uses a static variable to keep track of its current position while parsing a string. For two concurrent threads to execute strtok() cor- rectly, they need separate current position variables. TLS provides a way to maintain instances of variables that are global to the function being executed but not shared with any other thread.

TLS provides both dynamic and static methods of creating thread-local storage. The dynamic method is illustrated in Figure B.14. The TLS mechanism allocates global heap storage and attaches it to the thread environment block thatWindows allocates to every user-mode thread. The TEB is readily accessible by each thread and is used not just for TLS but for all the per-thread state information in user mode.

To use a thread-local static variable, the application declares the variable as follows to ensure that every thread has its own private copy:

declspec(thread) DWORD cur pos = 0;

**B.8 Summary**

Microsoft designed Windows to be an extensible, portable operating system —one able to take advantage of new techniques and hardware. Windows supports multiple operating environments and symmetric multiprocessing, including both 32-bit and 64-bit processors and NUMA computers. The use of kernel objects to provide basic services, along with support for client–server computing, enablesWindows to support awide variety of application environ- ments.Windows provides virtualmemory, integrated caching, and preemptive scheduling. It supports elaborate security mechanisms and includes interna- tionalization features. Windows runs on a wide variety of computers, so users can choose and upgrade hardware to match their budgets and performance requirements without needing to alter the applications they run.  

**56 Appendix B Windows 7**

**Practice Exercises**

**B.1** What type of operating system is Windows? Describe two of its major features.

**B.2** List the design goals of Windows. Describe two in detail.

**B.3** Describe the booting process for a Windows system.

**B.4** Describe the three main architectural layers of the Windows kernel.

**B.5** What is the job of the object manager?

**B.6** What types of services does the process manager provide?

**B.7** What is a local procedure call?

**B.8** What are the responsibilities of the I/O manager?

**B.9** What types of networking doesWindows support? HowdoesWindows implement transport protocols? Describe two networking protocols.

**B.10** How is the NTFS namespace organized?

**B.11** How does NTFS handle data structures? How does NTFS recover from a system crash? What is guaranteed after a recovery takes place?

**B.12** How does Windows allocate user memory?

**B.13** Describe some of the ways in which an application can use memory via the Win32 API.

**Further Reading**

\[Russinovich et al. (2017)\] provides an overview of Windows 7 and consider- able technical detail about system internals and components. \[Brown (2000)\] presents details of the security architecture of Windows.

The Microsoft Developer Network Library (http://msdn.microsoft.com) supplies a wealth of information on Windows and other Microsoft products, including documentation of all the published APIs.

\[Iseminger (2000)\] provides a good reference on theWindowsActiveDirec- tory. Detailed discussions of writing programs that use the Win32 API appear in \[Richter (1997)\].

The source code for a 2005 WRK version of the Windows kernel, together with a collection of slides and other CRK curriculummaterials, is available from www.microsoft.com/WindowsAcademic for use by universities.

**Bibliography**

**\[Brown (2000)\]** K. Brown, _Programming Windows Security_, Addison-Wesley (2000).

**\[Iseminger (2000)\]** D. Iseminger, _Active Directory Services for Microsoft Windows 2000. Technical Reference_, Microsoft Press (2000).  

**Bibliography 57**

**\[Richter (1997)\]** J. Richter, _Advanced Windows_, Microsoft Press (1997).

**\[Russinovich et al. (2017)\]** M.Russinovich,D.A. Solomon, andA. Ionescu,_Win- dows Internals–Part 1,_ Seventh Edition, Microsoft Press (2017).  

_C_**Appendix**

_BSD UNIX_

**This chapter was firs written in 1991 and has been updated over time.**

In Chapter 20, we presented an in-depth examination of the Linux operating system. In this chapter, we examine another popular UNIX version—UnixBSD. We start by presenting a brief history of the UNIX operating system. We then describe the system’s user and programmer interfaces. Finally, we discuss the internal data structures and algorithms used by the FreeBSD kernel to support the user–programmer interface.

**C.1 UNIX History**

The first version of UNIX was developed in 1969 by Ken Thompson of the Research Group at Bell Laboratories to use an otherwise idle PDP-7. Thomp- son was soon joined by Dennis Ritchie and they, with other members of the Research Group, produced the early versions of UNIX.

Ritchie had previously worked on the MULTICS project, and MULTICS had a strong influence on the newer operating system. Even the name **_UNIX_** is a pun on**_MULTICS_**. The basic organization of the file system, the idea of the command interpreter (or the shell) as a user process, the use of a separate process for each command, the original line-editing characters (# to erase the last character and @ to erase the entire line), and numerous other features came directly from MULTICS. Ideas from other operating systems, such as MIT’s CTSS and the XDS-940 system, were also used.

Ritchie and Thompson worked quietly on UNIX for many years. They moved it to a PDP-11/20 for a second version; for a third version, they rewrote most of the operating system in the systems-programming language C, instead of the previously used assembly language. C was developed at Bell Laborato- ries to support UNIX. UNIX was also moved to larger PDP-11 models, such as the 11/45 and 11/70. Multiprogramming and other enhancements were added when it was rewritten in C and moved to systems (such as the 11/45) that had hardware support for multiprogramming.

As UNIX developed, it became widely used within Bell Laboratories and gradually spread to a few universities. The first version widely available out-

**1**  

**2 Appendix C BSD UNIX**

side Bell Laboratories was Version 6, released in 1976. (The version number for early UNIX systems corresponds to the edition number of the _UNIX Program- mer’s Manual_ that was current when the distribution was made; the code and the manual were revised independently.)

In 1978, Version 7 was distributed. This UNIX system ran on the PDP-11/70 and the Interdata 8/32 and is the ancestor of most modern UNIX systems. In particular, it was soon ported to other PDP-11 models and to the VAX com- puter line. The version available on the VAX was known as 32V. Research has continued since then.

**C.1.1 UNIX Support Group**

After the distribution of Version 7 in 1978, the UNIX Support Group (USG) assumed administrative control and responsibility from the Research Group for distributions of UNIX within AT&T, the parent organization for Bell Labora- tories. UNIX was becoming a product, rather than simply a research tool. The Research Group continued to develop their own versions of UNIX, however, to support their internal computing. Version 8 included a facility called the **stream I/O system**, which allows flexible configuration of kernel IPC modules. It also contained RFS, a remote file system similar to Sun’s NFS. The current version is Version 10, released in 1989 and available only within Bell Laboratories.

USG mainly provided support for UNIX within AT&T. The first external distribution from USG was System III, in 1982. System III incorporated features of Version 7 and 32V, as well as features of several UNIX systems developed by groups other than Research. For example, features of UNIX/RT, a real-time UNIX system, and numerous portions of the Programmer’s Work Bench (PWB) software tools package were included in System III.

USG released System V in 1983; it is largely derived from System III. The divestiture of the various Bell operating companies from AT&T left AT&T in a position to market System V aggressively. USG was restructured as the UNIX System Development Laboratory (USDL), which released UNIX System V Release 2 (V.2) in 1984. UNIX System V Release 2, Version 4 (V.2.4) added a new implementation of virtualmemorywith copy-on-write paging and shared memory. USDL was in turn replaced by AT&T Information Systems (ATTIS), which distributed System V Release 3 (V.3) in 1987. V.3 adapts the V8 imple- mentation of the stream I/O system and makes it available as **_STREAMS_**. It also includes RFS, the NFS-like remote file system mentioned earlier.

**C.1.2 Berkeley Begins Development**

The small size, modularity, and clean design of early UNIX systems led to UNIX- based work at numerous other computer-science organizations, such as RAND, BBN, the University of Illinois, Harvard, Purdue, and DEC. Themost influential UNIX development group outside of Bell Laboratories and AT&T, however, has been the University of California at Berkeley.

Bill Joy and Ozalp Babaoglu did the first Berkeley VAX UNIX work in 1978. They added virtual memory, demand paging, and page replacement to 32V to produce 3BSD UNIX. This version was the first to implement any of these facilities on a UNIX system. The large virtual memory space of 3BSD allowed the development of very large programs, such as Berkeley’s own Franz LISP. The memory-management work convinced the Defense Advanced Research  

**C.1 UNIX History 3**

Projects Agency (DARPA) to fund Berkeley for the development of a standard UNIX system for government use; 4BSD UNIX was the result.

The 4 BSD work for DARPA was guided by a steering committee that included many notable people from the UNIX and networking communities. One of the goals of this project was to provide support for the DARPA Inter- net networking protocols (TCP/IP). This support was provided in a general manner. It is possible in 4.2 BSD to communicate uniformly among diverse network facilities, including local-area networks (such as Ethernets and token rings) andwide-area networks (such as NSFNET). This implementationwas the most important reason for the current popularity of these protocols. Many ven- dors of UNIX computer systems used it as the basis for their implementations, and it was even used in other operating systems. It permitted the Internet to grow from 60 connected networks in 1984 to more than 8,000 networks and an estimated 10 million users in 1993.

In addition, Berkeley adaptedmany features from contemporary operating systems to improve the design and implementation of UNIX. Many of the terminal line-editing functions of the TENEX (TOPS-20) operating system were provided by a new terminal driver. A new user interface (the C Shell), a new text editor (ex/vi), compilers for Pascal and LISP, and many new systems programswerewritten at Berkeley. For 4.2 BSD, certain efficiency improvements were inspired by the VMS operating system.

UNIX software from Berkeleywas released in **Berkeley Software Distribu- tions (BSD)**. It is convenient to refer to the BerkeleyVAXUNIX systems following 3 BSD as 4 BSD, but there were actually several specific releases, most notably 4.1 BSD and 4.2 BSD; 4.2 BSD, first distributed in 1983, was the culmination of the original Berkeley DARPA UNIX project. The equivalent version for PDP-11 systems was 2.9 BSD.

In 1986, 4.3 BSD was released. It was very similar to 4.2 BSD but included numerous internal changes, such as bug fixes and performance improvements. Some new facilities were also added, including support for the Xerox Network System protocols.

The next version was 4.3 BSD Tahoe, released in 1988. It included improved networking congestion control and TCP/IP performance. Disk configurations were separated from the device drivers and read off the disks themselves. Expanded time-zone support was also included. 4.3 BSD Tahoe was actually developed on and for the CCI Tahoe system (Computer Console, Inc., Power 6 computer), rather than for the usual VAX base. The corresponding PDP-11 release was 2.10.1BSD; it was distributed by the USENIX association, which also published the 4.3 BSD manuals. The 4.3.2 BSD Reno release saw the inclusion of an implementation of ISO/OSI networking.

The last Berkeley release, 4.4 BSD, was finalized in June of 1993. It included new X.25 networking support and POSIX standard compliance. It also had a radically new file system organization, with a new virtual file system interface and support for **_stackable_** file systems, allowing file systems to be layered on top of each other for easy inclusion of new features. An implementation of NFS was included in the release (Section 15.8), along with a new log-based file system (see Chapter 11). The 4.4 BSD virtual memory system was derived from Mach (described in Section A.13). Several other changes, such as enhanced security and improved kernel structure, were also included. With the release of version 4.4, Berkeley halted its research efforts.  

**4 Appendix C BSD UNIX**

**C.1.3 The Spread of UNIX**

UNIX 4 BSD was the operating system of choice for the VAX from its initial release (in 1979) until the release of Ultrix, DEC’s BSD implementation. Indeed, 4 BSD is still the best choice for many research and networking installations. The current set of UNIX operating systems is not limited to those from Bell Laboratories (which is currently owned by Lucent Technology) and Berkeley, however. SunMicrosystems helped popularize the BSD flavor of UNIX by ship- ping it on Sun workstations. As UNIX grew in popularity, it was moved to many computers and computer systems. A wide variety of UNIX and UNIX- like operating systems have been created. DEC supported its UNIX (Ultrix) on its workstations and is replacing Ultrix with another UNIX-derived operating system, OSF/1. Microsoft rewrote UNIX for the Intel 8088 family and called it XENIX, and its Windows NT operating system was heavily influenced by UNIX. IBM has UNIX (AIX) on its PCs, workstations, and mainframes. In fact, UNIX is available on almost all general-purpose computers. It runs on personal computers, workstations, minicomputers, mainframes, and supercomputers, from Apple Macintosh IIs to Cray IIs. Because of its wide availability, it is used in environments ranging from academic to military to manufacturing process control. Most of these systems are based on Version 7, System III, 4.2 BSD, or System V.

The wide popularity of UNIX with computer vendors has made UNIX the most portable of operating systems, and users can expect a UNIX environment independent of any specific computer manufacturer. But the large number of implementations of the system has led to remarkable variation in the program- ming and user interfaces distributed by the vendors. For true vendor indepen- dence, application-program developers need consistent interfaces. Such inter- faces would allow all “UNIX” applications to run on all UNIX systems, which is certainly not the current situation. This issue has become important as UNIX has become the preferred program-development platform for applications ranging from databases to graphics and networking, and it has led to a strong market demand for UNIX standards.

Several standardization projects have been undertaken. The first was the **_/usr/group 1984 Standard_**, sponsored by the UniForum industry user’s group. Since then, many official standards bodies have continued the effort, including IEEE and ISO (the POSIX standard). The X/Open Group international consor- tium completed XPG3, a Common Application Environment, which subsumes the IEEE interface standard. Unfortunately, XPG3 is based on a draft of the ANSI C standard rather than the final specification, and therefore needed to be redone as XPG4. In 1989, the ANSI standards body standardized the C program- ming language, producing an ANSI C specification that vendors were quick to adopt.

As such projects continue, the flavors of UNIX will converge and lead to one programming interface to UNIX, allowing UNIX to become even more popular. In fact, two separate sets of powerful UNIX vendors are working on this problem: The AT&T-guided UNIX International (UI) and the Open Software Foundation (OSF) have both agreed to follow the POSIX standard. Recently, many of the vendors involved in those two groups have agreed on further standardization (the COSE agreement).  

**C.1 UNIX History 5**

1969

1973

1976

1977

1978

1979

1980

1981

1982

1983

1984

1985

1986

1987

1988

1989

1990

1991

1992

1993

_USG/USDL/ATTIS DSG/USO/USL_

_Bell Labs Research_

_Berkley Software_

_Distributions_

First Edition

Fifth Edition

Sixth Edition

3.0

3.0.1

4.0.1

5.0

5.2 System V

System III

PWB MERT CB UNIX

UNIX/RT

2.10BSD

2.9BSD 4.1cBSD

4.1aBSD

2.8BSD

2BSD

4.0BSD

3BSD

1BSD

32V

Solaris

Solaris 2

SunOS 4

SunOS 3

SunOS

Eighth Edition

Ninth Edition

Tenth Edition

Plan 9

4.4BSD

4.3BSD Reno

4.3BSD Tahoe

4.3BSD

Seventh Edition

Chorus

Chorus V3

System V Release 3

System V Release 2

XENIX

XENIX 3

XENIX 5

OSF/1

Mach

4.2BSD

4.1BSD

UNIX System V Release 4

VAX

PDP-11PDP-11

VAX

**Figure C.1** History of UNIX versions up to 1993.

AT&T replaced its ATTIS group in 1989with the UNIX Software Organization (USO), which shipped the first merged UNIX, System V Release 4. This system combines features from System V, 4.3 BSD, and Sun’s SunOS, including long file names, the Berkeley file system, virtual memory management, symbolic links, multiple access groups, job control, and reliable signals; it also conforms to the published POSIX standard, POSIX.1. After USO produced SVR4, it became an independent AT&T subsidiary named Unix System Laboratories (USL); in 1993, it was purchased byNovell, Inc. Figure C.1 summarizes the relationships among the various versions of UNIX.  

**6 Appendix C BSD UNIX**

The UNIX system has grown from a personal project of two Bell Labora- tories employees to an operating system defined by multinational standard- ization bodies. At the same time, UNIX is an excellent vehicle for academic study, and we believe it will remain an important part of operating-system theory and practice. For example, the Tunis operating system, the Xinu oper- ating system, and the Minix operating system are based on the concepts of UNIX but were developed explicitly for classroom study. There is a plethora of ongoing UNIX-related research systems, including Mach, Chorus, Comandos, and Roisin. The original developers, Ritchie and Thompson, were honored in 1983 by theAssociation forComputingMachineryTuringAward for theirwork on UNIX.

**C.1.4 History of FreeBSD**

The specific UNIX version used in this chapter is the Intel version of FreeBSD. This system implements many interesting operating-system concepts, such as demand paging with clustering, as well as networking. The FreeBSD project began in early 1993 to produce a snapshot of 386 BSD to solve problems that could not be resolvedusing the existing patchmechanism. 386 BSDwas derived from 4.3 BSD-Lite (Net/2) and was released in June 1992 by William Jolitz. FreeBSD (coined by David Greenman) 1.0 was released in December 1993, and FreeBSD 1.1was released inMay 1994. Both versionswere based on 4.3 BSD-Lite. Legal issues betweenUCB andNovell required that 4.3 BSD-Lite code no longer be used, so the final 4.3 BSD-Lite releasewasmade in July 1994 (FreeBSD 1.1.5.1).

FreeBSD was then reinvented based on 4.4BSD-Lite code, which was incom- plete. FreeBSD 2.0 was released in November 1994. Later releases included 2.0.5 in June 1995, 2.1.5 in August 1996, 2.1.7.1 in February 1997, 2.2.1 in April 1997, 2.2.8 in November 1998, 3.0 in October 1998, 3.1 in February 1999, 3.2 in May 1999, 3.3 in September 1999, 3.4 inDecember 1999, 3.5 in June 2000, 4.0 inMarch 2000, 4.1 in July 2000, and 4.2 in November 2000.

The goal of the FreeBSD project is to provide software that can be used for any purpose with no strings attached. The idea is that the code will get the widest possible use and provide the most benefit. At present, it runs primarily on Intel platforms, althoughAlphaplatforms are supported.Work is underway to port to other processor platforms as well.

**C.2 Design Principles**

UNIX was designed to be a time-sharing system. The standard user interface (the shell) is simple and can be replaced by another, if desired. The file system is a multilevel tree, which allows users to create their own subdirectories. Each user data file is simply a sequence of bytes.

Disk files and I/O devices are treated as similarly as possible. Thus, device dependencies and peculiarities are kept in the kernel asmuch as possible. Even in the kernel, most of them are confined to the device drivers.

UNIX supports multiple processes. A process can easily create new pro- cesses. CPU scheduling is a simple priority algorithm. FreeBSD uses demand  

**C.2 Design Principles 7**

paging as a mechanism to support memory-management and CPU-scheduling decisions. Swapping is used if a system is suffering from excess paging.

Because UNIX was originated by Thompson and Ritchie as a system for their own convenience, it was small enough to understand. Most of the algo- rithms were selected for **_simplicity_**, not for speed or sophistication. The intent was to have the kernel and libraries provide a small set of facilities thatwas suf- ficiently powerful to allow a person to build a more complex system if needed. UNIX’s clean design has resulted in many imitations and modifications.

Although the designers of UNIX had a significant amount of knowledge about other operating systems, UNIX had no elaborate design spelled out before its implementation. This flexibility appears to have been one of the key factors in the development of the system. Some design principles were involved, however, even though they were not made explicit at the outset.

The UNIX system was designed by programmers for programmers. Thus, it has always been interactive, and facilities for program development have always been a high priority. Such facilities include the program **_make_** (which can be used to check which of a collection of source files for a program need to be compiled and then to do the compiling) and the **_Source Code Control System (SCCS)_** (which is used to keep successive versions of files available without having to store the entire contents of each step). The primary version-control system used by UNIX is the **_Concurrent Versions System_** (CVS) due to the large number of developers operating on and using the code.

The operating system is written mostly in C, which was developed to support UNIX, since neither Thompson nor Ritchie enjoyed programming in assembly language. The avoidance of assembly language was also necessary because of the uncertainty about the machines on which UNIX would be run. It has greatly simplified the problems ofmoving UNIX from one hardware system to another.

From the beginning, UNIX development systems have had all the UNIX sources available online, and the developers have used the systems under development as their primary systems. This pattern of development has greatly facilitated the discovery of deficiencies and their fixes, as well as of new possibilities and their implementations. It has also encouraged the plethora of UNIX variants existing today, but the benefits have outweighed the disadvantages. If something is broken, it can be fixed at a local site; there is no need to wait for the next release of the system. Such fixes, as well as new facilities, may be incorporated into later distributions.

The size constraints of the PDP-11 (and earlier computers used for UNIX) have forced a certain elegance.Where other systems have elaborate algorithms for dealing with pathological conditions, UNIX just does a controlled crash called **_panic_**. Instead of attempting to cure such conditions, UNIX tries to pre- vent them. Where other systems would use brute force or macro-expansion, UNIX mostly has had to develop more subtle, or at least simpler, approaches.

These early strengths of UNIX produced much of its popularity, which in turn produced new demands that challenged those strengths. UNIX was used for tasks such as networking, graphics, and real-time operation, which did not always fit into its original text-oriented model. Thus, changes were made to certain internal facilities, and new programming interfaces were added. Supporting these new facilities and others—particularly window interfaces  

**8 Appendix C BSD UNIX**

—required large amounts of code, radically increasing the size of the system. For instance, both networking and windowing doubled the size of the system. This pattern in turn pointed out the continued strength of UNIX—whenever a new development occurred in the industry, UNIX could usually absorb it but remain UNIX.

**C.3 Programmer Interface**

Like most operating systems, UNIX consists of two separable parts: the kernel and the systems programs. We can view the UNIX operating system as being layered, as shown in FigureC.2. Everything below the system-call interface and above the physical hardware is the **_kernel_**. The kernel provides the file system, CPU scheduling, memory management, and other operating-system functions through system calls. Systems programs use the kernel-supported system calls to provide useful functions, such as compilation and file manipulation.

System calls define the **_programmer interface_** to UNIX. The set of systems programs commonly available defines the **_user interface_**. The programmer and user interface define the context that the kernel must support.

Most systems programs are written in C, and the **_UNIX Programmer’s Manual_** presents all system calls as C functions. Asystem programwritten in C for FreeBSD on the Pentium can generally bemoved to anAlpha FreeBSD system and simply recompiled, even though the two systems are quite different. The details of system calls are known only to the compiler. This feature is a major reason for the portability of UNIX programs.

System calls for UNIX can be roughly grouped into three categories: file manipulation, process control, and information manipulation. In Chapter 2, we listed a fourth category, device manipulation, but since devices in UNIX are treated as (special) files, the same system calls support both files and devices (although there is an extra system call for setting device parameters).

(the users)

shells and commands compilers and interpreters

system libraries

_system-call interface to the kernel_

_kernel interface to the hardware_

file system swapping block I/O

system disk and tape drivers

CPU scheduling page replacement demand paging virtual memory

signals terminal handling

character I/O system terminal drivers

device controllers disks and tapes

memory controllers physical memory

terminal controllers terminals

**Figure C.2** 4.4BSD layer structure.  

**C.3 Programmer Interface 9**

**C.3.1 File Manipulation**

A **_file_** in UNIX is a sequence of bytes. Different programs expect various levels of structure, but the kernel does not impose a structure on files. For instance, the convention for text files is lines of ASCII characters separated by a single newline character (which is the linefeed character in ASCII), but the kernel knows nothing of this convention.

Files are organized in tree-structured **_directories_**. Directories are them- selves files that contain information on how to find other files. A **_path name_** to a file is a text string that identifies a file by specifying a path through the directory structure to the file. Syntactically, it consists of individual file-name elements separated by the slash character. For example, in _/usr/local/font_, the first slash indicates the root of the directory tree, called the **_root directory_**. The next element, _usr,_ is a subdirectory of the root, _local_ is a subdirectory of _usr_, and _font_ is a file or directory in the directory **_local_**. Whether _font_ is an ordinary file or a directory cannot be determined from the path-name syntax.

The UNIX file system has both **_absolute path names_** and **_relative path names_**. Absolute path names start at the root of the file system and are dis- tinguished by a slash at the beginning of the path name; _/usr/local/font_ is an absolute path name. Relative path names start at the **_current directory_**, which is an attribute of the process accessing the path name. Thus, _local/font_ indicates a file or directory named _font_ in the directory _local_ in the current directory, which might or might not be _/usr._

A file may be known by more than one name in one or more directories. Such multiple names are known as **_links_**, and all links are treated equally by the operating system. FreeBSD also supports **_symbolic links_**, which are files containing the path name of another file. The two kinds of links are also known as **_hard links_** and **_soft links_**. Soft (symbolic) links, unlike hard links, may point to directories and may cross file-system boundaries.

The file name “.” in a directory is a hard link to the directory itself. The file name “..” is a hard link to the parent directory. Thus, if the current directory is _/user/jlp/programs,_ then _../bin/wdf_ refers to _/user/jlp/bin/wdf._

Hardware devices have names in the file system. These **_device special files_** or **_special files_** are known to the kernel as device interfaces, but they are nonetheless accessed by the user by much the same system calls as are other files.

Figure C.3 shows a typical UNIX file system. The root (_/_ ) normally contains a small number of directories as well as _/kernel,_ the binary boot image of the operating system; _/dev_ contains the device special files, such as _/dev/console, /dev/lp0, /dev/mt0,_ and so on; and _/bin_ contains the binaries of the essential UNIX systems programs. Other binaries may be in _/usr/bin_ (for applications systems programs, such as text formatters), _/usr/compat_ (for programs from other operating systems, such as Linux), or _/usr/local/bin_ (for systems programs written at the local site). Library files—such as the C, Pascal, and FORTRAN subroutine libraries—are kept in _/lib_ (or _/usr/lib_ or _/usr/local/lib_).

The files of users themselves are stored in a separate directory for each user, typically in _/usr._ Thus, the user directory for _carol_ would normally be in _/usr/carol._ For a large system, these directories may be further grouped to ease administration, creating a file structure with _/usr/prof/avi_ and _/usr/staff/carol._ Administrative files and programs, such as the password file, are kept in _/etc._  

**10 Appendix C BSD UNIX**

_bin troff_

_spell_

_ucb man_

_telnet_

_local lib_

_bin_

_include_

_lib troff_

_tmac_

_tmp_

_vmunix_

_dev_

_lib_

_user_

_etc_

_tmp_

_console_

_lp0_

_sh_

_csh_

_libc.a_

_usr_

_jlp_

_avi_

_passwd_

_group_

_init_

_bin_

_/_

• • •

• • •

• • •

• • •

• • •

• • •

• • •

• • •

• • •

• • •

**Figure C.3** Typical UNIX directory structure.

Temporary files can be put in _/tmp,_ which is normally erased during system boot, or in _/usr/tmp._

Each of these directories may have considerably more structure. For exam- ple, the font-description tables for the troff formatter for the Merganthaler 202  

**C.3 Programmer Interface 11**

typesetter are kept in _/usr/lib/troff/dev202._ All the conventions concerning the location of specific files and directories have been defined by programmers and their programs. The operating-system kernel needs only _/etc/init,_which is used to initialize terminal processes, to be operable.

System calls for basic file manipulation are creat(), open(), read(), write(), close(), unlink(), and trunc(). The creat() system call, given a path name, creates an empty file (or truncates an existing one). An existing file is opened by the open() system call, which takes a path name and a mode (such as read, write, or read–write) and returns a small integer, called a **_file descriptor_**. The file descriptor may then be passed to a read() or write() system call (along with a buffer address and the number of bytes to transfer) to performdata transfers to or from the file. Afile is closedwhen its file descriptor is passed to the close() system call. The trunc() call reduces the length of a file to 0.

A file descriptor is an index into a small table of open files for this process. Descriptors start at 0 and seldom get higher than 6 or 7 for typical programs, depending on the maximum number of simultaneously open files.

Each read() or write() updates the current offset into the file, which is associated with the file-table entry and is used to determine the position in the file for the next read() or write(). The lseek() system call allows the position to be reset explicitly. It also allows the creation of sparse files (fileswith “holes” in them). The dup() and dup2() system calls can be used to produce a new file descriptor that is a copy of an existing one. The fcntl() system call can also do that and in addition can examine or set various parameters of an open file. For example, it can make each succeeding write() to an open file append to the end of that file. There is an additional system call, ioctl(), for manipulating device parameters. It can set the baud rate of a serial port or rewind a tape, for instance.

Information about the file (such as its size, protection modes, owner, and so on) can be obtained by the stat() system call. Several system calls allow some of this information to be changed: rename() (change file name), chmod() (change the protection mode), and chown() (change the owner and group). Many of these system calls have variants that apply to file descriptors instead of file names. The link() system call makes a hard link for an existing file, creating a new name for an existing file. A link is removed by the unlink(()) system call; if it is the last link, the file is deleted. The symlink() system call makes a symbolic link.

Directories are made by the mkdir() system call and are deleted by rmdir(). The current directory is changed by cd().

Although the standardfile calls (open() and others) can be used ondirecto- ries, it is inadvisable to do so, since directories have an internal structure that must be preserved. Instead, another set of system calls is provided to open a directory, to step through each file entry within the directory, to close the directory, and to perform other functions; these are opendir(), readdir(), closedir(), and others.

**C.3.2 Process Control**

A **_process_** is a program in execution. Processes are identified by their **_process identifier,_** which is an integer. A new process is created by the fork() system  

**12 Appendix C BSD UNIX**

call. The new process consists of a copy of the address space of the original process (the same program and the same variables with the same values). Both processes (the parent and the child) continue execution at the instruction after the fork() with one difference: the return code for the fork() is zero for the new (child) process, whereas the (nonzero) process identifier of the child is returned to the parent.

Typically, the execve() system call is used after a fork by one of the two processes to replace that process’s virtual memory space with a new program. The execve() system call loads a binary file into memory (destroying the memory image of the program containing the execve() system call) and starts its execution.

A process may terminate by using the exit() system call, and its parent process may wait for that event by using the wait() system call. If the child process crashes, the system simulates the exit() call. The wait() system call provides the process ID of a terminated child so that the parent can tell which of possibly many children terminated. A second system call, wait3(), is similar to wait() but also allows the parent to collect performance statistics about the child. Between the time the child exits and the time the parent completes one of the wait() system calls, the child is **_defunct_**. Adefunct process can do nothing but exists merely so that the parent can collect its status information. If the parent process of a defunct process exits before a child, the defunct process is inherited by the init process (which in turnwaits on it) and becomes a **_zombie_** process. A typical use of these facilities is shown in Figure C.4.

The simplest form of communication between processes is by **_pipes_**. Apipe may be created before the fork(), and its endpoints are then set up between the fork() and the execve(). A pipe is essentially a queue of bytes between two processes. The pipe is accessed by a file descriptor, like an ordinary file. One process writes into the pipe, and the other reads from the pipe. The size of the original pipe system was fixed by the system. With FreeBSD pipes are implemented on top of the socket system, which has variable-sized buffers. Reading from an empty pipe or writing into a full pipe causes the process to be blocked until the state of the pipe changes. Special arrangements are needed for a pipe to be placed between a parent and child (so only one is reading and one is writing).

All user processes are descendants of one original process, called init (which has process identifier 1). Each terminal port available for interactive use has a getty process forked for it by init. The getty process initializes termi- nal line parameters and waits for a user’s login name, which it passes through

shell process parent process shell process

child process zombie process

execve program

program executes exit

waitfork

**Figure C.4** A shell forks a subprocess to execute a program.  

**C.3 Programmer Interface 13**

an execve() as an argument to a login process. The login process collects the user’s password, encrypts it, and compares the result to an encrypted string taken from the file _/etc/passwd._ If the comparison is successful, the user is allowed to log in. The login process executes a **_shell_**, or command interpreter, after setting the numeric **_user identifier_** of the process to that of the user logging in. (The shell and the user identifier are found in _/etc/passwd_ by the user’s login name.) It is with this shell that the user ordinarily communicates for the rest of the login session. The shell itself forks subprocesses for the commands the user tells it to execute.

The user identifier is usedby the kernel to determine the user’s permissions for certain system calls, especially those involving file accesses. There is also a **_group identifier,_** which is used to provide similar privileges to a collection of users. In FreeBSD a process may be in several groups simultaneously. The login process puts the shell in all the groups permitted to the user by the files _/etc/passwd_ and _/etc/group._

Two user identifiers are used by the kernel: the effective user identifier and the real user identifier. The **_effective user identifier_** is used to determine file access permissions. If the file of a program being loaded by an execve() has the setuid bit set in its inode, the effective user identifier of the process is set to the user identifier of the owner of the file, whereas the **_real user identifier_** is left as it was. This scheme allows certain processes to have more than ordinary privileges while still being executable by ordinary users. The setuid idea was patented by Dennis Ritchie (U.S. Patent 4,135,240) and is one of the distinctive features of UNIX. A similar setgid bit exists for groups. A process may determine its real and effective user identifier with the getuid() and geteuid() calls, respectively. The getgid() and getegid() calls determine the process’s real and effective group identifier, respectively. The rest of a process’s groups may be found with the getgroups() system call.

**C.3.3 Signals**

**_Signals_** are a facility for handling exceptional conditions similar to software interrupts. There are 20 different signals, each corresponding to a distinct condition. A signal may be generated by a keyboard interrupt, by an error in a process (such as a bad memory reference), or by a number of asynchronous events (such as timers or job-control signals from the shell). Almost any signal may also be generated by the kill() system call.

The interrupt signal, SIGINT, is used to stop a command before that com- mand completes. It is usually produced by the ˆC character (ASCII 3). As of 4.2BSD, the important keyboard characters are defined by a table for each termi- nal and can be redefined easily. The quit signal, SIGQUIT, is usually produced by the ˆbs character (ASCII 28). The quit signal both stops the currently execut- ing program and dumps its current memory image to a file named _core_ in the current directory. The core file can be used by debuggers. SIGILL is produced by an illegal instruction and SIGSEGV by an attempt to address memory outside of the legal virtual memory space of a process.

Arrangements can be made either for most signals to be ignored (to have no effect) or for a routine in the user process (a signal handler) to be called. A signal handler may safely do one of two things before returning from catching a signal: call the exit() system call or modify a global variable. One signal  

**14 Appendix C BSD UNIX**

(the kill signal, number 9, SIGKILL) cannot be ignored or caught by a signal handler. SIGKILL is used, for example, to kill a runaway process that is ignoring other signals such as SIGINT and SIGQUIT.

Signals can be lost. If another signal of the same kind is sent before a previous signal has been accepted by the process to which it is directed, the first signal will be overwritten, and only the last signal will be seen by the process. In other words, a call to the signal handler tells a process that there has been at least one occurrence of the signal. Also, there is no relative priority among UNIX signals. If two different signals are sent to the same process at the same time, we cannot know which one the process will receive first.

Signals were originally intended to deal with exceptional events. As is true of most UNIX features, however, signal use has steadily expanded. 4.1BSD introduced job control, which uses signals to start and stop subprocesses on demand. This facility allows one shell to control multiple processes—starting, stopping, and backgrounding them as the user wishes. The SIGWINCH signal, invented by SunMicrosystems, is used for informing aprocess that thewindow in which output is being displayed has changed size. Signals are also used to deliver urgent data from network connections.

Users wanted more reliable signals and a bug fix in an inherent race condi- tion in the old signal implementation. Thus, 4.2BSD brought with it a race-free, reliable, separately implemented signal capability. It allows individual signals to be blocked during critical sections, and it has a new system call to let a pro- cess sleep until interrupted. It is similar to hardware-interrupt functionality. This capability is now part of the POSIX standard.

**C.3.4 Process Groups**

Groups of related processes frequently cooperate to accomplish a common task. For instance, processes may create, and communicate over, pipes. Such a set of processes is termed a **_process group_**, or a **_job_**. Signals may be sent to all processes in a group. A process usually inherits its process group from its parent, but the setpgrp() system call allows a process to change its group.

Process groups are used by the C shell to control the operation of mul- tiple jobs. Only one process group may use a terminal device for I/O at any time. This **_foreground_** job has the attention of the user on that terminal, while all other nonattached jobs (**_background_** jobs) perform their functions without user interaction. Access to the terminal is controlled by process group signals. Each job has a **_controlling terminal_** (again, inherited from its parent). If the process group of the controlling terminal matches the group of a process, that process is in the foreground and is allowed to perform I/O. If a nonmatching (background) process attempts the same, a SIGTTIN or SIGTTOU signal is sent to its process group. This signal usually causes the process group to freeze until it is foregrounded by the user, at which point it receives a SIGCONT signal, indicating that the process can perform the I/O. Similarly, a SIGSTOP may be sent to the foreground process group to freeze it.

**C.3.5 Information Manipulation**

System calls exist to set and return both an interval timer (getitimer()/ setitimer()) and the current time (gettimeofday()/settimeofday()) in  

**C.4 User Interface 15**

microseconds. In addition, processes can ask for their process identifier (get- pid()), their group identifier (getgid()), the name of the machine on which they are executing (gethostname()), and many other values.

**C.3.6 Library Routines**

The system-call interface to UNIX is supported and augmented by a large collection of library routines and header files. The header files provide the definition of complex data structures used in system calls. In addition, a large library of functions provides additional program support.

For example, the UNIX I/O system calls provide for the reading andwriting of blocks of bytes. Some applications may want to read and write only 1 byte at a time. Although possible, that would require a system call for each byte—a very high overhead. Instead, a set of standard library routines (the standard I/O package accessed through the header file<stdio.h>) provides another interface, which reads and writes several thousand bytes at a time using local buffers and transfers between these buffers (in user memory) when I/O is desired. Formatted I/O is also supported by the standard I/O package.

Additional library support is provided for mathematical functions, net- work access, data conversion, and so on. The FreeBSD kernel supports over 300 system calls; the C program library has over 300 library functions. The library functions eventually result in system calls where necessary (for exam- ple, the getchar() library routine will result in a read() system call if the file buffer is empty). However, the programmer generally does not need to distin- guish between the basic set of kernel system calls and the additional functions provided by library functions.

**C.4 User Interface**

Both the programmer and the user of a UNIX system deal mainly with the set of systems programs that have been written and are available for execution. These programs make the necessary system calls to support their function, but the system calls themselves are contained within the program and do not need to be obvious to the user.

The common systems programs can be grouped into several categories; most of them are file or directory oriented. For example, the systems programs to manipulate directories are mkdir to create a new directory, rmdir to remove a directory, cd to change the current directory to another, and pwd to print the absolute path name of the current (working) directory.

The ls program lists the names of the files in the current directory. Any of 28 options can ask that properties of the files be displayed also. For example, the -l option asks for a long listing showing the file name, owner, protection, date and time of creation, and size. The cp program creates a new file that is a copy of an existing file. The mv programmoves a file from one place to another in the directory tree. In most cases, this move simply requires a renaming of the file. If necessary, however, the file is copied to the new location, and the old copy is deleted. Afile is deleted by the rm program (which makes an unlink() system call).  

**16 Appendix C BSD UNIX**

To display a file on the terminal, a user can run cat. The cat program takes a list of files and concatenates them, copying the result to the standard output, commonly the terminal. On a high-speed cathode-ray tube (CRT) display, of course, the file may speed by too fast to be read. The more program displays the file one screen at a time, pausing until the user types a character to continue to the next screen. The head program displays just the first few lines of a file; tail shows the last few lines.

These are the basic systems programs widely used in UNIX. In addition, there are a number of editors (ed, sed, emacs, vi, and so on), compilers (C, python, FORTRAN, and so on), and text formatters (troff, TEX, scribe, and so on). There are also programs for sorting (sort) and comparing files (cmp, diff), looking for patterns (grep, awk), sending mail to other users (mail), and many other activities.

**C.4.1 Shells and Commands**

Both user-written and systems programs are normally executed by a command interpreter. The command interpreter in UNIX is a user process like any other. As noted earlier, it is called a shell—because it surrounds the kernel of the operating system. Users can write their own shells, and, in fact, several shells are in general use. The **_Bourne shell_**, written by Steve Bourne, is probably the most widely used—or, at least, the most widely available. The **_C shell_**, mostly the work of Bill Joy, a founder of Sun Microsystems, is the most popular on BSD systems. The Korn shell, by Dave Korn, has become popular because it combines the features of the Bourne shell and the C shell.

The common shells share much of their command-language syntax. UNIX is normally an interactive system. The shell indicates its readiness to accept another command by typing a prompt, and the user types a command on a single line. For instance, in the line

% **_ls -l_**

the percent sign is the usual C shell prompt, and the ls -l (typed by the user) is the (long) list-directory command. Commands can take arguments, which the user types after the command name on the same line, separated by white space (spaces or tabs).

Although a few commands are built into the shells (such as cd), a typical command is an executable binary object file. A list of several directories, the **_search path_**, is kept by the shell. For each command, each of the directories in the search path is searched, in order, for a file of the same name. If a file is found, it is loaded and executed. The search path can be set by the user. The directories _/bin_ and _/usr/bin_ are almost always in the search path, and a typical search path on a FreeBSD system might be

_( . /usr/avi/bin /usr/local/bin /bin /usr/bin )_

The ls command’s object file is _/bin/ls,_ and the shell itself is _/bin/sh_ (the Bourne shell) or _/bin/csh_ (the C shell).

Execution of a command is done by a fork() system call followed by an execve() of the object file. The shell usually then does a wait() to suspend  

**C.4 User Interface 17**

its own execution until the command completes (Figure C.4). There is a simple syntax (an ampersand \[&\] at the end of the command line) to indicate that the shell should _not_ wait for the completion of the command. A command left running in thismannerwhile the shell continues to interpret further commands is said to be a **_background_** command, or to be running in the background. Processes for which the shell _does_ wait are said to run in the **_foreground_**.

The C shell in FreeBSD systems provides a facility called **_job control_** (par- tially implemented in the kernel), as mentioned previously. Job control allows processes to be moved between the foreground and the background. The pro- cesses can be stopped and restarted on various conditions, such as a back- ground job wanting input from the user’s terminal. This scheme allows most of the control of processes provided by windowing or layering interfaces but requires no special hardware. Job control is also useful in window systems, such as the X Window System developed at MIT. Each window is treated as a terminal, allowing multiple processes to be in the foreground (one per win- dow) at any one time. Of course, background processes may exist on any of the windows. The Korn shell also supports job control, and job control (and process groups) will likely be standard in future versions of UNIX.

**C.4.2 Standard I/O**

Processes can open files as they like, but most processes expect three file descriptors (numbers 0, 1, and 2) to be openwhen they start. These file descrip- tors are inherited across the fork() (and possibly the execve()) that created the process. They are known as **_standard input_** (0), **_standard output_** (1), and **_standard error_** (2). All three are frequently open to the user’s terminal. Thus, the program can read what the user types by reading standard input, and the program can send output to the user’s screen by writing to standard output. The standard-error file descriptor is also open for writing and is used for error output; standard output is used for ordinary output. Most programs can also accept a file (rather than a terminal) for standard input and standard output. The programdoes not carewhere its input is coming from andwhere its output is going. This is one of the elegant design features of UNIX.

The common shells have a simple syntax for changing what files are open for the standard I/O streams of a process. Changing a standard file is called **_I/O redirection_**. The syntax for I/O redirection is shown in Figure C.5. In this

command meaning of command

% _ls_ > _filea_ direct output of _ls_ to file _filea_

% _pr_ < _filea_ > _fileb_

% _lpr_ < _fileb_

% % make program > & errs

input from _filea_ and output to _fileb_

input from _fileb_

save both standard output and standard error in a file

**Figure C.5** Standard /io/ redirection.  

**18 Appendix C BSD UNIX**

example, the ls command produces a listing of the names of files in the current directory, the pr command formats that list into pages suitable for a printer, and the lpr command spools the formatted output to a printer, such as _/dev/lp0._ The subsequent command forces all output and all error messages to be redirected to a file. Without the ampersand, error messages appear on the terminal.

**C.4.3 Pipelines, Filters, and Shell Scripts**

The first three commands of Figure C.5 could have been coalesced into the one command

% **_ls_** | **_pr_** | **_lpr_** Each vertical bar tells the shell to arrange for the output of the preceding command to be passed as input to the following command. A **pipe** is used to carry the data from one process to the other. One process writes into one end of the pipe, and another process reads from the other end. In the example, the write end of one pipe would be set up by the shell to be the standard output of ls, and the read end of the pipe would be the standard input of pr. Another pipe would be between pr and lpr.

Acommand such as pr that passes its standard input to its standard output, performing some processing on it, is called a **_filter._** Many UNIX commands can be used as filters. Complicated functions can be pieced together as pipelines of common commands. Also, common functions, such as output formatting, do not need to be built into numerous commands, because the output of almost any program can be piped through pr (or some other appropriate filter).

Both of the common UNIX shells are also programming languages, with shell variables and the usual higher-level programming-language control con- structs (loops, conditionals). The execution of a command is analogous to a subroutine call. A file of shell commands, a **_shell script_**, can be executed like any other command, with the appropriate shell being invoked automatically to read it. **_Shell programming_** thus can be used to combine ordinary programs conveniently for sophisticated applications without the need for any program- ming in conventional languages.

This external user view is commonly thought of as the definition of UNIX, yet it is the most easily changed definition. Writing a new shell with a quite different syntax and semantics would greatly change the user view while not changing the kernel or even the programmer interface. Several menu-driven and iconic interfaces for UNIX exist, and the X Window System is rapidly becoming a standard. The heart of UNIX is, of course, the kernel. This kernel is much more difficult to change than is the user interface, because all programs depend on the system calls that it provides to remain consistent. Of course, new system calls can be added to increase functionality, but programs must then be modified to use the new calls.

**C.5 Process Management**

A major design problem for operating systems is the representation of pro- cesses. One substantial difference between UNIX and many other systems is the ease with which multiple processes can be created andmanipulated. These  

**C.5 Process Management 19**

processes are represented in UNIX by various control blocks. No system con- trol blocks are accessible in the virtual address space of a user process; control blocks associated with a process are stored in the kernel. The kernel uses the information in these control blocks for process control and CPU scheduling.

**C.5.1 Process Control Blocks**

Themost basic data structure associatedwith processes is the **_process structure_**. Aprocess structure contains everything that the system needs to know about a process when the process is swapped out, such as its unique process identifier, scheduling information (for example, the priority of the process), and pointers to other control blocks. There is an array of process structures whose length is defined at system-linking time. The process structures of ready processes are kept linked together by the scheduler in a doubly linked list (the ready queue), and there are pointers from each process structure to the process’s parent, to its youngest living child, and to various other relatives of interest, such as a list of processes sharing the same program code (text).

The **_virtual address space_** of a user process is divided into text (program code), data, and stack segments. The data and stack segments are always in the same address space, but theymay grow separately, and usually in opposite directions. Most frequently, the stack grows down as the data grow up toward it. The text segment is sometimes (as on an Intel 8086 with separate instruction and data space) in an address space different from the data and stack, and it is usually read-only. The debugger puts a text segment in read–write mode to allow insertion of breakpoints.

Every process with sharable text (almost all, under FreeBSD) has a pointer from its process structure to a **_text structure_**. The text structure records how many processes are using the text segment, including a pointer into a list of their process structures, and where the page table for the text segment can be found on disk when it is swapped. The text structure itself is always resident in main memory. An array of such structures is allocated at system link time. The text, data, and stack segments for the processes may be swapped. When the segments are swapped in, they are paged.

The **_page tables_** record information on the mapping from the process’s virtual memory to physical memory. The process structure contains pointers to the page table, for use when the process is resident in main memory, or the address of the process on the swap device, when the process is swapped. There is no special separate page table for a shared text segment; every process sharing the text segment has entries for its pages in the process’s page table.

Information about the process needed only when the process is resident (that is, not swapped out) is kept in the **_user structure_** (or **_u structure_**), rather than in the process structure. This structure is mapped read-only into user virtual address space, so user processes can read its contents. It is writable by the kernel. The user structure contains a copy of the process control block, or PCB, which is kept here for saving the process’s general registers, stack pointer, program counter, and page-table base registers when the process is not running. There is space to keep system-call parameters and return values. All user and group identifiers associated with the process (not just the effective user identifier kept in the process structure) are kept here. Signals, timers, and quotas have data structures here. Of more obvious relevance to the ordinary  

**20 Appendix C BSD UNIX**

user, the current directory and the table of open files are maintained in the user structure.

Every process has both a user and a system mode. Most ordinary work is done in **_user mode_**, but when a system call is made, it is performed in **_system mode_**. The system and user phases of a process never execute simultaneously. When a process is executing in system mode, a **_kernel stack_** for that process is used, rather than the user stack belonging to that process. The kernel stack for the process immediately follows the user structure. The kernel stack and the user structure together compose the **_system data segment_** for the process. The kernel has its own stack for use when it is not doing work on behalf of a process (for instance, for interrupt handling).

Figure C.6 illustrates how the process structure is used to find the various parts of a process.

The fork() system call allocates a new process structure (with a new process identifier) for the child process and copies the user structure. There is ordinarily no need for a new text structure, as the processes share their text. The appropriate counters and lists are merely updated. A new page table is constructed, and new main memory is allocated for the data and stack segments of the child process. The copying of the user structure preserves open file descriptors, user and group identifiers, signal handling, and most similar properties of a process.

The vfork() system call does _not_ copy the data and stack to the new process; rather, the new process simply shares the page table of the old one. A new user structure and a new process structure are still created. A common use of this system call occurs when a shell executes a command and waits for its completion. The parent process uses vfork() to produce the child process. Because the child processwishes to use an execve() immediately to change its virtual address space completely, there is no need for a complete copy of the

resident tables

swappable process image

user space

system data structure

process structure

text structure

user structure

kernel stack

stack

data

text

**Figure C.6** Finding parts of a process using the process structure.  

**C.5 Process Management 21**

parent process. Such data structures as are necessary for manipulating pipes may be kept in registers between the vfork() and the execve(). Files may be closed in one process without affecting the other process, since the kernel data structures involved depend on the user structure, which is not shared. The parent is suspendedwhen it calls vfork() until the child either calls execve() or terminates, so that the parent will not change memory that the child needs.

When the parent process is large, vfork() can produce substantial savings in system CPU time. However, it is a fairly dangerous system call, since any memory change occurs in both processes until the execve() occurs. An alter- native is to share all pages by duplicating the page table but tomark the entries of both page tables as **_copy-on-write_**. The hardware protection bits are set to trap any attempt to write in these shared pages. If such a trap occurs, a new frame is allocated, and the shared page is copied to the new frame. The page tables are adjusted to show that this page is no longer shared (and therefore no longer needs to be write-protected), and execution can resume.

An execve() system call creates no new process or user structure. Rather, the text and data of the process are replaced.Open files are preserved (although there is a way to specify that certain file descriptors are to be closed on an execve()). Most signal-handling properties are preserved, but arrangements to call a specific user routine on a signal are canceled, for obvious reasons. The process identifier and most other properties of the process are unchanged.

**C.5.2 CPU Scheduling**

**_CPU scheduling_** in UNIX is designed to benefit interactive processes. Processes are given small CPU time slices by a priority algorithm that reduces to round- robin scheduling for CPU-bound jobs.

Every process has a **_scheduling priority_** associated with it; larger numbers indicate lower priority. Processes doing disk I/O or other important tasks have priorities less than “pzero” and cannot be killed by signals. Ordinary user processes have positive priorities and thus are less likely to be run than is any system process, although user processes can set precedence over one another through the nice command.

The more CPU time a process accumulates, the lower (more positive) its priority becomes, and vice versa. This negative feedback in CPU scheduling makes it difficult for a single process to take all the CPU time. Process aging is employed to prevent starvation.

Older UNIX systems used a 1-second quantum for the round-robin schedul- ing. FreeBSD reschedules processes every 0.1 second and recomputes priorities every second. The round-robin scheduling is accomplished by the **_timeout_** mechanism, which tells the clock interrupt driver to call a kernel subroutine after a specified interval. The subroutine to be called in this case causes the rescheduling and then resubmits a timeout to call itself again. The priority recomputation is also timed by a subroutine that resubmits a timeout for itself.

There is no preemption of one process by another in the kernel. A process may relinquish the CPU because it is waiting for I/O or because its time slice has expired. When a process chooses to relinquish the CPU, it goes to **_sleep_** on an **_event_**. The kernel primitive used for this purpose is called sleep() (not to be confused with the user-level library routine of the same name). Sleep() takes an argument that is, by convention, the address of a kernel data  

**22 Appendix C BSD UNIX**

structure related to an event for which a process is waiting. When the event occurs, the system process that knows about it calls wakeup()with the address corresponding to the event, and _all_ processes that had done a sleep on the same address are put in the ready queue to be run.

For example, a process waiting for disk I/O to complete will sleep on the address of the buffer header corresponding to the data being transferred.When the interrupt routine for the disk driver notes that the transfer is complete, it calls wakeup() on the buffer header. The interrupt uses the kernel stack for whatever process happened to be running at the time, and the wakeup() is done from that system process.

The process that actually does run is chosen by the scheduler. Sleep() takes a second argument, which is the scheduling priority to be used for this purpose. This priority argument, if less than “pzero,” also prevents the process from being awakened prematurely by some exceptional event, such as a signal.

When a signal is generated, it is left pending until the system half of the affected process next runs. This event usually happens soon, since the signal normally causes the process to be awakened if the process has beenwaiting for some other condition.

No memory is associated with events. The caller of the routine that does a sleep() on an event must be prepared to deal with a premature return, including the possibility that the reason for waiting has vanished.

**_Race conditions_** are involved in the event mechanism. If a process decides (because of checking a flag in memory, for instance) to sleep on an event, and the event occurs before the process can execute the primitive that does the sleep() on the event, the process sleepingmay then sleep forever. We prevent this situation by raising the hardware processor priority during the critical section so that no interrupts can occur. Thus, only the process desiring the event can run until it is sleeping. Hardware processor priority is used in this manner to protect critical regions throughout the kernel and is the greatest obstacle to porting UNIX to multiple-processor machines. However, this problem has not prevented such porting from being done repeatedly.

Many processes, such as text editors, are I/O bound and are, in general, scheduled mainly on the basis of waiting for I/O. Experience suggests that the UNIX scheduler performs best with I/O-bound jobs, as can be observed when several CPU-bound jobs, such as text formatters or language interpreters, are running.

What has been referred to here as**_CPU scheduling_** corresponds closely to the **_short-term scheduling_** of Chapter 3. However, the negative-feedback property of the priority scheme provides some long-term scheduling in that it largely determines the long-term **_job mix_**. Medium-term scheduling is done by the swapping mechanism described in Section C.6.

**C.6 Memory Management**

Much of UNIX’s early development was done on a PDP-11. The PDP-11 has only eight segments in its virtual address space, and the size of each is at most 8,192 bytes. The larger machines, such as the PDP-11/70, allow separate instruction and address spaces, effectively doubling the address space and number of segments, but this address space is still relatively small. In addition, the kernel  

**C.6 Memory Management 23**

was even more severely constrained due to dedication of one data segment to interrupt vectors, another to point at the per-process system data segment, and yet another for the UNIBUS (system I/O bus) registers. Further, on the smaller PDP-11s, total physicalmemorywas limited to 256 KB. The totalmemory resourceswere insufficient to justify or support complexmemory-management algorithms. Thus, UNIX swapped entire process memory images.

Berkeley introduced paging to UNIX with 3BSD. VAX 4.2BSD is a demand- paged virtual memory system. Paging eliminates external fragmentation of memory. (Internal fragmentation still occurs, but it is negligible with a reason- ably small page size.) Because paging allows execution with only parts of each process in memory, more jobs can be kept in main memory, and swapping can be kept to a minimum. **_Demand paging_** is done in a straightforward manner. When a process needs a page and the page is not there, a page fault to the kernel occurs, a frame of main memory is allocated, and the proper disk page is read into the frame.

There are a few optimizations. If the page needed is still in the page table for the process but has beenmarked invalid by the page-replacement process, it can be marked valid and used without any I/O transfer. Pages can similarly be retrieved from the list of free frames. When most processes are started, many of their pages are prepaged and are put on the free list for recovery by this mechanism.Arrangements can also bemade for a process to have noprepaging on startup. That is seldom done, however, because it results in more page- fault overhead, being closer to pure demand paging. FreeBSD implements page coloring with paging queues. The queues are arranged according to the size of the processor’s L1 and L2 caches. When a new page needs to be allocated, FreeBSD tries to get one that is optimally aligned for the cache. If the page has to be fetched from disk, it must be locked in memory for the duration of the transfer. This locking ensures that the page will not be selected for page replacement. Once the page is fetched and mapped properly, it must remain locked if raw physical I/O is being done on it.

The page-replacement algorithm is more interesting. 4.2BSD uses a modifi- cation of the **_second-chance (clock) algorithm_** described in Section 10.4.5. The map of all nonkernel main memory (the **_core map_** or **_cmap_**) is swept linearly and repeatedly by a software **_clock hand_**. When the clock hand reaches a given frame, if the frame is marked as being in use by some software condition (for example, if physical I/O is in progress using it) or if the frame is already free, the frame is left untouched, and the clock hand sweeps to the next frame. Otherwise, the corresponding text or process page-table entry for this frame is located. If the entry is already invalid, the frame is added to the free list. Otherwise, the page-table entry is made invalid but reclaimable (that is, if it has not been paged out by the next time it is wanted, it can just be made valid again).

BSD Tahoe added support for systems that implement the reference bit. On such systems, one pass of the clock hand turns the reference bit off, and a second pass places those pageswhose reference bits remain off onto the free list for replacement. Of course, if the page is dirty, it must first be written to disk before being added to the free list. Pageouts are done in clusters to improve performance.

There are checks to make sure that the number of valid data pages for a process does not fall too low and to keep the paging device from being flooded  

**24 Appendix C BSD UNIX**

with requests. There is also a mechanism by which a process can limit the amount of main memory it uses.

The LRU clock-hand scheme is implemented in the pagedaemon, which is process 2. (Remember that the swapper is process 0 and init is process 1.) This process spends most of its time sleeping, but a check is done several times per second (scheduled by a timeout) to see if action is necessary. If it is, process 2 is awakened. Whenever the number of free frames falls below a threshold, lotsfree, the pagedaemon is awakened. Thus, if there is always a large amount of free memory, the pagedaemon imposes no load on the system, because it never runs.

The sweep of the clock hand each time the pagedaemon process is awak- ened (that is, the number of frames scanned, which is usually more than the number paged out) is determined both by the number of frames lacking to reach lotsfree and by the number of frames that the scheduler has deter- mined are needed for various reasons (the more frames needed, the longer the sweep). If the number of frames free rises to lotsfree before the expected sweep is completed, the hand stops, and the pagedaemon process sleeps. The parameters that control the range of the clock-hand sweep are determined at system startup according to the amount of main memory, such that pagedae- mon does not use more than 10 percent of all CPU time.

If the scheduler decides that the paging system is overloaded, processes will be swapped out whole until the overload is relieved. This swapping usually happens only if several conditions are met: load average is high; free memory has fallen below a low limit, minfree; and the average memory available over recent time is less than a desirable amount, desfree, where lotsfree _\>_ desfree _\>_ minfree. In other words, only a chronic shortage of memory with several processes trying to run will cause swapping, and even then free memory has to be extremely low at the moment. (An excessive paging rate or a need for memory by the kernel itself may also enter into the calculations, in rare cases.) Processes may be swapped by the scheduler, of course, for other reasons (such as simply because they have not run for a long time).

The parameter lotsfree is usually one-quarter of the memory in the map that the clock hand sweeps, and desfree and minfree are usually the same across different systems but are limited to fractions of available mem- ory. FreeBSD dynamically adjusts its paging queues so these virtual memory parameters will rarely need to be adjusted. Minfree pages must be kept free in order to supply any pages that might be needed at interrupt time.

Every process’s text segment is, by default, shared and read-only. This scheme is practical with paging, because there is no external fragmentation, and the swap space gained by sharing more than offsets the negligible amount of overhead involved, as the kernel virtual space is large.

CPU scheduling, memory swapping, and paging interact. The lower the priority of a process, the more likely that its pages will be paged out and the more likely that it will be swapped in its entirety. The age preferences in choosing processes to swap guard against thrashing, but paging does so more effectively. Ideally, processes will not be swapped out unless they are idle, because each process will need only a small working set of pages in main memory at any one time, and the pagedaemon will reclaim unused pages for use by other processes.  

**C.7 File System 25**

The amount of memory the process will need is some fraction of that process’s total virtual size—up to one-half if that process has been swapped out for a long time.

**C.7 File System**

The UNIX file system supports two main objects: files and directories. Directo- ries are just files with a special format, so the representation of a file is the basic UNIX concept.

**C.7.1 Blocks and Fragments**

Most of the file system is taken up by **_data blocks_**, which contain whatever the users have put in their files. Let’s consider how these data blocks are stored on the disk.

The hardware disk sector is usually 512 bytes. A block size larger than 512 bytes is desirable for speed. However, because UNIX file systems usually contain a very large number of small files, much larger blocks would cause excessive internal fragmentation. That is why the earlier 4.1BSD file systemwas limited to a 1,024-byte (1-KB) block. The 4.2BSD solution is to use _two_ block sizes for files that have no indirect blocks. All the blocks of a file are of a large size (such as 8 KB) except the last. The last block is an appropriate multiple of a smaller fragment size (for example, 1,024 KB) to fill out the file. Thus, a file of size 18,000 bytes would have two 8-KB blocks and one 2-KB fragment (which would not be filled completely).

The block and fragment sizes are set during file-system creation according to the intended use of the file system. If many small files are expected, the fragment size should be small; if repeated transfers of large files are expected, the basic block size should be large. Implementation details force a maximum block-to-fragment ratio of 8:1 and a minimum block size of 4 KB, so typical choices are 4,096:512 for the former case and 8,192:1,024 for the latter.

Suppose data are written to a file in transfer sizes of 1-KB bytes, and the block and fragment sizes of the file system are 4 KB and 512 bytes. The file system will allocate a 1-KB fragment to contain the data from the first transfer. The next transfer will cause a new 2-KB fragment to be allocated. The data from the original fragment must be copied into this new fragment, followed by the second 1-KB transfer. The allocation routines attempt to find the required space on the disk immediately following the existing fragment so that no copying is necessary. If they cannot do so, up to seven copies may be required before the fragment becomes a block. Provisions have been made for programs to discover the block size for a file so that transfers of that size can be made, to avoid fragment recopying.

**C.7.2 Inodes**

Afile is represented by an **_inode_**, which is a record that stores most of the infor- mation about a specific file on the disk. (See Figure C.7.) The name _inode_ (pro- nounced _EYE node_) is derived from “index node” and was originally spelled “i-node”; the hyphen fell out of use over the years. The term is sometimes spelled “I node.”  

**26 Appendix C BSD UNIX**

direct blocks

data

data

data

data

data

data

data

data

data

data

• • ••

• •

• • •

• • •

• • •

• • •

mode

owners (2)

timestamps (3)

size block count

single indirect

double indirect

triple indirect

**Figure C.7** The UNIX inode.

The inode contains the user and group identifiers of the file, the times of the last file modification and access, a count of the number of hard links (directory entries) to the file, and the type of the file (plain file, directory, symbolic link, character device, block device, or socket). In addition, the inode contains 15 pointers to the disk blocks containing the data contents of the file. The first 12 of these pointers point to **_direct blocks_**. That is, they contain addresses of blocks that contain data of the file. Thus, the data for small files (no more than 12 blocks) can be referenced immediately, because a copy of the inode is kept in main memory while a file is open. If the block size is 4 KB, then up to 48 KB of data can be accessed directly from the inode.

The next three pointers in the inode point to **_indirect blocks_**. If the file is large enough to use indirect blocks, each of the indirect blocks is of the major block size; the fragment size applies only to data blocks. The first indirect block pointer is the address of a **_single indirect block_**. The single indirect block is an index block containing not data but the addresses of blocks that do contain data. Then, there is a **_double-indirect-block pointer_**, the address of a block that contains the addresses of blocks that contain pointers to the actual data blocks. The last pointer would contain the address of a **_triple indirect block_**; however, there is no need for it.

The minimum block size for a file system in 4.2BSD is 4 KB, so files with as many as 232 bytes will use only double, not triple, indirection. That is, since each block pointer takes 4 bytes, we have 49,152 bytes accessible in direct blocks, 4,194,304 bytes accessible by a single indirection, and 4,294,967,296 bytes reachable through double indirection, for a total of 4,299,210,752 bytes, which is larger than 232 bytes. The number 232 is significant because the file offset in the file structure in main memory is kept in a 32-bit word. Files therefore cannot be larger than 232 bytes. Since file pointers are signed integers  

**C.7 File System 27**

(for seeking backward and forward in a file), the actual maximum file size is 232−1 bytes. Two gigabytes is large enough for most purposes.

**C.7.3 Directories**

Plain files are not distinguished from directories at this level of implementa- tion. Directory contents are kept in data blocks, and directories are represented by an inode in the same way as plain files. Only the inode type field distin- guishes betweenplain files anddirectories. Plain files are not assumed to have a structure, whereas directories have a specific structure. In Version 7, file names were limited to 14 characters, so directorieswere a list of 16-byte entries: 2 bytes for an inode number and 14 bytes for a file name.

In FreeBSD file names are of variable length, up to 255 bytes, so directory entries are also of variable length. Each entry contains first the length of the entry, then the file name and the inode number. This variable-length entry makes the directory management and search routines more complex, but it allows users to choose much more meaningful names for their files and direc- tories. The first two names in every directory are “.” and “..”. New directory entries are added to the directory in the first space available, generally after the existing files. A linear search is used.

The user refers to a file by a path name, whereas the file system uses the inode as its definition of a file. Thus, the kernel has to map the supplied user path name to an inode. The directories are used for this mapping.

First, a starting directory is determined. As mentioned earlier, if the first character of the path name is “/,” the starting directory is the root directory. If the path name starts with any character other than a slash, the starting directory is the current directory of the current process. The starting directory is checked for proper file type and access permissions, and an error is returned if necessary. The inode of the starting directory is always available.

The next element of the path name, up to the next “/” or to the end of the path name, is a file name. The starting directory is searched for this name, and an error is returned if the name is not found. If the path name has yet another element, the current inode must refer to a directory; an error is returned if it does not or if access is denied. This directory is searched in the sameway as the previous one. This process continues until the end of the path name is reached and the desired inode is returned. This step-by-step process is needed because at any directory a mount point (or symbolic link, as discussed below) may be encountered, causing the translation to move to a different directory structure for continuation.

Hard links are simply directory entries like any other. We handle symbolic links for the most part by starting the search over with the path name taken from the contents of the symbolic link. We prevent infinite loops by counting the number of symbolic links encountered during a path-name search and returning an error when a limit (eight) is exceeded.

Nondisk files (such as devices) do not have data blocks allocated on the disk. The kernel notices these file types (as indicated in the inode) and calls appropriate drivers to handle I/O for them.

Once the inode is found by, for instance, the open() system call, a **_file structure_** is allocated to point to the inode. The file descriptor given to the user refers to this file structure. FreeBSD has a **_directory name cache_** to hold  

**28 Appendix C BSD UNIX**

user space

read (4, …)

system space disk space

data blocks

inode list

in-core inode

list

tables of open files

(per process)

file-structure table

sync

• • •

**Figure C.8** File-system control blocks.

recent directory-to-inode translations, which greatly increases file-system per- formance.

**C.7.4 Mapping a File Descriptor to an Inode**

A system call that refers to an open file indicates the file by passing a file descriptor as an argument. The file descriptor is used by the kernel to index a table of open files for the current process. Each entry in the table contains a pointer to a file structure. This file structure in turn points to the inode; see Figure C.8. The open file table has a fixed length, which is settable only at boot time. Therefore, there is a fixed limit on the number of concurrently open files in a system.

The read() and write() system calls do not take a position in the file as an argument. Rather, the kernel keeps a **_file offset_**, which is updated by an appropriate amount after each read() or write() according to the number of data actually transferred. The offset can be set directly by the lseek() system call. If the file descriptor indexed an array of inode pointers instead of file pointers, this offset would have to be kept in the inode. Because more than one process may open the same file, and each such process needs its own offset for the file, keeping the offset in the inode is inappropriate. Thus, the file structure is used to contain the offset. File structures are inherited by the child process after a fork(), so several processes may share the same offset location for a file.

The **_inode structure_** pointed to by the file structure is an in-core copy of the inode on the disk. The in-core inode has a few extra fields, such as a reference count of howmany file structures are pointing at it, and the file structure has a similar reference count for how many file descriptors refer to it. When a count becomes zero, the entry is no longer needed andmay be reclaimed and reused.

**C.7.5 Disk Structures**

The file system that the user sees is supported by data on amass storage device —usually, a disk. The user ordinarily knows of only one file system, but this one logical file system may actually consist of several _physical_ file systems, each on a different device. Because device characteristics differ, each separate  

**C.7 File System 29**

hardware device defines its ownphysical file system. In fact, we generallywant to partition large physical devices, such as disks, into multiple _logical_ devices. Each logical device defines a physical file system. Figure C.9 illustrates how a directory structure is partitioned into file systems, which are mapped onto logical devices,which are partitions of physical devices. The sizes and locations of these partitions were coded into device drivers in earlier systems, but they are maintained on the disk by FreeBSD.

Partitioning a physical device into multiple file systems has several bene- fits. Different file systems can support different uses. Althoughmost partitions will be used by the file system, at least one will be needed as a swap area for the virtual memory software. Reliability is improved, because software dam- age is generally limited to only one file system. We can improve efficiency by varying the file-system parameters (such as the block and fragment sizes) for each partition. Also, having separate file systems prevents one program from using all available space for a large file, because files cannot be split across file systems. Finally, disk backups are done per partition, and it is faster to search a backup tape for a file if the partition is smaller. Restoring the full partition from tape is also faster.

The number of file systems on a drive varies according to the size of the disk and the purpose of the computer system as a whole. One file system, the

logical file system file systems logical devices physical devices

root

swap

**Figure C.9** Mapping of a logical file system to physical devices.  

**30 Appendix C BSD UNIX**

**_root file system_**, is always available. Other file systemsmay be**_mounted_**—that is, integrated into the directory hierarchy of the root file system.

A bit in the inode structure indicates that the inode has a file system mounted on it. A reference to this file causes the **_mount table_** to be searched to find the device number of the mounted device. The device number is used to find the inode of the root directory of the mounted file system, and that inode is used. Conversely, if a path-name element is “..” and the directory being searched is the root directory of a file system that is mounted, the mount table is searched to find the inode it is mounted on, and that inode is used.

Each file system is a separate system resource and represents a set of files. The first sector on the logical device is the **_boot block_**, possibly containing a primary bootstrap program, which may be used to call a secondary bootstrap program residing in the next 7.5 KB. A system needs only one partition con- taining boot-block data, but the system manager may install duplicates via privileged programs, to allow booting when the primary copy is damaged. The **_superblock_** contains static parameters of the file system. These parameters include the total size of the file system, the block and fragment sizes of the data blocks, and assorted parameters that affect allocation policies.

**C.7.6 Implementations**

The user interface to the file system is simple and well defined, allowing the implementation of the file system itself to be changedwithout significant effect on the user. The file system was changed between Version 6 and Version 7 of 3BSD, and again between Version 7 and 4BSD. For Version 7, the size of inodes doubled, the maximum file and file-system sizes increased, and the details of free-list handling and superblock information changed. At that time also, seek() (with a 16-bit offset) became lseek() (with a 32-bit offset), to allow specification of offsets in larger files, but fewother changeswere visible outside the kernel.

In 4.0BSD, the size of blocks used in the file system was increased from 512 bytes to 1,024 bytes. Although this increased size produced increased internal fragmentation on the disk, it doubled throughput, due mainly to the greater number of data accessed on each disk transfer. This idea was later adopted by System V, along with a number of other ideas, device drivers, and programs.

4.2BSD added the Berkeley Fast File System, which increased speed and was accompanied by new features. Symbolic links required new system calls. Long file names necessitated new directory system calls to traverse the now- complex internal directory structure. Finally, truncate() calls were added. The Fast File Systemwas a success and is now found in most implementations of UNIX. Its performance is made possible by its layout and allocation policies, which we discuss next. In Section 14.4.4, we discussed changes made in SunOS to increase disk throughput further.

**C.7.7 Layout and Allocation Policies**

The kernel uses a_<**logical device number, inode number**\>_ pair to identify a file. The logical device number defines the file system involved. The inodes in the file system are numbered in sequence. In the Version 7 file system, all inodes are in an array immediately following a single superblock at the beginning of  

**C.7 File System 31**

the logical device,with the data blocks following the inodes. The inode number is effectively just an index into this array.

With the Version 7 file system, a block of a file can be anywhere on the disk between the end of the inode array and the end of the file system. Free blocks are kept in a linked list in the superblock. Blocks are pushed onto the front of the free list and are removed from the front as needed to serve new files or to extend existing files. Thus, the blocks of a file may be arbitrarily far from both the inode and one another. Furthermore, the more a file system of this kind is used, the more disorganized the blocks in a file become. We can reverse this process only by reinitializing and restoring the entire file system, which is not a convenient task to perform. This process was described in Section 14.7.4.

Another difficulty is that the reliability of the file system is suspect. For speed, the superblock of each mounted file system is kept in memory. Keeping the superblock in memory allows the kernel to access a superblock quickly, especially for using the free list. Every 30 seconds, the superblock is written to the disk, to keep the in-core and disk copies synchronized (by the update program, using the sync() system call). However, system bugs or hardware failures may cause a system crash, which destroys the in-core superblock between updates to the disk. Then, the free list on disk does not accurately reflect the state of the disk. To reconstruct it, we must perform a lengthy examination of all blocks in the file system. (This problem remains in the new file system.)

The 4.2BSD file-system implementation is radically different from that of Version 7. This reimplementation was done primarily to improve efficiency and robustness, and most such changes are invisible outside the kernel. Other changes introduced at the same time are visible at both the system-call and the user levels; examples include symbolic links and long file names (up to 255 characters). Most of the changes required for these features were not in the kernel, however, but in the programs that use them.

Space allocation is especially different. Themajor new concept in FreeBSD is the **_cylinder group_**. The cylinder group was introduced to allow localization of the blocks in a file. Each cylinder group occupies one ormore consecutive cylin- ders of the disk, so that disk accesseswithin the cylinder group requireminimal disk headmovement. Every cylinder group has a superblock, a cylinder block, an array of inodes, and some data blocks (Figure C.10).

data blocks

superblock

cylinder block

inodes

data blocks

**Figure C.10** 4.3 BSD cylinder group.  

**32 Appendix C BSD UNIX**

The superblocks in all cylinder groups are identical, so that a superblock can be recovered from any one of them in the event of disk corruption. The **_cylinder block_** contains dynamic parameters of the particular cylinder group. These include a bit map of free data blocks and fragments and a bitmap of free inodes. Statistics on recent progress of the allocation strategies are also kept here.

The header information in a cylinder group (the superblock, the cylinder block, and the inodes) is not always at the beginning of the group. If it were, the header information for every cylinder group might be on the same disk platter, and a single disk head crash could wipe out all of them. Therefore, each cylinder group has its header information at a different offset from the beginning of the group.

The directory-listing command ls commonly reads all the inodes of every file in a directory, making it desirable for all such inodes to be close together on the disk. For this reason, the inode for a file is usually allocated from the cylinder group containing the inode of the file’s parent directory. Not everything can be localized, however, so an inode for a new directory is put in a _different_ cylinder group from that of its parent directory. The cylinder group chosen for such a new directory inode is that with the greatest number of unused inodes.

To reduce disk head seeks involved in accessing the data blocks of a file, we allocate blocks from the same cylinder group as often as possible. Because a single file cannot be allowed to take up all the blocks in a cylinder group, a file exceeding a certain size (such as 2 MB) has further block allocation redirected to a different cylinder group; the new group is chosen from among those having more than average free space. If the file continues to grow, allocation is again redirected (at eachmegabyte) to yet another cylinder group. Thus, all the blocks of a small file are likely to be in the same cylinder group, and the number of long head seeks involved in accessing a large file is kept small.

There are two levels of disk-block-allocation routines. The global policy routines select a desired disk block according to the considerations already discussed. The local policy routines use the specific information recorded in the cylinder blocks to choose a block near the one requested. If the requested block is not in use, it is returned. Otherwise, the routine returns either the block rotationally closest to the one requested in the same cylinder or a block in a different cylinder but in the same cylinder group. If no more blocks are in the cylinder group, a quadratic rehash is done among all the other cylinder groups to find a block. If that fails, an exhaustive search is done. If enough free space (typically 10 percent) is left in the file system, blocks are usually found where desired, the quadratic rehash and exhaustive search are not used, and performance of the file system does not degrade with use.

Because of the increased efficiency of the Fast File System, typical disks are now utilized at 30 percent of their raw transfer capacity. This percentage is a marked improvement over that realized with the Version 7 file system, which used about 3 percent of the bandwidth.

BSD Tahoe introduced the Fat Fast File System, which allows the number of inodes per cylinder group, the number of cylinders per cylinder group, and the number of distinguished rotational positions to be set when the file system is created. FreeBSD previously set these parameters according to the disk hardware type.  

**C.8 I/O System 33**

**C.8 I/O System**

One of the purposes of an operating system is to hide the peculiarities of specific hardware devices from the user. For example, the file system presents a simple, consistent storage facility (the file) independent of the underlying disk hardware. In UNIX, the peculiarities of I/O devices are also hidden from the bulk of the kernel itself by the **_I/O system_**. The I/O system consists of a buffer caching system, general device-driver code, and drivers for specific hardware devices. Only the device driver knows the peculiarities of a specific device. The major parts of the I/O system are diagrammed in Figure C.11.

There are three main kinds of I/O in FreeBSD: block devices, character devices, and the socket interface. The socket interface, together with its pro- tocols and network interfaces, will be described in Section C.9.1.

**_Block devices_** include disks and tapes. Their distinguishing characteristic is that they are directly addressable in a fixed block size—usually 512 bytes. A block-device driver is required to isolate details of tracks, cylinders, and so on from the rest of the kernel. Block devices are accessible directly through appropriate device special files (such as _/dev/rp0_), but they are more commonly accessed indirectly through the file system. In either case, transfers are buffered through the **_block buffer cache_**, which has a profound effect on efficiency.

**_Character devices_** include terminals and line printers but also include almost everything else (except network interfaces) that does not use the block buffer cache. For instance, _/dev/mem_ is an interface to physical main memory, and _/dev/null_ is a bottomless sink for data and an endless source of end-of-file markers. Some devices, such as high-speed graphics interfaces, may have their own buffers or may always do I/O directly into the user’s data space; because they do not use the block buffer cache, they are classed as character devices. Terminals and terminal-like devices use **_C-lists_**, which are buffers smaller than those of the block buffer cache.

Block devices and character devices are the twomain device classes. Device drivers are accessed by one of two arrays of entry points. One array is for block devices; the other is for character devices. A device is distinguished by a class (block or character) and a **_device number_**. The device number consists of two parts. The **_major device number_** is used to index the array for character or block devices to find entries into the appropriate device driver. The **_minor_**

_the hardware_

_system-call interface to the kernel_

socket

protocols

network interface

plain file

file system

block-device driver

cooked block interface

raw tty interface

cooked TTY

line discipline

character-device driver

raw block interface

**Figure C.11** 4.3 BSD kernel I/O structure.  

**34 Appendix C BSD UNIX**

**_device number_** is interpreted by the device driver as, for example, a logical disk partition or a terminal line.

Adevicedriver is connected to the rest of the kernel only by the entry points recorded in the array for its class and by its use of common buffering systems. This segregation is important for portability and for system configuration.

**C.8.1 Block Buffer Cache**

The block devices, as mentioned, use a block buffer cache. The buffer cache consists of a number of buffer headers, each of which can point to a piece of physical memory as well as to a device number and a block number on the device. The buffer headers for blocks not currently in use are kept in several linked lists, one for each of the following:

• Buffers recently used, linked in LRU order (the LRU list)

• Buffers not recently used or without valid contents (the AGE list)

• EMPTY buffers with no physical memory associated with them

The buffers in these lists are also hashed by device and block number for search efficiency.

When a block is wanted from a device (a read), the cache is searched. If the block is found, it is used, and no I/O transfer is necessary. If it is not found, a buffer is chosen from the AGE list or, if that list is empty, the LRU list. Then the device number and block number associated with it are updated, memory is found for it if necessary, and the new data are transferred into it from the device. If there are no empty buffers, the LRU buffer is written to its device (if it is modified), and the buffer is reused.

On a write, if the block in question is already in the buffer cache, the new data are put in the buffer (overwriting any previous data), the buffer header is marked to indicate that the buffer has beenmodified, andno I/O is immediately necessary. The data will be written when the buffer is needed for other data. If the block is not found in the buffer cache, an empty buffer is chosen (as with a read), and a transfer is done to this buffer. Writes are periodically forced for dirty buffer blocks to minimize potential file-system inconsistencies after a crash.

The number of data in a buffer in FreeBSD is variable, up to a maximum over all file systems, usually 8 KB. The minimum size is the paging-cluster size, usually 1,024 bytes. Buffers are page-cluster aligned, and any page cluster may bemapped into only one buffer at a time, just as any disk blockmay bemapped into only one buffer at a time. The EMPTY list holds buffer headers, which are used if a physical memory block of 8 KB is split to holdmultiple, smaller blocks. Headers are needed for these blocks and are retrieved from EMPTY.

The number of data in a buffer may grow as a user process writes more data following those already in the buffer. When this increase occurs, a new buffer large enough to hold all the data is allocated, and the original data are copied into it, followed by the new data. If a buffer shrinks, a buffer is taken  

**C.8 I/O System 35**

off the empty queue, excess pages are put in it, and that buffer is released to be written to disk.

Some devices, such as magnetic tapes, require that blocks be written in a certain order. Facilities are therefore provided to force a synchronous write of buffers to these devices in the correct order. Directory blocks are also written synchronously, to forestall crash inconsistencies. Consider the chaos that could occur if many changes were made to a directory but the directory entries themselves were not updated!

The size of the buffer cache can have a profound effect on the performance of a system, because, if it is large enough, the percentage of cache hits can be high and the number of actual I/O transfers low. FreeBSD optimizes the buffer cache by continually adjusting the amount of memory used by programs and the disk cache.

Some interesting interactions occur among the buffer cache, the file system, and the disk drivers. When data are written to a disk file, they are buffered in the cache, and the disk driver sorts its output queue according to disk address. These two actions allow the disk driver to minimize disk head seeks and to write data at times optimized for disk rotation. Unless synchronous writes are required, a process writing to disk simply writes into the buffer cache, and the system asynchronously writes the data to disk when convenient. The user process sees very fast writes. When data are read from a disk file, the block I/O system does some read-ahead; however, writes are much nearer to asynchronous than are reads. Thus, output to the disk through the file system is often faster than is input for large transfers, counter to intuition.

**C.8.2 Raw Device Interfaces**

Almost every block device also has a character interface, and these are called **_raw device interfaces_**. Such an interface differs from the **_block interface_** in that the block buffer cache is bypassed.

Each disk driver maintains a queue of pending transfers. Each record in the queue specifies whether it is a read or a write and gives a main memory address for the transfer (usually in 512-byte increments), a device address for the transfer (usually the address of a disk sector), and a transfer size (in sectors). It is simple to map the information from a block buffer to what is required for this queue.

It is almost as simple to map a piece of main memory corresponding to part of a user process’s virtual address space. This mapping is what a raw disk interface, for instance, does. Unbuffered transfers directly to or from a user’s virtual address space are thus allowed. The size of the transfer is limited by the physical devices, some of which require an even number of bytes.

The kernel accomplishes transfers for swapping and paging simply by putting the appropriate request on the queue for the appropriate device. No special swapping or paging device driver is needed.

The 4.2BSD file-system implementation was actually written and largely tested as a user process that used a raw disk interface, before the code was moved into the kernel. In an interesting about-face, theMach operating system  

**36 Appendix C BSD UNIX**

has no file system per se. File systems can be implemented as user-level tasks (see Appendix D).

**C.8.3 C-Lists**

As mentioned, terminals and terminal-like devices use a character-buffering system that keeps small blocks of characters (usually 28 bytes) in linked lists called C-lists. Although all free character buffers are kept in a single free list, most device drivers that use them limit the number of characters that may be queued at one time for any given terminal line.

There are routines to enqueue and dequeue characters for such lists. A write() system call to a terminal enqueues characters on a list for the device. An initial transfer is started, and interrupts cause dequeuing of characters and further transfers.

Input is similarly interrupt driven. Terminal drivers typically support _two_ input queues, however, and conversion from the first (raw queue) to the other (canonical queue) is triggered when the interrupt routine puts an end-of-line character on the raw queue. The process doing a read on the device is then awakened, and its system phase does the conversion. The characters thus put on the canonical queue are then available to be returned to the user process by the read.

The device driver can bypass the canonical queue and return characters directly from the raw queue. This mode of operation is known as **_raw mode_**. Full-screen editors, as well as other programs that need to react to every keystroke, use this mode.

**C.9 Interprocess Communication**

Although many tasks can be accomplished in isolated processes, many others require interprocess communication. Isolated computing systems have long served for many applications, but networking is increasingly important. Fur- thermore, with the increasing use of personal workstations, resource sharing is becoming more common. Interprocess communication has not traditionally been one of UNIX’s strong points.

**C.9.1 Sockets**

The pipe (discussed in Section C.4.3) is the IPC mechanism most characteris- tic of UNIX. A pipe permits a reliable unidirectional byte stream between two processes. It is traditionally implemented as an ordinary file, with a few excep- tions. It has no name in the file system, being created instead by the pipe() system call. Its size is fixed, and when a process attempts to write to a full pipe, the process is suspended. Once all data previously written into the pipe have been read out, writing continues at the beginning of the file (pipes are not true circular buffers). One benefit of the small size of pipes (usually 4,096 bytes) is that pipe data are seldom actually written to disk; they usually are kept in memory by the normal block buffer cache.

In FreeBSD pipes are implemented as a special case of the **_socket_** mecha- nism. The socket mechanism provides a general interface not only to facilities such as pipes, which are local to one machine, but also to networking facilities.  

**C.9 Interprocess Communication 37**

Even on the same machine, a pipe can be used only by two processes related through use of the fork() system call. The socket mechanism can be used by unrelated processes.

A socket is an endpoint of communication. A socket in use usually has an **_address_** bound to it. The nature of the address depends on the **_communication domain_** of the socket. A characteristic property of a domain is that processes communicating in the same domain use the same **_address format_**. A single socket can communicate in only one domain.

The three domains currently implemented in FreeBSD are the UNIX domain (AF UNIX), the Internet domain (AF INET), and the XEROX Network Services (NS) domain (AF NS). The address format of the UNIX domain is that of an ordinary file-system path name, such as _/alpha/beta/gamma._ Processes commu- nicating in the Internet domain use DARPA Internet communications protocols (such as TCP/IP) and Internet addresses, which consist of a 32-bit host number and a 32-bit port number (representing a rendezvous point on the host).

There are several **socket types**, which represent classes of services. Each type may or may not be implemented in any communication domain. If a type is implemented in a given domain, it may be implemented by one or more protocols, which may be selected by the user:

• **Stream sockets.** These sockets provide reliable, duplex, sequenced data streams. No data are lost or duplicated in delivery, and there are no record boundaries. This type is supported in the Internet domain by TCP. In the UNIX domain, pipes are implemented as a pair of communicating stream sockets.

• **Sequenced packet sockets.** These sockets provide data streams like those of stream sockets, except that record boundaries are provided. This type is used in the XEROX AF NS protocol.

• **Datagram sockets.** These sockets transfer messages of variable size in either direction. There is no guarantee that such messages will arrive in the same order they were sent, or that they will be unduplicated, or that they will arrive at all, but the original message (or record) size is preserved in any datagram that does arrive. This type is supported in the Internet domain by UDP.

• **Reliably delivered message sockets.** These sockets transfer messages that are guaranteed to arrive and that otherwise are like the messages trans- ferred using datagram sockets. This type is currently unsupported.

• **Raw sockets.** These sockets allow direct access by processes to the proto- cols that support the other socket types. The protocols accessible include not only the uppermost ones but also lower-level protocols. For example, in the Internet domain, it is possible to reach TCP, IP beneath that, or an Ethernet protocol beneath that. This capability is useful for developing new protocols.

A set of system calls is specific to the socket facility. The socket() system call creates a socket. It takes as arguments specifications of the communication domain, the socket type, and the protocol to be used to support that type. The value returned by the call is a small integer called a **socket descriptor**, which  

**38 Appendix C BSD UNIX**

occupies the same name space as file descriptors. The socket descriptor indexes the array of open files in the _u_ structure in the kernel and has a file structure allocated for it. The FreeBSD file structure may point to a socket structure instead of to an inode. In this case, certain socket information (such as the socket’s type, its message count, and the data in its input and output queues) is kept directly in the socket structure.

For another process to address a socket, the socket must have a name. A name is bound to a socket by the bind() system call, which takes the socket descriptor, a pointer to the name, and the length of the name as a byte string. The contents and length of the byte string depend on the address format. The connect() system call is used to initiate a connection. The arguments are syntactically the same as those for bind(); the socket descriptor represents the local socket, and the address is that of the foreign socket to which the attempt to connect is made.

Many processes that communicate using the socket IPC follow the client– server model. In this model, the _server_ process provides a _service_ to the _client_ process. When the service is available, the server process listens on a well- known address, and the client process uses connect() to reach the server.

A server process uses socket() to create a socket and bind() to bind the well-known address of its service to that socket. Then, it uses the lis- ten() system call to tell the kernel that it is ready to accept connections from clients and to specify howmany pending connections the kernel should queue until the server can service them. Finally, the server uses the accept() sys- tem call to accept individual connections. Both listen() and accept() take as an argument the socket descriptor of the original socket. The system call accept() returns a new socket descriptor corresponding to the new connec- tion; the original socket descriptor is still open for further connections. The server usually uses fork() to produce a new process after the accept() to service the client while the original server process continues to listen for more connections. There are also system calls for setting parameters of a connection and for returning the address of the foreign socket after an accept().

When a connection for a socket type, such as a stream socket, is established, the addresses of both endpoints are known, and no further addressing infor- mation is needed to transfer data. The ordinary read() and write() system calls may then be used to transfer data.

The simplest way to terminate a connection, and to destroy the associated socket, is to use the close() system call on its socket descriptor. We may also wish to terminate only one direction of communication of a duplex connection; the shutdown() system call can be used for this purpose.

Some socket types, such as datagram sockets, do not support connections. Instead, their sockets exchange datagrams thatmust be addressed individually. The system calls sendto() and recvfrom() are used for such connections. Both take as arguments a socket descriptor, a buffer pointer and length, and an address-buffer pointer and length. The address buffer contains the appropriate address for sendto() and is filled in with the address of the datagram just received by recvfrom(). The number of data actually transferred is returned by both system calls.

The select() system call can be used to multiplex data transfers on sev- eral file descriptors and/or socket descriptors. It can even be used to allow one server process to listen for client connections for many services and to fork()  

**C.9 Interprocess Communication 39**

a process for each connection as the connection is made. The server does a socket(), bind(), and listen() for each service and then does a select() on all the socket descriptors.When select() indicates activity on a descriptor, the server does an accept() on it and forks a process on the new descriptor returned by accept(), leaving the parent process to do a select() again.

**C.9.2 Network Support**

Almost all current UNIX systems support the UUCP network facilities, which aremostly used over dial-up telephone lines to support the UUCPmail network and the USENET news network. These are, however, rudimentary networking facilities; they do not support even remote login, much less remote proce- dure calls or distributed file systems. These facilities are almost completely implemented as user processes and are not part of the operating system itself.

FreeBSD supports the DARPA Internet protocols UDP, TCP, IP, and ICMP on a wide range of Ethernet, token-ring, and ARPANET interfaces. The framework in the kernel to support these protocols is intended to facilitate the implementa- tion of further protocols, and all protocols are accessible via the socket interface. Rob Gurwitz of BBN wrote the first version of the code as an add-on package for 4.1BSD.

The International Standards Organization’s (ISO) Open System Intercon- nection (OSI) Reference Model for networking prescribes seven layers of net- work protocols and strictmethods of communication between them.An imple- mentation of a protocol may communicate only with a peer entity speaking the same protocol at the same layer or with the protocol–protocol interface of a protocol in the layer immediately above or below in the same system. The ISO networking model is implemented in FreeBSD Reno and 4.4BSD.

The FreeBSD networking implementation, and to a certain extent the socket facility, is more oriented toward the ARPANET Reference Model (ARM). The ARPANET in its original form served as a proof of concept for many network- ing ideas, such as packet switching and protocol layering. The ARPANET was retired in 1988 because the hardware that supported it was no longer state of the art. Its successors, such as the NSFNET and the Internet, are even larger and serve as communications utilities for researchers and test-beds for Internet gateway research. The ARM predates the ISO model; the ISO model was in large part inspired by the ARPANET research.

Although the ISO model is often interpreted as setting a limit of one pro- tocol communicating per layer, the ARM allows several protocols in the same layer. There are only four protocol layers in the ARM:

• **Process/applications.** This layer subsumes the application, presentation, and session layers of the ISO model. Such user-level programs as the file- transfer protocol (FTP) and Telnet (remote login) exist at this level.

• **Host–host.** This layer corresponds to ISO’s transport and the top part of its network layers. Both the Transmission Control Protocol (TCP) and the Internet Protocol (IP) are in this layer, with TCP on top of IP. TCP corresponds to an ISO transport protocol, and IP performs the addressing functions of the ISO network layer.

• **Network interface.**This layer spans the lower part of the ISO network layer and the entire data-link layer. The protocols involved here depend on the  

**40 Appendix C BSD UNIX**

physical network type. The ARPANET uses the IMP-Host protocols, whereas an Ethernet uses Ethernet protocols.

• **Network hardware.** The ARM is primarily concerned with software, so there is no explicit network hardware layer. However, any actual network will have hardware corresponding to the ISO physical layer.

The networking framework in FreeBSD is more generalized than either the ISO model or the ARM, although it is most closely related to the ARM (Figure C.12).

User processes communicate with network protocols (and thus with other processes on other machines) via the socket facility. This facility corresponds to the ISO session layer, as it is responsible for setting up and controlling communications.

Sockets are supported by protocols—possibly by several, layered one on another. Aprotocol may provide services such as reliable delivery, suppression of duplicate transmissions, flow control, and addressing, depending on the socket type being supported and the services required by any higher protocols.

A protocol may communicate with another protocol or with the network interface that is appropriate for the network hardware. There is little restriction in the general framework on what protocols may communicate with what other protocols or on how many protocols may be layered on top of one another. The user process may, bymeans of the raw socket type, directly access any layer of protocol from the uppermost used to support one of the other socket types, such as streams, down to a raw network interface. This capability is used by routing processes and also for new protocol development.

Most often, there is one **network-interface driver** per network controller type. The network interface is responsible for handling characteristics specific to the local network being addressed. This arrangement ensures that the proto- cols using the interface do not need to be concerned with these characteristics.

The functions of the network interface depend largely on the **network hardware**, which iswhatever is necessary for the network. Somenetworksmay

ISO reference model

ARPANET reference model

4.2BSD layers

example layering

process applications

host–host

network interface

network hardware

protocol

network interfaces

network hardware

sockets

user programs and libraries

Ethernet driver

interlan controller

sock\_stream

telnet

TCP

IP

application

presentation

session transport

hardware

network data link

**Figure C.12** Network reference models and layering.  

**C.10 Summary 41**

support reliable transmission at this level, but most do not. Some networks provide broadcast addressing, but many do not.

The socket facility and the networking framework use a common set of memory buffers, or _mbufs_. These are intermediate in size between the large buffers used by the block I/O system and the C-lists used by character devices. An _mbuf_ is 128 bytes long; 112 bytes may be used for data, and the rest is used for pointers to link the_mbuf_ into queues and for indicators of howmuch of the data area is actually in use.

Data are ordinarily passed between layers—socket–protocol, protocol– protocol, or protocol–network interface—in _mbufs_. The ability to pass the buffers containing the data eliminates some data copying, but there is still frequently a need to remove or add protocol headers. It is also convenient and efficient for many purposes to be able to hold data that occupy an area the size of the memory-management page. Thus, the data of an_mbuf_ may reside not in the _mbuf_ itself but elsewhere in memory. There is an _mbuf_ page table for this purpose, as well as a pool of pages dedicated to _mbuf_ use.

**C.10 Summary**

The early advantages of UNIX were that it was written in a high-level lan- guage, was distributed in source form, and provided powerful operating- system primitives on an inexpensive platform. These advantages led to UNIX’s popularity at educational, research, and government institutions and eventu- ally in the commercial world. This popularity produced many strains of UNIX with varying and improved facilities.

UNIX provides a file system with tree-structured directories. The kernel supports files as unstructured sequences of bytes. Direct access and sequential access are supported through system calls and library routines.

Files are stored as an array of fixed-size data blocks with perhaps a trailing fragment. The data blocks are found by pointers in the inode. Directory entries point to inodes. Disk space is allocated from cylinder groups to minimize head movement and to improve performance.

UNIX is a multiprogrammed system. Processes can easily create new pro- cesses with the fork() system call. Processes can communicate with pipes or, more generally, sockets. They may be grouped into jobs that may be controlled with signals.

Processes are represented by two structures: the process structure and the user structure. CPU scheduling is a priority algorithm with dynamically computed priorities that reduces to round-robin scheduling in the extreme case.

FreeBSD memory management uses swapping supported by paging. A pagedaemon process uses a modified second-chance page-replacement algo- rithm to keep enough free frames to support the executing processes.

Page and file I/O uses a block buffer cache tominimize the amount of actual I/O. Terminal devices use a separate character-buffering system.

Networking support is one of the most important features in FreeBSD. The socket concept provides the programming mechanism to access other processes, even across a network. Sockets provide an interface to several sets of protocols.  

**42 Appendix C BSD UNIX**

**Further Reading**

\[McKusick et al. (2015)\] provides a good general discussion of FreeBSD. A modern scheduler for FreeBSD is described in \[Roberson (2003)\]. Locking in the Multithreaded FreeBSD Kernel is described in \[Baldwin (2002)\].

FreeBSD is described in _The FreeBSD Handbook_, which can be downloaded from http://www.freebsd.org.

**Bibliography**

**\[Baldwin (2002)\]** J. Baldwin, “Locking in the Multithreaded FreeBSD Kernel”, _USENIX BSD_ (2002).

**\[McKusick et al. (2015)\]** M. K. McKusick, G. V. Neville-Neil, and R. N. M. Wat- son,_The Design and Implementation of the FreeBSDUNIXOperating System–Second Edition_, Pearson (2015).

**\[Roberson (2003)\]** J. Roberson, “ULE: A Modern Scheduler For FreeBSD”, _Pro- ceedings of the USENIX BSDCon Conference_ (2003), pages 17–28.  

_D_**Appendix**_The Mach System_

**This chapter was firs written in 1991 and has been updated over time but is no longer modified**

In this appendix we examine the Mach operating system. Mach is designed to incorporate the many recent innovations in operating-system research to produce a fully functional, technically advanced system. Unlike UNIX, which was developed without regard for multiprocessing, Mach incorporates mul- tiprocessing support throughout. This support is exceedingly flexible, accom- modating shared-memory systems as well as systems with no memory shared between processors. Mach is designed to run on computer systems ranging fromone processor to thousands of processors. In addition, it is easily ported to many varied computer architectures. A key goal of Mach is to be a distributed system capable of functioning on heterogeneous hardware.

Although many experimental operating systems are being designed, built, and used, Mach satisfies the needs of most users better than the others because it offers full compatibility with UNIX 4.3 BSD. This compatibility also gives us a unique opportunity to compare two functionally similar, but internally dissimilar, operating systems. Mach and UNIX differ in their emphases, so our Mach discussion does not exactly parallel our UNIX discussion. In addition, we do not include a section on the user interface, because that component is similar to the user interface in 4.3 BSD.As youwill see,Mach provides the ability to layer emulation of other operating systems as well; other operating systems can even run concurrently with Mach.

**D.1 History of the Mach System**

Mach traces its ancestry to the Accent operating system developed at Carnegie Mellon University (CMU). Although Accent pioneered a number of novel operating-system concepts, its utility was limited by its inability to execute UNIX applications and its strong ties to a single hardware architecture, which made it difficult to port. Mach’s communication system and philosophy are derived from Accent, but many other significant portions of the system (for example, the virtual memory system and the management of tasks and threads) were developed from scratch. An important goal of the Mach effort was support for multiprocessors.

**1**  

**2 Appendix D The Mach System**

Mach’s development followed an evolutionary path from BSD UNIX sys- tems.Mach codewas initially developed inside the 4.2BSD kernel, with BSD ker- nel components replaced by Mach components as the Mach components were completed. The BSD components were updated to 4.3 BSD when that became available. By 1986, the virtual memory and communication subsystems were running on the DEC VAX computer family, including multiprocessor versions of the VAX. Versions for the IBM RT/PC and for Sun 3 workstations followed shortly; 1987 saw the completion of the Encore Multimax and Sequent Balance multiprocessor versions, including task and thread support, as well as the first official releases of the system, Release 0 and Release 1.

Through Release 2, Mach provided compatibility with the corresponding BSD systems by including much of BSD’s code in the kernel. The new features and capabilities of Mach made the kernels in these releases larger than the corresponding BSD kernels. Mach 3 (Figure D.1) moved the BSD code outside of the kernel, leaving a much smaller microkernel. This system implements only basic Mach features in the kernel; all UNIX-specific code has been evicted to run in user-mode servers. Excluding UNIX-specific code from the kernel allows replacement of BSD with another operating system or the simultaneous execution of multiple operating-system interfaces on top of the microkernel. In addition to BSD, user-mode implementations have been developed for DOS, the Macintosh operating system, and OSF/1. This approach has similarities to the virtual machine concept, but the virtual machine is defined by software (the Mach kernel interface), rather than by hardware. With Release 3.0, Mach became available on awide variety of systems, including single-processor Sun, Intel, IBM, and DEC machines and multiprocessor DEC, Sequent, and Encore systems.

Mach was propelled to the forefront of industry attention when the Open Software Foundation (OSF) announced in 1989 that it would useMach 2.5 as the basis for its new operating system, OSF/1. The release of OSF/1 occurred a year later, and it now competes with UNIX SystemV, Release 4, the operating system of choice among **_UNIX International (UI)_** members. OSF members include key technological companies such as IBM, DEC, and HP. Mach 2.5 is also the basis for the operating system on the NeXT workstation, the brainchild of Steve Jobs, of Apple Computer fame. OSF is evaluating Mach 3 as the basis for a future

Mach

tasks and threads

IPC virtual memory

scheduling

4.3 BSD

OSF/1

HPUX

OS/2

database system

**Figure D.1** Mach 3 structure.  

**D.2 Design Principles 3**

operating-system release, and research on Mach continues at CMU, OSF, and elsewhere.

**D.2 Design Principles**

The Mach operating system was designed to provide basic mechanisms that most current operating systems lack. The goal is to design an operating system that is BSD-compatible and, in addition, excels in the following areas:

• Support for diverse architectures, including multiprocessors with varying degrees of shared memory access: uniform memory access (UMA), non- uniform memory access (NUMA), and no remote memory access (NORMA)

• Ability to function with varying intercomputer network speeds, from wide-area networks to high-speed local-area networks and tightly coupled multiprocessors

• Simplified kernel structure, with a small number of abstractions (in turn, these abstractions are sufficiently general to allow other operating systems to be implemented on top of Mach.)

• Distributed operation, providing network transparency to clients and an object-oriented organization both internally and externally

• Integrated memory management and interprocess communication, to provide efficient communication of large numbers of data as well as communication-based memory management

• Heterogeneous system support, to make Mach widely available and inter- operable among computer systems from multiple vendors

The designers of Mach have been heavily influenced by BSD (and by UNIX in general), whose benefits include

• A simple programmer interface, with a good set of primitives and a con- sistent set of interfaces to system facilities

• Easy portability to a wide class of single processors

• An extensive library of utilities and applications

• The ability to combine utilities easily via pipes

Of course, the designers also wanted to redress what they saw as the drawbacks of BSD:

• Akernel that has become the repository ofmany redundant features—and that consequently is difficult to manage and modify

• Original design goals that made it difficult to provide support for multiprocessors, distributed systems, and shared program libraries (for instance, because the kernel was designed for single processors, it has no provisions for locking code or data that other processors might be using.)  

**4 Appendix D The Mach System**

• Too many fundamental abstractions, providing too many similar, compet- ing means with which to accomplish the same tasks

The development ofMach continues to be a huge undertaking. The benefits of such a system are equally large, however. The operating system runs on many existing single-processor and multiprocessor architectures, and it can be easily ported to future ones. It makes research easier, because computer scientists can add features via user-level code, instead of having to write their own tailor-made operating system. Areas of experimentation include operat- ing systems, databases, reliable distributed systems,multiprocessor languages, security, and distributed artificial intelligence. In its current version, the Mach system is usually as efficient as other major versions of UNIX when performing similar tasks.

**D.3 System Components**

To achieve the design goals of Mach, the developers reduced the operating- system functionality to a small set of basic abstractions, out of which all other functionality can be derived. TheMach approach is to place as little as possible within the kernel but to make what is there powerful enough that all other features can be implemented at the user level.

Mach’s design philosophy is to have a simple, extensible kernel, concen- trating on communication facilities. For instance, all requests to the kernel, and all data movement among processes, are handled through one communication mechanism. Mach is therefore able to provide system-wide protection to its users by protecting the communication mechanism. Optimizing this one com- munication path can result in significant performance gains, and it is simpler than trying to optimize several paths. Mach is extensible, because many tradi- tionally kernel-based functions can be implemented as user-level servers. For instance, all pagers (including the default pager) can be implemented exter- nally and called by the kernel for the user.

Mach is an example of an object-oriented system where the data and the operations that manipulate that data are encapsulated into an abstract object. Only the operations of the object are able to act on the entities defined in it. The details of how these operations are implemented are hidden, as are the internal data structures. Thus, a programmer can use an object only by invoking its defined, exported operations. A programmer can change the internal opera- tions without changing the interface definition, so changes and optimizations do not affect other aspects of system operation. The object-oriented approach supported by Mach allows objects to reside anywhere in a network of Mach systems, transparent to the user. The port mechanism, discussed later in this section, makes all of this possible.

Mach’s primitive abstractions are the heart of the systemand are as follows:

• A **task** is an execution environment that provides the basic unit of resource allocation. It consists of a virtual address space and protected access to system resources via ports, and it may contain one or more threads.

• A **thread** is the basic unit of execution andmust run in the context of a task (which provides the address space). All threads within a task share the  

**D.3 System Components 5**

task’s resources (ports, memory, and so on). There is no notion of a **_process_** inMach. Rather, a traditional process is implemented as a taskwith a single thread of control.

• A **port** is the basic object-reference mechanism in Mach and is imple- mented as a kernel-protected communication channel. Communication is accomplished by sending messages to ports; messages are queued at the destination port if no thread is immediately ready to receive them. Ports are protected by kernel-managed capabilities, or **port rights**. A task must have a port right to send a message to a port. The programmer invokes an operation on an object by **_sending_** a message to a port associated with that object. The object being represented by a port **_receives_** the messages.

• A **port set** is a group of ports sharing a common message queue. A thread can receive messages for a port set and thus service multiple ports. Each receivedmessage identifies the individual port (within the set) fromwhich it was received. The receiver can use this to identify the object referred to by the message.

• A **message** is the basic method of communication between threads in Mach. It is a typed collection of data objects. For each object, it may contain the actual data or a pointer to out-of-line data. Port rights are passed in messages; this is the only way to move them among tasks. (Passing a port right in shared memory does not work, because the Mach kernel will not permit the new task to use a right obtained in this manner.)

• A **memory object** is a source of memory. Tasks can access it by mapping portions of an object (or the entire object) into their address spaces. The object can be managed by a user-mode external memory manager. One example is a file managed by a file server; however, a memory object can be any object for which memory-mapped access makes sense. A mapped buffer implementation of a UNIX pipe is another example.

Figure D.2 illustrates these abstractions, which we explain further in the remainder of this chapter.

An unusual feature of Mach, and a key to the system’s efficiency, is the blending of memory and interprocess-communication (IPC) features. Whereas some other distributed systems (such as Solaris, with its NFS features) have special-purpose extensions to the file system to extend it over a network, Mach provides a general-purpose, extensible merger of memory andmessages at the heart of its kernel. This feature not only allowsMach to be used for distributed and parallel programming but also helps in the implementation of the kernel itself.

Mach connects memory management and IPC by allowing each to be used in the implementation of the other. Memory management is based on the use of memory objects. A memory object is represented by a port (or ports), and IPC messages are sent to this port to request operations (for example, pagein, pageout) on the object. Because IPC is used, memory objects can reside on remote systems and be accessed transparently. The kernel caches the contents of memory objects in local memory. Conversely, memory-management tech- niques are used in the implementation of message passing. Where possible,  

**6 Appendix D The Mach System**

task

data region

text region

threads

program counter

memory object

message

port

port set

secondary storage

**Figure D.2** Mach’s basic abstractions.

Mach passes messages by moving pointers to shared memory objects, rather than by copying the objects themselves.

IPC tends to involve considerable system overhead. For intrasystem mes- sages, it is generally less efficient than communication accomplished through shared memory. Because Mach is a message-based kernel, message handling must be carried out efficiently. Most of the inefficiency of message handling in traditional operating systems is due to either the copying ofmessages from one task to another (for intracomputer messages) or low network-transfer speed (for intercomputer messages). To solve these problems, Mach uses virtual memory remapping to transfer the contents of large messages. In other words, the message transfer modifies the receiving task’s address space to include a copy of the message contents. Virtual copy (or copy-on-write) techniques are used to avoid or delay the actual copying of the data. This approach has several advantages:

• Increased flexibility in memory management for user programs

• Greater generality, allowing the virtual copy approach to be used in tightly and loosely coupled computers

• Improved performance over UNIX message passing

• Easier task migration (because ports are location independent, a task and all its ports can be moved from one machine to another. All tasks that previously communicated with the moved task can continue to do so because they reference the task only by its ports and communicate via messages to these ports.)  

**D.4 Process Management 7**

In the sections that follow, we detail the operation of process management, IPC, andmemorymanagement. Then, we discussMach’s chameleonlike ability to support multiple operating-system interfaces.

**D.4 Process Management**

A task can be thought of as a traditional process that does not have an instruc- tion pointer or a register set. A task contains a virtual address space, a set of port rights, and accounting information. A task is a passive entity that does nothing unless it has one or more threads executing in it.

**D.4.1 Basic Structure**

A task containing one thread is similar to a UNIX process. Just as a fork() system call produces a new UNIX process, Mach creates a new task by using fork(). The new task’s memory is a duplicate of the parent’s address space, as dictated by the **inheritance attributes** of the parent’s memory. The new task contains one thread, which is started at the same point as the creating fork() call in the parent. Threads and tasks can also be suspended and resumed.

Threads are especially useful in server applications, which are common in UNIX, since one task can have multiple threads to service multiple requests to the task. Threads also allow efficient use of parallel computing resources. Rather than having one process on each processor, with the corresponding per- formance penalty and operating-system overhead, a task can have its threads spread among parallel processors. Threads add efficiency to user-level pro- grams as well. For instance, in UNIX, an entire process must wait when a page fault occurs or when a system call is executed. In a task with multiple threads, only the thread that causes the page fault or executes a system call is delayed; all other threads continue executing. Because Mach has kernel- supported threads (Chapter 4), the threads have some cost associated with them. Theymust have supporting data structures in the kernel, andmore com- plex kernel-scheduling algorithms must be provided. These algorithms and thread states are discussed in Chapter 4.

At the user level, threads may be in one of two states:

• **Running.** The thread is either executing or waiting to be allocated a pro- cessor. A thread is considered to be running even if it is blocked within the kernel (waiting for a page fault to be satisfied, for instance).

• **Suspended.** The thread is neither executing on a processor nor waiting to be allocated a processor. A thread can resume its execution only if it is returned to the running state.

These two states are also associated with a task. An operation on a task affects all threads in a task, so suspending a task involves suspending all the threads in it. Task and thread suspensions are separate, independent mecha- nisms, however, so resuming a thread in a suspended task does not resume the task.

Mach provides primitives fromwhich thread-synchronization tools can be built. This practice is consistent with Mach’s philosophy of providing mini-  

**8 Appendix D The Mach System**

mum yet sufficient functionality in the kernel. The Mach IPC facility can be used for synchronization, with processes exchanging messages at rendezvous points. Thread-level synchronization is provided by calls to start and stop threads at appropriate times. A **_suspend count_** is kept for each thread. This count allows multiple suspend() calls to be executed on a thread, and only when an equal number of resume() calls occur is the thread resumed. Unfor- tunately, this feature has its own limitation. Because it is an error for a start() call to be executed before a stop() call (the suspend count would become negative), these routines cannot be used to synchronize shared data access. However, wait() and signal() operations associated with semaphores, and used for synchronization, can be implemented via the IPC calls. We discuss this method in Section D.5.

**D.4.2 The C Threads Package**

Mach provides low-level but flexible routines instead of polished, large, and more restrictive functions. Rather than making programmers work at this low level, Mach provides many higher-level interfaces for programming in C and other languages. For instance, the C threads package provides multiple threads of control, shared variables, mutual exclusion for critical sections, and condition variables for synchronization. In fact, C threads is one of the major influences on the POSIX Pthreads standard, which many operating systems support. As a result, there are strong similarities between the C threads and Pthreads programming interfaces. The thread-control routines include calls to perform these tasks:

• Create a new thread within a task, given a function to execute and param- eters as input. The thread then executes concurrently with the creating thread, which receives a thread identifier when the call returns.

• Destroy the calling thread, and return a value to the creating thread.

• Wait for a specific thread to terminate before allowing the calling thread to continue. This call is a synchronization tool, much like the UNIX wait() system calls.

• Yield use of a processor, signaling that the scheduler can run another thread at this point. This call is also useful in the presence of a preemptive scheduler, as it can be used to relinquish the CPU voluntarily before the time quantum (or scheduling interval) expires if a thread has no use for the CPU.

Mutual exclusion is achieved through the use of spinlocks, as discussed in Chapter 6. The routines associated with mutual exclusion are these:

• The routine mutex alloc() dynamically creates a mutex variable.

• The routine mutex free() deallocates a dynamically created mutex vari- able.

• The routine mutex lock() locks a mutex variable. The executing thread loops in a spinlock until the lock is attained. A deadlock results if a thread with a lock tries to lock the same mutex variable. Bounded waiting is  

**D.4 Process Management 9**

not guaranteed by the C threads package. Rather, it is dependent on the hardware instructions used to implement the mutex routines.

• The routine mutex unlock() unlocks a mutex variable, much like the typical signal() operation of a semaphore.

General synchronization without busy waiting can be achieved through the use of condition variables, which can be used to implement a monitor, as described in Chapter 6. A condition variable is associated with a mutex variable and reflects a Boolean state of that variable. The routines associated with general synchronization are these:

• The routine condition alloc() dynamically allocates a condition vari- able.

• The routine condition free() deletes a dynamically created condition variable allocated as a result of condition alloc().

• The routine condition wait() unlocks the associated mutex variable and blocks the thread until a condition signal() is executed on the condition variable, indicating that the event being waited for may have occurred. The mutex variable is then locked, and the thread continues. A condition signal() does not guarantee that the condition still holds when the unblocked thread finally returns from its condition wait() call, so the awakened thread must loop, executing the condition wait() routine until it is unblocked and the condition holds.

As an example of the C threads routines, consider the bounded-buffer synchronization problem of Section 7.1.1. The producer and consumer are represented as threads that access the common bounded-buffer pool. We use a mutex variable to protect the buffer while it is being updated. Once we have exclusive access to the buffer, we use condition variables to block the producer thread if the buffer is full and to block the consumer thread if the buffer is empty. As in Chapter 6, we assume that the buffer consists of n slots, each capable of holding one item. The mutex semaphore provides mutual exclusion for accesses to the buffer pool and is initialized to the value 1. The empty and full semaphores count the number of empty and full buffers, respectively. The semaphore empty is initialized to the value n; the semaphore full is initialized to the value 0. The condition variable nonempty is true while the buffer has items in it, and nonfull is true if the buffer has an empty slot. The first step includes the allocation of the mutex and condition variables:

mutex alloc(mutex); condition alloc(nonempty, nonfull);

The code for the producer thread is shown in Figure D.3, and the code for the consumer thread is shown in Figure D.4. When the program terminates, the mutex and condition variables need to be deallocated:

mutex free(mutex); condition free(nonempty, nonfull);  

**10 Appendix D The Mach System**

do _{_ . . .

// produce an item into nextp . . .

mutex lock(mutex); while(full)

condition wait(nonfull, mutex); . . .

// add nextp to buffer . . .

condition signal(nonempty); mutex unlock(mutex);

_}_ while(TRUE);

**Figure D.3** The structure of the producer process.

**D.4.3 The CPU Scheduler**

The CPU scheduler for a thread-basedmultiprocessor operating system ismore complex than its process-based relatives. There are generally more threads in a multithreaded system than there are processes in a multitasking system. Keeping track ofmultiple processors is also difficult and is a relatively new area of research.Mach uses a simple policy to keep the scheduler manageable. Only threads are scheduled, so no knowledge of tasks is needed in the scheduler. All threads compete equally for resources, including time quanta.

Each thread has an associated priority number ranging from 0 through 127, which is based on the exponential average of its usage of the CPU. That is, a thread that recently used the CPU for a large amount of time has the lowest

do _{_ mutex lock(mutex); while(empty)

condition wait(nonempty, mutex); . . .

// remove an item from the buffe to nextc . . .

condition signal(nonfull); mutex unlock(mutex);

. . . // consume the item in nextc

. . . _}_ until(FALSE);

**Figure D.4** The structure of the consumer process.  

**D.4 Process Management 11**

priority. Mach uses the priority to place the thread in one of 32 global run queues. These queues are searched in priority order for waiting threads when a processor becomes idle. Mach also keeps per-processor, or local, run queues. A local run queue is used for threads that are bound to an individual processor. For instance, a device driver for a device connected to an individual CPU must run on only that CPU.

Instead of a central dispatcher that assigns threads to processors, each processor consults the local and global run queues to select the appropriate next thread to run. Threads in the local run queue have absolute priority over those in the global queues, because it is assumed that they are performing some chore for the kernel. The run queues—like most other objects in Mach—are locked when they are modified to avoid simultaneous changes by multiple processors. To speed dispatching of threads on the global run queue, Mach maintains a list of idle processors.

Additional scheduling difficulties arise from the multiprocessor nature of Mach. A fixed time quantum is not appropriate because, for instance, there may be fewer runnable threads than there are available processors. It would be wasteful to interrupt a thread with a context switch to the kernel when that thread’s quantum runs out, only to have the thread be placed right back in the running state. Thus, instead of using a fixed-length quantum, Mach varies the size of the time quantum inversely with the total number of threads in the system. It keeps the time quantum over the entire system constant, however. For example, in a systemwith 10 processors, 11 threads, and a 100-millisecond quantum, a context switch needs to occur on each processor only once per second to maintain the desired quantum.

Of course, complications still exist. Even relinquishing the CPU while wait- ing for a resource is more difficult than it is on traditional operating systems. First, a thread must issue a call to alert the scheduler that the thread is about to block. This alert avoids race conditions and deadlocks, which could occur when the execution takes place in amultiprocessor environment. A second call actually causes the thread to be moved off the run queue until the appropriate event occurs. The scheduler uses many other internal thread states to control thread execution.

**D.4.4 Exception Handling**

Mach was designed to provide a single, simple, consistent exception-handling system, with support for standard as well as user-defined exceptions. To avoid redundancy in the kernel, Mach uses kernel primitives whenever possible. For instance, an exception handler is just another thread in the task in which the exception occurs. Remote procedure call (RPC) messages are used to synchro- nize the execution of the thread causing the exception (the **_victim_**) and that of the handler and to communicate information about the exception between the victim and handler. Mach exceptions are also used to emulate the BSD signal package.

Disruptions to normal program execution come in two varieties: internally generated exceptions and external interrupts. Interrupts are asynchronously generated disruptions of a thread or task, whereas exceptions are caused by the occurrence of unusual conditions during a thread’s execution. Mach’s general- purpose exception facility is used for error detection and debugger support.  

**12 Appendix D The Mach System**

This facility is also useful for other functions, such as taking a core dump of a bad task, allowing tasks to handle their own errors (mostly arithmetic), and emulating instructions not implemented in hardware.

Mach supports two different granularities of exception handling. Error handling is supported by per-thread exception handling, whereas debuggers use per-task handling. It makes little sense to try to debug only one thread or to have exceptions frommultiple threads invokemultiple debuggers. Aside from this distinction, the only difference between the two types of exceptions lies in their inheritance fromaparent task. Task-wide exception-handling facilities are passed from the parent to child tasks, so debuggers are able to manipulate an entire tree of tasks. Error handlers are not inherited and default to no handler at thread- and task-creation time. Finally, error handlers take precedence over debuggers if the exceptions occur simultaneously. The reason for this approach is that error handlers are normally part of the task and therefore should execute normally even in the presence of a debugger.

Exception handling proceeds as follows:

• The victim thread causes notification of an exception’s occurrence via a raise() RPC message sent to the handler.

• The victim then calls a routine to wait until the exception is handled.

• The handler receives notification of the exception, usually including infor- mation about the exception, the thread, and the task causing the exception.

• The handler performs its function according to the type of exception. The handler’s action involves **_clearing_** the exception, causing the victim to **_resume_**, or **_terminating_** the victim thread.

To support the execution of BSD programs, Mach needs to support BSD- style signals. Signals provide software-generated interrupts and exceptions. Unfortunately, signals are of limited functionality in multithreaded operating systems. The first problem is that, in UNIX, a signal’s handler must be a routine in the process receiving the signal. If the signal is caused by a problem in the process itself (for example, a division by 0), the problem cannot be remedied, because a process has limited access to its own context. A second, more trou- blesome aspect of signals is that they were designed for only single-threaded programs. For instance, itmakes no sense for all threads in a task to get a signal, but how can a signal be seen by only one thread?

Because the signal system must work correctly with multithreaded appli- cations for Mach to run 4.3 BSD programs, signals could not be abandoned. Producing a functionally correct signal package required several rewrites of the code, however. A final problem with UNIX signals is that they can be lost. This loss occurs when another signal of the same type occurs before the first is handled. Mach exceptions are queued as a result of their RPC implementation.

Externally generated signals, including those sent from one BSD process to another, are processed by the BSD server section of the Mach 2.5 kernel. Their behavior is therefore the same as it is under BSD. Hardware exceptions are a different matter, because BSD programs expect to receive hardware exceptions as signals. Therefore, a hardware exception caused by a thread must arrive at the thread as a signal. So that this result is produced, hardware exceptions are  

**D.5 Interprocess Communication 13**

converted to exception RPCs. For tasks and threads that do not make explicit use of theMach exception-handling facility, the destination of this RPC defaults to an in-kernel task. This task has only one purpose: Its thread runs in a continuous loop, receiving the exception RPCs. For each RPC, it converts the exception into the appropriate signal,which is sent to the thread that caused the hardware exception. It then completes the RPC, clearing the original exception condition.With the completion of the RPC, the initiating thread reenters the run state. It immediately sees the signal and executes its signal-handling code. In this manner, all hardware exceptions begin in a uniform way—as exception RPCs. Threads not designed to handle such exceptions, however, receive the exceptions as they would on a standard BSD system—as signals. In Mach 3.0, the signal-handling code is moved entirely into a server, but the overall structure and flow of control is similar to those of Mach 2.5.

**D.5 Interprocess Communication**

Most commercial operating systems, such as UNIX, provide communication between processes and between hosts with fixed, global names (or Internet addresses). There is no location independence of facilities, because any remote system needing to use a facility must know the name of the system providing that facility. Usually, data in the messages are untyped streams of bytes. Mach simplifies this picture by sending messages between location-independent ports. The messages contain typed data for ease of interpretation. All BSD communication methods can be implemented with this simplified system.

The two components of Mach IPC are ports and messages. Almost every- thing in Mach is an object, and all objects are addressed via their commu- nication ports. Messages are sent to these ports to initiate operations on the objects by the routines that implement the objects. By depending on only ports and messages for all communication, Mach delivers location independence of objects and security of communication. Data independence is provided by the NetMsgServer task (Section D.5.3).

Mach ensures security by requiring that message senders and receivers have **_rights_**. Aright consists of a port name and a capability—send or receive— on that port, and is much like a capability in object-oriented systems. Only one task may have receive rights to any given port, but many tasks may have send rights. When an object is created, its creator also allocates a port to represent the object and obtains the access rights to that port. Rights can be given out by the creator of the object, including the kernel, and are passed in messages. If the holder of a receive right sends that right in a message, the receiver of the message gains the right, and the sender loses it. A task may allocate ports to allow access to any objects it owns or for communication. The destruction of either a port or the holder of the receive right causes the revocation of all rights to that port, and the tasks holding send rights can be notified if desired.

**D.5.1 Ports**

Aport is implemented as a protected, bounded queue within the kernel of the system on which the object resides. If a queue is full, a sender may abort the  

**14 Appendix D The Mach System**

send,wait for a slot to become available in the queue, or have the kernel deliver the message.

Several system calls provide the port with the following functionalities:

• Allocate a new port in a specified task and give the caller’s task all access rights to the new port. The port name is returned.

• Deallocate a task’s access rights to a port. If the task holds the receive right, the port is destroyed, and all other tasks with send rights are, potentially, notified.

• Get the current status of a task’s port.

• Create a backup port, which is given the receive right for a port if the task containing the receive right requests its deallocation or terminates.

When a task is created, the kernel creates several ports for it. The function task self() returns the name of the port that represents the task in calls to the kernel. For instance, to allocate a new port, a task calls port allocate()with task self() as the name of the task that will own the port. Thread creation results in a similar thread self() thread kernel port. This scheme is similar to the standard process-ID concept found in UNIX. Another port is returned by task notify(); this is the port towhich the kernel will send event-notification messages (such as notifications of port terminations).

Ports can also be collected into **_port sets_**. This facility is useful if one thread is to service requests coming in on multiple ports—for example, for multiple objects. A port may be a member of no more than one port set at a time. Furthermore, if a port is in a set, it may not be used directly to receivemessages. Instead, messages will be routed to the port set’s queue. A port set may not be passed in messages, unlike a port. Port sets are objects that serve a purpose similar to the 4.3 BSD select() system call, but they are more efficient.

**D.5.2 Messages**

A message consists of a fixed-length header and a variable number of typed data objects. The header contains the destination’s port name, the name of the reply port to which return messages should be sent, and the length of the message (Figure D.5). The data in the message (or in-line data) were limited to less than 8 KB in Mach 2.5 systems, but Mach 3.0 has no limit. Each data section may be a simple type (numbers or characters), port rights, or pointers to out-of-line data. Each section has an associated type, so that the receiver can unpack the data correctly even if it uses a byte ordering different from that used by the sender. The kernel also inspects the message for certain types of data. For instance, the kernel must process port information within a message, either by translating the port name into an internal port data structure address or by forwarding it for processing to the NetMsgServer (Section D.5.3).

The use of pointers in a message provides the means to transfer the entire address space of a task in one single message. The kernel also must process pointers to out-of-line data, since a pointer to data in the sender’s address space would be invalid in the receiver’s—especially if the sender and receiver reside on different systems. Generally, systems send messages by copying the data from the sender to the receiver. Because this technique can be inefficient, especially for large messages, Mach takes a different approach. The data refer-  

**D.5 Interprocess Communication 15**

destination port reply port size/operation pure typed data port rights out-of-line-data

message control

memory cache object memory cache object

port

message queue

port

messagemessage

• • •

**Figure D.5** Mach messages.

enced by a pointer in a message being sent to a port on the same system are not copied between the sender and the receiver. Instead, the address map of the receiving task is modified to include a copy-on-write copy of the pages of themessage. This operation is_much_ faster than a data copy andmakesmessage passing more efficient. In essence, message passing is implemented via virtual memory management.

In Version 2.5, this operation was implemented in two phases. A pointer to a region of memory caused the kernel to map that region into its own space temporarily, setting the sender’s memory map to copy-on-write mode to ensure that any modifications did not affect the original version of the data. When a message was received at its destination, the kernel moved its mapping to the receiver’s address space, using a newly allocated region of virtual memory within that task.

In Version 3, this processwas simplified. The kernel creates a data structure that would be a copy of the region if it were part of an addressmap. On receipt, this data structure is added to the receiver’smap and becomes a copy accessible to the receiver.

The newly allocated regions in a task do not need to be contiguous with previous allocations, so Mach virtual memory is said to be **_sparse_**, consisting of regions of data separated by unallocated addresses. A full message transfer is shown in Figure D.6.

**D.5.3 The NetMsgServer**

For a message to be sent between computers, the message’s destination must be located, and the message must be transmitted to the destination. UNIX tra- ditionally leaves these mechanisms to the low-level network protocols, which require the use of statically assigned communication endpoints (for example,  

**16 Appendix D The Mach System**

send operation

B

P1

kernel mapA map B map

A

receive operation

B

P1

kernel mapA map B map

A

**Figure D.6** Mach message transfer.

the port number for services based on TCP or UDP). One of Mach’s tenets is that all objects within the system are location independent and that the loca- tion is transparent to the user. This tenet requires Mach to provide location- transparent naming and transport to extend IPC across multiple computers.

This naming and transport are performed by the **Network Message Server** (**NetMsgServer**), a user-level, capability-based networking daemon that for- wards messages between hosts. It also provides a primitive network-wide name service that allows tasks to register ports for lookup by tasks on any other computer in the network. Mach ports can be transferred only in messages, and messagesmust be sent to ports. The primitive name service solves the problem of transferring the first port. Subsequent IPC interactions are fully transparent, because the NetMsgServer tracks all rights and out-of-line memory passed in intercomputer messages and arranges for the appropriate transfers. The NetMsgServers maintain among themselves a distributed database of port rights that have been transferred between computers and of the ports to which these rights correspond.

The kernel uses the NetMsgServer when a message needs to be sent to a port that is not on the kernel’s computer. Mach’s kernel IPC is used to transfer the message to the local NetMsgServer. The NetMsgServer then uses whatever network protocols are appropriate to transfer the message to its peer on the other computer. The notion of a NetMsgServer is protocol independent, and NetMsgServers have been built to use various protocols. Of course, the NetMsgServers involved in a transfer must agree on the protocol used. Finally, the NetMsgServer on the destination computer uses that kernel’s IPC to send the message to the correct destination task.

The ability to extend local IPC transparently across nodes is supported by the use of proxy ports. When a send right is transferred from one computer to another, the NetMsgServer on the destination computer creates a new port, or proxy, to represent the original port at the destination. Messages sent to this proxy are received by the NetMsgServer and are forwarded transparently  

**D.5 Interprocess Communication 17**

to the original port. This procedure is one example of how NetMsgServers cooperate to make a proxy indistinguishable from the original port.

Because Mach is designed to function in a network of heterogeneous sys- tems, it must provide a way for systems to send data formatted in a way that is understandable by both the sender and the receiver. Unfortunately, computers differ in the formats they use to store various types of data. For instance, an integer on one systemmight take 2 bytes to store, and the most significant byte might be stored before the least significant one. Another systemmight reverse this ordering. The NetMsgServer therefore uses the type information stored in a message to translate the data from the sender’s to the receiver’s format. In this way, all data are represented correctly when they reach their destination.

The NetMsgServer on a given computer accepts RPCs that add, look up, and remove network ports from the NetMsgServer’s name service. As a secu- rity precaution, a port value provided in an add request for a port must match that in the remove request for a thread to ask for a port name to be removed from the database.

As an example of theNetMsgServer’s operation, consider a thread on node A sending a message to a port that happens to be in a task on node B. The program simply sends a message to a port to which it has a send right. The message is first passed to the kernel, which delivers it to its first recipient, the NetMsgServer on node A. The NetMsgServer then contacts (through its database information) the NetMsgServer on node B and sends the message. The NetMsgServer on node B presents the message to the kernel with the appropriate local port for node B. The kernel finally provides the message to the receiving task when a thread in that task executes a msg receive() call. This sequence of events is shown in Figure D.7.

Mach 3.0 provides an alternative to the NetMsgServer as part of its improved support for NORMAmultiprocessors. The NORMA IPC subsystem of Mach 3.0 implements functionality similar to the NetMsgServer directly in the

sender

kernel

system A

user process

NetMsg- server

receiver

kernel

system B

user process

NetMsg- server

**Figure D.7** Network IPC forwarding by NetMsgServer.  

**18 Appendix D The Mach System**

Mach kernel, providing much more efficient internode IPC for multicomputers with fast interconnection hardware. For example, the time-consuming copying of messages between the NetMsgServer and the kernel is eliminated. Use of the NORMA IPC does not preclude use of the NetMsgServer; the NetMsgServer can still be used to provide Mach IPC service over networks that link a NORMA multiprocessor to other computers. In addition to the NORMA IPC, Mach 3.0 also provides support for memory management across a NORMA system and enables a task in such a system to create child tasks on nodes other than its own. These features support the implementation of a single-system-image operating system on a NORMA multiprocessor. The multiprocessor behaves like one large system rather than an assemblage of smaller systems (for both users and applications).

**D.5.4 Synchronization Through IPC**

The IPC mechanism is extremely flexible and is used throughout Mach. For example, it may be used for thread synchronization. A port may be used as a synchronization variable and may have _n_ messages sent to it for _n_ resources. Any thread wishing to use a resource executes a receive call on that port. The threadwill receive amessage if the resource is available. Otherwise, it will wait on the port until a message is available there. To return a resource after use, the thread can send a message to the port. In this regard, receiving is equivalent to the semaphore operation wait(), and sending is equivalent to signal(). This method can be used for synchronizing semaphore operations among threads in the same task, but it cannot be used for synchronization among tasks, because only one task may have receive rights to a port. For more general-purpose semaphores, a simple daemon can be written to implement the same method.

**D.6 Memory Management**

Given the object-oriented nature of Mach, it is not surprising that a principal abstraction in Mach is the memory object. Memory objects are used to manage secondary storage and generally represent files, pipes, or other data that are mapped into virtual memory for reading and writing (Figure D.8). Memory objectsmay be backed by user-levelmemorymanagers, which take the place of the more traditional kernel-incorporated virtual memory pager found in other operating systems. In contrast to the traditional approach of having the kernel manage secondary storage, Mach treats secondary-storage objects (usually files) as it does all other objects in the system. Each object has a port associated with it and may be manipulated by messages sent to its port. Memory objects —unlike the memory-management routines in monolithic, traditional kernels —allow easy experimentation with new memory-manipulation algorithms.

**D.6.1 Basic Structure**

The virtual address space of a task is generally sparse, consisting ofmany holes of unallocated space. For instance, a memory-mapped file is placed in some set of addresses. Largemessages are also transferred as sharedmemory segments. For each of these segments, a section of virtual memory address is used to provide the threads with access to the message. As new items are mapped or  

**D.6 Memory Management 19**

previous entry

address space start/end

next entry

inheritance

protection current/max

object

offset therein

map entry

text initialized

data uninitialized

data stack

head tail

user address space

virtual memory object

port for secondary

storage

cached pages

**Figure D.8** Mach virtual memory task address map.

removed from the address space, holes of unallocated memory appear in the address space.

Mach makes no attempt to compress the address space, although a task may fail (or crash) if it has no room for a requested region in its address space. Given that address spaces are 4 GB or more, this limitation is not currently a problem. However, maintaining a regular page table for a 4-GB address space for each task, especially one with holes in it, would use excessive amounts of memory (1 MB or more). The key to sparse address spaces is that page-table space is used only for currently allocated regions.When a page fault occurs, the kernel must check to see whether the page is in a valid region, rather than sim- ply indexing into the page table and checking the entry. Although the resulting lookup ismore complex, the benefits of reducedmemory-storage requirements and simpler address-space maintenance make the approach worthwhile.

Mach also has system calls to support standard virtual memory function- ality, including the allocation, deallocation, and copying of virtual memory. When allocating a new virtual memory object, the thread may provide an address for the object or may let the kernel choose the address. Physical mem- ory is not allocated until pages in this object are accessed. The object’s backing store is managed by the default pager (Section D.6.2). Virtual memory objects  

**20 Appendix D The Mach System**

are also allocated automatically when a task receives a message containing out-of-line data.

Associated system calls return information about a memory object in a task’s address space, change the access protection of the object, and specify how an object is to be passed to child tasks at the time of their creation (shared, copy-on-write, or not present).

**D.6.2 User-Level Memory Managers**

A secondary-storage object is usually mapped into the virtual address space of a task. Mach maintains a cache of memory-resident pages of all mapped objects, as in other virtual memory implementations. However, a page fault occurring when a thread accesses a nonresident page is executed as a message to the object’s port. The concept that a memory object can be created and serviced by nonkernel tasks (unlike threads, for instance, which are created and maintained only by the kernel) is important. The end result is that, in the traditional sense, memory can be paged by user-written memory managers. When the object is destroyed, it is up to the memory manager to write back any changed pages to secondary storage. No assumptions are made by Mach about the content or importance of memory objects, so the memory objects are independent of the kernel.

In several circumstances, user-level memory managers are insufficient. For instance, a task allocating a new region of virtual memory might not have a memory manager assigned to that region, since it does not represent a secondary-storage object (butmust be paged), or amemorymanagermight fail to perform pageout. Mach itself also needs a memory manager to take care of its memory needs. For these cases, Mach provides a default memory manager. The Mach 2.5 default memory manager uses the standard file system to store data that must be written to disk, rather than requiring a separate swap space, as in 4.3 BSD. In Mach 3.0 (and OSF/1), the default memory manager is capable of using either files in a standard file system or dedicated disk partitions. The default memorymanager has an interface similar to that of the user-level ones, but with some extensions to support its role as the memory manager that can be relied on to perform pageout when user-level managers fail to do so.

Pageout policy is implemented by an internal kernel thread, the **_pageout daemon_**. Apaging algorithm based on FIFOwith second chance (Section 10.4.5) is used to select pages for replacement. The selected pages are sent to the appropriate manager (either user level or default) for actual pageout. A user- level manager may be more intelligent than the default manager, and it may implement a different paging algorithm suitable to the object it is backing (that is, by selecting some other page and forcibly paging it out). If a user-level manager fails to reduce the resident set of pages when asked to do so by the kernel, the default memorymanager is invoked, and it pages out the user-level manager to reduce the user-level manager’s resident set size. Should the user- level manager recover from the problem that prevented it from performing its own pageouts, it will touch these pages (causing the kernel to page them in again) and can then page them out as it sees fit.

If a thread needs access to data in a memory object (for instance, a file), it invokes the vm map() system call. Included in this system call is a port that identifies the object and the memory manager that is responsible for the  

**D.6 Memory Management 21**

region. The kernel executes calls on this port when data are to be read or written in that region. An added complexity is that the kernel makes these calls asynchronously, since it would not be reasonable for the kernel to be waiting on a user-level thread. Unlike the situation with pageout, the kernel has no recourse if its request is not satisfied by the external memory manager. The kernel has no knowledge of the contents of an object or of how that object must be manipulated.

Memory managers are responsible for the consistency of the contents of a memory object mapped by tasks on different machines. (Tasks on a single machine share a single copy of a mappedmemory object.) Consider a situation in which tasks on two different machines attempt to modify the same page of an object at the same time. It is up to the manager to decide whether these modifications must be serialized. A conservative manager implementing strict memory consistency would force the modifications to be serialized by grant- ing write access to only one kernel at a time. A more sophisticated manager could allow both accesses to proceed concurrently (for example, if themanager knew that the two tasks were modifying distinct areas within the page and that it could merge the modifications successfully at some future time). Most external memory managers written for Mach (for example, those implement- ing mapped files) do not implement logic for dealing with multiple kernels, due to the complexity of such logic.

When the first vm map() call is made on a memory object, the kernel sends a message to the memory manager port passed in the call, invoking the mem- ory manager init() routine, which the memory manager must provide as part of its support of a memory object. The two ports passed to the mem- ory manager are a **control port** and a **name port**. The control port is used by the memory manager to provide data to the kernel—for example, pages to be made resident. Name ports are used throughout Mach. They do not receive messages but are used simply as points of reference and comparison. Finally, the memory object must respond to a memory manager init() call with a memory object set attributes() call to indicate that it is ready to accept requests. When all tasks with send rights to a memory object relinquish those rights, the kernel deallocates the object’s ports, thus freeing the memory manager and memory object for destruction.

Several kernel calls are needed to support external memorymanagers. The vm map() call was just discussed. In addition, some commands get and set attributes and provide page-level locking when it is required (for instance, after a page fault has occurred but before the memory manager has returned the appropriate data). Another call is used by the memory manager to pass a page (or multiple pages, if read-ahead is being used) to the kernel in response to a page fault. This call is necessary since the kernel invokes the memory manager asynchronously. Finally, several calls allow the memory manager to report errors to the kernel.

Thememorymanager itselfmust provide support for several calls so that it can support an object. We have already discussed memory object init() and others. When a thread causes a page fault on a memory object’s page, the ker- nel sends a memory object data request() to the memory object’s port on behalf of the faulting thread. The thread is placed in a wait state until the mem- ory manager either returns the page in a memory object data provided() call or returns an appropriate error to the kernel. Any of the pages that have  

**22 Appendix D The Mach System**

been modified, or any “precious pages” that the kernel needs to remove from resident memory (due to page aging, for instance), are sent to the memory object via memory object data write(). **_Precious pages_** are pages that may not have been modified but that cannot be discarded as they otherwise would be because the memory manager no longer retains a copy. The memory man- ager declares these pages to be precious and expects the kernel to return them when they are removed frommemory. Precious pages save unnecessary dupli- cation and copying of memory.

In the current version, Mach does not allow external memory managers to affect the page-replacement algorithm directly. Mach does not export the memory-access information that would be needed for an external task to select the least recently used page, for instance. Methods of providing such informa- tion are currently under investigation. An external memory manager is still useful for a variety of reasons, however:

• It may reject the kernel’s replacement victim if it knows of a better candi- date (for instance, MRU page replacement).

• It may monitor the memory object it is backing and request pages to be paged out before the memory usage invokes Mach’s pageout daemon.

• It is especially important in maintaining consistency of secondary storage for threads on multiple processors, as we show in Section D.6.3.

• It can control the order of operations on secondary storage to enforce consistency constraints demanded by database management systems. For example, in transaction logging, transactions must be written to a log file on disk before they modify the database data.

• It can control mapped file access.

**D.6.3 Shared Memory**

Mach uses shared memory to reduce the complexity of various system facili- ties, as well as to provide these features in an efficient manner. Sharedmemory generally provides extremely fast interprocess communication, reduces over- head in file management, and helps to support multiprocessing and database management. Mach does not use shared memory for all these traditional shared-memory roles, however. For instance, all threads in a task share that task’s memory, so no formal shared-memory facility is needed within a task. However, Machmust still provide traditional shared memory to support other operating-system constructs, such as the UNIX fork() system call.

It is obviously difficult for tasks onmultiplemachines to sharememory and to maintain data consistency. Mach does not try to solve this problem directly; rather, it provides facilities to allow the problem to be solved. Mach supports consistent shared memory only when the memory is shared by tasks running on processors that sharememory. Aparent task is able to declarewhich regions of memory are to be **_inherited_** by its children and which are to be readable –writable. This scheme is different from copy-on-write inheritance, in which each task maintains its own copy of any changed pages. A writable object is addressed from each task’s address map, and all changes are made to the same copy. The threads within the tasks are responsible for coordinating changes to memory so that they do not interfere with one another (by writing to the  

**D.7 Programmer Interface 23**

same location concurrently). This coordination can be done through normal synchronization methods: critical sections or mutual-exclusion locks.

For the case of memory shared among separate machines, Mach allows the use of external memory managers. If a set of unrelated tasks wishes to share a section of memory, the tasks can use the same external memory manager and access the same secondary-storage areas through it. The implementor of this system would need to write the tasks and the external pager. This pager could be as simple or as complicated as needed. A simple implementation would allow no readers while a page was being written to. Any write attempt would cause the pager to invalidate the page in all tasks currently accessing it. The pager would then allow the write and would revalidate the readers with the new version of the page. The readers would simply wait on a page fault until the page again became available. Mach provides such a memory manager: the Network Memory Server (NetMemServer). For multicomputers, the NORMA configuration of Mach 3.0 provides similar support as a standard part of the kernel. This XMM subsystem allows multicomputer systems to use external memory managers that do not incorporate logic for dealing with multiple kernels. The XMM subsystem is responsible for maintaining data consistency among multiple kernels that share memory and makes these kernels appear to be a single kernel to the memory manager. The XMM subsystem also imple- ments virtual copy logic for the mapped objects that it manages. This virtual copy logic includes both copy-on-reference amongmulticomputer kernels and sophisticated copy-on-write optimizations.

**D.7 Programmer Interface**

Aprogrammer can work at several levels within Mach. There is, of course, the system-call level, which, in Mach 2.5, is equivalent to the 4.3 BSD system-call interface. Version 2.5 includes most of 4.3 BSD as one thread in the kernel. A BSD system call traps to the kernel and is serviced by this thread on behalf of the caller, much as standard BSD would handle it. The emulation is not multithreaded, so it has limited efficiency.

Mach 3.0 has moved from the single-server model to support of multiple servers. It has therefore become a true microkernel without the full features normally found in a kernel. Rather, full functionality can be provided via emu- lation libraries, servers, or a combination of the two. In keepingwith the defini- tion of amicrokernel, the emulation libraries and servers run outside the kernel at user level. In this way, multiple operating systems can run concurrently on one Mach 3.0 kernel.

An emulation library is a set of routines that lives in a read-only part of a program’s address space. Any operating-system calls the program makes are translated into subroutine calls to the library. Single-user operating systems, such as MS-DOS and the Macintosh operating system, have been implemented solely as emulation libraries. For efficiency reasons, the emulation library lives in the address space of the program needing its functionality; in theory, how- ever, it could be a separate task.

More complex operating systems are emulated through the use of libraries and one ormore servers. System calls that cannot be implemented in the library are redirected to the appropriate server. Servers can be multithreaded for  

**24 Appendix D The Mach System**

improved efficiency; BSD and OSF/1 are implemented as single multithreaded servers. Systems can be decomposed into multiple servers for greater modu- larity.

Functionally, a system call starts in a task and passes through the kernel before being redirected, if appropriate, to the library in the task’s address space or to a server. Although this extra transfer of control decreases the efficiency of Mach, this decrease is balanced to some extent by the ability ofmultiple threads to execute BSD-like code concurrently.

At the next higher programming level is the C threads package. This pack- age is a run-time library that provides a C language interface to the basic Mach threads primitives. It provides convenient access to these primitives, includ- ing routines for the forking and joining of threads, mutual exclusion through mutex variables (Section D.4.2), and synchronization through use of condi- tion variables. Unfortunately, it is not appropriate for the C threads package to be used between systems that share no memory (NORMA systems), since it depends on shared memory to implement its constructs. There is currently no equivalent of C threads for NORMAsystems. Other run-time libraries have been written for Mach, including threads support for other languages.

Although the use of primitives makes Mach flexible, it also makes many programming tasks repetitive. For instance, significant amounts of code are associated with sending and receiving messages in each task that uses mes- sages (which, in Mach, is most tasks). The designers of Mach therefore provide an interface generator (or stub generator) called**_MIG_**. MIG is essentially a com- piler that takes as input a definition of the interface to be used (declarations of variables, types, and procedures) and generates the RPC interface code needed to send and receive the messages fitting this definition and to connect the messages to the sending and receiving threads.

**D.8 Summary**

The Mach operating system is designed to incorporate the many recent inno- vations in operating-system research to produce a fully functional, technically advanced operating system.

TheMach operating systemwas designedwith three critical goals inmind:

• Emulate 4.3 BSD UNIX so that the executable files from a UNIX system can run correctly under Mach.

• Have amodern operating system that supportsmanymemorymodels and parallel and distributed computing.

• Design a kernel that is simpler and easier to modify than is 4.3 BSD.

As we have shown, Mach is well on its way to achieving these goals. Mach 2.5 includes 4.3 BSD in its kernel, which provides the emulation

needed but enlarges the kernel. This 4.3 BSD code has been rewritten to provide the same 4.3 functionality but to use the Mach primitives. This change allows the 4.3 BSD support code to run in user space on a Mach 3.0 system.  

**Further Reading 25**

Mach uses lightweight processes, in the form of multiple threads of exe- cution within one task (or address space), to support multiprocessing and parallel computation. Its extensive use of messages as the only communica- tion method ensures that protection mechanisms are complete and efficient. By integrating messages with the virtual memory system, Mach also ensures that messages can be handled efficiently. Finally, by having the virtual memory systemusemessages to communicate with the daemonsmanaging the backing store,Mach provides great flexibility in the design and implementation of these memory-object-managing tasks.

By providing low-level, or primitive, system calls from which more com- plex functions can be built,Mach reduces the size of the kernelwhile permitting operating-system emulation at the user level, much like IBM’s virtual machine systems.

**Further Reading**

The Accent operating systemwas described by \[Rashid and Robertson (1981)\]. A historical overview of the progression from an even earlier system, RIG, through Accent to Mach was given by \[Rashid (1986)\]. General discussions concerning the Mach model were offered by \[Tevanian et al. (1989)\].

\[Accetta et al. (1986)\] presented an overviewof the original design ofMach. The Mach scheduler was described in detail by \[Tevanian et al. (1987a)\] and \[Black (1990)\]. An early version of the Mach shared memory and memory- mapping system was presented \[Tevanian et al. (1987b)\].

**Bibliography**

**\[Accetta et al. (1986)\]** M. Accetta, R. Baron, W. Bolosky, D. B. Golub, R. Rashid, A. Tevanian, and M. Young, “Mach: ANew Kernel Foundation for UNIX Devel- opment”, _Proceedings of the Summer USENIX Conference_ (1986), pages 93–112.

**\[Black (1990)\]** D. L. Black, “Scheduling Support for Concurrency and Paral- lelism in the Mach Operating System”, _IEEE Computer_, Volume 23, Number 5 (1990), pages 35–43.

**\[Rashid (1986)\]** R. F. Rashid, “From RIG to Accent to Mach: The Evolution of a Network Operating System”, _Proceedings of the ACM/IEEE Computer Society, Fall Joint Computer Conference_ (1986), pages 1128–1137.

**\[Rashid and Robertson (1981)\]** R. Rashid and G. Robertson, “Accent: A Com- munication-Oriented Network Operating System Kernel”, _Proceedings of the ACM Symposium on Operating System Principles_ (1981), pages 64–75.

**\[Tevanian et al. (1987a)\]** A. Tevanian, Jr., R. F. Rashid, D. B. Golub, D. L. Black, E. Cooper, andM.W. Young, “Mach Threads and the Unix Kernel: The Battle for Control”, _Proceedings of the Summer USENIX Conference_ (1987).

**\[Tevanian et al. (1987b)\]** A. Tevanian, Jr., R. F. Rashid,M.W. Young, D. B. Golub, M. R. Thompson, W. Bolosky, and R. Sanzi, “A UNIX Interface for Shared  

**26 Appendix D The Mach System**

Memory and Memory Mapped Files Under Mach”, Technical report, Carnegie- Mellon University (1987).

**\[Tevanian et al. (1989)\]** A. Tevanian, Jr., and B. Smith, “Mach: The Model for Future Unix”, _Byte_ (1989).