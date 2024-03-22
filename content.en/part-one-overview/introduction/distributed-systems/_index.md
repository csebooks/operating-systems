---
title: 'Distributed Systems'
weight: 8
references:
    videos:
        - youtube:NYBKXzl5bWU
        - youtube:rYK-kTBUrK4
    links:
        - https://www.geeksforgeeks.org/what-is-a-distributed-system/
        - https://www.confluent.io/learn/distributed-systems/
    books:
        - b1:
            title: Distributed Algorithms 
            url:  https://www.google.co.in/books/edition/Distributed_Algorithms/QqNWAgAAQBAJ?hl=en&gbpv=0
        - b2:
            title: Designing Distributed Systems
            url: https://www.google.co.in/books/edition/Designing_Distributed_Systems/5hJNDwAAQBAJ?hl=en&gbpv=0
---

# Distributed Systems

A distributed system is a collection of physically separate, possibly heteroge- neous computer systems that are networked to provide users with access to the various resources that the system maintains. Access to a shared resource increases computation speed, functionality, data availability, and reliability. Some operating systems generalize network access as a form of file access, with the details of networking contained in the network interface’s device driver.  
Others make users specifically invoke network functions. Generally, systems contain a mix of the two modes—for example FTP and NFS. The protocols that create a distributed system can greatly affect that system’s utility and popularity.

A **network**, in the simplest terms, is a communication path between two or more systems. Distributed systems depend on networking for their functional- ity. Networks vary by the protocols used, the distances between nodes, and the transport media. **TCP/IP** is the most common network protocol, and it provides the fundamental architecture of the Internet. Most operating systems support TCP/IP, including all general-purpose ones. Some systems support proprietary protocols to suit their needs. For an operating system, it is necessary only that a network protocol have an interface device—a network adapter, for example —with a device driver to manage it, as well as software to handle data. These concepts are discussed throughout this book.

Networks are characterized based on the distances between their nodes. A **local-area network** (**LAN**) connects computers within a room, a building, or a campus. A **wide-area network** (**WAN**) usually links buildings, cities, or countries. Aglobal companymay have aWAN to connect its offices worldwide, for example. These networks may run one protocol or several protocols. The continuing advent of new technologies brings about new forms of networks. For example, a **metropolitan-area network** (**MAN**) could link buildings within a city. BlueTooth and 802.11 devices use wireless technology to communicate over a distance of several feet, in essence creating a **personal-area network** (**PAN**) between a phone and a headset or a smartphone and adesktop computer.

Themedia to carry networks are equally varied. They include copperwires, fiber strands, andwireless transmissions between satellites,microwave dishes, and radios. When computing devices are connected to cellular phones, they create a network. Even very short-range infrared communication can be used for networking. At a rudimentary level, whenever computers communicate, they use or create a network. These networks also vary in their performance and reliability.

Some operating systems have taken the concept of networks and dis- tributed systems further than the notion of providing network connectivity. A **network operating system** is an operating system that provides features such as file sharing across the network, along with a communication scheme that allows different processes on different computers to exchange messages. A computer running a network operating system acts autonomously from all other computers on the network, although it is aware of the network and is able to communicate with other networked computers. A distributed operat- ing system provides a less autonomous environment. The different computers communicate closely enough to provide the illusion that only a single operat- ing system controls the network.We cover computer networks and distributed systems in Chapter 19.