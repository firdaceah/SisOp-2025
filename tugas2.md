# Introduction Operating System

Name: Firda Rahayu

NRP: 3124521002

Class: 1 TI A

## Practice Exercises

### 1.1 What are the three main purposes of an operating system?

Answer:

The three main purposes are:

- To provide an environment for a computer user to execute programs
  on computer hardware in a convenient and efficient manner.
- To allocate the separate resources of the computer as needed to
  solve the problem given. The allocation process should be as fair
  and efficient as possible.
- As a control program it serves two major functions: (1) supervision
  of the execution of user programs to prevent errors and improper use
  of the computer, and (2) management of the operation and control
  of I/O devices.

### 1.2 We have stressed the need for an operating system to make efficient use of the computing hardware. When is it appropriate for the operating system to forsake this principle and to “waste” resources? Why is such a system not really wasteful?

Answer:

Single-user systems should maximize use of the system for the user. A
GUI might “waste” CPU cycles, but it optimizes the user’s interaction
with the system.

### 1.3 What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?

Answer:

The main difficulty is keeping the operating system within the fixed time
constraints of a real-time system. If the system does not complete a task
in a certain time frame, it may cause a breakdown of the entire system it
is running. Therefore when writing an operating system for a real-time
system, the writer must be sure that his scheduling schemes don’t allow
response time to exceed the time constraint.

### 1.4 Keeping in mind the various definitions of operating system, consider whether the operating system should include applications such as web browsers and mail programs. Argue both that it should and that it should not, and support your answers.

Answer:

An argument in favor of including popular applications with the
operating system is that if the application is embedded within the
operating system, it is likely to be better able to take advantage of
features in the kernel and therefore have performance advantages
over an application that runs outside of the kernel. Arguments against
embedding applications within the operating system typically dominate
however:

1. the applications are applications - and not part of an
   operating system
2. any performance benefits of running within the
   kernel are offset by security vulnerabilities
3. it leads to a bloated
   operating system.

### 1.5 How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security)?

Answer:

The distinction between kernel mode and user mode provides a rudimentary form of protection in the following manner. Certain instructions
could be executed only when the CPU is in kernel mode. Similarly, hardware devices could be accessed only when the program is executing in
kernel mode. Control over when interrupts could be enabled or disabled
is also possible only when the CPU is in kernel mode. Consequently, the
CPU has very limited capability when executing in user mode, thereby
enforcing protection of critical resources.

### 1.6 Which of the following instructions should be privileged?

- a. Set value of timer.
- b. Read the clock.
- c. Clear memory.
- d. Issue a trap instruction.
- e. Turn off interrupts.
- f. Modify entries in device-status table.
- g. Switch from user to kernel mode.
- h. Access I/O device.

Answer:

The following operations need to be privileged: Set value of timer, clear
memory, turn off interrupts, modify entries in device-status table, access
I/O device. The rest can be performed in user mode.

### 1.7 Some early computers protected the operating system by placing it in a memory partition that could not be modified by either the user job or the operating system itself. Describe two difficulties that you think could arise with such a scheme.

Answer:

The data required by the operating system (passwords, access controls,
accounting information, and so on) would have to be stored in or passed
through unprotected memory and thus be accessible to unauthorized
users.

### 1.8 Some CPUs provide for more than two modes of operation. What are two possible uses of these multiple modes?

Answer:

Although most systems only distinguish between user and kernel
modes, some CPUs have supported multiple modes. Multiple modes
could be used to provide a finer-grained security policy. For example,
rather than distinguishing between just user and kernel mode, you
could distinguish between different types of user mode. Perhaps users
belonging to the same group could execute each other’s code. The
machine would go into a specified mode when one of these users was
running code. When the machine was in this mode, a member of the
group could run code belonging to anyone else in the group.

Another possibility would be to provide different distinctions within
kernel code. For example, a specific mode could allow USB device drivers
to run. This would mean that USB devices could be serviced without
having to switch to kernel mode, thereby essentially allowing USB device
drivers to run in a quasi-user/kernel mode.

### 1.9 Timers could be used to compute the current time. Provide a short description of how this could be accomplished.

Answer:

A program could use the following approach to compute the current
time using timer interrupts. The program could set a timer for some
time in the future and go to sleep. When it is awakened by the interrupt,
it could update its local state, which it is using to keep track of the
number of interrupts it has received thus far. It could then repeat this
process of continually setting timer interrupts and updating its local
state when the interrupts are actually raised.

### 1.10 Give two reasons why caches are useful. What problems do they solve? What problems do they cause? If a cache can be made as large as the device for which it is caching (for instance, a cache as large as a disk), why not make it that large and eliminate the device?

Answer:

Caches are useful when two or more components need to exchange
data, and the components perform transfers at differing speeds. Caches
solve the transfer problem by providing a buffer of intermediate speed
between the components. If the fast device finds the data it needs in the
cache, it need not wait for the slower device. The data in the cache must
be kept consistent with the data in the components. If a component has
a data value change, and the datum is also in the cache, the cache must
also be updated. This is especially a problem on multiprocessor systems
where more than one process may be accessing a datum. A component
may be eliminated by an equal-sized cache, but only if: (a) the cache
and the component have equivalent state-saving capacity (that is, if the
component retains its data when electricity is removed, the cache must
retain data as well), and (b) the cache is affordable, because faster storage
tends to be more expensive.

### 1.11 Distinguish between the client–server and peer-to-peer models of distributed systems.

Answer:

The client-server model firmly distinguishes the roles of the client and
server. Under this model, the client requests services that are provided
by the server. The peer-to-peer model doesn’t have such strict roles. In
fact, all nodes in the system are considered peers and thus may act as
either clients or servers—or both. A node may request a service from
another peer, or the node may in fact provide such a service to other
peers in the system.

For example, let’s consider a system of nodes that share cooking
recipes. Under the client-server model, all recipes are stored with the
server. If a client wishes to access a recipe, it must request the recipe from
the specified server. Using the peer-to-peer model, a peer node could ask
other peer nodes for the specified recipe. The node (or perhaps nodes)
with the requested recipe could provide it to the requesting node. Notice
how each peer may act as both a client (it may request recipes) and as a
server (it may provide recipes).

## Chapter 1 Exercises

### 1.12 How do clustered systems differ from multiprocessor systems? What is required for two machines belonging to a cluster to cooperate to provide a highly available service?

Answer:

Clustered systems are typically constructed by combining multiple computers into a single system to perform a computational task distributed across the cluster. Multiprocessor systems on the other hand could be a single physical entity comprising of multiple CPUs. A clustered system is less tightly coupled than a multiprocessor system. Clustered systems communicate using messages, while processors in a multiprocessor system could communicate using shared memory. In order for two machines to provide a highly available service, the state on the two machines should be replicated and should be consistently updated. When one of the machines fails, the other could then take over the functionality of the failed machine.

### 1.13 Consider a computing cluster consisting of two nodes running a database. Describe two ways in which the cluster software can manage access to the data on the disk. Discuss the benefits and disadvantages of each.

Answer:

Consider the following two alternatives: asymmetric clustering and parallel clustering. With asymmetric clustering, one host runs the database application with the other host simply monitoring it. If the server fails, the monitoring host becomes the active server. This is appropriate for providing redundancy. However, it does not utilize the potential processing power of both hosts. With parallel clustering, the database application can run in parallel on both hosts. The difficulty in implementing parallel clusters is providing some form of distributed locking mechanism for files on the shared disk.

### 1.14 What is the purpose of interrupts? How does an interrupt differ from a trap? Can traps be generated intentionally by a user program? If so, for what purpose?

Answer:

An interrupt is a hardware-generated change of flow within the system. An interrupt handler issummoned to deal with the cause of the interrupt; control is then returned to the interrupted context and instruction. A trap is a software-generated interrupt. An interrupt can be used to signal the completion of an I/O to obviate the need for device polling. A trap can be used to call operating system routines or to catch arithmetic errors.

### 1.15 Explain how the Linux kernel variables HZ and jiffies can be used to determine the number of seconds the system has been running since it was booted.

Answer:

In Linux, HZ defines the number of timer ticks per second, and jiffies is a counter that increments with each tick. To calculate uptime, you divide jiffies by HZ. For example, if HZ is 100 and jiffies is 500,000 means the system has been running for 5000 sec since boot

### 1.16 Direct memory access is used for high-speed I/O devices in order to avoid increasing the CPU’s execution load.

- a. How does the CPU interface with the device to coordinate the transfer?
- b. How does the CPU know when the memory operations are complete?
- c. The CPU is allowed to execute other programs while the DMA controller is transferring data. Does this process interfere with the execution of the user programs? If so, describe what formsof interference are caused.

Answer:

- a. The CPU sets up the Direct Memory Access (DMA) transfer by giving the DMA controller details like memory addresses, transfer size, and the I/O device involved. Once configured, the DMA controller handles the transfer independently.
- b. When the transfer is complete, the DMA controller sends an interrupt to the CPU, letting it know that the operation has finished.
- c. Yes, DMA can interfere with user programs because it accesses the memory bus, temporarily blocking the CPU from accessing memory. This can cause minor delays in execution, especially if multiple DMA transfers happen at once. However, the performance gain from offloading data transfers usually outweighs the small interruptions.

### 1.17 Some computer systems do not provide a privileged mode of operation in hardware. Is it possible to construct a secure operating system for these computer systems? Give arguments both that it is and that it is not possible.

Answer:

Possible: A secure OS can still be built using software-based protection mechanisms like virtualization, sandboxing, and access control policies. The OS can enforce strict execution rules and limit what user programs can do, reducing security risks.

