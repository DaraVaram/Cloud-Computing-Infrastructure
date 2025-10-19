# Lecture 3: Physical Layer
This lecture focuses on the physical layer: 

![PhysicalLayer](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/PhysicalLayer.png)

## Overview
The physical layer comprises of physical compute, storage, and network resources. It is basically everything that physically needs to exist "somewhere" for the cloud to be able to operate. 
- The compute systems **execute** the software of **both** the **providers** and the **consumers**.
- The storage systems store the **business** and **application** data.
- The network systems work to connect compute with each other and with the storage systems.
    - They are also responsible to connect multiple clouds to each other (if they exist), and data centers to each other as well.
 
In a data center: There are power generators assigned to different zones (within the data center) in case of a black-out in one of the zones. This is to avoid down-time. 

![OverviewPhysicalLayer](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/PhysicalLayerOverview.png)


## Introduction to Compute Systems
A computing platform (HW, FW, SW) that runs platform and application SW. 
- Executes both the providers' and the consumers' software

Compute systems are provided to consumers in 2 ways: 
1. **Shared hosting**: Multiple consumers sharing the same compute systems (accessing the A100s in AUS, through CSE or through AWS). This is an example of multi-tenancy.
2. **Dedicated hosting**: Individual consumers have dedicated compute systems (You provision a VM just for your own use through Azure. Only you have an SSH key into that machine. Not everyone).

Typically, providers use compute virtualization and offer compute systems in the form of VMs. 

_Knowing the characteristics of an environment (for example, the physical layer) is a must._ This is a note from Dr. Raafat.

 ## Key Components of a Compute System

 | Component | Description | 
 | ------ | ------ | 
 | Processor | An integrated circuit (IC) that executes SW programs by performing arithemetic, logical and I/O operations. |
 | Random Access Memory (RAM) | A volatile data storage device containing the programs for execution and the data used by the processor. |
 | Read-Only Memory (ROM) | A semi-conductor memory containing boot, power management, and other device-specific FW. |
 | Motherboard | Holds the processor, RAM, ROM, network and I/O ports and other integrated components, such as GPU, and network interface cards (NIC). |
 | Chipset | A collection of microchips on the motherboard to manage specific functions, such as processor access to RAM and and two peripheral ports. |

 ## Types of Compute Systems
 1. Rack-mounted: Needs extra config. and integration steps
 2. Blade: Commonly used, it's water cooled, modular, meaning that it's easy to expand and integrate.
- It can expand the pool of servers by inserting blade servers into the chasis. What is the chasis? It supplies power, if it loses power, the whole thing is cooked.

### Rack-mounted Compute Systems
Designed to be fixed on a frame called a "rack." 
- Standardized enclosure with mounting slots for vertically stacking compute systems. Like literally vertically stacking them in a column.
- Simplifies network cabling, consolidates network equipment and reduces floor space use.
- Administrators may use a console that's mounted directly onto the rack to manage the compute system.

### Blade Compute Systems
Comprises an electronic circuit board with **only the core processing components**.
- Multiple blades are housed in a Blade chasis
    - The chasis provides integrated power supply, cooling, networking and management.
- Blades are interconnected via a high-speed bus.
- Modular design, which increases the compute system density and scalability

## Storage Systems
A storage system is the repository for saving and retrieving electronic data. Providers offer the storage capacity along with the compute system, or as a service. 
    - Storage as a service enables data backup and long-term data retention. 

Cloud storage provides **massive scalability** and **rapid elasticity** of storage resources. Typically, a provider uses virtualization to create **storage pools** that can be **shared** by multiple consumers.

If the compute dies, one can provision another without losing any data. We can also scale up the storage without impact on compute or the data itself. This is the idea of **de-coupling**.

### Types of Storage Devices

| Type | Description | 
| ----- | ----- | 
| Magnetic Disk Drive | <ul><li>Stores data on a circular disk with a ferromagnetic coating</li> <li>Provides random read / write access </li> <li> Most popular storage device with large storage capacity</li></ul> This is basically an HDD
| Solid-State (Flash) Drive | <ul><li>Stores data on a semi-conductor-based memory </li> <li> Very low latency per I/O, low power requirements, and very high throughput </li></ul>


## RAID
Redundant Array of Independent Disks (RAID): A storage technology in which data is written in **blocks** across multiple disk drives that are combined into a **logical unit** called a RAID group.

- This **improves the storage system performance** by serving by mulitple drives simultaneously.
- Provides **data protection** against drive **failures**.
- What are the three key techniques used for RAID:
    - Striping
    - Mirroring
    - Parity
 
| Technique | Description | Figure | 
| ------ | ------ | ------- | 
| Striping | A RAID technique to spread data across multiple drives in order to use the drives in parallel. <ul><li>Gain in performance, but if one drive dies, then the data on it is gone. There's **no redundancy**.</li></ul> | <img src="https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/RAID.png" width="8000"/> |
|  Mirroring | A RAID technique to store the same data simultaneously on two different drives, yielding two copies of the data. <ul><li> This allows for redundancy, but it's logically more expensive. You'll need more storage. </li></ul>| <img src="https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/RAIDMirroring.png" width="8000"/> |
| Parity | A RAID technique to protect **striped** data from drive failure by performing a mathematical operation on individual strips and storing the result on a portion of the RAID group. <ul><li>If the parity fails, it's easy to recover from it **if the other drives are alive**.</li></ul>| <img src="https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/RAIDParity.png" width="8000"/>




### Common RAID levels
| RAID Level | Description | 
| ----- | ------ |
| RAID 0 | **Striped** set with **no fault toelrance**. |
| RAID 1 | Disk **mirroring**. |
| RAID 1+0 | Nested RAID, **striping and mirroring**. |
| RAID 3 | Striped set with **parallel axis** and a **dedicated parity disk**.  |
| RAID 5 | Striped set with **independent disk access** and **distributed parity**. |
| RAID 6 | Striped set with **independent disk access** and **dual distributed parity**. |

**Apparently, this is an exam question.**
