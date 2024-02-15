---
title: 'Final Thoughts on Distributed File Systems'
weight: 9
---

## Final Thoughts on Distributed File Systems

The line between DFS client–server and cluster-based architectures is blurring. The NFS Version 4.1 specification includes a protocol for a parallel version of NFS called pNFS, but as of this writing, adoption is slow.  

GFS, HDFS, and other large-scale DFSs export a non-POSIX API, so they cannot transparently map directories to regular user machines as NFS and OpenAFS do. Rather, for systems to access these DFSs, they need client code installed. However, other software layers are rapidly being developed to allow NFS to be mounted on top of such DFSs. This is attractive, as it would take advantage of the scalability and other advantages of cluster-based DFSs while still allowing native operating-system utilities and users to access files directly on the DFS.

As of this writing, the open-source HDFS NFS Gateway supports NFS Ver- sion 3 and works as a proxy between HDFS and the NFS server software. Since HDFS currently does not support random writes, the HDFS NFS Gateway also does not support this capability. That means a file must be deleted and recreated from scratch even if only one byte is changed. Commercial organi- zations and researchers are addressing this problem and building stackable frameworks that allow stacking of a DFS, parallel computing modules (such as MapReduce), distributed databases, and exported file volumes through NFS.

One other type of file system, less complex than a cluster-based DFS but more complex than a client–server DFS, is a **clustered file system** (**CFS**) or **parallel file system** (**PFS**). A CFS typically runs over a LAN. These systems are important and widely used and thus deserve mention here, though we do not cover them in detail. Common CFSs include **Lustre** and **GPFS**, although there are many others. A CFS essentially treats **_N_** systems storing data and **_Y_** systems accessing that data as a single client–server instance. Whereas NFS, for example, has per-server naming, and two separate NFS servers generally provide two different naming schemes, a CFS knits various storage contents on various storage devices on various servers into a uniform, transparent name space. GPFS has its own file-system structure, but Lustre uses existing file systems such as ZFS for file storage and management. To learn more, see http://lustre.org.

Distributed file systems are in common use today, providing file sharing within LANs, within cluster environments, and across WANs. The complexity of implementing such a system should not be underestimated, especially con- sidering that the DFS must be operating-system independent for widespread adoption and must provide availability and good performance in the presence of long distances, commodity hardware failures, sometimes frail networking, and ever-increasing users and workloads.

## Summary

• A distributed system is a collection of processors that do not share mem- ory or a clock. Instead, each processor has its own local memory, and the processors communicate with one another through various communica- tion lines, such as high-speed buses and the Internet. The processors in a distributed system vary in size and function.

• Adistributed system provides the user with access to all system resources. Access to a shared resource can be provided by data migration, compu- tation migration, or process migration. The access can be specified by the user or implicitly supplied by the operating system and applications.  

• Protocol stacks, as specified by network layering models, add information to a message to ensure that it reaches its destination.

• Anaming system (such as DNS)must be used to translate from a host name to a network address, and another protocol (such as ARP) may be needed to translate the network number to a network device address (an Ethernet address, for instance).

• If systems are located on separate networks, routers are needed to pass packets from source network to destination network.

• The transport protocols UDP and TCP direct packets to waiting processes through the use of unique system-wide port numbers. In addition, the TCP protocol allows the flow of packets to become a reliable, connection- oriented byte stream.

• There are many challenges to overcome for a distributed system to work correctly. Issues include naming of nodes and processes in the system, fault tolerance, error recovery, and scalability. Scalability issues include handling increased load, being fault tolerant, and using efficient storage schemes, including the possibility of compression and/or deduplication.

• A DFS is a file-service system whose clients, servers, and storage devices are dispersed among the sites of a distributed system. Accordingly, service activity has to be carried out across the network; instead of a single cen- tralized data repository, there are multiple independent storage devices.

