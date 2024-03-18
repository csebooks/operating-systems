---
title: 'Building and Booting an Operating System'
weight: 9
references:
    videos:
        - youtube:wD0PrF3fGSY
        - youtube:bDsTwHIqs2g
    links:
        - https://www.javatpoint.com/booting-in-operating-system
        - https://www.geeksforgeeks.org/booting-and-dual-booting-of-operating-system/
    books:
        - b1:
            title: Hands-on Booting
            url: https://www.google.co.in/books/edition/Hands_on_Booting/lJjuDwAAQBAJ?hl=en&gbpv=0
        - b2:
            title: Live Linux CDs
            url: https://www.google.co.in/books/edition/Live_Linux_CDs/2S3eUgb39C8C?hl=en&gbpv=0
---

# Building and Booting an Operating System

It is possible to design, code, and implement an operating system specifically for one specific machine configuration. More commonly, however, operating systems are designed to run on any of a class of machines with a variety of peripheral configurations.

### Operating-System Generation

Most commonly, a computer system,when purchased, has an operating system already installed. For example, youmay purchase a new laptop withWindows or macOS preinstalled. But suppose you wish to replace the preinstalled oper- ating system or add additional operating systems. Or suppose you purchase a computer without an operating system. In these latter situations, you have a few options for placing the appropriate operating system on the computer and configuring it for use.

If you are generating (or building) an operating system from scratch, you must follow these steps:

**1\.** Write the operating system source code (or obtain previously written source code).

**2\.** Configure the operating system for the system on which it will run.

**3\.** Compile the operating system.

**4\.** Install the operating system.

**5\.** Boot the computer and its new operating system.

Configuring the system involves specifying which features will be included, and this varies by operating system. Typically, parameters describing how the system is configured is stored in a configuration file of some type, and once this file is created, it can be used in several ways.

At one extreme, a system administrator can use it to modify a copy of the operating-system source code. Then the operating system is completely compiled (known as a **system build**). Data declarations, initializations, and constants, along with compilation, produce an output-object version of the operating system that is tailored to the system described in the configuration file.

At a slightly less tailored level, the system description can lead to the selec- tion of precompiled objectmodules from an existing library. Thesemodules are linked together to form the generated operating system. This process allows the library to contain the device drivers for all supported I/O devices, but only those needed are selected and linked into the operating system. Because the system is not recompiled, system generation is faster, but the resulting system may be overly general andmay not support different hardware configurations.

At the other extreme, it is possible to construct a system that is completely modular. Here, selection occurs at execution time rather than at compile or link time. System generation involves simply setting the parameters that describe the system configuration.  



The major differences among these approaches are the size and generality of the generated system and the ease of modifying it as the hardware configu- ration changes. For embedded systems, it is not uncommon to adopt the first approach and create an operating system for a specific, static hardware config- uration. However, most modern operating systems that support desktop and laptop computers aswell asmobile devices have adopted the second approach. That is, the operating system is still generated for a specific hardware config- uration, but the use of techniques such as loadable kernel modules provides modular support for dynamic changes to the system.

We now illusrate how to build a Linux system from scratch, where it is typically necessary to perform the following steps:

**1\.** Download the Linux source code from http://www.kernel.org.

**2\.** Configure the kernel using the “make menuconfig” command. This step generates the .config configuration file.

**3\.** Compile themain kernel using the “make” command. The make command compiles the kernel based on the configuration parameters identified in the .config file, producing the file vmlinuz, which is the kernel image.

**4\.** Compile the kernel modules using the “make modules” command. Just as with compiling the kernel, module compilation depends on the con- figuration parameters specified in the .config file.

**5\.** Use the command “make modules install” to install the kernel mod- ules into vmlinuz.

**6\.** Install the new kernel on the system by entering the “make install” command.

When the system reboots, it will begin running this new operating system. Alternatively, it is possible to modify an existing system by installing a

Linux virtual machine. This will allow the host operating system (such as Windows or macOS) to run Linux. (We introduced virtualization in Section 1.7 and cover the topic more fully in Chapter 18.)

There are a few options for installing Linux as a virtual machine. One alternative is to build a virtual machine from scratch. This option is similar to building a Linux system from scratch; however, the operating system does not need to be compiled. Another approach is to use a Linux virtual machine appliance, which is an operating system that has already been built and con- figured. This option simply requires downloading the appliance and installing it using virtualization software such as VirtualBox or VMware. For example, to build the operating system used in the virtual machine provided with this text, the authors did the following:

