---
title: 'Virtualization Research'
weight: 8
---

## Virtualization Research

As mentioned earlier, machine virtualization has enjoyed growing popularity in recent years as a means of solving system compatibility problems. Research has expanded to cover many other uses of machine virtualization, including support for microservices running on library operating systems and secure partitioning of resources in embedded systems. Consequently, quite a lot of interesting, active research is underway.

Frequently, in the context of cloud computing, the same application is run on thousands of systems. To better manage those deployments, they can be virtualized. But consider the execution stack in that case—the application on top of a service-rich general-purpose operating system within a virtual machine managed by a hypervisor. Projects like **unikernels**, built on **library operating systems**, aim to improve efficiency and security in these environments. Unikernels are specialized machine images, using one address space, that shrink the attack surface and resource footprint of deployed applications. In essence, they compile the application, the system libraries it calls, and the kernel services it uses into a single binary that runs within a virtual environment (or even on bare metal). While research into changing how operating system kernels, hardware, and applications interact is not new (see https://pdos.csail.mit.edu/6.828/2005/readings/engler95exokernel.pdf,  

for example), cloud computing and virtualization have created renewed interest in the area. See http://unikernel.org for more details.

The virtualization instructions in modern CPUs have given rise to a new branch of virtualization research focusing not onmore efficient use of hardware but rather on better control of processes. Partitioning hypervisors partition the existing machine physical resources amongst guests, thereby fully committing rather than overcommitting machine resources. Partitioning hypervisors can securely extend the features of an existing operating system via functionality in another operating system (run in a separate guest VM domain), running on a subset of machine physical resources. This avoids the tedium of writing an entire operating system from scratch. For example, a Linux system that lacks real-time capabilities for safety- and security-critical tasks can be extendedwith a lightweight real-time operating system running in its own virtual machine. Traditional hypervisors have higher overhead than running native tasks, so a new type of hypervisor is needed.

Each task runs within a virtual machine, but the hypervisor only initializes the system and starts the tasks and is not involved with continuing operation. Each virtualmachine has its own allocated hardware and is free tomanage that hardware without interference from the hypervisor. Because the hypervisor does not interrupt task operations and is not called by the tasks, the tasks can have real-time aspects and can be much more secure.