• There are two main types of DFS models: the client–server model and the cluster-based model. The client-server model allows transparent file sharing among one or more clients. The cluster-based model distributes the files among one ormore data servers and is built for large-scale parallel data processing.

• Ideally, a DFS should look to its clients like a conventional, centralized file system (although it may not conform exactly to traditional file-system interfaces such as POSIX). Themultiplicity and dispersion of its servers and storage devices should be transparent. A transparent DFS facilitates client mobility by bringing the client’s environment to the site where the client logs in.

• There are several approaches to naming schemes in a DFS. In the sim- plest approach, files are named by some combination of their host name and local name, which guarantees a unique system-wide name. Another approach, popularized by NFS, provides a means to attach remote directo- ries to local directories, thus giving the appearance of a coherent directory tree.

• Requests to access a remote file are usually handled by two complemen- tary methods. With remote service, requests for accesses are delivered to the server. The server machine performs the accesses, and the results are forwarded back to the client. With caching, if the data needed to satisfy the access request are not already cached, then a copy of the data is brought from the server to the client. Accesses are performed on the cached copy. The problem of keeping the cached copies consistent with the master file is the cache-consistency problem.  


**Practice Exercises**

**19.1** Why would it be a bad idea for routers to pass broadcast packets between networks? What would be the advantages of doing so?

**19.2** Discuss the advantages and disadvantages of caching name transla- tions for computers located in remote domains.

**19.3** What are two formidable problems that designers must solve to imple- ment a network system that has the quality of transparency?

**19.4** To build a robust distributed system, you must know what kinds of failures can occur.

a. List three possible types of failure in a distributed system.

b. Specify which of the entries in your list also are applicable to a centralized system.

**19.5** Is it always crucial to know that the message you have sent has arrived at its destination safely? If your answer is “yes,” explain why. If your answer is “no,” give appropriate examples.

**19.6** A distributed system has two sites, A and B. Consider whether site A can distinguish among the following:

a. B goes down.

b. The link between A and B goes down.

c. B is extremely overloaded, and its response time is 100 times longer than normal.

What implications does your answer have for recovery in distributed systems?

**Further Reading**

\[Peterson and Davie (2012)\] and \[Kurose and Ross (2017)\] provide general overviews of computer networks. The Internet and its protocols are described in \[Comer (2000)\]. Coverage of TCP/IP can be found in \[Fall and Stevens (2011)\] and \[Stevens (1995)\]. UNIX network programming is described thoroughly in \[Steven et al. (2003)\].

Ethernet and WiFi standards and speeds are evolving quickly. Current IEEE 802.3 Ethernet standards can be found at http://standards.ieee.org/about/get/ 802/802.3.html. Current IEEE 802.11 Wireless LAN standards can be found at http://standards.ieee.org/about/get/802/802.11.html.

Sun’s network file system (NFS) is described by \[Callaghan (2000)\]. Infor- mation about OpenAFS is available from http://www.openafs.org.

Information on the Google file system can be found in \[Ghe- mawat et al. (2003)\]. The Google MapReduce method is described in http://research.google.com/archive/mapreduce.html. The Hadoop dis- tributed file system is discussed in \[K. Shvachko and Chansler (2010)\], and the Hadoop framework is discussed in http://hadoop.apache.org/.

To learn more about Lustre, see http://lustre.org.  


**Bibliography**

**\[Callaghan (2000)\]** B. Callaghan, _NFS Illustrated_, Addison-Wesley (2000).

**\[Comer (2000)\]** D. Comer, _Internetworking with TCP/IP, Volume I,_ Fourth Edition, Prentice Hall (2000).

**\[Fall and Stevens (2011)\]** K. Fall and R. Stevens, _TCP/IP Illustrated, Volume 1: The Protocols,_ Second Edition, John Wiley and Sons (2011).

**\[Ghemawat et al. (2003)\]** S. Ghemawat, H. Gobioff, and S.-T. Leung, “The Google File System”, _Proceedings of the ACM Symposium on Operating Systems Principles_ (2003).

