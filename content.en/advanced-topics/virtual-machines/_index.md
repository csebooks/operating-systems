---
title: 'Virtual Machines'
weight: 1
---

# Virtual Machines

The term **_virtualization_** has many meanings, and aspects of virtualization permeate all aspects of computing. Virtual machines are one instance of this trend. Generally, with a virtual machine, guest operating systems and applica- tions run in an environment that appears to them to be native hardware and that behaves toward them as native hardware would but that also protects, manages, and limits them.

This chapter delves into the uses, features, and implementation of virtual machines. Virtual machines can be implemented in several ways, and this chapter describes these options. One option is to add virtual machine support to the kernel. Because that implementationmethod is themost pertinent to this book, we explore itmost fully. Additionally, hardware features provided by the CPU and even by I/O devices can support virtual machine implementation, so we discuss how those features are used by the appropriate kernel modules.

**CHAPTER OBJECTIVES**

• Explore the history and benefits of virtual machines.

• Discuss the various virtual machine technologies.

• Describe the methods used to implement virtualization.

• Identify the most common hardware features that support virtualization and explain how they are used by operating-system modules.

• Discuss current virtualization research areas.