**1\.** Downloaded the Ubuntu ISO image from https://www.ubuntu.com/

**2\.** Instructed the virtual machine software VirtualBox to use the ISO as the bootable medium and booted the virtual machine

**3\.** Answered the installation questions and then installed and booted the operating system as a virtual machine  



### System Boot

After an operating system is generated, it must be made available for use by the hardware. But how does the hardware know where the kernel is or how to load that kernel? The process of starting a computer by loading the kernel is known as **booting** the system. On most systems, the boot process proceeds as follows:

**1\.** A small piece of code known as the **bootstrap program** or **boot loader** locates the kernel.

**2\.** The kernel is loaded into memory and started.

**3\.** The kernel initializes hardware.

**4\.** The root file system is mounted.

In this section, we briefly describe the boot process in more detail. Some computer systems use amultistage boot process:When the computer

is first powered on, a small boot loader located in nonvolatile firmware known as **BIOS** is run. This initial boot loader usually does nothing more than load a second boot loader, which is located at a fixed disk location called the **boot block**. The program stored in the boot block may be sophisticated enough to load the entire operating system into memory and begin its execution. More typically, it is simple code (as it must fit in a single disk block) and knows only the address on disk and the length of the remainder of the bootstrap program.

Many recent computer systems have replaced the BIOS-based boot process with **UEFI** (UnifiedExtensible Firmware Interface). UEFI has several advantages over BIOS, including better support for 64-bit systems and larger disks. Perhaps the greatest advantage is that UEFI is a single, complete boot manager and therefore is faster than the multistage BIOS boot process.

Whether booting from BIOS or UEFI, the bootstrap program can perform a variety of tasks. In addition to loading the file containing the kernel program into memory, it also runs diagnostics to determine the state of the machine —for example, inspecting memory and the CPUand discovering devices. If the diagnostics pass, the program can continue with the booting steps. The bootstrap can also initialize all aspects of the system, from CPU registers to device controllers and the contents of main memory. Sooner or later, it starts the operating system and mounts the root file system. It is only at this point is the system said to be **running**.

**GRUB** is an open-source bootstrap program for Linux and UNIX systems. Boot parameters for the system are set in a GRUB configuration file, which is loaded at startup. GRUB is flexible and allows changes to be made at boot time, including modifying kernel parameters and even selecting among different kernels that can be booted. As an example, the following are kernel parameters from the special Linux file /proc/cmdline, which is used at boot time:

BOOT IMAGE=/boot/vmlinuz-4.4.0-59-generic root=UUID=5f2e2232-4e47-4fe8-ae94-45ea749a5c92

BOOT IMAGE is the name of the kernel image to be loaded into memory, and root specifies a unique identifier of the root file system.  



To save space as well as decrease boot time, the Linux kernel image is a compressed file that is extracted after it is loaded intomemory. During the boot process, the boot loader typically creates a temporary RAM file system, known as initramfs. This file system contains necessary drivers and kernel modules that must be installed to support the **_real_** root file system (which is not in main memory). Once the kernel has started and the necessary drivers are installed, the kernel switches the root file system from the temporary RAM location to the appropriate root file system location. Finally, Linux creates the systemd process, the initial process in the system, and then starts other services (for example, a web server and/or database). Ultimately, the system will present the user with a login prompt. In Section 11.5.2, we describe the boot process for Windows.

It is worthwhile to note that the booting mechanism is not independent from the boot loader. Therefore, there are specific versions of the GRUB boot loader for BIOS and UEFI, and the firmware must know as well which specific bootloader is to be used.

The boot process for mobile systems is slightly different from that for traditional PCs. For example, although its kernel is Linux-based, Android does not use GRUB and instead leaves it up to vendors to provide boot loaders. The most common Android boot loader is LK (for “little kernel”). Android systems use the same compressed kernel image as Linux, as well as an initial RAM file system. However, whereas Linux discards the initramfs once all necessary drivers have been loaded, Androidmaintains initramfs as the root file system for the device. Once the kernel has been loaded and the root file system mounted, Android starts the init process and creates a number of services before displaying the home screen.

Finally, boot loaders for most operating systems—including Windows, Linux, and macOS, as well as both iOS and Android—provide booting into **recovery mode** or **single-user mode** for diagnosing hardware issues, fixing corrupt file systems, and even reinstalling the operating system. In addition to hardware failures, computer systems can suffer from software errors and poor operating-system performance, which we consider in the following section.