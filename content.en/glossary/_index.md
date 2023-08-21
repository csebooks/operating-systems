---
title: 'Glossary'
weight: 18
---

  

**G-1**

**50-percent rule A statistical fi nding that frag-** mentation may result in the loss of 50 percent of space.

**absolute code** Code with bindings to absolute memory addresses.

**absolute path name** A path name starting at the top of the fi le system hierarchy.

**abstract data type (ADT)** A programming con- struct that encapsulates data with a set of functions to operate on that data that are independent of any specifi c implementation of the ADT.

**access matrix** An abstract model of protection in which each row represents a domain, each column an object, and each entry a set of access rights.

**access right** The ability to execute an operation on an object.

**access-control list** A list of user names allowed to access a fi le.

**acknowledgment packet** In networking, a packet sent in response to the successful receipt of a mes- sage or packet.

**activation record** A record created when a func- tion or subroutine is called; added to the stack by the call and removed when the call returns. Con- tains function parameters, local variables, and the return address.

**active directory (AD)** The Windows distributed information system, which is the Windows imple- mentation of LDAP.

**acyclic graph** In directory structure implemen- tation, a structure that contains no cycles (loops).

**adaptive mutex** A Solaris scheduling feature that starts as a standard spinlock and, if the object is locked and the lock is not held by a thread run- ning on a CPU, blocks and sleeps until the lock is released.

**address space layout randomization (ASLR)** An operating system technique to avoid code-injection attacks that place memory objects like the stack and heap at unpredictable locations.

**address windowing extension (AWE)** A Win- dows mechanism for memory allocation that allows developers to directly request free pages of

RAM from the memory manager and later commit virtual memory on top of those pages.

**address-space identifi er A part of a TLB entry** that identifi es the process associated with that entry and, if the requesting process doesn’t match the ID, causes a TLB miss for address- space protection.

**address-space layout randomization (ASRL)** A Windows 7 feature that randomizes process mem- ory addresses to avoid viruses that jump to specifi c code locations to gain privileges.

**admission control** In real-time scheduling, a practice whereby the scheduler may not allow a process to start if it cannot guarantee that the task will be serviced by its deadline.

**advanced confi guration and power interface (ACPI)** Firmware common to PCs and servers that manages certain aspects of hardware, includ- ing power and device information.

**advanced encryption standard (AES)** The NIST cipher designed to replace DES and triple DES.

**advanced local procedure call (ALPC)** In Win- dows OS, a method used for communication between two processes on the same machine.

**advanced technology attachment (ATA)** An older- generation I/O bus.

**advisory fi le-lock mechanism A fi le-locking** system in which the operating system does not enforce locking and fi le access, leaving it to pro- cesses to implement the details.

**AFS (OpenAFS) A network fi le system designed** at Carnegie Mellon University with the goal of enabling servers to support as many clients as possible.

**aging** A solution to scheduling starvation that involves gradually increasing the priority of threads as they wait for CPU time.

**ahead-of-time (AOT) compilation** A feature of the Android RunTime (ART) virtual machine envi- ronment in which Java applications are compiled to native machine code when they are installed on a system (rather than just in time, when they are executed).  

**G-2** **Glossary**

**allocation problem** The determination by the operating system of where to store the blocks of a fi le.

**Amazon Elastic Compute Cloud (ec2)** An instance of cloud computing implemented by Amazon.

**AMD 64** A 64-bit CPU designed by Advanced Micro Devices; part of a class of CPUs collectively known as x86-64.

**AMD-V** AMD CPU virtualization technology.

**analytic evaluation** A means of comparing scheduling-algorithm effectiveness by analyzing an algorithm against a workload and assigning it a score.

**anomaly detection** In intrusion detection, the use of various techniques to detect anomalous behavior that could be a sign of an attack.

**anonymous access** Remote access that allows a user to transfer fi les without having an account on the remote system.

**anonymous memory** Memory not associated with a fi le. Pages not associated with a fi le, if dirty and paged out, must not lose their contents and are stored in swap space as anonymous memory.

**Apple fi le system (APFS) The 2017 fi le system** from Apple that is the default on all modern Apple devices; features a rich feature set, space sharing, clones, snapshots, and copy-on-write design.

**Apple iOS** The mobile operating system created by Apple Inc.

**application component** In Android, a basic build- ing block that provides utility to an Android app.

**application containment** A virtualization-like operating system feature that segregates applica- tions from the operating system (examples include Solaris Zones, BSD Jails, and IBM WPARs).

**application frameworks layer** In the layered macOS and iOS operating system design, the layer that that includes Cocoa and Cocoa Touch frame- works, providing an API for Objective-C and Swift programming languages.

**application programming interface (API)** A set of commands, functions, and other tools that can be used by a programmer in developing a program.

application program A program designed for end-user execution, such as a word processor, spreadsheet, compiler, or Web browser.

**application proxy fi rewall A fi rewall that under-** stands protocols spoken by applications across a network, accepts connections to a target, and cre- ates connections to that target, limiting and fi xing what is sent from the originator.

**application state** A software construct used for data storage.

**arbitrary code guard (ACG)** A Windows 7 exploit-mitigation feature.

**argument vector** In Linux and UNIX, a list con- taining the command-line arguments used to invoke a process (and available to the process).

**ASIC An application-specifi c integrated circuit** (hardware chip) that performs its tasks without an operating system.

**assignment edge** In a system resource-allocation graph, an edge (arrow) indicating a resource assignment.

**asymmetric clustering A confi guration in which** one machine in a cluster is in hot-standby mode while the other is running applications.

**asymmetric encryption algorithm** A cipher algo- rithm in which different keys are used for encryp- tion and decryption.

**asymmetric multiprocessing** A simple multi- processor scheduling algorithm in which only one processor accesses the system data structures and others run user threads, reducing the need for data sharing. A boss processor controls the system; the other processors either look to the boss for instruc- tion or have predefi ned tasks.

**asynchronous** In I/O, a request that executes while the caller continues execution.

**asynchronous procedure call (APC)** A facility that enables a user thread to specify a function that is to be called when the user thread receives notifi - cation of a particular event.

**asynchronous threading** Threading in which a parent creates a child thread and then resumes execution, so that the parent and child execute con- currently and independently of one another.

**asynchronous write** A write that is buffered and written in arbitrary order, with the request- ing thread continuing execution after the write is requested.

**atomic safe-save** In APFS, a feature primitive that performs fi le, bundle of fi les, and directory renaming in single atomic operations.

**atomic variable** A programming language con- struct that provides atomic operations on basic data types such as integers and booleans.

**atomically** A computer activity (such as a CPU instruction) that operates as one uninterruptable unit.

**attack** An attempt to break a computer system’s security.

**attack surface** The sum of the methods available to attack a system (e.g., all of the network ports that are open, plus physical access).  

**Glossary G-3**

**attacker** Someone attempting to breach a com- puter system’s security.

**attribute In the Windows NTFS fi le system, one** of the elements making up a fi le. Each fi le is seen as a structured object consisting of typed attributes, with each attribute an independent byte stream that can be created, deleted, read, and written.

**audit trail** The collection of activities in a log for monitoring or review.

**authentication** The process of correctly identify- ing a person or device. In cryptography, constrain- ing the set of potential senders of a message.

**automatic working-set trimming** In Windows, a process whereby, if a threshold of minimum free memory is reached, the number of working-set frames is decreased for every process.

**automount A network/distributed fi le system** feature in which fi le systems from remote servers are automatically located and mounted as needed.

**autoprobe** In Linux, a device driver probe that auto-detects device confi guration.

**B**+ **tree** A tree data structure in which every path from the root of the tree to the leaf is the same length.

**back door** A daemon left behind after a success- ful attack to allow continued access by the attacker. In cryptography, a method of gaining access to encrypted information without fi rst having the secret keys. More generally, a method of passing arbitrary commands or information when an inter- face does not provide a standard method.

**background** Describes a process or thread that is not currently interactive (has no interactive input directed to it), such as one not currently being used by a user. In the Grand Central Dispatch Apple OS scheduler, the scheduling class representing tasks that are not time sensitive and are not visible to the user.

**backing store** The secondary storage area used for process swapping.

**backup In fi le systems, a copy or copies of the** fi le system or changes to the fi le system that can be used to restore the fi le system if it is damaged or destroyed.

**bad block** An unusable sector on an HDD.

**balanced binary search tree** A tree containing n items that has, at most, lg n levels, thus ensuring worst-case performance of O(lg n).

**bandwidth** The total amount of data transferred divided by the total time between the fi rst request for service and the completion of the last transfer.

**banker’s algorithm** A deadlock avoidance algo- rithm, less effi cient than the resource-allocation graph

scheme but able to deal with multiple instances of each resource type.

**base fi le record In the Windows NTFS fi le sys-** tem, a descriptor of a large fi le containing pointers to overfl ow records that hold additional pointers and attributes.

**base register** A CPU register containing the start- ing address of an address space. Together with the limit register, it defi nes the logical address space.

**basic fi le system A logical layer of the operating** system responsible for issuing generic commands to the I/O control layer, such as “read block x,” and also buffering and caching I/O.

**batch interface** A method for giving commands to a computer in which commands are entered into fi les, and the fi les are executed, without any human interaction.

**Bayes’ theorem** A formula for determining con- ditional probability—e.g., the probability of an intrusion record detecting a real intrusion.

**Belady’s anomaly** An anomaly in frame- allocation algorithms in which a page-fault rate may increase as the number of allocated frames increases.

**best-fi t In memory allocation, selecting the** smallest hole large enough to satisfy the memory request.

**big data** Extremely large sets of data; distributed systems are well suited to working with big data.

**big.LITTLE** ARM processor implementation of HMP in which high-performance big cores are combined with energy effi cient LITTLE cores.

**big-endian** A system architecture in which the most signifi cant byte in a sequence of bytes is stored fi rst.

**binary search tree** A type of binary tree data structure that requires an ordering between the parent’s two children in which left child ⇐ right child.

**binary semaphore** A semaphore of values 0 and 1 that limits access to one resource (acting similarly to a mutex lock).

**binary translation** A virtualization method in which, when a guest is running in virtual kernel mode, every instruction is inspected by the virtual machine manager, and instructions that would behave differently in real kernel mode are trans- lated into a set of new instructions that perform the equivalent task; used to implement virtual- ization on systems lacking hardware support for virtualization.

**binary tree** A tree data structure in which a par- ent may have at most two children.  

**G-4** **Glossary**

**binder** In Android RPC, a framework (system component) for developing object-oriented OS ser- vices and allowing them to communicate.

**bind** Tie together. For example, a compiler binds a symbolic address to a relocatable address so the routine or variable can be found during execution.

**Bionic** A type of standard C library used by Android; it has a smaller memory footprint than glibc and is more effi cient on slower (mobile) CPUs.

**BIOS Code stored in fi rmware and run at boot** time to start system operation.

**bit** The basic unit of computer storage. A bit can contain one of two values, 0 or 1.

**bit vector** A string of n binary digits that can be used to represent the status of n items. The availabil- ity of each item is indicated by the value of a binary digit: 0 means that the resource is available, while 1 indicates that it is unavailable (or vice-versa).

**bit-level striping** The splitting of data at the bit level, with each bit in a byte or word stored on a separate device.

**bitmap** A string of n binary digits that can be used to represent the status of n items. The avail- ability of each item is indicated by the value of a binary digit: 0 means that the resource is available, while 1 indicates that it is unavailable (or vice- versa).

**BKL** In Linux kernel version 2.2, the “big kernel lock” spinlock, which protected all kernel data structures.

**blade server** A computer with multiple processor boards, I/O boards, and networking boards placed in the same chassis. The difference between these and traditional multiprocessor systems is that each blade-processor board boots independently and runs its own operating system.

**block** A self-contained unit of work. The small- est physical storage device storage unit, typically 512B or 4KB. In the Grand Central Dispatch Apple OS scheduler, a language extension that allows designation of a section of code that can be submit- ted to dispatch queues.

**block cipher** A cipher that works on blocks of data (rather than bits).

**block device** An I/O device that is randomly accessible, with block-size chunks being the small- est I/O unit.

**block-device interface** The interface for I/O to block devices.

**blocking** In interprocess communication, a mode of communication in which the sending process is

blocked until the message is received by the receiv- ing process or by a mailbox and the receiver blocks until a message is available. In I/O, a request that does not return until the I/O completes.

**block-level striping** The splitting of data at the block level, with each block stored on a separate device.

**boot block A block of code stored in a specifi c** location on disk with the instructions to boot the kernel stored on that disk. The UFS boot control block.

**boot control block** A storage block of data con- taining information needed by the system to boot from the volume containing the block.

**boot disk** A disk that has a boot partition and a kernel to load to boot the system. A device that has a boot partition and can store an operating system for booting the computer.

**boot partition** A storage device partition con- taining an executable operating system.

**boot sector The fi rst sector of a Windows boot** device, containing the bootstrap code.

**booting** The procedure of starting a computer by loading the kernel.

**bootstrap** The set of steps taken at computer power-on to bring the system to full operation.

**bootstrap loader** The small program that loads the kernel as part of the bootstrap procedure.

**bootstrap port** In Mach message passing, a pre- defi ned port that allows a task to register a port it has created.

**bootstrap program** The program that allows the computer to start running by initializing hardware and loading the kernel.

**bootstrap server** In Mach message passing, a system-wide service for registering ports.

**Border Gateway Protocol** A network protocol for determining network routes so that packets can move from source to destination across a WAN.

**bottleneck** A performance-limiting aspect of computing (e.g., poorly written code or a hard- ware component that is not as fast as others in the system).

**bounded buffer A buffer with a fi xed size.**

**bounded waiting** A practice that places limits on the time a thread or process is forced to wait for something.

**Bourne-Again shell** A common shell, or com- mand interpreter.

**BPF compiler collection (BCC)** A rich toolkit for tracing system activity on Linux for debugging and performance-tuning purposes.  

**Glossary G-5**

**bridging** In networking, the connection of two devices—e.g., a virtual-machine guest and the net- work to which the host computer is connected.

**broadcast** In networking, the sending of one or more packets to all devices on the local network.

**browser** A process that accepts input in the form of a URL (Uniform Resource Locator), or web address, and displays its contents on a screen.

**buddies** Pairs of equal size, used in the buddy method of memory allocation.

**buddy heap** In Linux, the use of a power-of-two allocator for the kernel heap.

**buffer** A memory area that stores data being transferred (e.g., between two devices or between a device and a process).

**buffer cache In fi le I/O, a cache of blocks used to** decrease device I/O.

**bug** An error in computer software or hardware.

**bus** A communication system; e.g., within a computer, a bus connects various components, such as the CPU and I/O devices, allowing them to transfer data and commands.

**busy waiting** A practice that allows a thread or process to use CPU time continuously while waiting for something. An I/O loop in which an I/O thread continuously reads status information while waiting for I/O to complete.

**byte** Eight bits.

**bytecode** A computer object code resulting from compiling a program in a language (such as Java) that runs on a virtual machine.

**C library (libc)** The standard UNIX/Linux sys- tem API for programs written in the C program- ming language.

**cache** A temporary copy of data stored in a reserved memory area to improve performance. In the slab allocator, a cache consists of two or more slabs.

**cache coherency** The coordination of the con- tents of caches such that an update to a value stored in one cache is immediately refl ected in all other caches that hold that value.

**cache management** The management of a cache’s contents.

**cache-consistency problem** A challenge in cach- ing in which the cached copies of data must be kept consistent with the master copy of the data.

**caching** The use of temporary data storage areas to improve performance.

**cancellation point** With deferred thread cancel- lation, a point in the code at which it is safe to ter- minate the thread.

**Canonical** A popular Linux distribution.

**capability** In protection, the representation of an object in a capability list.

**capability list** In protection, a list of objects together with the operations allowed on those objects.

**capability-based protection** A protection facil- ity in which the powers of root are divided into specifi c abilities, each represented by a bit in a bit mask that is used to allow or deny operations.

**cascading termination** A technique in which, when a process is ended, all of its children are ended as well.

**Ceph** A brand of object storage management software.

**certifi cate authority A trusted signer of digital** certifi cates.

**character device** An I/O device that has a char- acter (byte) as its smallest I/O unit.

**character-stream interface** The interface for I/O to character devices (like keyboards).

**checksum** The general term for an error detec- tion and correction code.

**children** In a tree data structure, nodes con- nected below another node.

**chip multithreading (CMT)** A CPU with multi- ple cores, where each core supports multiple hard- ware threads.

**chipset** The CPU and support chips that create a computer and defi ne its architecture.

**circular buffer A buffer that uses a fi xed amount** of storage and wraps writes from the end of the buffer to the beginning when the buffer fi lls (so that the buffer acts as if it’s circular in shape).

**Circular SCAN (CSCAN) scheduling** An HDD I/O scheduling algorithm in which the disk head moves from one end of the disk to the other performing I/O as the head passes the desired cylinders; the head then reverses direction and continues.

**claim edge** In the deadlock resource-allocation- graph algorithm, an edge indicating that a process might claim a resource in the future.

**class loader** In Java, a helper component that loads .class fi les for execution by the Java virtual machine.

**class** In Java, a program component that is a col- lection of data fi elds and functions (methods) that operate on those fi elds.

**clean-up handler** A function that allows any resources a thread has acquired to be released before the thread is terminated.  

**G-6** **Glossary**

**client** A computer that uses services from other computers (such as a web client). The source of a communication.

**client interface** In distributed computing, a set of services provided to a caller of services.

**client system** A computer that uses services from other computers (such as a web client).

