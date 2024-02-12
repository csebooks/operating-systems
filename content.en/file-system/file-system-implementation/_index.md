---
title: 'File -System Implementation'
weight: 2
---


# File -System Implementation

As we saw in Chapter 13, the file system provides the mechanism for on- line storage and access to file contents, including data and programs. File systems usually reside permanently on secondary storage, which is designed to hold a large amount of data. This chapter is primarily concerned with issues surrounding file storage and access on the most common secondary-storage media, hard disk drives and nonvolatile memory devices. We explore ways to structure file use, to allocate storage space, to recover freed space, to track the locations of data, and to interface other parts of the operating system to secondary storage. Performance issues are considered throughout the chapter.

A given general-purpose operating system provides several file systems. Additionally,many operating systems allow administrators or users to add file systems.Why somany? File systems vary inmany respects, including features, performance, reliability, and design goals, and different file systemsmay serve different purposes. For example, a temporary file system is used for fast storage and retrieval of nonpersistent files, while the default secondary storage file system (such as Linux ext4) sacrifices performance for reliability and features. As we’ve seen throughout this study of operating systems, there are plenty of choices and variations, making thorough coverage a challenge. In this chapter, we concentrate on the common denominators.

**CHAPTER OBJECTIVES**

• Describe the details of implementing local file systems and directory struc- tures.

• Discuss block allocation and free-block algorithms and trade-offs.

• Explore file system efficiency and performance issues.

• Look at recovery from file system failures.

• Describe the WAFL file system as a concrete example.