Within the class of partitioning hypervisors are the **Quest-V**, **eVM**, **Xtratum** and **Siemens Jailhouse** projects. These are **separation hypervisors** (see http://www.csl.sri.com/users/rushby/papers/sosp81.pdf) that use virtualization to partition separate system components into a chip-level distributed system. Secure shared memory channels are then implemented using hardware extended page tables so that separate sandboxed guests can communicate with one another. The targets of these projects are areas such as robotics, self-driving cars, and the Internet of Things. See https://www.cs.bu.edu/richwest/papers/west-tocs16.pdf for more details.

## Summary

• Virtualization is a method for providing a guest with a duplicate of a system’s underlying hardware. Multiple guests can run on a given system, each believing that it is the native operating system and is in full control.

• Virtualization started as a method to allow IBM to segregate users and provide themwith their own execution environments on IBMmainframes. Since then, thanks to improvements in system and CPU performance and innovative software techniques, virtualization has become a common fea- ture in data centers and even on personal computers. Because of its pop- ularity, CPU designers have added features to support virtualization. This snowball effect is likely to continue, with virtualization and its hardware support increasing over time.

• The virtual machine manager, or hypervisor, creates and runs the virtual machine. Type 0 hypervisors are implemented in the hardware and require modifications to the operating system to ensure proper operation. Some  


type 0 hypervisors offer an example of paravirtualization, in which the operating system is aware of virtualization and assists in its execution.

• Type 1 hypervisors provide the environment and features needed to cre- ate, run, and manage guest virtual machines. Each guest includes all of the software typically associated with a full native system, including the operating system, device drivers, applications, user accounts, and so on.

• Type 2 hypervisors are simply applications that run on other operating systems, which do not know that virtualization is taking place. These hypervisors do not have hardware or host support so must perform all virtualization activities in the context of a process.

• Programming-environment virtualization is part of the design of a pro- gramming language. The language specifies a containing application in which programs run, and this application provides services to the pro- grams.

• Emulation is used when a host system has one architecture and the guest was compiled for a different architecture. Every instruction the guest wants to execute must be translated from its instruction set to that of the native hardware. Although this method involves some performance penalty, it is balanced by the usefulness of being able to run old programs on newer, incompatible hardware or run games designed for old consoles on modern hardware.

• Implementing virtualization is challenging, especially when hardware support is minimal. The more features provided by the system, the easier virtualization is to implement and the better the performance of the guests.

• VMMs take advantage of whatever hardware support is available when optimizing CPU scheduling, memory management, and I/O modules to provide guests with optimum resource use while protecting the VMM from the guests and the guests from one another.

• Current research is extending the uses of virtualization. Unikernels aim to increase efficiency and decrease security attack surface by compiling an application, its libraries, and the kernel resources the application needs into one binary with one address space that runs within a virtual machine. Partitioning hypervisors provide secure execution, real-time operation, and other features traditionally only available to applications running on dedicated hardware.

**Further Reading**

The original IBM virtual machine is described in \[Meyer and Seawright (1970)\]. \[Popek and Goldberg (1974)\] established the characteristics that help define VMMs. Methods of implementing virtual machines are discussed in \[Agesen et al. (2010)\].

Intel x86 hardware virtualization support is described in \[Neiger et al. (2006)\]. AMD hardware virtualization support is described in a white paper available at http://developer.amd.com/assets/NPT-WP-1%201-final-TM.pdf.  


Memory management in VMware is described in \[Waldspurger (2002)\]. \[Gordon et al. (2012)\] propose a solution to the problem of I/O overhead in virtualized environments. Some protection challenges and attacks in virtual environments are discussed in \[Wojtczuk and Ruthkowska (2011)\].

For earlywork on alternative kernel designs, see https://pdos.csail.mit.edu /6.828/2005/readings/engler95exokernel.pdf. For more on unikernels, see \[West et al. (2016)\] and http://unikernel.org. Partitioning hypervisors are dis- cussed in http://ethdocs.org/en/latest/introduction/what-is-ethereum.html, and https://lwn.net/Articles/578295 and \[Madhavapeddy et al. (2013)\]. Quest- V, a separation hypervisor, is detailed in http://www.csl.sri.com/users/rushby/ papers/sosp81.pdf and https://www.cs.bu.edu/ richwest/papers/west-tocs16 .pdf.

The open-source**_VirtualBox_**project is available fromhttp://www.virtualbox .org. The source code for LXC is available at https://linuxcontainers.org/lxc/dow nloads.

For more on docker, see https://www.docker.com/what-docker. Informa- tion aboutKubernetes can be found at https://kubernetes.io/docs/concepts/ov erview/what-is-kubernetes.

**Bibliography**

**\[Agesen et al. (2010)\]** O. Agesen, A. Garthwaite, J. Sheldon, and P. Subrah- manyam, “The Evolution of an x86 Virtual Machine Monitor”, _Proceedings of the ACM Symposium on Operating Systems Principles_ (2010), pages 3–18.

**\[Gordon et al. (2012)\]** A. Gordon, N. A. N. Har’El, M. Ben-Yehuda, A. Landau, A. Schuster, andD. Tsafrir, “ELI: Bare-metal Performance for I/OVirtualization”, _Proceedings of the International Conference on Architectural Support for Programming Languages and Operating Systems_ (2012), pages 411–422.

**\[Madhavapeddy et al. (2013)\]** A.Madhavapeddy, R.Mirtier, C. Rotsos, D. Scott, B. Singh, T.Gazagnaire, S. Smith, S.Hand, and J. Crowcroft, “Unikernels: Library Operating Systems for the Cloud” (2013).

**\[Meyer and Seawright (1970)\]** R. A. Meyer and L. H. Seawright, “A Virtual Machine Time-Sharing System”, _IBM Systems Journal_, Volume 9, Number 3 (1970), pages 199–218.

**\[Neiger et al. (2006)\]** G. Neiger, A. Santoni, F. Leung, D. Rodgers, and R. Uhlig, “Intel Virtualization Technology: Hardware Support for Efficient Processor Vir- tualization”, _Intel Technology Journal_, Volume 10, (2006).

**\[Popek and Goldberg (1974)\]** G. J. Popek and R. P. Goldberg, “Formal Require- ments for Virtualizable Third Generation Architectures”, _Communications of the ACM_, Volume 17, Number 7 (1974), pages 412–421.

**\[Waldspurger (2002)\]** C. Waldspurger, “Memory Resource Management in VMware ESX Server”, _Operating Systems Review_, Volume 36, Number 4 (2002), pages 181–194.

**\[West et al. (2016)\]** R. West, Y. Li, E. Missimer, and M. Danish, “A Virtualized Separation Kernel for Mixed Criticality Systems”, Volume 34, (2016).  

## Chapter 18 Virtual Machines

**\[Wojtczuk and Ruthkowska (2011)\]** R. Wojtczuk and J. Ruthkowska, “Follow- ing the White Rabbit: Software Attacks Against Intel VT-d Technology”, _The Invisible Things Lab’s blog_ (2011).  

**Chapter 18 Exercises**

**18.1** Describe the three types of traditional hypervisors.

**18.2** Describe four virtualization-like execution environments, and explain how they differ from “true” virtualization.

**18.3** Describe four benefits of virtualization.

**18.4** Why are VMMs unable to implement trap-and-emulate-based virtual- ization on some CPUs? Lacking the ability to trap and emulate, what method can a VMM use to implement virtualization?

**18.5** What hardware assistance for virtualization can be provided by mod- ern CPUs?

**18.6** Why is live migration possible in virtual environments but much less possible for a native operating system?

**EX-55**  