**\[K. Shvachko and Chansler (2010)\]** S. R. K. Shvachko, H. Kuang and R. Chansler, “The Hadoop Distributed File System” (2010).

**\[Kurose and Ross (2017)\]** J. Kurose and K. Ross, _Computer Networking—A Top– Down Approach,_ Seventh Edition, Addison-Wesley (2017).

**\[Peterson and Davie (2012)\]** L. L. Peterson and B. S. Davie, _Computer Networks: A Systems Approacm,_ Fifth Edition, Morgan Kaufmann (2012).

**\[Steven et al. (2003)\]** R. Steven, B. Fenner, andA. Rudoff,_Unix Network Program- ming, Volume 1: The Sockets Networking API,_ Third Edition, John Wiley and Sons (2003).

**\[Stevens (1995)\]** R. Stevens, _TCP/IP Illustrated, Volume 2: The Implementation_, Addison-Wesley (1995).  

**Exercises**

**Chapter 19 Exercises**

**19.7** What is the difference between computation migration and process migration? Which is easier to implement, and why?

**19.8** Even though the OSI model of networking specifies seven layers of functionality, most computer systems use fewer layers to implement a network. Why do they use fewer layers? What problems could the use of fewer layers cause?

**19.9** Explainwhy doubling the speed of the systems on an Ethernet segment may result in decreased network performance when the UDP transport protocol is used. What changes could help solve this problem?

**19.10** What are the advantages of using dedicated hardware devices for routers? What are the disadvantages of using these devices compared with using general-purpose computers?

**19.11** Inwhat ways is using a name server better than using static host tables? What problems or complications are associated with name servers? What methods could you use to decrease the amount of traffic name servers generate to satisfy translation requests?

**19.12** Name servers are organized in a hierarchical manner. What is the pur- pose of using a hierarchical organization?

**19.13** The lower layers of the OSI network model provide datagram service, with no delivery guarantees for messages. A transport-layer protocol such as TCP is used to provide reliability. Discuss the advantages and disadvantages of supporting reliable message delivery at the lowest possible layer.

**19.14** Run the program shown in Figure 19.4 and determine the IP addresses of the following host names:

• www.wiley.com

• www.cs.yale.edu

• www.apple.com

• www.westminstercollege.edu

• www.ietf.org

**19.15** A DNS name can map to multiple servers, such as www.google.com. However, if we run the program shown in Figure 19.4, we get only one IP address. Modify the program to display all the server IP addresses instead of just one.

**19.16** The original HTTP protocol used TCP/IP as the underlying network protocol. For each page, graphic, or applet, a separate TCP session was constructed, used, and torn down. Because of the overhead of building and destroying TCP/IP connections, performance problems resulted from this implementation method. Would using UDP rather than TCP be a good alternative?What other changes could you make to improve HTTP performance?

**EX-56**  

**19.17** What are the advantages and the disadvantages of making the com- puter network transparent to the user?

**19.18** What are the benefits of a DFS compared with a file system in a central- ized system?

**19.19** For each of the following workloads, identify whether a cluster-based or a client–server DFS model would handle the workload best. Explain your answers.

• Hosting student files in a university lab.

• Processing data sent by the Hubble telescope.

• Sharing data with multiple devices from a home server.

**19.20** Discuss whether OpenAFS and NFS provide the following: (a) location transparency and (b) location independence.

**19.21** Under what circumstances would a client prefer a location- transparent DFS? Under what circumstances would she prefer a location-independent DFS? Discuss the reasons for these preferences.

**19.22** What aspects of a distributed system would you select for a system running on a totally reliable network?

**19.23** Compare and contrast the techniques of caching disk blocks locally, on a client system, and remotely, on a server.

**19.24** Which scheme would likely result in a greater space saving on a multiuser DFS: file-level deduplication or block-level deduplication? Explain your answer.

**19.25** What types of extra metadata information would need to be stored in a DFS that uses deduplication?

**EX-57**