**client-server model** A mode of computing in which a server provides services to one or more clients. In distributed computing, a model in which a computer acts as a resource server to other com- puters that are clients of those resources.

**client-side caching (CSC)** In Windows, a cach- ing method used to allow remote users to work off-line and then consolidate their changes once they are online.

**clock** In the second-chance page-replacement algorithm, a circular queue that contains possible victim frames. A frame is replaced only if it has not been recently referenced.

**clone In fi le systems, a snapshot that is read-** write and modifi able. In virtualization, a copy of a guest that enables another instance of the guest to run in a separate virtual machine.

**CLOOK scheduling** An HDD I/O scheduling algorithm that modifi es CSCAN by stopping the head after the fi nal request is completed (rather than at the innermost or outermost cylinder).

**closed-source** An operating system or other program available only in compiled binary code format.

**closure** In functional programming languages, a construct to provide a simple syntax for parallel applications.

**cloud computing** A computing environment in which hardware, software, or other resources are made available to customers across a WAN, such as the Internet, usually with APIs for management. A type of computing that delivers computing, stor- age, and even applications “as a service” across a network.

**cloud storage** Storage accessed from a computer over a network to a distant, shared resource data center.

**cluster** In Windows storage, a power-of-2 num- ber of disk sectors collected for I/O optimization.

**cluster-based model** In distributed computing, a model of resource sharing where all systems are equal users and providers of resources.

**clustered fi le system (CFS) A fi le system that is** LAN-based and treats N systems storing data and Y clients accessing the data as a single client-server

instance; more complex than a client-server DFS but less complex than a cluster-based DFS. GPFS and Lustre are examples.

**clustered page table** A page table similar to a hashed page table, but a table entry refers to sev- eral (a cluster of) pages.

**clustered system** A system that gathers together multiple CPUs. Clustered systems differ from multiprocessor systems in that they are composed of two or more individual systems—or nodes— joined together.

**clustering** In general, gathering N items together. In virtual memory, paging in a group of contiguous pages when a single page is requested via a page fault.

**cluster In fi le system block allocation, several** contiguous blocks.

**coalescing** In general, combining. In the buddy memory allocation algorithm, freed memory in adjacent buddies can be coalesced into larger segments.

**code integrity** A Windows 7 module that checks the digital signatures of kernel modules to be sure they have not been tampered with by attackers.

**code review** A software development method in which the developer submits code to other devel- opers for review and approval.

**code signing** The use of a digital signature to authenticate a program.

**code-injection attack An attack that modifi es** otherwise well-behaved executable code.

**command interpreter** The operating system component that interprets user commands and causes actions based on them.

**command-line interface (CLI)** A method of giv- ing commands to a computer based on a text input device (such as a keyboard).

**Common Criteria** The international 2005 succes- sor to the Orange Book standard developed by the U.S. Department of Defense.

**common Internet fi le system (CIFS) The Win-** dows network fi le system, now used on many systems.

**communication port** In Windows OS, a port used to send messages between two processes.

**communications** A category of system calls.

**compaction The shuffl ing of storage to consoli-** date used space and leave one or more large holes available for more effi cient allocation.

**compartmentalization** The process of protecting each system component through the use of specifi c permissions and access restrictions.  

**Glossary G-7**

**Completely Fair Queuing (CFQ)** In Linux, the default I/O scheduler in kernel 2.6 and later versions.

**Completely Fair Scheduler (CFS)** In Linux, the priority-based, preemptive scheduler included with the 2.6 kernel.

**component object model (COM)** The Windows mechanism for interprocess communication.

**compression** The use of algorithms to reduce the amount of data stored or sent.

**compression ratio** In memory compression, a measurement of the effectiveness of the compres- sion (the ratio of the compressed space to the orig- inal amount of uncompressed space).

**compression unit** In NTFS, a unit of 16 contigu- ous clusters used in memory compression.

**computation migration** The use of a network to allow a task to remotely request resources to speed a computation.

**computation speedup** An increase in the amount of CPU compute power.

**computational kernel** A Windows mechanism for specifying tasks to run on GPUs.

**compute-server system** A server that provides an interface to which a client can send a request for an action (e.g., read data). In response, the server exe- cutes the action and sends the results to the client.

**Concurrency Runtime (ConcRT)** A Microsoft Windows concurrent programming framework for C++ that is designed for task-based parallelism on multicore processors.

**condition variable** A component of a monitor lock; a container of threads waiting for a condition to be true to enter the critical section.

**conditional-wait** A component of the monitor construct that allows for waiting on a variable with a priority number to indicate which process should get the lock next.

**confi nement problem The problem of guaran-** teeing that no information initially held in an object can migrate outside of its execution environment.

**confl ict phase During scheduling, the time the** dispatcher spends moving a thread off a CPU and releasing resources held by lower-priority threads that are needed by the higher-priority thread that is about to be put onto the CPU.

**confl ict-resolution mechanism In Linux, the** kernel module facility that allows different device drivers to reserve hardware resources and to pro- tect those resources from accidental use by other drivers.

**congestion control** In networking, the attempt to approximate the state of networks between send- ers and receivers to avoid packet loss.

**connection port** In Windows OS, a communica- tions port used to maintain connection between two processes, published by a server process.

**connectionless socket (UDP)** In Java, a mode of communication.

**connection-oriented socket (TCP)** In Java, a mode of communication.

**consistency checker** A system program, such as UNIX fsck, that reads fi le system metadata and tries to correct any inconsistencies (such as a fi le’s length being incorrectly recorded).

**consolidation** In virtualization, the practice of running multiple guests per host, reducing the number of physical servers needed for a given workload.

**constant angular velocity (CAV)** A device- recording method in which the medium spins at a constant velocity and the bit density decreases from inner to outer tracks.

**constant linear velocity (CLV)** A device-recording method that keeps a constant density of bits per track by varying the rotational speed of the medium.

**consumer** A process role in which the process consumes information produced by a producer process.

**container** In application containment, a virtual layer between the operating system and a process in which the application runs, limiting its normal access to system resources.

**container object** In Windows 10, a category of objects that contain other objects (e.g., directories, which contain fi les).

**containers** In APFS, large free spaces in storage from which fi le systems can draw allocations.

**containment** A method for preventing deadlocks by creation and lock management of a higher- order resource that contains the locks of lower- order resources.

**contended** A term describing the condition of a lock when a thread blocks while trying to acquire it.

**content addressable storage** Another term for object storage; so called because objects can be retrieved based on their contents.

**context** When describing a process, the state of its execution, including the contents of registers, its program counter, and its memory context, includ- ing its stack and heap.

**context switch** The switching of the CPU from one process or thread to another; requires perform- ing a state save of the current process or thread and a state restore of the other.  

**G-8** **Glossary**

**contiguous allocation A fi le-block allocation** method in which all blocks of the fi le are allocated as a contiguous chunk on secondary storage.

**contiguous bit** In ARM v8 CPUs, a TLB bit indi- cating that the TLB holds a mapping to contiguous blocks of memory.

**contiguous memory allocation** A memory allo- cation method in which each process is contained in a single section of memory that is contiguous to the section containing the next process.

**control partition** In type 0 virtualization, a vir- tual hardware partition that provides services to the other partitions (and has higher privileges).

**control program** A program that manages the execution of user programs to prevent errors and improper use of the computer. It is especially concerned with the operation and control of I/O devices.

**control register** A device I/O register where commands are placed by the computer.

**control-fl ow guard (CFG) A Windows 7 exploit-** mitigation feature.

**controller** A special processor that manages I/O devices.

**convoy effect** A scheduling phenomenon in which a number of threads wait for one thread to get off a core, causing overall device and CPU uti- lization to be suboptimal.

**cooperating process** A process that can affect or be affected by other processes executing in the system.

**cooperative** A form of scheduling in which threads voluntarily move from the running state.

**coordination** Ordering of the access to data by multiple threads or processes.

**copy protection** The implementation of a mech- anism to prevent the unauthorized copying of a licensed work (e.g., media, programs, operating systems).

**copy semantics** The meaning assigned to data copying—e.g., whether a block write from a pro- cess allows the data to be modifi ed after the write has been requested.

**copy-on-write** Generally, the practice by which any write causes the data to fi rst be copied and then modifi ed, rather than overwritten. In virtual mem- ory, on a write attempt to a shared page, the page is fi rst copied, and the write is made to that copy.

**core** Within a CPU, the component that executes instructions.

**core dump** A copy of the state of a process written to disk when a process crashes; used for debugging.

**core frameworks** In the layered macOS and iOS operating system design, the layer that defi nes frameworks that support graphics and media, including QuickTime and OpenGL.

**counting semaphore** A semaphore that has a value between 0 and N, to control access to a resource with N instances.

**CPU burst** Scheduling process state in which the process executes on CPU.

**CPU scheduler** Kernel routine that selects a thread from the threads that are ready to execute and allocates a core to that thread.

**CPU scheduling** The process by which the sys- tem chooses which job will run next If several jobs are ready to run at the same time.

**CPU-bound process** A process that spends more time executing on CPU than it does performing I/O.

**crash** Termination of execution due to a problem. A failure in the kernel results in a system crash and reboot, while a process failure results in a process crash.

**crash dump** A copy of the state of the kernel written to disk during a crash; used for debugging.

**critical section** A section of code responsible for changing data that must only be executed by one thread or process at a time to avoid a race condition.

**critical-section object** A user-mode mutex object that can often be acquired and released without kernel intervention; a Windows OS scheduling feature.

**cryptography** A tool used to constrain the poten- tial senders and/or receivers of a message (or stored data).

**current-fi le-position pointer A per-process** pointer to the location in a fi le to which the next read or from which the next write will occur.

**cycle** A repeating loop.

**cycle stealing** The act of a device, such as a DMA controller, using the bus and preventing the CPU from using it temporarily.

**cylinder** On an HDD, the set of tracks under the read-write heads on all platters in the device.

**cylinder groups** A sequential collection of storage media (typically a group of cylinders) that are man- aged as a single unit and subdivided into blocks.

**daemon** A service that is provided outside of the kernel by system programs that are loaded into memory at boot time and run continuously.

**daisy chain** In computer I/O, a connection method involving connecting devices to each other in a string (device A to B, B to C, C to D, etc.).  

**Glossary G-9**

**dark web** The part of the World Wide Web that is not easy to reach (say, by search engines) and that is sometimes used for bad behavior (such as sell- ing information stolen in successful attacks).

**Darwin** The Apple code name for its open- source kernel.

**data execution prevention (DEP)** A Windows 7 exploit-mitigation feature.

**data migration** The entire transfer of one or more fi les from one site to another.

**data parallelism** A computing method that dis- tributes subsets of the same data across multiple cores and performs the same operation on each core.

**data section** The data part of a program or pro- cess; it contains global variables.

**data striping** The splitting of data across multi- ple devices.

**data-encryption standard (DES)** A cipher (algo- rithm for doing encryption and decryption) pro- vided by the U.S. National Institute of Standards and Technology (NIST).

**datagram** A basic transfer unit on a packet- switched network like the Internet protocol (i.e., a network packet).

**data-in register** A device I/O register where data is placed to be sent to the device.

**data-out register** A device I/O register where data is placed by the device to be read by the computer.

**DCOM** The distributed computing extension to object linking and embedding (OLE).

**deadlock** The state in which two processes or threads are stuck waiting for an event that can only be caused by one of the processes or threads.

**deadlock avoidance** An operating system method in which processes inform the operating system of which resources they will use during their life- times so the system can approve or deny requests to avoid deadlock.

**deadlock prevention** A set of methods intended to ensure that at least one of the necessary condi- tions for deadlock cannot hold.

**deadlocked** The state in which two processes or threads are stuck waiting for an event that can only be caused by one of the processes or threads.

**Debian** A popular Linux distribution.

**debugger** A system program designed to aid programmers in fi nding and correcting errors.

**debugging The activity of fi nding and removing** errors.

**deduplication** The removal of duplicate infor- mation (bits, blocks, or fi les).

**default heap** The heap data structure created when a Win32 process is initialized.

**default signal handler** The signal handler that receives signals unless a user-defi ned signal han- dler is provided by a process.

**defense in depth** The theory that more layers of defense provide stronger defense than fewer layers.

**deferred procedure call (DPC)** In Windows scheduling, a call initiated by the interrupt that occurs when a time quantum expires, eventually causing the expired thread to be moved off a core and replaced with the next thread in the ready queue.

**degree of multiprogramming** The number of processes in memory.

**delayed-write policy** In caching, a policy whereby data are fi rst written to a cache; later, the cache writes the change to the master copy of the data.

**demand paging** In memory management, bring- ing in pages from storage as needed rather than, e.g., in their entirety at process load time.

**demand-zero memory** In Linux, a virtual mem- ory region backed by nothing; when a process tries to read a page in such a region, it is given a page of memory fi lled with zeros.

**demilitarized zone In fi rewalling, a security** domain less trusted than some other security domain (e.g., the domain containing a web server compared to the domain containing the crucial company database).

**denial-of-service** Preventing legitimate use of a system.

**dentry object** The VFS representation of a directory.

**desktop** In a GUI, the standard workspace rep- resented by the GUI on the screen, in which a user executes tasks.

**desktop activity moderator (DAM)** A Windows 8 component that supports the system state “con- nected standby” on mobile devices, freezing com- puter activity but allowing rapid return to full functionality.

**desktop window manager** A Windows Vista user-mode component to manage GUI windows.

**deterministic modeling** A type of analytic eval- uation that takes a particular predetermined work- load and defi nes the performance of each algo- rithm for that workload.

**development kernel** A kernel released for devel- opers to use, rather than for production use.

**device controller** The I/O managing processor within a device.  

**G-10** **Glossary**

**device driver** An operating system component that provides uniform access to various devices and manages I/O to those devices.

**device manipulation** A category of system calls.

**device object** In Windows, the object represent- ing a device.

**device queue** The list of processes waiting for a particular I/O device.

**device-status table** A kernel data structure for tracking the status and queues of operations for devices.

**digital certifi cate A public key digitally signed** by a trusted party.

**digital rights management** The implementa- tion of a mechanism to prevent the unauthorized copying of a licensed work (e.g., media, programs, operating systems).

**digital signature** The authenticator produced by a digital-signature algorithm.

**digital-signature algorithm** A cryptographic checksum calculated in asymmetric encryption; used to authenticate a message.

**dining-philosophers problem** A classic syn- chronization problem in which multiple operators (philosophers) try to access multiple items (chop- sticks) simultaneously.

**direct access A fi le-access method in which** contents are read in random order, or at least not sequentially.

**direct blocks** In UFS, blocks containing pointers to data blocks.

**direct communication** In interprocess commu- nication, a communication mode in which each process that wants to communicate must explicitly name the recipient or sender of the communication.

**direct I/O** Block I/O that bypasses operating- system block features such as buffering and locking.

**direct memory access (DMA)** A resource- conserving and performance-improving operation for device controllers allowing devices to transfer large amounts of data directly to and from main memory.

**direct virtual memory access (DVMA)** DMA that uses virtual addresses rather than physical mem- ory addresses as transfer sources and destinations.

**dirty bit** An MMU bit used to indicate that a frame has been modifi ed (and therefore must have its contents saved before page replacement).

**discretionary access control (DAC)** Optional, as opposed to mandatory, access control.

**disinfecting** In the context of computer viruses, removing the components of a virus.

**disk arm** An HDD component that holds the read- write head and moves over cylinders of platters.

**disk image** Generally, the contents of a disk encapsulated in a fi le. In virtualization, a guest vir- tual machine’s boot fi le system contents contained in a disk image.

**diskless** A term describing systems that have no local storage.

**dispatch latency** The amount of time the dis- patcher takes to stop one thread and put another thread onto the CPU.

**dispatch queue** An Apple OS feature for paral- lelizing code; blocks are placed in the queue by Grand Central Dispatcher (GCD) and removed to be run by an available thread.

**dispatched** Selected by the process scheduler to be executed next.

**dispatcher** The kernel routine that gives control of a core to the thread selected by the scheduler.

**dispatcher objects** A Windows scheduler feature that controls dispatching and synchronization. Threads synchronize according to several different mechanisms, including mutex locks, semaphores, events, and timers.

**distributed denial-of-service attack (DDoS)** An attack from multiple sources (frequently a botnet of zombies) with the purpose of denying legiti- mate use of the attacked resource.

**distributed fi le system (DFS) A fi le system that** works across a network in which remote directo- ries are visible from a local machine.

**distributed information system** A set of pro- tocols providing unifi ed information needed for remote computing.

**distributed lock manager (DLM)** A function used by a clustered system to supply access con- trol and locking to ensure that no confl icting oper- ations occur.

**distributed naming service** A set of protocols providing unifi ed information needed for remote computing.

**distributed system** A collection of loosely cou- pled nodes interconnected by a communication network.

**distribution** A release of a version of an operat- ing system.

**docker** An orchestration tool for containers.

**domain switching** The mechanism for switching dynamic domains.

**domain-name system (DNS)** The Internet sys- tem for resolving host names to host-ids, in which  

**Glossary G-11**

a distributed information system provides host- name-to-network-address translations for the Internet.

**double buffering** The copying of data twice (e.g., from a device to the kernel and then from the kernel to a process’s address space), or the use of two buffers to decouple producers and consumers.

**double caching** The problem in which the same data might be in two different caches; solved by a unifi ed buffer cache.

**double indirect block** In UFS, a block containing pointers to a single indirect block, which points to data blocks.

**down time** Generally, time during which a facil- ity, system, or computing component are off-line and unavailable.

**driver end** The interface between STREAMS and the device being controlled.

