---
title: 'Mass-Storage Structure'
weight: 1
---


# Mass-Storage Structure

In this chapter, we discuss how mass storage—the nonvolatile storage sys- tem of a computer—is structured. The main mass-storage system in modern computers is secondary storage, which is usually provided by hard disk drives (HDD) and nonvolatilememory (NVM) devices. Some systems also have slower, larger, tertiary storage, generally consisting of magnetic tape, optical disks, or even cloud storage.

Because the most common and important storage devices in modern com- puter systems are HDDs and NVM devices, the bulk of this chapter is devoted to discussing these two types of storage. We first describe their physical struc- ture.We then consider scheduling algorithms, which schedule the order of I/Os to maximize performance. Next, we discuss device formatting and manage- ment of boot blocks, damaged blocks, and swap space. Finally, we examine the structure of RAID systems.

There are many types of mass storage, and we use the general term **_non- volatile storage_** (NVS) or talk about storage “drives” when the discussion includes all types. Particular devices, such as HDDs and NVM devices, are specified as appropriate.

**CHAPTER OBJECTIVES**

• Describe the physical structures of various secondary storage devices and the effect of a device’s structure on its uses.

• Explain the performance characteristics of mass-storage devices.

• Evaluate I/O scheduling algorithms.

• Discuss operating-system services provided for mass storage, including RAID.

