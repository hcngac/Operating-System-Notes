# Operating System Notes - Introduction

This set of notes is about the concepts and implementation details of operating system. This set of notes mainly cope with the course COMP3111 in HKUST. The main sections are:

1. Operating System Structure
2. Process Concept
3. Threads Concept
4. Process Scheduling
5. Synchronization
6. Deadlocks

**Computer System Structure**

1. Hardware
2. Operating System
3. System and Application Programs
4. Users

**Computer Startup**

Bootstrap program stored in firmware \(ROM or EEPROM\)

* Initializes all aspect of the system
* Loads operating system kernel
* Load system processes or system daemon

UNIX's first process is "init"

**Computer Organization and Operation**

Concurrent execution of CPUs and device controller, completing for the memory access

Each device controller has local buffer

CPU moves data across memory and local buffers

I/O is from device to local buffer

Device controller generate interrupt when operation finished

**Interrupt**

Interrupt transfer control to interrupt service routine, through interrupt vector

Interrupt vector contains addresses of different interrupt service routine for different interrupts

**Trap/Exception**

Software-generated interrupt

**Direct Memory Access**

Device controller can access main memory directly without CPU intervention

**Storage Hierarchy**

1. Cache
2. Main Memory
3. Secondary Storage
4. Magnetic Disks
5. Optical Disks
6. Magnetic Tapes

**Caching**

Improve CPU performance by reducing memory access time

**Main Function of OS**

Resource Allocator

User Convenience

**OS Structure**

Multiprogramming \(job scheduling\)

Timeshare Multitasking

**Dual-Mode**

Kernel mode for privileged instruction

User mode for normal execution

Determined by mode bit

**Timer**

Generate interrupt over time

Ensure OS can get control over CPU back

**Multiprocessor System**

Two processors share same computer bus, main memory, devices

Advantages:

1. Increased Throughput
2. Economy of Scale
3. Increased Reliability

**Asymmetric Multiprocessing**

One master CPU distribute jobs to slave CPUs

**Symmetric Multiprocessing \(SMP\)**

Each CPU ahs own set of registers and cache, sharing the same main memory

**Uniform Memory Access \(UMA\)**

Memory access time of CPUs are same

**Non-uniform Memory Access \(NUMA\)**

Memory access time of CPUs can be different

**Multicore**

Multiple computing core in a single chip

Faster in terms of communication and less power consumption

**Clustered System**

Compute nodes are loosely coupled

Share storage via Storage-area Network

Provide high-availability

Asymmetric Clustering: One machine on hot-standby mode

Symmetric Clustering: Multiple nodes running applications, monitoring each other

High-performance computing: parallelization of running of some applications

Distributed Lock Manager \(DLM\): Deal with synchronization problem in clustering

**Protection**

Access control of users and processes to resources

**Security**

Defend against internal or external attacks

**Computing Environment**

1. Traditional
2. Mobile
3. Distributed
4. Client-Server
5. Peer-to-Peer
6. Virtualization
7. Cloud Computing
8. Real-Time Embedded System

**Open Source OS**

1. Darwin \(kernel of MacOS\)
2. Linux
3. BSD UNIX
4. Sun Solaris