**driver object** In Windows, the object represent- ing a device driver.

**driver-registration system** In Linux, the kernel module facility that tells the rest of the kernel that a new driver is available.

**DTrace** A facility originally developed at Sun Microsystems that dynamically adds probes to a running system, both in user processes and in the kernel, for state analysis, performance tuning, and debugging.

**dual-booted** A term describing a computer that can boot one of two or more installed operating systems.

**dynamic loading** The loading of a process rou- tine when it is called rather than when the process is started.

**dynamic random-access memory (DRAM)** The common version of RAM, which features high read and write speeds.

**dynamic storage-allocation The class of fi le-** block allocation methods that satisfy a request for n blocks from a list of free holes available.

**dynamic storage-allocation problem** The prob- lem of how to satisfy a request for size n of mem- ory from a list of free holes.

**dynamically linked libraries (DLLs)** System libraries that are linked to user programs when the processes are run, with linking postponed until execution time.

**earliest-deadline-fi rst (EDF) A real-time sched-** uling algorithm in which the scheduler dynam- ically assigns priorities according to completion deadlines.

**ease of use The amount of diffi culty and complex-** ity involved in using some aspect of computing.

**EEPROM** Electrically erasable programmable read-only memory; a type of fi rmware.

**effective access time** The measured or statisti- cally calculated time it takes to access something; e.g., see effective memory-access time.

**effective memory-access time** The statistical or real measure of how long it takes the CPU to read or write to memory.

**effective transfer rate** The actual, measured transfer rate of data between two devices (such as a computer and a disk drive).

**effective UID** The UID the process is currently using, which can be different from the login UID due to, e.g., escalating privileges.

**electrical storage** Storage devices made from electrical components, such as fl ash memory; one form of nonvolatile storage.

**ELF** The UNIX standard format for relocatable and executable fi les.

**embedded computer** A computer system within some other, larger system (such as a car) that per- forms specifi c, limited functions and has little or no user interface.

**emulation** A methodology used to enable a pro- cess to run when the compiled program’s original (source) CPU type is different from the target CPU type on which the program is to run.

**emulator** A program that allows applications written for one hardware environment to run in a different hardware environment, such as a differ- ent type of CPU.

**encapsulate** In general, to enclose. In Java, encapsulation gives a class the ability to protect its data and methods from other classes loaded in the same JVM.

**encryption** The use of cryptography to limit the receivers of a message or access to data.

**entry section** The section of code within a pro- cess that requests permission to enter its critical section.

**entry set** In Java, the set of threads waiting to enter a monitor.

**environment vector** In Linux and UNIX, a list containing all of the environment variables of the shell that invoked a process (and are available to the process).

**environmental subsystem** In Windows, an oper- ating environment that emulates a specifi c operat- ing system by translating process API calls from that operating system to Windows calls.  

**G-12** **Glossary**

**equal allocation** An allocation algorithm that assigns equal amounts of a resource to all requestors. In virtual memory, assigning an equal number of frames to each process.

**error-correcting code (ECC)** A value calculated from bytes of data and recalculated later to check for changes in the data.

**eSATA** A type of I/O bus.

**escalate privileges** To gain extra permissions for an activity, as when a user needs access to a device that is restricted.

**escape** Generally, a method of passing arbitrary commands or information when an interface does not provide a standard method.

**event latency** The amount of time between when an event occurs and when it is serviced.

**event** A Windows OS scheduling feature that is similar to a condition variable.

**eVM** An example of a partitioning hypervisor.

**exception** A software-generated interrupt caused either by an error (such as division by zero or invalid memory access) or by a specifi c request from a user program than an operating-system ser- vice be performed.

**exception dispatcher** The Windows component that processes exceptions.

**exclusive lock A fi le lock similar to a writer lock** in that only one process at a time can obtain the lock.

**executable and linkable format (ELF)** The UNIX standard format for relocatable and executable fi les.

**executable fi le A fi le containing a program that** is ready to be loaded into memory and executed.

**execution tracing** A Windows method of moni- toring process execution and recording details for analysis and debugging.

**exit section** The section of code within a process that cleanly exits the critical section.

**expansion bus** A computer bus for connecting slow devices like keyboards.

**exponential average** A calculation used in sched- uling to estimate the next CPU burst time based on the previous burst times (with exponential decay on older values).

**export list The list of fi le systems available for** remote mounting from a server.

**ext3 One of the most common types of Linux fi le** systems.

**extended fi le attributes Extended metadata** about a fi le, including items such as character encoding details, fi le checksums, etc.

**extended fi le system The most common class of** Linux fi le systems, with ext3 and ext4 being the most commonly used fi le system types.

**extended fi le system (extfs) The most common** class of Linux fi le systems, with ext3 and ext4 being the most commonly used fi le system types.

**extensibility** The ability of an operating system to accommodate advances in computing technol- ogy via extensions (such as new kernel modules and new device drivers).

**extent** A chunk of contiguous storage space added to previously allocated space; a pointer is used to link the spaces.

**external data representation** A system used to resolve differences when data are exchanged between big- and little-endian systems.

**external fragmentation** Fragmentation in which available memory contains holes that together have enough free space to satisfy a request but no single hole is large enough to satisfy the request. More generally, the fragmentation of an address space into small, less usable chunks.

**fair scheduling** In the Completely Fair Sched- uler, the scheduler algorithm that allots a pro- portion of the processor’s time rather than time slices.

**false negatives** Results indicating that some- thing is not a match to what is being detected, even though it is.

**false positives** Results indicating that something is a match to what is being detected, even though it isn’t.

**fast directory sizing** In APFS, a feature that tracks and rapidly reports on directory sizes.

**fast I/O mechanism** In Windows, a high-speed bypass of the standard I/O handling mechanism in which the driver stack is called directly rather than having an IRP sent and processed.

**fault-tolerant system** A system that can suffer a failure of any single component and still continue operation.

**fi ber User-mode code that can be scheduled** according to a user-defi ned scheduling algorithm.

**fi bre channel (FC) A type of storage I/O bus** used in data centers to connect computers to stor- age arrays. A storage-attachment network.

**fi le The smallest logical storage unit; a collection** of related information defi ned by its creator.

**fi le attributes Metadata about a fi le, such as who** created it and when, fi le size, etc.

**fi le descriptor (fd) UNIX open-fi le pointer, cre-** ated and returned to a process when it opens a fi le.  

**Glossary G-13**

**fi le handle Windows name for the open-fi le fi le** descriptor.

**fi le info window A GUI view of the fi le metadata.**

**fi le manipulation A category of system calls.**

**fi le mapping In Windows, the fi rst step in** memory-mapping a fi le.

**fi le migration A fi le system feature in which a fi le’s** location is changed automatically by the system.

**fi le object The VFS representation of an open fi le.**

**fi le reference In Windows NTFS, a unique fi le ID** that is the index of the fi le in the master fi le table (much like a UNIX inode number).

**fi le session The series of accesses between open()** and close() system calls that make up all the oper- ations on a fi le by a process.

**fi le system The system used to control data stor-** age and retrieval; provides effi cient and conve- nient access to storage devices by allowing data to be stored, located, and retrieved easily.

**File System Hierarchy Standard** A standard document specifying the overall layout of the stan- dard Linux fi le systems.

**fi le-allocation table (FAT) A simple but effective** method of disk-space allocation used by MS-DOS. A section of storage at the beginning of each vol- ume is set aside to contain the table, which has one entry per block, is indexed by block number, and contains the number of the next block in the fi le.

**fi le-control block (FCB) A per-fi le block that con-** tains all the metadata about a fi le, such as its access permissions, access dates, and block locations.

**fi le-organization module A logical layer of the** operating system responsible for fi les and for translation of logical blocks to physical blocks.

**fi le-server system A server that provides a** fi le-system interface where clients can create, update, read, and delete fi les (e.g., a web server that delivers fi les to clients running web browsers).

**fi lter drivers In Windows, drivers allowed to** insert themselves into the I/O processing chain.

**fi rewall A computer, appliance, process, or** network router that sits between trusted and untrusted systems or devices. It protects a network from security breaches by managing and blocking certain types of communications.

**fi rewall chains In Linux, an ordered list of** rules that specifi es one of a number of possible fi rewall-decision functions plus matching compo- nents. A confi guration of the fi rewall rules.

**fi rmware Software stored in ROM or EEPROM** for booting the system and managing low level hardware.

**fi rst-come fi rst-served (FCFS) The simplest** scheduling algorithm. The thread that requests a core fi rst is allocated the core fi rst.

**fi rst-fi t In memory allocation, selecting the fi rst** hole large enough to satisfy a memory request.

**fi rst-level interrupt handler In some operat-** ing systems, an interrupt handler responsible for reception and queuing of interrupts; the inter- rupts are actually handled at another level (by the second-level handler).

**fl ash translation layer (FTL) For nonvolatile** memory, a table that tracks currently valid blocks.

**fl ow control Generally, a method to pause a** sender of I/O. In networking, a technique to limit the rate of data fl ow (e.g., to avoid buffer overfl ow and packet loss on a router).

**fl ush Erasure of entries in, e.g., a TLB or other** cache to remove invalid data.

**folder A fi le system component that allows users** to group fi les together.

**folder redirection** In Windows, for roaming users, a method for automatically storing a user’s documents and other fi les on a remote server.

**foreground** Describes a process or thread that is interactive (has input directed to it), such as a window currently selected as active or a terminal window currently selected to receive input.

**foreground process** A process currently open and appearing on the display, with keyboard or other I/O device input directed to it.

**fork-join** A strategy for thread creation in which the main parent thread creates (forks) one or more child threads and then waits for the children to ter- minate and join with it.

**forward-mapped** Describes a scheme for hier- archical page tables in which address translation starts at the outer page table and moves inward.

**fourth extended fi le system (ext4) In Linux, a** current version of the extended fi le system, the successor to ext3.

**fragments** In networking, parts of messages. A message is split into fragments if it is too large to fi t in one packet.

**frame table** In paged memory, the table con- taining frame details, including which frames are allocated, which are free, total frames in the system, etc.

**frame-allocation algorithm** The operating- system algorithm for allocating frames among all demands for frames.

**frames** Fixed-sized blocks of physical memory.  

**G-14** **Glossary**

**free operating system** An operating system released under a license that makes its source code available and allows no-cost use, redistribution, and modifi cation.

**free-behind** Sequential I/O performance opti- mization that removes a page or block from a buf- fer as soon as I/O to the next page is requested.

**free-frame list** A kernel-maintained data struc- ture containing the list of currently available free frames of physical memory.

**free-space list In fi le-system block allocation, the** data structure tracking all free blocks in the fi le system.

**front-end processors** Small computers that per- form certain tasks in an overall system; used by some systems to manage I/O and offl oad the general-purpose CPU.

**fsgid** In Linux, an added process property that allows fi le system access on behalf of another group.

**fsuid** In Linux, an added process property that allows fi le system access on behalf of another user.

**full backup In fi le systems, a backup that** includes all of the contents of a fi le system.

**functional language** A programming language that does not require states to be managed by pro- grams written in that language (e.g., Erlang and Scala).

**fuzzing** A technique that tests for proper input val- idation (e.g., to avoid undetected buffer overruns).

**Galois fi eld math An advanced error-correcting** calculation done in some forms of RAID.

**Gantt chart** A bar chart that can be used to illus- trate a schedule.

**garbage collection** In general, recovery of space containing no-longer-valid data.

**general tree** A tree data structure in which a par- ent may have unlimited children.

**gestures** A user interface component in which motions cause computer actions (e.g., “pinching” the screen).

**gigabyte (GB)** 1,024^3 bytes.

**git** A version control system used for GNU/ Linux and other programs.

**global replacement** In virtual memory frame allocation, allowing a process to select a replace- ment frame from the set of all frames in the system, not just those allocated to the process.

**GNU C compiler (gcc)** The standard C compiler of the GNU project, used throughout the industry on Linux and many other system.

**GNU General Public License (GPL)** A license agreement that codifi es copylefting (allowing and requiring open sourcing of the associated pro- grams); a common license under which free soft- ware is released.

**GNU/Linux (aka Linux)** An open-source operat- ing system composed of components contributed by the GNU foundation and Linus Torvalds, as well as many others.

**Google Android** The mobile operating system created by Google Inc.

**Google fi le system (GFS) A cluster-based dis-** tributed fi le system designed and used by Google.

**GPFS A common commercial clustered fi le sys-** tem by IBM.

**graceful degradation** The ability of a system to continue providing service proportional to the level of surviving hardware.

**graphical user interface (GUI)** A computer interface comprising a window system with a pointing device to direct I/O, choose from menus, and make selections and, usually, a keyboard to enter text.

**graphics processing unit (GPU)** A hardware component, sometimes part of the CPU and some- times a separate device, that provides graphics computation and sometimes graphics output to a display.

**graphics shaders** Processes that provide the shading within graphics images.

**group In fi le permissions, a collection of users** that have access to a fi le based on assigned access rights.

**group identifi er Similar to a user identifi er, but** used to identify a group of users to determine access rights.

**group rights In fi le permissions, the access rights** belonging to a user group.

**GRUB** A common open-source bootstrap loader that allows selection of boot partitions and options to be passed to the selected kernel.

**guard pages** In Windows, no-access-allowed pages at the tops of the kernel-mode and user- mode stacks that detect stack overfl ows.

**guest** In virtualization, an operating system run- ning in a virtual environment (rather than natively on the computer hardware).

**hacker** Someone attempting to breach computer security.

**Hadoop distributed fi le system (HDFS) A cluster-** based distributed fi le system used for big-data projects.  

**Glossary G-15**

**Hadoop fi le system An example of object stor-** age management software.

**haiku A three-line poem in which the fi rst line** contains fi ve syllables, the second line contains seven syllables, and the third line contains fi ve syllables.

**handle** Generally, an opaque value that provides access to an object or data structure; e.g., a fi le handle is returned when a fi le is opened and is a pointer to an entry in an open-fi le table.

**handle table** In Windows, a per-process handle table containing entries that track (by their han- dles) the objects used by the process.

**hard affi nity The situation in which an operat-** ing system allows a process’s threads to run on the same processor at all times (as opposed to being moved to various processors).

**hard disk drive (HDD)** A secondary storage device based on mechanical components, includ- ing spinning magnetic media platters and moving read-write heads.

**hard error** An unrecoverable error (possibly resulting in data loss).

**hard links File-system links in which a fi le has** two or more names pointing to the same inode.

**hard real-time systems** Systems in which a thread must be serviced by its deadline; service after the deadline has expired is the same as no service at all.

**hard working-set limit** In Windows memory management, the maximum amount of physical memory that a process is allowed to use.

**hardware** The CPU, memory devices, input/ output (I/O) devices, and any other physical com- ponents that are part of a computer.

**hardware objects** The CPU, memory devices, input/output (I/O) devices, and any other phys- ical components that are part of a computer

**hardware threads** Threads associated with the processing core. A given CPU core may run mul- tiple hardware threads to optimize core use—e.g., to avoid memory stalls by switching hardware threads if the current thread causes a stall.

**hardware transactional memory (HTM)** A trans- actional memory implementation using hardware cache hierarchies and cache coherency protocols to manage and resolve confl icts involving shared data residing in separate processors’ caches.

**hardware-abstraction layer (HAL)** A kernel layer that isolates chipset-specifi c hardware aspects from general-purpose code.

**hash function** A function that takes data as its input, performs a numeric operation on the data,

and returns a numeric value. Also, an algorithm for creating a hash (a small, fi xed-size block of data calculated from a larger data set, used to determine if a message has been changed).

**hash map** A data structure that maps \[key:value\] pairs using a hash function; a hash function can then be applied to a key to obtain its matching value.

**hash value** The calculation resulting from a hash function.

**hashed page table** A page table that is hashed for faster access; the hash value is the virtual page number.

**head crash** On an HDD, a mechanical problem involving the read-write head touching a platter.

**heap section** The section of process memory that is dynamically allocated during process run time; it stores temporary variables.

**heartbeat** In computer clustering, a repeating signal to determine the state of the members of the cluster (e.g., to determine if a system is down).

**heterogeneous multiprocessing (HMP)** A fea- ture of some mobile computing CPUs in which cores vary in their clock speeds and power management.

**high-availability** Describes a service that will continue even if one or more systems in the cluster fail.

**high-performance computing** A computing facility designed for use with a large number of resources to be used by software designed for par- allel operation.

**high-performance event timer** A hardware timer provided by some CPUs.

**hit ratio** The percentage of times a cache pro- vides a valid lookup (used, e.g., as a measure of a TLB’s effectiveness).

**hives** In Windows, an internal repository of data.

**hole** In variable partition memory allocation, a contiguous section of unused memory. Also an alternative rock band formed by Courtney Love.

**honeypot** A false resource exposed to attackers; the resource appears real and enables the system to monitor and gain information about the attack.

**horizontal scalability** The ability to scale capac- ity not by expanding one item but by adding more items.

**host** In virtualization, the location of the virtual machine manager, which runs guest operating sys- tems; generally, a computer.

**host bus adapter (HBA)** A device controller installed in a host bus port to allow connection of one or more devices to the host.  

**G-16** **Glossary**

**host controller** The I/O-managing processors within a computer (e.g., inside a host bus adapter).

**host name** A human-readable name for a computer.

**host-attached storage** Storage accessed through local I/O ports (directly attached to a computer, rather than across a network or SAN).

**host-id** In networking, the unique number iden- tifying a system on a network.

**hostname** The alphanumeric name for a system (such as becca.colby.edu).

