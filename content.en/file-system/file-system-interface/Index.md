---
title: 'File -System Interface'
weight: 1
---


# File -System Interface

For most users, the file system is the most visible aspect of a general-purpose operating system. It provides the mechanism for on-line storage of and access to both data and programs of the operating system and all the users of the computer system. The file system consists of two distinct parts: a collection of files, each storing related data, and a directory structure, which organizes and provides information about all the files in the system. Most file systems live on storage devices, which we described in Chapter 11 andwill continue to discuss in the next chapter. In this chapter, we consider the various aspects of files and the major directory structures. We also discuss the semantics of sharing files among multiple processes, users, and computers. Finally, we discuss ways to handle file protection, necessary when we have multiple users and want to control who may access files and how files may be accessed.

**CHAPTER OBJECTIVES**

• Explain the function of file systems.

• Describe the interfaces to file systems.

• Discuss file-system design tradeoffs, including access methods, file shar- ing, file locking, and directory structures.

• Explore file-system protection.