Not possible: Without hardware-enforced privilege levels, user programs could directly access system resources, making it easier for malware or faulty programs to corrupt memory, modify system settings, or interfere with critical operations. Software-based protections alone may not be strong enough to prevent all security threats.

### 1.18 Many SMP systems have different levels of caches; one level is local to each processing core, and another level is shared among all processing cores. Why are caching systems designed this way?

Answer:

The different levels are based on access speed as well as size. In general, the closer the cache is to the CPU, the faster the access. However, faster caches are typically more costly. Therefore, smaller and faster caches are placed local to each CPU, and shared caches that are larger, yet slower, are shared among several different processors.

### 1.19 Rank the following storage systems from slowest to fastest:

- a. Hard-disk drives
- b. Registers
- c. Optical disk
- d. Main memory
- e. Nonvolatile memory
- f. Magnetic tapes
- g. Cache

Answer:

1. Magnetic tapes
2. Optical disk
3. Hard-disk drives
4. Nonvolatile memory
5. Main memory
6. Cache
7. Registers

### 1.20 Consider an SMP system similar to the one shown in Figure 1.8. Illustrate with an example how data residing in memory could in fact have a different value in each of the local caches.

Answer:

Say processor 1 reads data A with value 5 from main memory into its local cache. Similarly, processor 2 reads data A into its local cache as well. Processor 1 then updates A to 10. However, since A resides in processor1’s local cache, the update only occurs there and not in the local cache for processor 2.

### 1.21 Discuss, with examples, how the problem of maintaining coherence of cached data manifests itself in the following processing environments:

- a. Single-processor systems
- b. Multiprocessor systems
- c. Distributed systems

Answer:

- a. In single-processor systems, the memory needs to be updated when a processor issues updates to cached values. These updates can be performed immediately or in a lazy manner.
- b. In a multiprocessor system, different processors might be caching the same memory location in its local caches. When updates are made, the other cached locations need to be invalidated or updated.
- c. In distributed systems, consistency of cached memory values is not an issue. However, consistency problems might arise when a client caches file data.

### 1.22 Describe a mechanism for enforcing memory protection in order to prevent a program from modifying the memory associated with other programs.

Answer:

The processor could keep track of what locations are associated with each process and limit access to locations that are outside of a program’s extent. Information regarding the extent of a program’s memory could be maintained by using base and limits registers and by performing a check for every memory access.

### 1.23 Which network configuration LAN or WAN would best suit the following environments?

- a. A campus student union
- b. Several campus locations across a statewide university system
- c. A neighborhood

Answer:

- a. LAN, Covers a small area with high-speed connectivity.
- b. WAN, Connects multiple distant locations.
- c. LAN, If within a small area, like a community network.

### 1.24 Describe some of the challenges of designing operating systems for mobile devices compared with designing operating systems for traditional PCs.

Answer:

The greatest challenges in designing mobile operating systems include:

- Less storage capacity means the operating system must manage memory carefully.
- The operating system must also manage power consumption carefully
- Less processing power plus fewer processors mean the operating system must carefully allocate processors to applications.

### 1.25 What are some advantages of peer-to-peer systems over client-server systems?

Answer:

Peer-to-peer is useful because services are distributed across a collection of peers, rather than having a single, centralized server. Peer-to-peer provides fault tolerance and redundancy. Also, because peers constantly migrate, they can provide a level of security over a server that always exists at a known location on the Internet. Peer-to-peer systems can also potentially provide higher network bandwidth because you can collectively use all the bandwidth of peers, rather than the single bandwidth that is available to a single server.

### 1.26 Describe some distributed applications that would be appropriate for a peer-to-peer system.

Answer:

- File-sharing networks, Users share files directly without a central server.
- Blockchain and cryptocurrencies, Transactions are verified by multiple peers instead of a central authority.
- Video conferencing, Calls can be routed directly between users.
- Online gaming, Some multiplayer games use P2P to reduce server load and latency.

### 1.27 Identify several advantages and several disadvantages of open-source operating systems. Indentify the types of people who would find each aspect to be an advantage or a disadvantage

Answer:

Open-source operating systems have the advantages of having many people working on them, many people debugging them, ease of access and distribution, and rapid update cycles. Further, for students and programmers there is certainly an advantage to being able to view and modify the source code. Typically, open-source operating systems are free for some forms of use, usually just requiring payment for support services. Commercial operating system companies usually do not like the competition that open-source operating systems bring because these features are difficult to compete against. Some open-source operating systems do not offer paid support programs. Some companies avoid open-source projects because they need paid support, so that they have some entity to hold accountable if there is a problem or they need help fixing an issue. Finally, some complain that a lack of discipline in the coding of open-source operating systems means that backward-compatibility is lacking making upgrades difficult, and that the frequent release cycle exacerbates these issues by forcing users to upgrade frequently.