**hot spare** An unused storage device ready to be used to recover data (e.g., in a RAID set).

**hot-standby mode** A condition in which a com- puter in a cluster does nothing but monitor the active server. If that server fails, the hot-standby host becomes the active server.

**huge pages** A feature that designates a region of physical memory where especially large pages can be used.

**hybrid cloud** A type of cloud computing that includes both public and private cloud components.

**hypercall** In paravirtualization, a call from a guest to the hypervisor to request a virtualization service, such as a page table change.

**hyper-threading** Intel’s technology for assigning multiple hardware threads to a single processing core.

**hypervisor** The computer function that manages the virtual machine; also called a virtual machine manager (VMM).

**I/O burst** Scheduling process state in which the CPU performs I/O.

**I/O bus** A physical connection of an I/O device to a computer system.

**I/O channel** A dedicated, special-purpose CPU found in large systems like mainframes for per- forming I/O or offl oading the general-purpose CPU.

**I/O control** A logical layer of the operating sys- tem responsible for controlling I/O, consisting of device drivers and interrupt handlers.

**I/O manager** In Windows, the system compo- nent responsible for I/O.

**I/O port** A hardware connector allowing connec- tion of an I/O device.

**I/O request packet (IRP)** In Windows, a data structure to request fi le I/O that is sent from the I/O manager to the appropriate device driver.

**I/O subsystem** The I/O devices and the part of the kernel that manages I/O.

**I/O-bound process** A process that spends more of its time doing I/O than doing computations

**icons Images representing objects (such as fi les** or applications) that users can chose via the GUI.

**idempotent** Describes a function that, when applied more than once, has the same result every time.

**identifi er Generally, a numeric tag for a device** or object. In networking, the unique host-id num- ber identifying a system on a network.

**idle process** In Windows, a process that serves as the container of all idle threads.

**idle thread** In some operating systems, a special thread that runs on the CPU when no other thread is ready to run.

**immutable shared fi le In a remote fi le system,** a fi le that, once shared by its creator, cannot be modifi ed.

**imperative language** Language for implement- ing algorithms that are state-based (e.g., C, C++, Java, and C#).

**impersonation** In Windows, the representation of a thread by a token for security purposes.

**implicit threading** A programming model that transfers the creation and management of thread- ing from application developers to compilers and run-time libraries.

**incremental backup In fi le systems, a backup** that contains only some parts of a fi le system (the parts that have changed since the last full and incremental backups).

**indefi nite blocking A situation in which one** or more processes or threads waits indefi nitely within a semaphore.

**index In fi le systems, an access method built** on top of direct access in which a fi le contains an index with pointers to the contents of the fi le.

**index block** In indexed allocation, a block that contains pointers to the blocks containing the fi le’s data.

**index root** In NTFS, the part of the directory con- taining the top level of the B+ tree.

**indexed allocation In fi le-system block alloca-** tion, combining all block pointers in one or more index blocks to address limits in linked allocation and allow direct access to each block.

**indirect block** In UFS, a block containing point- ers to direct blocks, which point to data blocks.

**Infi niBand (IB) A high-speed network commu-** nications link.

**infi nite blocking A scheduling risk in which a** thread that is ready to run is never put onto the  

**Glossary G-17**

CPU due to the scheduling algorithm; it is starved for CPU time.

**information maintenance** A category of system calls.

**infrastructure as a service (IaaS)** A type of com- puting in which servers or storage are available over the Internet (e.g, storage available for making backup copies of production data).

**inode In many fi le systems, a per-fi le data struc-** ture holding most of the metadata of the fi le. The FCB in most UNIX fi le systems.

**inode object** The VFS representation of an indi- vidual fi le.

**input/output operations per second** A measure of random access I/O performance; the number of inputs + outputs per second.

**integrity label** In Windows Vista and later ver- sions, a mandatory access control component assigned to each securable object and subject.

**integrity levels** A mechanism, introduced in Windows Vista, that acts as a rudimentary capabil- ity system for controlling access.

**Intel 64** Intel 64 bit CPUs, part of a class of CPUs collectively known as x86-64

**interactive** Describes a type of computing that provides direct communication between the user and the system.

**intermachine interface** In distributed comput- ing, a set of low-level functions for cross-machine interaction.

**internal fragmentation** Fragmentation that is internal to a partition.

**Internet** A worldwide system of interconnected computer networks.

**Internet key exchange (IKE)** A protocol that uses public key encryption to allow secure sym- metric key exchange for IPSec.

**Internet protocol (IP)** The low-level network- ing protocol on which TCP and UDP are layered; responsible for routing IP datagrams through net- works such as the Internet.

**Internet protocol security (IPSec)** A network pro- tocol suite providing authentication and symmetric- key encryption of packets of network data.

**Internet Service Providers (ISPs)** Companies that provide Internet access.

**interpretation** A methodology that allows a pro- gram in computer language to be either executed in its high-level form or translated to an interme- diate form rather than being compiled to native code.

**interprocess communication (IPC)** Communica- tion between processes.

**interrupt** A hardware mechanism that enables a device to notify the CPU that it needs attention.

**interrupt address** A variable provided along with an interrupt signal to indicate the source of the interrupt.

**interrupt chaining** A mechanism by which each element in an interrupt vector points to the head of a list of interrupt handlers, which are called indi- vidually until one is found to service the interrupt request.

**Interrupt latency** The period of time from the arrival of an interrupt at the CPU to the start of the routine that services the interrupt.

**interrupt object** The Windows representation of an interrupt.

**interrupt priority level** Prioritization of inter- rupts to indicate handling order.

**interrupt request level (IRQL)** A prioritization method used in interrupt management.

**interrupt service routine (ISR)** An operating system routine that is called when an interrupt sig- nal is received.

**interrupt vector** An operating-system data struc- ture indexed by interrupt address and pointing to the interrupt handlers. A kernel memory data structure that holds the addresses of the interrupt service routines for the various devices.

**interrupt-controller hardware** Computer hard- ware components for interrupt management.

**interrupt-dispatch table** The Windows term for its interrupt vector.

**interrupt-handler routine** An operating system routine that is called when an interrupt signal is received.

**interrupt-request line** The hardware connection to the CPU on which interrupts are signaled.

**intruder** Someone attempting to breach security.

**intrusion prevention** The attempt to detect attempted and successful intrusions and properly respond to them.

**intrusion-prevention systems (IPS)** Systems to detect and prevent intrusions, usually in the form of self-modifying fi rewalls.

**inverted page table** A page-table scheme that has one entry for each real physical page frame in memory; the entry maps to a logical page (virtual address) value.

**iSCSI** The protocol used to communicate with SCSI devices; used across a network for more dis- tant access.  

**G-18** **Glossary**

**Itanium** Intel IA-64 CPU.

**iteration space** In Intel threading building blocks, the range of elements that will be iterated.

**Java virtual machine** In programming- environment virtualization, the process that implements the Java language and allows execu- tion of Java code.

**job objects** In Windows, data structures for tracking collections of processes (e.g., to set CPU usage limits).

**job pool** The location where jobs are kept on disk while waiting for main memory to become available.

**job scheduling** The task of choosing which jobs to load into memory and execute.

**job** A set of commands or processes executed by a batch system.

**journaling In a fi le system that features a write** transaction log, logging of write activities for replay across actual fi le-system structures and con- sistency protection.

**journaling fi le system A fi le system that features** a write transaction log where all write activities are logged for replay across actual fi le-system struc- tures and consistency protection.

**just-in-time (JIT)** In Java virtual machine implementations, describes a compiler that con- verts bytecode to native CPU instructions the fi rst time the bytecode is interpreted to speed later execution.

**Kerberos** A network authentication protocol invented at M.I.T. that forms the basis for the Mic- rosoft network authentication protocol.

**kernel** The operating system component run- ning on the computer at all times after system boot.

**kernel abstractions** Components provided with the Mach microkernel to add functionality beyond the microkernel, such as tasks, threads, memory objects, and ports.

**kernel environment** In the layered macOS and iOS operating system design, the Darwin layer that includes the Mach microkernel and the BSD UNIX kernel.

**kernel extensions (kexts)** Third-party com- ponents added to the kernel (usually to support third-party devices or services).

**kernel mode** A CPU mode in which all instruc- tions are enabled. The kernel runs in this mode. See also user mode.

**kernel threads** Threads running in kernel mode.

**kernel-mode driver framework (KMDF)** A framework in Windows to facilitate the writing of kernel-mode device drivers.

**kernel-mode thread (KT)** In Windows, the name for the state of a thread when it is running in kernel mode.

**Kernighan’s Law** “Debugging is twice as hard as writing the code in the fi rst place. Therefore, if you write the code as cleverly as possible, you are, by defi nition, not smart enough to debug it.”

**keys** In the context of protection, unique bit pat- terns held by domains corresponding with unique bit patterns (locks) held by objects. Generally, secrets used in cryptography.

**keystream An infi nite set of bits used to encrypt** a plain-text stream through an XOR operation in a stream cipher.

**keystroke logger** A program that captures key- strokes entered by users.

**kilobyte (KB)** 1,024 bytes.

**Kubernetes** An orchestration tool for containers.

**labels In mandatory access control, identifi ers** assigned to objects and/or subjects. The label is checked by the operating system when an opera- tion is requested to determine if it is allowed.

**layered approach** A kernel architecture in which the operating system is separated into a number of layers (levels); typically, the bottom layer (layer 0) is the hardware, and the highest (layer N) is the user interface.

**lazy swapper** A swapping method in which only pages that are requested are brought from second- ary storage into main memory.

**least frequently used (LFU)** In general, an algo- rithm that selects the item that has been used least frequently. In virtual memory, when access counts are available, selecting the page with the lowest count.

**least privilege** Design principle stating that every program and every privileged user of the system should operate using the least amount of privilege necessary to complete the job.

**least recently used (LRU)** In general, an algo- rithm that selects the item that has been used least recently. In memory management, selecting the page that has not been accessed in the longest time.

**lgroups** In Solaris, locality groups located in the kernel; each lgroup gathers together CPUs and memory, and each CPU in that group can access any memory in the group within a defi ned latency interval. A method for dealing with NUMA.

**library operating systems** The applications that run on unikernels, containing both the kernel and the application code.  

**Glossary G-19**

**lightweight directory-access protocol (LDAP)** A secure distributed naming service used through- out the computer industry.

**lightweight process (LWP)** A virtual processor- like data structure allowing a user thread to map to a kernel thread.

**limit register A CPU register that defi nes the** size of the range. Together with the base register, it defi nes the logical address space.

**line discipline** In Linux, an interpreter for the information from a terminal device.

**link In fi le naming, a fi le that has no contents but** rather points to another fi le.

**linked allocation A type of fi le-system block** allocation in which each fi le is a linked list of allo- cated blocks containing the fi le’s contents. Blocks may be scattered all over the storage device.

**linked list** A data structure in which items are linked to one another.

**linker** A system service that combines relocat- able object fi les into a single binary executable fi le.

**Linux distribution** A Linux system plus admin- istrative tools to simplify the installation, upgrad- ing, and management of the system.

**Linux instance** A set of Pico processes running in Windows created by WSL containing an init pro- cess and a bash shell (allowing executing of Linux commands within Windows)

**Linux kernel** The operating-system kernel of a Linux system.

**Linux system The kernel, programs, and fi les** that comprise a complete, runnable Linux system.

**list** A data structure that presents a collection of data values as a sequence.

**little-endian** A system architecture that stores the least signifi cant byte fi rst in a sequence of bytes.

**Little’s formula** A scheduling equation (n = ? × W) that is particularly useful because it is valid for any scheduling algorithm and arrival distribution.

**live migration** In virtualization, the movement of a running guest between two separate physical hosts.

**LiveCD** An operating system that can be booted and run from a CD-ROM (or more generally from any media) without being installed on a system’s boot disk(s).

**LiveDVD** An operating system that can be booted and run from a DVD (or more generally from any media) without being installed on a sys- tem’s boot disk(s).

**livelock** A condition in which a thread continu- ously attempts an action that fails.

**liveness** A set of properties that a system must satisfy to ensure that processes make progress during their execution life cycle.

**living document A document that is modifi ed** over time to keep it up to date.

**load balancing** The movement of jobs or net- work packets between various components (say, computers in a network) to distribute the load or route around failures. Load balancing attempts to keep the workload evenly distributed across all processors in an SMP system.

**load sharing** The ability of a system with multi- ple CPU cores to schedule threads on those cores.

**loadable kernel module (LKM)** A kernel structure in which the kernel has a set of core components and can link in additional services via modules, either at boot time or during run time.

**loader** A system service that loads a binary exe- cutable fi le into memory, where it is eligible to run on a CPU core.

**local procedure call** In Windows, a method used for communication between two processes on the same machine.

**local replacement** In virtual-memory frame allo- cation, allowing a process to select a replacement frame only from the set of all frames allocated to the process.

**local replacement algorithm** A virtual-memory page replacement algorithm that avoids thrash- ing by not allowing a process to steal frames from other processes.

**local-area network (LAN)** A network that con- nects computers within a room, a building, or a campus.

**locality** The tendency of processes to reference memory in patterns rather than randomly.

**locality model** A model for page replacement based on the working-set strategy.

**locality of reference** The tendency of processes to reference memory in patterns rather than randomly.

**location independence** In distributed comput- ing, a feature in which the name of an object does not need to be changed when the object’s physical location changes.

**location transparency** In distributed computing, a feature in which the name of an object does not reveal its physical location.

**lock** A mechanism that restricts access by pro- cesses or subroutines to ensure integrity of shared data.  

**G-20** **Glossary**

**locked In general, fi xed in place. In memory** management, pages can be locked into memory to prevent them from being paged out.

**lock-free** An algorithm that provides protection from race conditions without requiring the over- head of locking.

**locking** Protecting critical sections, data struc- tures, or objects though the use of code that coor- dinates access.

**lock-key scheme** In protection, a compromise between access lists and capability lists in which each object has a unique bit pattern (a lock) and each domain has a unique bit pattern (a key).

**log fi le A fi le containing error or “logging” infor-** mation; used for debugging or understanding the state or activities of the system.

**log-based transaction-oriented fi le system A fi le** system that features a write transaction log where all write activities are logged for replay across actual fi le-system structures and consistency protection.

**logic bomb** A remote-access tool designed to operate only when a specifi c set of logical condi- tions is met.

**logical address** Address generated by the CPU; must be translated to a physical address before it is used.

**logical address space** The set of all logical addresses generated by a program.

**logical blocks** Logical addresses used to access blocks on storage devices.

**logical cluster numbers** In Windows, the name given to secondary storage physical addresses.

**logical fi le system A logical layer of the oper-** ating system responsible for fi le and fi le-system metadata management; maintains the FCBs.

**logical formatting The creation of a fi le system** in a volume to ready it for use.

**logical memory** Memory as viewed by the user; usually a large uniform array, not matching physi- cal memory in virtual memory systems.

**logical records** File contents logically designated as fi xed-length structured data.

**LOOK** An HDD I/O scheduling algorithm mod- ifi cation of SCAN that stops the head after the last request is complete (rather than at the innermost or outermost cylinder).

**loopback** Communication in which a connection is established back to the sender.

**loosely coupled** Describes a kernel design in which the kernel is composed of components that have specifi c and limited functions.

**lottery scheduling** A scheduling algorithm in which “lottery tickets” are given to threads and a lottery number is chosen at random to determine the next thread to get CPU time.

**low-fragmentation heap (LFH)** An optimization of the Windows default heap designed to decrease fragmentation.

**low-level formatting** The initialization of a stor- age medium in preparation for its use as a com- puter storage device.

**Lustre A common open-source clustered fi le** system.

**LXC** A Linux container technology.

**Mach** An operating system with microkernel structure and threading; developed at Carnegie Mellon University.

**Mach-O The macOS format of executable fi les.**

**magic cookie** A crude method of storing a text string at the start of a text fi le to indicate the type of text in the fi le.

**magic number** A crude method of storing a number at the start of a fi le to indicate the type of the data in the fi le.

**magnetic tape** A magnetic media storage device consisting of magnetic tape spooled on reels and passing over a read-write head. Used mostly for backups.

**main queue** Apple OS per-process block queue.

**main TLB** ARM CPU outer-level TLB; checked after the micro TLB lookup and before a miss causes a page table walk.

**mainframe** The largest class of computers (along with supercomputers), hosting hundreds of users and many and/or large jobs.

**major fault** In virtual memory, a page fault that can be resolved without having to page in data from secondary storage.

**malware** Software designed to exploit, disable, or damage computer systems.

**mandatory access control (MAC)** Access control settings enforced in the form of system policy.

**mandatory fi le-lock mechanism A fi le-locking** system in which the operating system enforces locking and fi le access.

**man-in-the-middle attack** An attack in which the attacker sits in the middle of the data fl ow of a communication, masquerading as the sender to the receiver and vice versa.

**MapReduce** A Google-created big data pro- gramming model and implementation for parallel processing across nodes in a distributed cluster. A layer on top of the Google fi le system (GFS), it  

**Glossary G-21**

allows developers to carry out large-scale parallel computations easily.

**marshaling** Packaging a communication into an expected format for transmittal and reception.

**maskable** Describes an interrupt that can be delayed or blocked (such as when the kernel is in a critical section).

**masquerading** A practice in which a participant in a communication pretends to be someone else (another host or another person).

**master boot record (MBR)** Windows boot code, stored in the fi rst sector of a boot partition.

**master fi le directory (MFD) In two-level directory** implementation, the index pointing to each UFD.

**master fi le table The NTFS volume control block.**

**master key** In the lock-key protection scheme, a key that is associated with each object and can be defi ned or replaced with the set-key operation to revoke or change access rights.

**matchmaker** A function that matches a caller to a service being called (e.g., a remote procedure call attempting to fi nd a server daemon).

**mean time between failure (MTBF)** The statis- tical mean time that a device is expected to work correctly before failing.

**mean time to data loss** The statistical mean of the time until data is lost.

**mean time to repair** The statistical mean of the time to repair a device (e.g., to get a replacement and install it).

**mechanical storage device** A storage device based on moving mechanical parts (such as HDDs, optical disks, and magnetic tape); one form of nonvolatile storage.

**mechanism An operation that defi nes how** something will be done.

**medium access control (MAC) address** A unique byte number assigned to every Ethernet device allowing it to be located by packets sent across a LAN.

**megabyte (MB)** 1,024^2 bytes.

**memory** Volatile storage within a computer system.

**memory barriers** Computer instructions that force any changes in memory to be propagated to all other processors in the system.

**memory compression** In memory management, an alternative to paging involving compressing the contents of frames to decrease the memory used.

**memory compression process** In Windows 10, a process that maintains a working set of com- pressed standby pages.

**memory fences** Computer instructions that force any changes in memory to be propagated to all other processors in the system.

**memory manager (MM)** The Windows name for the component that manages memory.

**memory mapping A fi le-access method in which** a fi le is mapped into the process memory space so that standard memory access instructions read and write the contents of the fi le; an alternative to the use of read() and write() calls.

**memory model** Computer architecture mem- ory guarantee, usually either strongly ordered or weakly ordered.

**memory resident** Objects, such as pages, that are in main memory and ready for threads to use or execute.

**memory stall** An event that occurs when a thread is on CPU and accesses memory content that is not in the CPU’s cache. The thread’s execution stalls while the memory content is fetched.

**memory transaction** A sequence of memory read–write operations that are atomic.

**memory-management unit (MMU)** The hard- ware component of a computer CPU or mother- board that allows it to access memory.

**memory-mapped fi le A fi le that is loaded into** physical memory via virtual memory methods, allowing access by reading and writing to the memory address occupied by the fi le.

**memory-mapped I/O** A device I/O method in which device-control registers are mapped into the address space of the processor.

**message** In networking, a communication, con- tained in one or more packets, that includes source and destination information to allow correct delivery. In message-passing communications, a packet of information with metadata about its sender and receiver.

**message digest** The calculation resulting from a hash function.

**message passing** In interprocess communi- cation, a method of sharing data in which mes- sages are sent and received by processes. Packets of information in predefi ned formats are moved between processes or between computers.

**message-authentication code (MAC)** A cryp- tographic checksum calculated in symmetric encryption; used to authenticate short values.

**message-passing model** A method of interprocess communication in which messages are exchanged.

**metadata A set of attributes of an object. In fi le** systems, e.g., all details of a fi le except the fi le’s contents.  

**G-22** **Glossary**

**metaslabs** Chunks of blocks. In ZFS, a pool of stor- age is split into metaslabs for easier management.

**methods** In Java, functions that act on objects and data fi elds.

**metropolitan-area network (MAN)** A network linking buildings within a city.

**micro TLB** ARM CPU inner-level TLBs, one for instructions and one for data.

**microkernel** An operating-system structure that removes all nonessential components from the kernel and implements them as system and user- level programs.

**Microsoft interface defi nition language The** Microsoft text-based interface defi nition language; used, e.g., to write client stub code and descriptors for RPC.

**middleware** A set of software frameworks that provide additional services to application developers.

**minicomputer** A mid-sized computer, smaller than a mainframe but larger (in resources and users) than a workstation.

**minidisks** Virtual disks used in early IBM vir- tual systems.

**minimum granularity** In the Completely Fair Scheduler, a confi gurable variable representing the minimum length of time any process is allocated to the processor.

**miniport driver** In Windows I/O, the device- specifi c driver.

**minor fault** In virtual memory, a page fault resolved by executing an I/O to bring in the page from secondary storage.

**mirrored volume** A volume in which two devices are mirrored.

**mirroring** In storage, a type of RAID protection in which two physical devices contain the same content. If one device fails, the content can be read from the other.

**mobile computing** A mode of computing involv- ing small portable devices like smartphones and tablet computers.

**mode bit** A CPU status bit used to indicate the current mode: kernel (0) or user (1).

**modify bit** An MMU bit used to indicate that a frame has been modifi ed (and therefore must have its contents saved before page replacement).

**module loader and unloader** In Linux, user-mode utilities that work with the module-management system to load modules into the kernel.

**module-management system** In Linux, the facil- ity that allows kernel modules to be loaded into

memory and to communicate with the rest of the kernel.

**monitor** A high-level language synchroniza- tion construct that protects variables from race conditions.

**monitor call** A software-triggered interrupt allowing a process to request a kernel service.

**monoculture** A community of computer systems that are very similar to one another. This similarity makes them easier to attack and thus represents a threat to security.

**monolithic** In kernel architecture, describes a ker- nel without structure (such as layers or modules).

**Moore’s Law** A law predicting that the number of transistors on an integrated circuit would dou- ble every eighteen months.

**most frequently used (MFU)** In general, an algo- rithm that selects the item that has been used most frequently. In virtual memory, when access counts are available, selecting the page with the highest count.

**mount point The location within the fi le struc-** ture where a fi le system is attached.

**mount protocol The protocol for mounting a fi le** system in a remote fi le system.

**mount table** An in-memory data structure con- taining information about each mounted volume. It tracks fi le systems and how they are accessed.

**mounting Making a fi le system available for use** by logically attaching it to the root fi le system.

**multicore** Multiple processing cores within the same CPU chip or within a single system.

**multicore processor** Multiple processing cores within the same CPU chip.

**multicore systems** Systems that have two or more hardware processors (CPU cores) in close commu- nication, sharing the computer bus and sometimes the clock, memory, and peripheral devices.

**multifactor authentication** Authentication based on two or more sources of data, with more sources generally providing stronger authentication.

**multilevel feedback queue** A scheduling algo- rithm that allows a process to move between queues.

**multilevel queue** A scheduling algorithm that partitions the ready queue into several separate queues.

**multiple universal-naming-convention provider (MUP)** The component within Windows that executes remote fi le accesses.

**multiple user interface (MUI)** A Windows Vista feature that allows multiple user interfaces,  

**Glossary G-23**

possibly confi gured for different locales, to be used concurrently.

**multiprocessor** Multiple processors within the same CPU chip or within a single system.

**multiprocessor systems** Systems that have two or more hardware processors (CPU cores) in close communication, sharing the computer bus and sometimes the clock, memory, and peripheral devices.

**multiprogramming** A technique that increases CPU utilization by organizing jobs (code and data) so that the CPU always has a job to execute.

**multitasking** The concurrent performance of multiple jobs. A CPU executes multiple jobs by switching among them, but the switches occur so frequently that users can interact with the processes.

**multithreaded** A term describing a process or program with multiple threads of control, allow- ing multiple simultaneous execution points.

**mutex lock** A mutual exclusion lock; the sim- plest software tool for assuring mutual exclusion.

**mutual exclusion** A property according to which only one thread or process can be executing code at once.

**name server** In the domain-name system, a host or software that provides resolving services.

**named pipes** A connection-oriented messaging mechanism—e.g., allowing processes to communi- cate within a single computer system.

**named semaphore** A POSIX scheduling con- struct that exists in the fi le system and can be shared by unrelated processes.

**named shared-memory object** In Windows API, a section of a memory-mapped fi le accessible by name from multiple processes.

**namespace In Linux, a process’s specifi c view of** the fi le system hierarchy.

**naming** In distributed computing, the mapping between logical and physical objects.

**national-language-support (NLS)** A Windows API providing support for localization (including date, time, and money formats).

**need-to-know principle** The principle that only those resources currently needed should be avail- able to use at a given time.

**nested page tables (NPTs)** In virtualization, a method used by the virtual machine manager to maintain page-table state both for guests and for the system.

**network** In the simplest terms, a communication path between two or more systems.

**network address translation** In networking, the mapping of one header address to another by mod- ifying the network packets (e.g., allowing a host to provide IP addresses to multiple guests while presenting only one IP address to the connected network).

**network computer** A limited computer that understands only web-based computing.

**network device interface specifi cation (NDIS)** An internal Windows networking inter- face separating network adapters from transport protocols.

**network devices** I/O devices that connect to a network.

**network fi le system (NFS) A common network** fi le system used by UNIX, Linux, and other operat- ing systems to share fi les across a network.

**network operating system** A type of operating system that provides features such as fi le sharing across a network, along with a communication scheme that allows different processes on differ- ent computers to exchange messages. It provides an environment in which users can access remote resources by remote login or data transfer between remote and local systems.

**network time protocol** A network protocol for synchronizing system clocks.

**network virtual memory** A distributed comput- ing feature similar to virtual memory but with the backing store on a remote system.

**network-attached storage (NAS)** Storage accessed from a computer over a network.

**NFS protocol The protocol used for remote fi le** access, remote fi le system mounting, etc., by the NFS fi le system.

**nice value** One of a range of values from ?20 to +19, where a numerically lower value indicates a higher relative scheduling priority.

**NIS** A distributed naming service that provides username, password, hostname, and printer infor- mation to a set of computers.

**nonblocking** A type of I/O request that allows the initiating thread to continue while the I/O operation executes. In interprocess communi- cation, a communication mode in which the sending process sends the message and resumes operation and the receiver process retrieves either a valid message or a null if no message is available. In I/O, a request that returns whatever data is currently available, even if it is less than requested.

**noncontainer objects** In Windows 10, a category of objects that cannot contain other objects.  

**G-24** **Glossary**

**nonmaskable interrupt** An interrupt that cannot be delayed or blocked (such as an unrecoverable memory error)

**nonpreemptive** Scheduling in which, once a core has been allocated to a thread, the thread keeps the core until it releases the core either by terminating or by switching to the waiting state.

**nonpreemptive kernels** A type of kernel that does not allow a process running in kernel mode to be preempted; a kernel-mode process will run until it exits kernel mode, blocks, or voluntarily yields control of the CPU.

**nonrepudiation** Proof that an entity performed an action (frequently performed by digital signatures).

**non-uniform memory access (NUMA)** An archi- tecture aspect of many computer systems in which the time to access memory varies based on which core the thread is running on (e.g., a core interlink is slower than accessing DIMMs directly attached to core).

**nonvolatile memory (NVM)** Persistent storage based on circuits and electric charges.

**nonvolatile storage (NVS)** Storage in which data will not be lost in a power outage or similar event.

**NOOP** The Linux NVM scheduling algorithm, fi rst come fi rst served but with adjacent requests merged into fewer, larger I/O requests.

**NUMA node** One or more cores (e.g., cores that share a cache) that are grouped together as a scheduling entity for affi nity or other uses.

**NVM express (NVMe)** A high-speed I/O bus for NVM storage.

**NVRAM** DRAM with battery or other backup power, rendering it nonvolatile.

**object** An instance of a class or an instance of a data structure. In Windows and generally, an instance of an object type.

**object linking and embedding (OLE)** A Micro- soft technology allowing services to provide func- tions to components (e.g., for inserting spread- sheets into Word documents).

**object manager** In Windows, the kernel (execu- tive) component that manipulates objects.

**object type In Windows, a system-defi ned data** type that has a set of attributes and methods that help defi ne its behavior.

**off-line** Generally, a facility, system, or comput- ing component that is unavailable. In fi le system implementation, operations executing while the fi le system is unavailable for use.

**one-time password** A password that is only valid once.

**on-line** Generally, a facility, system, or comput- ing component that is available. In fi le system implementation, operations executing while the fi le system is available for use.

**open count** The number of processes having an open fi le.

**open-fi le table An operating system data struc-** ture containing details of every fi le open within the system.

**open-source operating system** An operating system or other program available in source-code format rather than as compiled binary code.

**operating system** A program that manages a computer’s hardware, provides a basis for appli- cation programs, and acts as an intermediary between the computer user and the computer hardware.

**optimal page-replacement algorithm** A theo- retically optimal page replacement algorithm that has the lowest page-fault rate of all algorithms and never suffers from Belady’s anomaly.

**Orange Book** U.S. Department of Defense Trusted Computer System Evaluation Criteria; a method of classifying the security of a system design.

**orphan** The child of a parent process that termi- nates in a system that does not require a terminat- ing parent to cause its children to be terminated.

**OS/2** A PC operating system from the mid 1980s co-developed by IBM and Microsoft to replace MS-DOS; generally considered to be a failure.

**OSI protocol stack** A set of cooperating network protocols that form a fully functional network. The OSI model formalized some of the earlier work done in network protocols but is currently not in widespread use.

**out-of-band** In networking, a term describing data delivered in a manner independent of the main data stream (e.g., delivery of a symmetric key in a paper document).

**out-of-memory (OOM) killer** In Linux, a routine that executes when free memory is very low, termi- nating processes to free memory.

**over-allocating** Generally, providing access to more resources than are physically available. In virtual memory, allocating more virtual memory than there is physical memory to back it.

**overcommitment** In virtualization, providing resources to guests that exceed available physical resources.

**over-provisioning** In non-volatile memory, space set aside for data writes that is not counted in the device free space.  

**Glossary G-25**

**owner In fi le permissions, the userid that owns** and controls access to a fi le.

**owner rights In fi le permissions, the userid that** owns and controls access to a fi le.

**page address extension (PAE)** Intel IA-32 CPU architecture hardware that allows 32-bit proces- sors to access physical address space larger than 4GB.

**page allocator** The kernel routine responsible for allocating frames of physical memory.

**page cache In fi le I/O, a cache that uses virtual** memory techniques to cache fi le data as pages rather than fi le-system-oriented blocks for effi ciency.

**page directory** In Intel IA-32 CPU architecture, the outermost page table.

**page directory pointer table** PAE pointer to page tables.

**page fault** A fault resulting from a reference to a non-memory-resident page of memory.

**page frame** A Windows virtual memory data structure.

**page frame number (PFN)** In Windows, the name of the indicator of the page frame address.

**page number** Part of a memory address gener- ated by the CPU in a system using paged memory; an index into the page table.

**page offset** Part of a memory address generated by the CPU in a system using paged memory; the offset of the location within the page of the word being addressed.

**page replacement** In virtual memory, the selec- tion of a frame of physical memory to be replaced when a new page is allocated.

**page slot** In Linux swap-space management, a part of the data structure tracking swap-space use.

**page table** In paged memory, a table containing the base address of each frame of physical mem- ory, indexed by the logical page number.

**page-directory entry (PDE)** A Windows virtual- memory data structure.

**page-fault frequency** The frequency of page faults.

**page-fault rate** A measure of how often a page fault occurs per memory access attempt.

**pageout policy** Generally, an algorithm for deciding which memory pages to page out. In Linux, the virtual memory pageout policy uses a modifi ed version of the second-chance algorithm.

**pager** The operating-system component that handles paging.

**page-replacement algorithm** In memory man- agement, the algorithm that chooses which victim frame of physical memory will be replaced by a needed new frame of data.

**page A fi xed-sized block of logical memory.**

**page-table base register** In paged memory, the CPU register pointing to the in-memory page table.

**page-table entry (PTE)** A Windows virtual memory data structure.

**page-table length register** A CPU register indi- cating the size of the page table.

**paging** A common memory management scheme that avoids external fragmentation by splitting physical memory into fi xed-sized frames and logical memory into blocks of the same size called pages.

**paging fi le The Windows term for backing store.**

**paging mechanism** In Linux, the kernel compo- nent that carries out the transfer of pages back and forth to backing store.

**paired password** In authentication, a challenge- response set of secret keys, where only the correct response to the challenge provides authentication.

**parallel fi le system (PFS) A fi le system that is** LAN-based and treats N systems storing data and Y clients accessing the data as a single client-server instance; more complex than a client-server DFS but less complex than a cluster-based DFS. GPFS and Lustre are examples.

**parallel regions** Blocks of code that may run in parallel.

**parallel systems** Systems that have two or more hardware processors (CPU cores) in close commu- nication, sharing the computer bus and sometimes the clock, memory, and peripheral devices.

**parallelization** The process of dividing a pro- gram into separate components that run in parallel on individual cores in a computer or computers in a cluster.

**paravirtualization** A technique in which a guest operating system is modifi ed to work in coopera- tion with a virtual machine manager.

**parent** In a tree data structure, a node that has one or more nodes connected below it.

**partition** Logical segregation of storage space into multiple area; e.g., on HDDs, creating several groups of contiguous cylinders from the devices’ full set of cylinders.

**partition boot sector** The NTFS boot control block.

**passphrase** A longer, generally more secure password composed of multiple words.  

**G-26** **Glossary**

**password** A secret key, usually used to authenti- cate a user to a computer.

**path name The fi le-system name for a fi le, which** contains all the mount-point and directory-entry information needed to locate the fi le (e.g., “C:/ foo/bar.txt” and “/foo/bar.txt”)

**path-name translation The parsing of a fi le name** into separate directory entries, or components.

**PCIe bus** A common computer I/O bus connect- ing the CPU to I/O devices.

**peer-to-peer (p2p)** A mode of distributed com- puting in which all nodes act as both clients of other nodes and servers to other nodes.

**penetration test** The scanning of a target entity to look for known vulnerabilities.

**performance tuning** The activity of improving performance by removing bottlenecks.

**periodic** A type of real-time process that repeat- edly moves at fi xed intervals between two modes: needing CPU time and not needing CPU time.

**permissions** An entity’s access rights to an object (e.g., a user’s access rights to a fi le).

**per-process open-fi le table A kernel in-memory** per-process data structure containing pointers to the system-wide open-fi le table, as well as other information, for all fi les the process has open.

**personal fi rewall A software layer, either part** of the operating system or added to a computer, limiting communication to and from a given host.

**personal identifi cation number A usually short** and not very secure password composed of some combination of digits 0-9.

**personal-area network (PAN)** A network linking devices within several feet of each other (e.g., on a person).

**petabyte (PB)** 1,024^5 bytes.

**Peterson’s solution** A historically interesting algorithm for implementing critical sections.

**phishing** A class of social engineering attacks in which a legitimate-looking e-mail or website tricks a user into breaching confi dentiality or enabling privilege escalation.

**PHY** The physical hardware component that connects to a network (implements layer 1 in the OSI model).

**physical address** Actual location in physical memory of code or data.

**physical address space** The set of all physical addresses generated by a program.

**physical formatting** The initialization of a stor- age medium in preparation for its use as a com- puter storage device.

**physical-to-virtual (P-to-V)** In virtualization, the conversion of a physical system’s operating sys- tem and applications to a virtual machine.

**Pico** In WSL, a special Linux-enabling process that translates Linux system calls to the LXCore and LXSS services.

**pinning** In memory management, locking pages into memory to prevent them from being paged out.

**pipe** A logical conduit allowing two processes to communicate.

**platform as a service (PaaS)** A software stack ready for application use via the Internet (e.g., a database server).

**platter** An HDD component that has a magnetic media layer for holding charges.

**plug-and-play (PnP) manager** In Windows, the manager responsible for detecting and enumerat- ing devices when the system is booting and adding and removing devices when the system is running.

**pluggable authentication module (PAM)** A shared library that can be used by any system com- ponent to authenticate users.

**plug-in** An add-on functionality that expands the primary functionality of a process (e.g., a web browser plug-in that displays a type of content dif- ferent from what the browser can natively handle).

**point-to-point tunneling protocol (PPTP)** A protocol in Windows and other systems allowing communication between remote-access server modules and client systems connected across a WAN.

**policy A rule that defi nes what will be done.**

**policy algorithm** In Linux, a part of the paging system that decides which pages to write out to backing store and when to write them.

**polling** An I/O loop in which an I/O thread con- tinuously reads status information waiting for I/O to complete.

**pool** In virtual memory, a group of free pages kept available for rapid allocation (e.g., for copy- on-write). In ZFS, drives, partitions, or RAID sets that can contain one or more fi le systems.

**pop** The action of removing an item from a stack data structure.

**port** A communication address; a system may have one IP address for network connections but many ports, each for a separate communication. In computer I/O, a connection point for devices to attach to computers. In software development, to move code from its current platform to another platform (e.g., between operating systems or hardware systems). In the Mach OS, a mailbox for communication.  

**Glossary G-27**

**port driver** In Windows I/O, the common driver for a class of devices.

**port number** In TCP/IP and UDP/IP network- ing, an address of a service on a system.

**port set** A collection of ports, as declared by a task, that can be grouped together and treated as one port for the purposes of the task.

**portable** An aspect of software that describes its ease of transfer between CPU architectures and computer systems.

**portable executable (PE)** The Windows format for executable fi les.

**portals** Gateways between requestors and ser- vices running on provider computers.

**position-independent code (PIC)** In Linux, binary code compiled from shared libraries that can be loaded anywhere in memory.

**positioning time** On an HDD, the time it takes the read-write head to position over the desired track.

**power manager** In Windows, the component that implements power management policies.

**power users** Users with unusually deep knowl- edge of a system.

**power-of-2 allocator** In the buddy system, an allocator that satisfi es memory requests, in units sized as a power of 2, from a fi xed-sized segment consisting of contiguous pages.

**power-on self-test (POST) A fi rmware routine** run at system power-on that tests the system for hardware issues, identifi es and initializes many of the attached devices, and builds the description of the devices used by the advanced confi guration and power interface (ACPI).

**preemptive** A form of scheduling in which pro- cesses or threads are involuntarily moved from the running state (e.g., by a timer signaling the kernel to allow the next thread to run).

**preemptive kernel** A type of kernel that allows a process to be preempted while it is running in kernel mode.

**preemptive multitasking** A model of multitask- ing in which threads on cores may be preempted by higher-priority threads before fi nishing their scheduled time quanta.

**prepaging** In virtual memory, bringing pages into memory before they are requested.

**principle of least privilege** A design principle stating that every program and every privileged user of the system should operate using the least amount of privilege necessary to complete the job.

**priority inversion** A scheduling challenge aris- ing when a higher-priority process needs to read

or modify kernel data that are currently being accessed by a lower-priority process.

**priority number** A number indicating the posi- tion of a process in a conditional-wait queue in a monitor construct.

**priority paging** Prioritizing selection of victim frames based on some criteria, such as avoiding selection of shared library pages.

**priority replacement algorithm** A virtual mem- ory page replacement algorithm that avoids thrashing by not allowing a process to steal frames from other processes.

**priority-inheritance protocol** A protocol for solving priority inversion in which all processes that are accessing resources needed by a higher- priority process inherit that higher priority until they are fi nished with the resources in question.

**priority scheduling** A scheduling algorithm in which a priority is associated with each thread and the free CPU core is allocated to the thread with the highest priority.

**private cloud** Cloud computing run by a com- pany for that company’s own use.

**private key** In an asymmetric encryption algo- rithm, a key that must be kept private for use in authenticating, encrypting, and decrypting.

**privilege escalation** The enabling of more priv- ileges than an entity (process, system, person) should have.

**privileged instructions** Instructions that can execute only if the CPU is in in kernel mode.

**privileged mode** A CPU mode in which all instructions are enabled. The kernel runs in this mode. See also user mode.

**proc fi le system (/proc) A pseudo fi le system** using fi le-system interfaces to provide access to a system’s process name space.

**procedural language** A language that imple- ments state-based algorithms (e.g., C, C++, Java, and C#).

**process** A program loaded into memory and executing.

**process control** A category of system calls.

**process control block** A per-process kernel data structure containing many pieces of information associated with the process.

**process identifi er (pid) A unique value for each** process in the system that can be used as an index to access various attributes of a process within the kernel.

**process lifetime management (PLM)** A Win- dows power-saving feature that suspends all  

**G-28** **Glossary**

threads within a process that has not been used for a few seconds.

**process migration** The movement of a process between computers.

**process name** A human-readable name for a process.

**process scheduler** A scheduler that selects an available process (possibly from a set of several processes) for execution on a CPU.

**process synchronization** Coordination of access to data by two or more threads or processes.

**process-contention scope (PCS)** A scheduling scheme, used in systems implementing the many- to-one and many-to-many threading models, in which competition for the CPU takes place among threads belonging to the same process.

**processor affi nity A kernel scheduling method** in which a process has an affi nity for (prefers) the processor on which it is currently running.

**processor groups** In Windows 7, processors grouped together for management and scheduling.

**producer** A process role in which the process produces information that is consumed by a con- sumer process.

**production kernels** Kernels released for produc- tion use (as opposed to development use).

**profi ling Periodically sampling the instruction** pointer to determine which code is being executed; used in debugging and performance tuning.

**program counter** A CPU register indicating the main memory location of the next instruction to load and execute.

**programmable interval timer** A hardware timer provided by many CPUs.

**programmed I/O (PIO)** A method of transfer- ring data between a CPU and a peripheral device in which data are transferred one byte at a time.

**programming-environment virtualization** Vir- tualization in which a virtual machine manager does not virtualize real hardware but instead creates an optimized virtual system (examples include Oracle Java and Microsoft.Net).

**project** In Solaris scheduling, a group of pro- cesses scheduled as a unit.

**proportional allocation** An allocation algorithm that assigns a resource in proportion to some aspect of the requestor. In virtual memory, the assignment of page frames in proportion to the size each process.

**proportional share** A scheduler that operates by allocating T shares among all applications, ensur- ing that each gets a specifi c portion of CPU time.

**protection** A category of system calls. Any mecha- nism for controlling the access of processes or users to the resources defi ned by a computer system.

**protection domain** In protection, a set of resources that a process may access. In virtualiza- tion, a virtual machine manager creates a protec- tion domain for each guest to inform the CPU of which physical memory pages belong to that guest.

**protection mask** In Linux and UNIX, a set of bits assigned to an object specifying which access modes (read, write, execute) are to be granted to processes with owner, group, or world access writes to the object.

**protection rings** A model of privilege separation consisting of a series of rings, with each successive ring representing greater execution privileges.

**pseudo device driver** In virtualization, a guest device driver that does not directly control sys- tem hardware but rather works with the virtual machine manager to access the device.

**PTE table** A Windows virtual-memory data structure.

**Pthreads** The POSIX standard (IEEE 1003.1c) defi ning an API for thread creation and synchroni- zation (a specifi cation for thread behavior, not an implementation).

**public cloud** Cloud computing available via the Internet to anyone willing to pay for the services offered.

**public domain** The total absence of copyright protection. Software in the public domain can be used as desired by anyone, with no limits.

**public key** In asymmetric encryption algorithm, a key that can be distributed for encrypting and decrypting.

**public key encryption** A cipher algorithm in which different keys are used for encryption and decryption.

**pull migration** Migration that occurs when an idle processor pulls a waiting thread from a busy processor.

**pure demand paging** A demand paging scheme wherein no page is brought into memory until it is referenced.

**push** The action of placing a value on a stack data structure.

**push migration** Migration in which a task peri- odically checks the load on each processor and, if it fi nds an imbalance, evenly distributes the load by moving (or pushing) threads from overloaded to idle or less busy processors.

**Quest-V** An example of a partitioning hypervisor.  

**Glossary G-29**

**queue** A sequentially ordered data structure that uses the fi rst-in, fi rst-out (FIFO) principle; items are removed from a queue in the order in which they were inserted.

**queueing-network analysis** An area of comput- ing study in which algorithms are analyzed for various characteristics and effectiveness.

**race condition** A situation in which two threads are concurrently trying to change the value of a variable.

**RAID levels** The various types of RAID protection.

**RAM drives** Sections of a system’s DRAM pre- sented to the rest of the system as if they were secondary storage devices.

**random-access memory (RAM)** Rewritable memory, also called main memory. Most programs run from RAM, which is managed by the kernel.

**ransomware** A class of malware that disables computer access (frequently by encrypting fi les or the entire system) until a ransom is paid.

**rate** Generally, a measure of speed or frequency. A periodic real-time process has a scheduling rate of 1/p, where p is the length of its running period.

**rate-monotonic** A scheduling algorithm that schedules periodic tasks using a static priority pol- icy with preemption.

**raw partition** A partition within a storage device not containing a fi le system.

**raw disk** Direct access to a secondary storage device as an array of blocks with no fi le system.

**raw I/O** Direct access to a secondary storage device as an array of blocks with no fi le system.

**read pointer The location in a fi le from which the** next read will occur.

**read-ahead** Sequential I/O performance optimi- zation that reads and caches several subsequent pages when a read of one page is requested.

**readers-writers problem** A synchronization problem in which one or more processes or threads write data while others only read data.

**reader-writer lock** A lock appropriate for access to an item by two types of accessors, read-only and read-write.

**read-modify-write cycle** The situation in which a write of data smaller than a block requires the entire block to be read, modifi ed, and written back.

**read-only memory (ROM)** A storage device whose contents are not modifi able.

**read-write (RW)** Access that allows reading and writing.

**ready queue** The set of processes ready and waiting to execute.

**real-time** A term describing an execution envi- ronment in which tasks are guaranteed to com- plete within an agreed-to time.

**real-time class** A scheduling class that seg- regates real-time threads from other threads to schedule them separately and provide them with their needed priority.

**real-time operating systems (RTOS)** Systems used when rigid time requirements have been placed on the operation of a processor or the fl ow of data; often used as control devices in dedicated applications.

**reapers** In memory management, routines that scan memory, freeing frames to maintain a mini- mum level of available free memory.

**recovery mode** A system boot state providing limited services and designed to enable the system admin to repair system problems and debug sys- tem startup.

**Red Hat** A popular Linux distribution.

**red-black tree** A tree containing n items and hav- ing at most lg n levels, thus ensuring worst-case performance of O(lg n).

**redirector** In Windows, a client-side object that forwards I/O requests to a remote system.

**redundant arrays of independent disks (RAID)** A disk organization technique in which two or more storage devices work together, usually with protection from device failure.

**reentrant code** Code that supports multiple con- current threads (and can thus be shared).

**reference bit** An MMU bit indicating that a page has been referenced.

**reference string** A trace of accesses to a resource. In virtual memory, a list of pages accessed over a period of time.

**referenced pointer** In Windows, a means by which kernel-mode code can access objects; must be obtained by calling a special API.

**regions** In ARM v8 CPUs, contiguous areas of memory with separate privilege and access rules.

**registry A fi le, set of fi les, or service used to store** and retrieve confi guration information. In Win- dows, the manager of hives of data.

**regressive round-robin** A variation on round- robin scheduling in which a thread that uses its entire CPU scheduling quantum is given a longer quantum and higher priority.

**relative access A fi le-access method in which** contents are read in random order, or at least not sequentially.  

**G-30** **Glossary**

**relative block number** An index relative to the beginning of a fi le. The fi rst relative block of the fi le is block 0, the next is block 1, and so on through the end of the fi le.

**relative path name** A path name starting at a rel- ative location (such as the current directory).

**relocatable code** Code with bindings to mem- ory addresses that are changed at loading time to refl ect where the code is located in main memory.

**relocatable object fi le The output of a compiler** in which the contents can be loaded into any loca- tion in physical memory.

**relocation** An activity associated with linking and loading that assigns fi nal addresses to pro- gram parts and adjusts code and data in the pro- gram to match those addresses.

**relocation register** A CPU register whose value is added to every logical address to create a phys- ical address (for primitive memory management).

**remainder section** Whatever code remains to be processed after the critical and exit sections.

**remote access tool (RAT)** A back-door daemon left behind after a successful attack to allow con- tinued access by the attacker.

**remote desktop** The representation of a desktop session to another system across a network, for remote access to the computer’s GUI.

**remote desktop protocol (RDP)** A network protocol to allow remote access to a computer’s display contents and keyboard and mouse input devices.

**remote fi le transfer A function of a network** operating system providing a means to transfer fi les between network-attached computers.

**remote procedure calls (RPCs)** Procedure calls sent across a network to execute on another com- puter; commonly used in client-server computing.

**remote-service mechanism** A facility, imple- mented by a feature such as RPC, in which clients ask a remote system to perform a function for them.

**renderer** A process that contains logic for render- ing contents (such as web pages) onto a display.

**rendezvous** In interprocess communication, when blocking mode is used, the meeting point at which a send is picked up by a receive.

**replay attack** The malicious or fraudulent repeti- tion of a valid transmission.

**replication In fi le systems, the duplication and** synchronization of a set of data over a network to another system. In storage, the automatic duplica- tion of writes between separate sites.

**request edge** In a system resource-allocation graph, an edge (arrow) indicating a resource request.

**request manager** In Linux, the kernel compo- nent that manages the reading and writing of buf- fer contents to and from a block-device driver.

**resolve** Generally, to translate from a symbolic representation to a numeric one. In networking, to translate from a host name to a host-id. With fi les, to follow a link and fi nd the target fi le.

**resource allocator** An operating system or appli- cation that determines how resources are to be used.

**resource manager** The role of an operating sys- tem in managing the computer’s resources.

**resource sharing** The ability for multiple users, computers, etc., to access computing resources.

**resource utilization** The amount of a given resource (hardware or software) that is being used.

**response time** The amount of time it takes the system to respond to user action.

**restore In fi le systems, the act of repairing or** recovering fi les or a fi le system from a backup.

**resume** In virtualization, the continuation of execution after a guest’s suspension.

**reverse engineering** The procedure of convert- ing a compiled binary fi le into a human-readable format.

**rich text format A fi le format developed by** Microsoft that includes formatting details but can be used by various applications and operating systems, enabling fi les to be transferred between programs and systems.

**risk assessment** A systemic security analysis that attempts to value the assets of the entity in question and determine the odds that a security incident will affect the entity.

**roaming profi le In Windows, a collection of user** preferences and settings that are kept on a server and allow a user’s environment to follow that user from computer to computer.

**role-based access control (RBAC)** A method of access control in which roles rather than users have access rights; applies the principle of least privilege to the protection of operating systems.

**role** In RBAC, a named set of privileges that can be available to a user.

**root partition** The storage partition that con- tains the kernel and the root fi le system; the one mounted at boot.

**rotational latency** On an HDD, the time it takes the read-write head, once over the desired cylin- der, to access the desired track.  

**Glossary G-31**

**round-robin (RR)** A scheduling algorithm simi- lar to FCFS scheduling, but with preemption added to enable the system to switch between threads; designed especially for time-sharing systems.

**router** A device or software that connects net- works to each other (e.g., a home network to the Internet).

**RSA** The most widely used public key cipher.

**run queue** The queue holding the threads that are ready to run on a CPU.

**running** The state of the operating system after boot when all kernel initialization has completed and system services have started. In general, the system state after booting and before crashing or being shut down.

**run-time environment (RTE)** The full suite of software needed to execute applications written in a given programming language, including its com- pilers, libraries, and loaders.

**safe computing** Human behavior aimed at avoiding viruses and other security problems (e.g., by avoiding downloading pirated software).

**safe sequence** “In deadlock avoidance, a sequence of processes <P1, P2, ..., Pn> in which, for each Pi, the resource requests that Pi can make can be satisfi ed by the currently available resources plus the resources held by all Pj, with j < i.”

**safe state** In deadlock avoidance, a state in which a system can allocate resources to each process in some order and still avoid deadlock.

**sandbox** A contained environment (e.g., a virtual machine).

**sandboxing** Restricting what an object can do by placing it in a contained environment (e.g., run- ning a process on a virtual machine).

**SAS** A common type of I/O bus.

**scalability** Generally, the ability of a facility or service to increase capacity as needed by the users (e.g., to add more cores when the load increases).

**SCAN algorithm** An HDD I/O scheduling algo- rithm in which the disk head moves from one end of the disk to the other performing I/O as the head passes the desired cylinders; the head then reverses direction and repeats.

**scatter-gather** An I/O method in which multiple sources or destinations of I/O are specifi ed in one command structure.

**scheduler** The part of the operating system that determines the next job to be done (e.g., the next process to be executed).

**scheduler activation** A threading method in which the kernel provides an application with a set of LWPs, and the application can schedule user threads onto an available virtual processor and receive upcalls from the kernel to be informed of certain events.

**scheduling classes** In Linux, classes on which scheduling is based; each class is assigned a spe- cifi c priority.

**scheduling domain** A set of CPU cores that can be balanced against one another.

**scope** The time between when a lock is acquired and when it is released.

**script kiddie** An attacker who did not design the attack but instead is using an attack designed by a more sophisticated attacker.

**search path** In some operating systems, the sequence of directories searched for an executable fi le when a command is executed.

**second extended fi le system (ext2) In Linux, an** outdated version of the extended fi le system

**secondary storage** A storage system capable of holding large amounts of data permanently; most commonly, HDDs and NVM devices.

**second-chance page-replacement algorithm** A FIFO page replacement algorithm in which, if the reference bit is set, the bit is cleared and the page is not replaced.

**second-level interrupt handler** In some oper- ating systems, the interrupt handler that actu- ally handles interrupts; reception and queueing of interrupts are handled at another level (by the fi rst-level handler).

**section object** The Windows data structure that is used to implement shared memory.

**sector forwarding** The replacement of an unus- able HDD sector with another sector at some other location on the device.

**sector slipping** The renaming of sectors to avoid using a bad sector.

**sector sparing** The replacement of an unusable HDD sector with another sector at some other location on the device.

**sector On an HDD platter, a fi xed-size section of** a track.

**secure** The state of a system whose resources are used and accessed as intended under all circumstances.

**secure by default** Describes a system or com- puter whose initial confi guration decreases its attack surface.  

**G-32** **Glossary**

**secure monitor call (SMC)** An ARM processor special instruction that can be used by the kernel to request services from the TrustZone.

**secure system process** In Windows, the pro- cess representing the fact that the secure kernel is loaded.

**security** The defense of a system from external and internal attacks. Such attacks include viruses and worms, denial-of-service attacks, identity theft, and theft of service.

**security access token** In Windows 10, a token created when a user logs in that contains the user’s security ID, the security IDs of the groups the user belongs to, and a list of special privileges the user has.

**security context** In Windows 10, a characteris- tic, based on a user’s access token, that enables a program run by the user to access what the user is allowed to access.

**security descriptor** In Windows 10, a feature that describes the security attributes of an object.

**security domain** The separation of systems and devices into classes, with each class having similar security needs.

**security ID (SID)** In Windows, a value used to uniquely identify a user or group for security purposes.

**security policy** A document describing the set of things being secured, how they are to be secured, and how users are to behave in matters relating to security.

**security reference monitor (SRM)** A Windows component that checks the effective security token whenever a thread opens a handle to a protected data structure.

**security through obscurity** A security layer in which information is kept private or obscured in the hope that it won’t be discovered and used by attackers; an ineffective security method.

**security token** In Windows, a token associated with each process containing the SIDs of the user and the user’s groups, the user’s privileges, the integrity level of the process, the attributes and claims associated with the user, and any relevant capabilities.

**seek** The operation of changing the current fi le-position pointer.

**seek time** On an HDD, the time it takes the read- write head to position over the desired cylinder.

**semaphore** An integer variable that, apart from initialization, is accessed only through two stan- dard atomic operations: wait() and signal().

**semiconductor memory** The various types of memory constructed from semiconductors.

**sense key** In the SCSI protocol, information in the status register indicating an error.

**separation hypervisor** An experimental system that uses virtualization to partition separate sys- tem components into a chip-level distributed com- puting system.

**sequence number** In networking, a counter assigned to packets to order their assembly after delivery.

**sequential access A fi le-access method in which** contents are read in order, from beginning to end.

**serial-attached SCSI (SAS)** A common type of I/O bus.

**server** In general, any computer, no matter the size, that provides resources to other computers.

**server subject** In Windows 10 security, a process implemented as a protected server that uses the security context of the client when acting on the client’s behalf.

**server system** A system providing services to other computers (e.g., a web server).

**server-message-block (SMB)** The Windows pro- tocol for sending I/O requests over a network; a version was published as the common internet fi le system (CIFS).

**service** A software entity running on one or more machines and providing a particular type of func- tion to calling clients. In Android, an application component with no user interface; it runs in the background while executing long-running opera- tions or performing work for remote processes.

**service control manager (SCM)** In Windows 7, the component that manages services associated with plug-and-play devices.

**service-trigger** A mechanism in Windows 7 that allows plug-and-play device insertion to launch a service.

**session** In networking, a complete round of com- munication, frequently beginning with a login and ending with a logoff to terminate communications.

**session hijacking** The interception of a commu- nication.

**session key** The TLS symmetric key, used for a web communication session, exchanged via asym- metric cryptography.

**SHA-1** An algorithm for creating a hash (a small, fi xed-size block of data calculated from a larger data set, used to determine if a message has been changed).  

**Glossary G-33**

**shared libraries** Libraries that can be loaded into memory once and used by many processes; used in systems that support dynamic linking.

**shared lock A fi le lock similar to a reader lock** in that several processes can obtain the lock concurrently.

**shared memory** In interprocess communication, a section of memory shared by multiple processes and used for message passing.

**shared system interconnect** A bus connecting CPUs to memory in such a way that all CPUs can access all system memory; the basis for NUMA systems.

**shared-memory model** An interprocess com- munication method in which multiple processes share memory and use that memory for message passing.

**shares** A basis for making scheduling decisions. The fair-share scheduling class uses CPU shares instead of priorities to allocate CPU time.

**shell** One of the command interpreters on a sys- tem with multiple command interpreters to choose from.

**shell script A fi le containing a set series of com-** mands (similar to a batch fi le) that are specifi c to the shell being used.

**shortest-job-fi rst (SJF) A scheduling algorithm** that associates with each thread the length of the thread’s next CPU burst and schedules the shortest fi rst.

**shortest-remaining-time-fi rst (SJRF) A schedul-** ing algorithm that gives priority to the thread with the shortest remaining time until completion.

**shortest-seek-time-fi rst (SSTF) algorithm An** HDD I/O scheduling algorithm that sorts requests by the amount of seek time required to accomplish the request; the shortest time has the highest priority.

**shoulder surfi ng Attempting to learn a pass-** word or other secret information by watching the target user at the keyboard.

**siblings** In a tree data structure, child nodes of the same parent.

**Siemens Jailhouse** An example of a partitioning hypervisor.

**signal** In UNIX and other operating systems, a means used to notify a process that an event has occurred.

**signature** In intrusion detection, a pattern of behavior associated with an attack.

**simple subject** In Windows 10 security, a sub- ject that manages a user-initiated program’s permissions.

**simultaneous multithreading (SMT)** The situa- tion in which, in a CPU with multiple cores, each core supports multiple hardware threads.

**single indirect block** In UFS, a block contain- ing pointers to direct blocks, which point to data blocks.

**single instruction multiple data (SIMD)** A form of parallelism in which multiple compute elements perform the same single instruction operating on multiple data points.

**single step** A CPU mode in which a trap is exe- cuted by the CPU after every instruction (to allow examination of the system state after every instruc- tion); useful in debugging.

**single-threaded** A process or program that has only one thread of control (and so executes on only one core at a time).

**single-user mode** A system boot state providing limited services and designed to enable the system admin to repair system problems and debug system startup.

**Siri** The Apple voice-recognition system.

**sketch** An Arduino program.

**slab** A section of memory made up of one or more contiguous pages; used in slab allocation.

**slab allocation** A memory allocation method in which a slab of memory is allocated and split into chunks that hold objects of a given size. As the objects are freed, the chunks can coalesce into larger chunks, eliminating fragmentation.

**Slackware** An early but still widely used Linux distribution.

**slim reader-write lock (SRW)** A type of lock in modern Windows OS that favors neither readers nor writers.

**small computer-systems interface (SCSI)** One type of interface between a system and its storage (SCSI). See also ATA and SATA.

**snapshot In fi le systems, a read-only view of** a fi le system at a particular point in time; later changes do not affect the snapshot view.

**sniff** In network communication, to capture information by recording data as it is transmitted.

**sniffi ng An attack in which the attacker moni-** tors network traffi c to obtain useful information.

**social engineering** A practice in which an attacker tricks someone into performing some task for the attacker (such as sending the attacker confi - dential information).

**socket** An endpoint for communication. An interface for network I/O.  

**G-34** **Glossary**

**soft affi nity An operating system’s policy of** attempting to keep a process running on the same processor but not guaranteeing that it will do so.

**soft error** An error that is recoverable by retrying the operation.

**soft real-time systems** Systems that provide no guarantee as to when a critical real-time thread will be scheduled; they guarantee only that the thread will be given preference over noncritical threads

**Software as a Service (SaaS)** A type of comput- ing in which one or more applications (such as word processors or spreadsheets) are available as a service via the Internet.

**software engineering A fi eld of study and a career** involving writing software (i.e., programming.)

**software interrupt** A software-generated inter- rupt; also called a trap. The interrupt can be caused either by an error (e.g., division by zero or invalid memory access) or by a specifi c request from a user program that an operating-system service be performed.

**software objects** The software components that make up a computer or device (fi les, programs, semaphores, etc.).

**software transactional memory (STM)** Transac- tional memory implemented exclusively in soft- ware; no special hardware is needed.

**Solaris** A UNIX derivative that is the main oper- ating system of Sun Microsystems (now owned by Oracle Corporation). There is an active open source version called Illumos.

**Solaris ZFS An advanced fi le system, fi rst** included as part of Solaris.

**solid-state disk** A disk-drive-like storage device that uses fl ash-memory-based nonvolatile memory.

**source fi le A fi le containing the source code of a** program.

**space sharing** A feature of APFS in which storage is treated as a pool and space is shared among the fi le systems created in that pool (much like ZFS).

**SPARC** A proprietary RISC CPU created by Sun Microsystems and now owned by Oracle Corpora- tion. There is an active open source version called OpenSPARC.

**sparse** In memory management, a term describ- ing a page table that has noncontiguous, scattered entries. A sparse address space has many holes.

**spinlock** A locking mechanism that continuously uses the CPU while waiting for access to the lock.

**split-screen** Running multiple foreground pro- cesses (e.g., on an iPad) but splitting the screen among the processes.

**spoof The imitation of a legitimate identifi er** (such as an IP address) by an illegitimate user or system.

**spool** A buffer that holds output for a device (such as a printer) that cannot accept interleaved data streams.

**springboard** The iOS touch-screen interface.

**spyware** A Trojan horse variation in which the installed malware gathers information about a person or organization.

**stack** A sequentially ordered data structure that uses the last-in, fi rst-out (LIFO) principle for add- ing and removing items; the last item placed onto a stack is the fi rst item removed.

**stack algorithm** A class of page-replacement algorithms that do not suffer from Belady’s anomaly.

**stack inspection** In Java, a protection procedure in which a calling sequence is checked to ensure that some caller in the sequence has been granted access to the resource called.

**stack section** The section of process memory that contains the stack; it contains activation records and other temporary data.

**stall** A CPU state occurring when the CPU is waiting for data from main memory and must delay execution.

**starvation** The situation in which a process or thread waits indefi nitely within a semaphore. Also, a scheduling risk in which a thread that is ready to run is never put onto the CPU due to the scheduling algorithm; it is starved for CPU time.

**state** The condition of a process, including its current activity as well as its associated memory and disk contents.

**state information In remote fi le systems, the** set of information pertaining to connections and ongoing fi le operations (e.g., which fi les are open).

**state restore** Copying a process’s context from its saved location to the CPU registers in preparation for continuing the process’s execution.

**state save** Copying a process’s context to save its state in order to pause its execution in preparation for putting another process on the CPU.

**stateless In remote fi le systems, a protocol in** which state need not be maintained for proper operation.

**static linking** Linking in which system libraries are treated like other object modules and com- bined by the loader into a binary program image.

**status register** A device I/O register in which status is indicated.  

**Glossary G-35**

**storage-area network (SAN)** A local-area storage network allowing multiple computers to connect to one or more storage devices.

**stream cipher** A cipher that encrypts or decrypts a stream of bits or bytes (rather than a block).

**stream head** The interface between STREAMS and user processes.

**stream modules** In STREAMS, modules of func- tionality loadable into a STREAM.

**STREAMS** A UNIX I/O feature allowing the dynamic assembly of pipelines of driver code.

**stub** A small, temporary place-holder function replaced by the full function once its expected behavior is known.

**subject** In Windows 10 security, an entity used to track and manage user permissions.

**subsystem** A subset of an operating system responsible for a specifi c function (e.g., memory management).

**SunOS** The predecessor of Solaris by Sun Microsystems Inc.

**superblock** The UFS volume control block.

**superblock object** The VFS representation of the entire fi le system.

**supervisor mode** A CPU mode in which all instructions are enabled. The kernel runs in this mode. See also user mode.

**SuSE** A popular Linux distribution.

**suspend** In virtualization, to freeze a guest operating system and its applications to pause execution.

**swap map** In Linux swap-space management, a part of the data structure tracking swap-space use.

**swap space** Secondary storage backing-store space used to store pages that are paged out of memory.

**swapped** Moved between main memory and a backing store. A process may be swapped out to free main memory temporarily and then swapped back in to continue execution.

**swapping** Moving a process between main memory and a backing store. A process may be swapped out to free main memory temporarily and then swapped back in to continue execution.

**swap-space management** The low-level operating- system task of managing space on secondary stor- age for use in swapping and paging.

**symmetric clustering** A situation in which two or more hosts are running applications and are monitoring each other.

**symmetric encryption algorithm** A cryptogra- phy algorithm in which the same keys are used to encrypt and decrypt the message or data.

**symmetric multiprocessing (SMP)** Multipro- cessing in which each processor performs all tasks, including operating-system tasks and user pro- cesses. Also, a multiprocessor scheduling method in which each processor is self-scheduling and may run kernel threads or user-level threads.

**synchronous** In interprocess communication, a mode of communication in which the sending process is blocked until the message is received by the receiving process or by a mailbox and the receiver blocks until a message is available. In I/O, a request that does not return until the I/O completes.

**synchronous threading** Threading in which a parent thread creating one or more child threads waits for them to terminate before it resumes.

**synchronous writes** Writes that are stored in the order in which they were issued, are not buffered, and have requesting threads wait for the writes to complete before continuing.

**system administrators** Computer users that con- fi gure, monitor, and manage systems.

**system build** Creation of an operating-system build and confi guration for a specifi c computer site.

**system call** Software-triggered interrupt allow- ing a process to request a kernel service.

**system call** The primary interface between processes and the operating system, providing a means to invoke services made available by the operating system.

**system-call fi ltering An operating-system facil-** ity to limit which system calls can be executed by a process.

**system daemon** A service that is provided out- side the kernel by system programs that are loaded into memory at boot time and run continuously.

**system disk** A storage device that has a boot par- tition and can store an operating system and other information for booting the computer.

**system integrity protection (SIP)** A feature of macOS 10.11 and later versions that uses extended fi le attributes to mark system fi les as restricted so that even the root user cannot tamper with them.

**system mode** A CPU mode in which all instruc- tions are enabled. The kernel runs in this mode. See also user mode.

**system process** A service that is provided out- side the kernel by system programs that are loaded into memory at boot time and run continuously. In  

**G-36** **Glossary**

Windows, a process that serves as the container of all internal kernel worker threads and other sys- tem threads created by drivers for polling, house- keeping, and other background work.

**system program** A program associated with the operating system but not necessarily part of the kernel.

**system resource-allocation graph** A directed graph for precise description of deadlocks.

**system restore point** In Windows, a copy of the system hives taken before any signifi cant change is made to system confi guration.

**system service** A collection of applications included with or added to an operating system to provide services beyond those provided by the kernel.

**system utility** A collection of applications included with or added to an operating system to provide services beyond what are provided by the kernel.

**system-call fi rewall A fi rewall within a com-** puter that limits the system calls a process can trigger.

**system-call interface** An interface that serves as the link to system calls made available by the operating system and that is called by processes to invoke system calls.

**system-contention scope (SCS)** A thread- scheduling method in which kernel-level threads are scheduled onto a CPU regardless of which pro- cess they are associated with (and thus contend with all other threads on the system for CPU time).

**system-development time** The time during which an operating system is developed, before it is made available in fi nal “release” form.

**system-wide open-fi le table A kernel in-memory** data structure containing a copy of the FCB of each open fi le, as well as other information.

**target latency** In the Completely Fair Scheduler, a confi gurable variable which is the interval of time during which every runnable task should run at least once.

**targeted latency** An interval of time during which every runnable thread should run at least once.

**task control block** A per-process kernel data structure containing many pieces of information associated with the process.

**task parallelism** A computing method that dis- tributes tasks (threads) across multiple comput- ing cores, with each task is performing a unique operation.

**task** A process, a thread activity, or, generally, a unit of computation on a computer.

**templating** In virtualization, using one standard virtual-machine image as a source for multiple vir- tual machines.

**terabyte (TB)** 1,024^4 bytes.

**terminal concentrator** A type of front-end pro- cessor for terminals.

**tertiary storage** A type of storage that is slower and cheaper than main memory or secondary stor- age; frequently magnetic tape or optical disk.

**text fi le A type of fi le containing text (alphanu-** meric characters).

**text section** The executable code of a program or process.

**thin client** A limited computer (terminal) used for web-based computing.

**third extended fi le system (ext3) In Linux, a cur-** rent version of the extended fi le system; the suc- cessor to ext2.

**thrashing** Paging memory at a high rate. A sys- tem thrashes when there is insuffi cient physical memory to meet virtual memory demand.

**thread** A process control structure that is an execution location. A process with a single thread executes only one task at a time, while a multi- threaded process can execute a task per thread.

**thread cancellation** Termination of a thread before it has completed.

**thread dump** In Java, a snapshot of the state of all threads in an application; a useful debugging tool for deadlocks.

**thread library** A programming library that pro- vides programmers with an API for creating and managing threads.

**thread pool** A number of threads created at pro- cess startup and placed in a pool, where they sit and wait for work.

**thread-environment block (TEB)** In Win32, a user-mode threads data structure that contains numerous per-thread fi elds.

**thread-local storage (TLS)** Data available only to a given thread.

**threat** The potential for a security violation.

**throughput** Generally, the amount of work done over time. In scheduling, the number of threads completed per unit time.

**tightly coupled systems** Systems with two or more processors in close communication, sharing the computer bus and sometimes the clock, mem- ory, and peripheral devices.  

**Glossary G-37**

**time quantum** A small unit of time used by scheduling algorithms as a basis for determining when to preempt a thread from the CPU to allow another to run.

**time sharing** A practice in which the CPU exe- cutes multiple jobs by switching among them, but the switches occur so frequently that the users can interact with the processes.

**time slice** A small unit of time used by scheduling algorithms as a basis for determining when to pre- empt a thread from the CPU to allow another to run.

**timer** A hardware component that can be set to interrupt the computer after a specifi ed period.

**timestamp counter (TSC)** In Windows Vista, a counter that tracks execution time.

**TLB miss** A translation look-aside buffer lookup that fails to provide the address translation because it is not in the TLB.

**TLB reach** The amount of memory addressable by the translation look-aside buffer.

**TLB walk** The steps involved in walking through page-table structures to locate the needed transla- tion and then copying that result into the TLB.

**touch screen** A touch-sensitive screen used as a computer input device.

**touch-screen interface** A user interface in which touching a screen allows the user to interact with the computer.

**trace tapes** A tool used in the evaluation of scheduling algorithms. Thread details are cap- tured on real systems, and various algorithms are analyzed to determine their effectiveness.

**track** On an HDD platter, the medium that is under the read-write head during a rotation of the platter.

**transaction** Generally, the execution of a set of steps that make up one activity. In log-based transaction-oriented fi le systems, a set of opera- tions completed as part of a request (e.g., “write this block to that fi le”).

**transactional memory** A type of memory sup- porting memory transactions.

**transfer rate The rate at which data fl ows.**

**translation granules** Features of ARM v8 CPUs that defi ne page sizes and regions.

**translation look-aside buffer (TLB)** A small, fast-lookup hardware cache used in paged mem- ory address translation to provide fast access to a subset of memory addresses.

**translation table base register** ARM v8 CPU reg- ister pointing to the level 0 (outer) page table for the current thread.

**transmission control protocol/Internet protocol (TCP/IP)** The most common network protocol; it provides the fundamental architecture of the Internet.

**transparent** In distributed computing, a term describing the automatic sharing of resources so that users do not know if a resource is local or remote.

**transport driver interface (TDI)** In Windows networking, an interface that supports connect- based and connectionless transports on top of the transport layer.

**transport layer security (TLS)** A cryptographic protocol that enables two computers to communi- cate securely; the standard protocol by which web browsers communicate to web servers.

**trap** A software interrupt. The interrupt can be caused either by an error (e.g., division by zero or invalid memory access) or by a specifi c request from a user program that an operating-system ser- vice be performed.

**trap door** A back-door daemon left behind after a successful attack to allow continued access by the attacker.

**trap-and-emulate** In virtualization, a method used to implement virtualization on systems lack- ing hardware support (such as CPU instructions) for virtualization; any action that would cause the guest to call the operating system is intercepted, and the result is emulated.

**tree** A data structure that can be used to repre- sent data hierarchically; data values in a tree struc- ture are linked through parent–child relationships.

**triple DES A modifi cation of DES that uses the** same algorithm three times and uses two or three keys to make the encryption more diffi cult to break.

**triple indirect block** In UFS, a block containing pointers to double indirect blocks, which point to single indirect blocks, which point to data blocks.

**Trojan horse** A program that acts in a clandes- tine or malicious manner rather than simply per- forming its stated function.

**TrustZone (TZ)** ARM processor implementation of the most secure protection ring.

**tunnel** In computer communication, a container of communications within another type of com- munication (e.g., a VPN that allows web traffi c).

**turnstile** A Solaris scheduling feature using a queue structure containing threads blocked on a lock.

**two-factor authentication** Authentication based on two separate sources of data (e.g., a brain provid- ing a password and a fi nger providing a fi ngerprint).  

**G-38** **Glossary**

**type 0 hypervisor** A hardware-based virtual- ization solution that provides support for virtual machine creation and management via fi rmware (e.g., IBM LPARs and Oracle LDOMs).

**type 1 hypervisor** Operating-system-like soft- ware built to provide virtualization (e.g., VMware ESX, Joyent SmartOS and Citrix Xenserver).

**type 2 hypervisor** An application that runs on standard operating systems but provides virtual machine management features to guest operating systems (e.g., VMware workstation and fusion, and Oracle Virtualbox)

**type safety** In Java, a feature that ensures that classes cannot treat integers as pointers, write past the end of an array, or otherwise access memory in arbitrary ways.

**unbounded buffer** A buffer with no practical limit on its memory size.

**uncontended** A term describing a lock that is available when a thread attempts to acquire it.

**unifi ed buffer cache In fi le I/O, a cache used for** both memory-mapped I/O and direct fi le I/O.

**unifi ed extensible fi rmware interface (UEFI) The** modern replacement for BIOS containing a com- plete boot manager.

**unifi ed virtual memory In fi le I/O, the use of** page caching for all types of I/O (explicit fi le sys- tem I/O and page fault I/O).

**uniform memory access (UMA)** Access to all main memory by all processors, without performance dif- ferences based on CPU or memory location.

**uniform naming convention (UNC)** A name format that includes the system and its resources (e.g.m \\\\server\_name\\share\_name\\x\\y\\z).

**unikernels** Specialized machine images that contain both an operating system and applications for effi cient execution and increased security.

**universal serial bus (USB)** A type of I/O bus.

**universal Windows platform (UWP)** Windows 10 architecture that provides a common app plat- form for all devices that run it, including mobile devices.

**UNIX fi le system (UFS) An early UNIX fi le sys-** tems; uses inodes for FCB.

**UnixBSD** A UNIX derivative based on work done at the University of California at Berkeley (UCB).

**unnamed semaphore** A POSIX scheduling con- struct that can only be used by threads in the same process.

**unstructured data Data that are not in a fi xed** format (like a database record) but rather are free- form (like a twitter.com tweet).

**upcall** A threading method in which the kernel sends a signal to a process thread to communicate an event.

**upcall handler** A function in a process that han- dles upcalls.

**USB drive** Nonvolatile memory in the form of a device that plugs into a USB port.

**user** The human using a computer, or the identi- fi cation of the human to the computer.

**user account** In Windows 10, an account belong- ing to a user (rather than a system account used by the computer).

**user authentication The identifi cation of a user** of a computer.

**user datagram protocol (UDP)** A communica- tions protocol layered on IP that is connectionless, is low latency, and does not guarantee delivery.

**user experience layer** In the layered macOS and iOS operating system design, the layer that defi nes the software interface that allows users to interact with computing devices.

**user fi le directory (UFD) In two-level directory** implementation, a per-user directory of fi les.

**user identifi er (user ID) (UID) A unique numer-** ical user identifi er.

**user interface (UI)** A method by which a user interacts with a computer.

**user mode** A CPU mode for executing user pro- cesses in which some instructions are limited or not allowed. See also kernel mode.

**user programs** User-level programs, as opposed to system programs.

**user rights** Permissions granted to users.

**user thread** A thread running in user mode.

**user-defi ned signal handler The signal handler** created by a process to provide non-default signal handling.

**user-initiated** In the Grand Central Dispatch Apple OS scheduler, the scheduling class repre- senting tasks that interact with the user but need longer processing times than user-interactive tasks.

**user-interactive** In the Grand Central Dispatch Apple OS scheduler, the scheduling class repre- senting tasks that interact with the user.

**user-mode driver framework (UMDF)** A frame- work in Windows to facilitate the writing of user- mode device drivers.

**user-mode scheduling (UMS)** A Microsoft Win- dows 7 feature that allows applications to create and manage threads independently of the kernel. This feature supports task-based parallelism by  

**Glossary G-39**

decomposing processes into tasks, which are then scheduled on available CPUs; it is used on AMD64 systems.

**user-mode thread (UT)** In Windows, the state of a thread when it is running in user mode.

**utility** In the Grand Central Dispatch Apple OS scheduler, the scheduling class representing tasks that require a longer time to complete but do not demand immediate results.

**utility storage** An inServ feature in which stor- age space can be increased as needed.

**valid-invalid** A page-table bit indicating whether a page-table entry points to a page within the logical address space of that process.

**variable-partition** A simple memory-allocation scheme in which each partition of memory con- tains exactly one process.

**vectored I/O** An I/O method in which multiple sources or destinations of I/O are specifi ed in one command structure.

**version control system** Software that manages software distributions by allowing contributors to “push” changes into a repository and “pull” a ver- sion of the software source-code tree to a system (e.g., for compilation).

**victim frame** In virtual memory, the frame selected by the page-replacement algorithm to be replaced.

**view** In Windows, an address range mapped in shared memory. Also, the second step in memory- mapping a fi le, allowing a process to access the fi le contents.

**virtual address** An address generated by the CPU; must be translated to a physical address before it is used.

**virtual address control block (VACB)** The data structure in Windows that represents a cache block in the unifi ed I/O cache.

**virtual address descriptor (VAD)** In Windows, a per-process descriptor of a virtual address range, kept in a tree data structure.

**virtual address space** The logical view of how a process is stored in memory.

**virtual CPU (VCPU)** In virtualization, a virtual- ized host CPU available to allocate to a guest oper- ating system by the virtual machine manager.

**virtual fi le system (VFS) The fi le-system imple-** mentation layer responsible for separating fi le- system-generic operations and their implementation and representing a fi le throughout a network

**virtual machine (VM)** The abstraction of hard- ware allowing a virtual computer to execute on a

physical computer. Multiple virtual machines can run on a single physical machine (and each can have a different operating system).

**virtual machine control structures (VMCSs)** Hardware features provided by CPUs that support virtualization to track guest state.

**virtual machine manager (VMM)** The computer function that manages the virtual machine; also called a hypervisor.

**virtual machine sprawl** The situation in which there are so many virtual machines on a system that their use, history, and state become confusing and diffi cult to track; caused by the ease of creating virtual machines.

**virtual memory** A technique that allows the exe- cution of a process that is not completely in memory. Also, separation of computer memory address space from physical into logical, allowing easier programming and larger name space.

**virtual memory fork** The vfork() system call, which forks a child process, suspends the parent, and lets the child share the parent’s address space for both read and write operations (changes are visible to the parent).

**virtual private network (VPN)** An encrypted tunnel between two systems, commonly using IPSec, allowing secure remote access.

**virtual run time** A Linux scheduling aspect that records how long each task has run by maintaining the virtual run time of each task.

**virtual trust level (VTL)** A Windows 10 virtual- ization feature using Hyper-V to add more secure system modes.

**virtualization** A technology for abstracting the hardware of a single computer into several differ- ent execution environments, thereby creating the illusion that each environment is running on its own private computer.

**virtual-to-physical (V-to-P)** In virtualization, the conversion of a virtual machine guest to a physical system’s operating system and applications.

**virus** A fragment of code embedded in a legiti- mate program that, when executed, can replicate itself; may modify or destroy fi les and cause sys- tem crashes and program malfunctions.

**virus dropper** The part of a virus that inserts the virus into the system.

**virus signature** A pattern that can be used to identify a virus within a system.

**VMware** Virtualization software company.

**VMware Workstation** A popular commercial type 2 hypervisor for x86 Windows systems.  

**G-40** **Glossary**

**vnode The virtual fi le system fi le representa-** tion structure, similar to the FCB for local fi les but applied to remote fi les.

**voice recognition** A computer interface based on spoken commands, which the computer parses and turns into actions.

**volatile** Describes storage whose content can be lost in a power outage or similar event.

**volatile storage** Storage whose content can be lost in a power outage or similar event.

**volume** A container of storage; frequently, a device containing a mountable fi le system (including a fi le containing an image of the contents of a device).

**volume control block** A per-volume storage block containing data describing the volume.

**von Neumann architecture** The structure of most computers, in which both process instructions and data are stored in the same main memory.

**VT-x** Intel x86 CPU virtualization-supporting instructions.

**wait queue** In process scheduling, a queue hold- ing processes waiting for an event to occur before they need to be put on CPU.

**wait set** In Java, a set of threads, each waiting for a condition that will allow it to continue.

**wait-for graph** In deadlock detection, a variant of the resource-allocation graph with resource nodes removed; indicates a deadlock if the graph contains a cycle

**wear leveling** In nonvolatile memory, the effort to select all NAND cells over time as write targets to avoid premature media failure due to wearing out a subset of cells.

**wide-area network (WAN)** A network that links buildings, cities, or countries.

**WiFi** Wireless networking, consisting of devices and protocols that allow devices to attach to a net- work via radio waves rather than cables.

**Win32 API** The fundamental interface to the capabilities of Windows.

**Windows 10** A release of Microsoft Windows from 2009.

**Windows group policy** In Windows, a policy providing centralized management and confi gura- tion of operating systems, applications, and user settings in an Active Directory environment.

**Windows Subsystem for Linux (WSL)** A Win- dows 10 component allowing native Linux appli- cations (ELF binaries) to run on Windows.

**Windows XP** A widely popular version of Mic- rosoft Windows released in 2001.

**Winsock** The Windows socket API (similar to BSD sockets) for network communications.

**wired down** A term describing a TLB entry that is locked into the TLB and not replaceable by the usual replacement algorithm.

**wireless network** A communication network composed of radio signals rather than physical wires.

**witness A lock order verifi er.**

**word** A unit made up of one or more bytes. For example, a computer that has 64-bit registers and 64-bit memory addressing typically has 64-bit (8-byte) words.

**working set** The set of pages in the most recent page references.

**working-set maximum** The maximum number of frames allowed to a process in Windows.

**working-set minimum** The minimum number of frames guaranteed to a process in Windows.

**working-set model** A model of memory access based on tracking the set of most recently accessed pages.

**working-set window** A limited set of most recently accessed pages (a “window” view of the entire set of accessed pages).

**workstation** A powerful personal computer (PC) for engineering and other demanding workloads.

**world rights A category of fi le access rights.**

**World Wide Web (WWW)** The Internet; a worldwide system of interconnected computer networks.

**WORM** Write-once, read-many-times storage.

**worm** A program that spreads malware between computers without intervention from humans.

**worst-fi t In memory allocation, selecting the** largest hole available.

**write amplifi cation The creation of I/O requests** not by applications but by NVM devices doing garbage collection and space management, poten- tially impacting the devices’ write performance.

**write pointer The location in a fi le to which the** next write will occur.

**write-anywhere fi le layout (WAFL) The fi le sys-** tem that is the heart of the NetApp, Inc., storage appliances.

**write-back caching** In caching, a policy whereby data are fi rst written to the cache; later, the cache writes the change to the master copy of the data.

**write-on-close policy** In caching, a policy whereby writes reside in the cache until the fi le is  

**Glossary G-41**

closed and are only then written back to the master copy of the data.

**write-through policy** In caching, a policy whereby writes are not cached but are written through the cache to the master copy of the data.

**x86-64** A class of 64-bit CPUs running an iden- tical instruction set; the most common CPUs in desktop and server systems.

**Xen** Virtualization software company.

**XML fi rewall A fi rewall that examines and limits** XML traffi c.

**Xtratum** An example of a partitioning hypervisor.

**yellow pages** A distributed naming service that provides username, password, hostname, and printer information to a set of computers.

**zero-day attacks** Attacks that have not been seen before and therefore cannot be detected via their signatures.

**zero-fi ll-on-demand The writing of zeros into** a page before it is made available to a process (to keep any old data from being available to the process).

**ZFS Oracle fi le system, created by Sun Microsys-** tems, with modern algorithms and features and few limits on fi le and device sizes.

**zombie** A process that has terminated but whose parent has not yet called wait() to collect its state and accounting information.

**zombie systems** Compromised systems that are being used by attackers without the owners’ knowledge.

**zones** In application containment, a virtual layer between the operating system and a process in which the application runs, limiting its normal access to system resources. In Linux, the four regions of kernel memory.