## 1. What enables a LUN to be presented to an application with more capacity than is physically allocated to it on the storage system?
- Virtual storage provisioning ✅
- Multipathing
- Virtual storage reclamation
- Virtual storage rebalancing

Justification: It can't be any of the others. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md) 

Definition: It enables to present a LUN to an application with more capacity than is physically allocated to it on the storage system.


## 2. Which of the following is/are true about the cloud portal's key functions?
- Interaction with the orchestration layer ✅
- Organization and display of service information and management functions to the user ✅
- It is a tool responsible for managing and controlling the underlying cloud infrastructure and enables provisioning of IT resources for creating cloud services
- Has key resource provisioning techniques

Justification: 
- Key resource provisioning is in the control layer
- Tool responsible for managing and controlling... is also in the control layer. Copy pasted from the definition. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md), [Lecture 2](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-2.md) (where they talk about the service layer **and** the service orchestration layer)


## 3. What is the key function of the control layer of a cloud infrastructure?
- Manages and controls the cloud infrastructure ✅
- Prevents service instances from monopolizing the resources ✅
- Resource provisioning ✅
- Optimizes utilization of resources ✅

Justification: All of these are mentioned as part of lecture 5, which is the control layer lecture. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 4. What is enabled by cache tiering?
- Tiering between hard disk drives and DRAM cache
- Creation of a large capacity secondary cache only using DRAM cache
- Creation of a large capacity secondary cache using hard disk drives
- Tiering between DRAM cache and solid state drives ✅

Justification: Cache tiering means we have DRAM primary, and then the secondary is the SSD. This is in lecture 5, see the figure there. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 5. A technique that identifies the unused space in thin LUNs and re-assigns it to the storage pool is...
- Virtual storage reclamation ✅
- Virtual storage rebalancing
- Virtual storage provisioning
- Multipathing

Justification: You are taking back / reclaiming the unused storage, so, by definition, it's reclamation. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)


## 6. What is the manager type that provides a single management interface to manage cloud infrastructure resources and provisioning resources for services?
- Unified Manager ✅
- Element Manager
- Application Manager 
- Task Manager

Justification: It cannot be the application manager because there's no mention of direct communication with the controllers. It is what sits on top. There's also no explicit mention of external.

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 7. A technique that provides the ability to automatically restripe data across all the disk drives over the entire pool when new disk drives are added to the pool is...
- Virtual storage rebalancing ✅
- Virtual storage provisioning
- Virtual storage reclamation
- Multipathing

Justification: It's from the definition itself. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md) **Provides the ability to rebalance allocated extents on physical disk drives over the pool when new drives are added.** 

## 8. This is for final. **Not covered in midterm material**

## 9. Why is resource management an essential component for Cloud computing?
- Controls utilization of resources ✅
- To allocate requests to available resources ✅
- Prevents instances from monopolizing resources ✅
- To provide quality of service to consumers ✅

Justification: All of them are related to "good" resource management

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 10. A resource allocation technique was functioning as follows: when two service instances with two different service levels: service instance 1 has "Industrial subscription" service level with 3X priority and service instance 2 that has "student subscription" service level with X priority. When a resource contention occurs, the service instance 1 was given a priority to access available resources. This is an example of...
- Application manager allocation
- Absolute resource allocation
- Relative resource allocation ✅
- Element Manager allocation

Justification: This is clearly a proportion. There's no guarantee of upper or lower bounds. Therefore, by its definition, it's relative resource allocation. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md) **Relative Resource Allocation: Resource allocation to a service instance is defined proportionally relative to the resource allocated to other service instances. What does this mean? There's no guarantee of lower or upper bounds for the resource allocation. It's all relative to the usage basically across multiple consumers.**

## 11. A vendor offers a tool that manages resources along with the storage system to configure and make the storage resources available for the applications. This type of manager is...
- Element Manager ✅
- Application Manager
- Unified Manager
- Task manager

Justification: Because it's for a specific element (in this case, storage). It's not managing the other managers that manage other elements. 

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 12. In Dynamic Memory Allocation in the control layer...
- Distribute the load across hypervisors
- VMs have agent installed in guest OS that communicate with hypervisor ✅
- Reclaims memory pages ✅
- VMs have agent that communicate with each other via an agent communication language (ACL) using the FIPA-ACL standard

Justification: Literally just from the definition of dynamic memory allocation.

Reference: [Lecture 5](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-5.md)

## 13. Select all that apply. Data can be accessed on a compute system...
- Block level ✅
- Object level ✅
- PaaS
- File Level ✅

Justification: All three of these apply. PaaS has nothing to do with it though. 

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md): Check where it says Data Access Methods. 

## 14. What is a benefit of using RAID?
- Protects data against drive failure ✅ 
- Increases the data security on a drive 
- Improves the data integrity on a drive
- Improves the performance of a single drive

Justification: All it does is protect against data failure so that we don't lose data (can be done with parity, striping, etc...). It also cannot be integrity because at best, we can just discover failures. We **cannot mitigate** them.

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 15. Object-based storage contains data with user-defined attributes.
- True ✅
- False

Justification: Recall metadata and the fact that Google Drive gives you a unique link for your file.

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 16. In a FC SAN, which FC port type does an N_Port connect to? 
- E_Port
- G_Port
- N_Port
- F_Port ✅

Justification: It's the F_Port, because the node port connects to the fabric port (the node connects to the FC switch). It's in the figure in FC SAN. Also, there's no G_Port at all, and the E_Ports connect to each other because they're switch-to-switch. 
u
Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 17. Which solution for building a cloud infrastructure is a self-contained, pre-configured unit that combines compute, storage, network, virtualization, and management components? 
- Cloud-ready converged infrastructure ✅
- Best-of-Breed cloud infrastructure components
- Brownfield

Justification: It comes ready-made already. You're not getting things from different vendors, etc... or setting them up yourself. 

Reference: [Lecture 2](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-2.md)


## 18. What is a mechanism in a Fibre Channel switch that logically segments node ports within a fabric into groups and enables communication of nodes within the group? 
- Port Binding
- Zoning ✅
- LUN masking
- VLAN

Justification: The answer is zoning, but it's not in the slides. Not in what we've covered from 1-5. However, it's pretty straightforward. You're zoning the different nodes to be grouped with each other. Grouping is the same idea as zoning. 

## 19. What is specified by the physical layer in the cloud computing reference model? 
- Resource pooling
- Operating environment for the compute, storage, network resources ✅
- Hypervisor
- Control software

Justification: Resource pooling is in the virtual layer (Be careful here: The control layer sends the green flag. Recall the notes. The virtual layer is what actually does the resource pooling). Hypervisor is in the virtual layer. Control software is in the control layer. This is all that's left. 

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 20. Select all choices that describe traditional NAS. 
- Traditional NAS is the same as scale-out NAS
- Addition of nodes scales cluster capacity and performance without disruption
- Traditional NAS is the same as Scale-up NAS ✅
- Capacity and performance of a single system is scaled by upgrading or adding NAS components ✅

Justification: From my notes, traditional and scale-up are the same thing. The definition of scaling up is upgrading the system itself and adding components. **Not nodes**.

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 21. Which is a consolidation of block, file, and object-based access within one storage platform? 
- File-based storage 
- Unified Storage ✅
- Flash-based storage
- Scale-out NAS

Justification: Come on man. 

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md)

## 22. A compute system is configured to access data from a block-based storage system over a network. What must be true about the file system? 
- It is managed by the storage system
- It is managed by the computer system
- It is part of the storage area network. ✅
- It is managed by the object-based storage device node.

Justification: You're accessing the data through a network. It's not part of the compute system itself. It's also in the diagram where SAN is the middleman

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md) (Block-based storage system slide / diagram)

## 23. What uniquely identifies an FC switch in an FC SAN? 
- World Wide Node Name
- Domain Identifier ✅
- FC Address
- Area Identifier

Justification: I don't remember it, but I wrote down domain identifier in my notes. 

Reference: [Lecture 3](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-3.md) (Check the section on FC SAN)

## 24. Striping is a RAID technique to spread data across multiple drives in order to use the drives in parallel. 
- True
- False

## 25. What is a benefit of using RAID?
- Increases the data security on a drive
- Improves data integrity on a drive
- Protects data against drive failure

Justification:

Reference:

## 26. What uniquely identifies an FC switch in an FC SAN?
- Domain identifier
- World Wide Node Name
- FC address
- Area identifier

Justification:

Reference:

## 27. Select all choices that apply: Block-based storage system contains the following main components...
- Front-end
- cache
- backend
- physical disk

Justification:

Reference:

## 28. What is enabled by cache tiering?
- Creation of a large capacity secondary cache only using DRAM cache
- Creation of a large capacity secondary cache using hard disk drives
- Tiering between hard disk drives and DRAM cache
- Tiering between DRAM cache and solid state drives

Justification:

Reference:

## 29. What enables a LUN to be presented to an application with more capacity than is physically allocated to it on the storage system?
- Virtual storage provisioning
- Virtual storage reclamation
- Virtual storage rebalancing
- Multipathing

Justification:

Reference:

## 30. A technique that provides the ability to automatically restripe data across all the disk drives over the entire pool when new disk drives are added to the pool is...
- Virtual storage rebalancing
- Virtual storage provisioning
- Virtual storage reclamation
- Multipathing

Justification:

Reference:

## 31. Why is resource management an essential component for Cloud computing?
- Prevents instances from monopolizing resources
- Controls utilization of resources
- To allocate requests to available resources
- To provide quality of service to consumers

Justification:

Reference:

## 32. Which of the following is/are true about the cloud portal key functions?
- Organization and display of service information and management functions to the user
- Has key resource provisioning techniques
- It is a tool responsible for managing and controlling the underlying cloud infrastructure and enables provisioning of IT resources for creating cloud services
- Interaction with the orchestration layer

Justification:

Reference:

## 33. In Dynamic Memory Allocation in the control layer...
- Reclaims memory pages
- VMs have agent installed in guest OS that communicate with hypervisor
- Distribute the load across hypervisors
- VMs have agent that communicate with each other via an agent communication language (ACL) using the FIPA ACL standard

Justification:

Reference:

## 34. Which of the following are true about the orchestration software?
- Programmatically integrates and sequences various system functions into automated workflows
- Provides a library of predefined workflows and an interface to create user-defined workflows
- presents service catalog and cloud interfaces
- is a tool responsible for managing and controlling the underlying cloud infrastructure and enables provisioning

Justification:

Reference:

## 35. A vendor offers a tool that manages resources along with the storage system to configure and make the resources available for the applications. This type of manager is...
- Application Manager
- Element Manager
- Unified Manager
- Task manager

Justification:

Reference:

## 36. What is the manager type that provides a simple management interface to manage cloud infrastructure resources and provisioning resources for services?
- Unified Manager
- Element Manager
- Application Manager
- Task Manager

Justification:

Reference:

## 37. What is the key function of the control layer of a cloud infrastructure?
- Optimizes utilization of resources
- Prevents service instances from monopolizing the resources
- Resource provisioning
- manages and controls the cloud infrastructure

Justification:

Reference:

## 38. A technique that identifies the unused space in thin LUNs and re-assigns it to the storage pool is...
- Virtual storage provisioning
- Virtual storage reclamation
- Virtual storage rebalancing
- Multipathing

Justification:

Reference:


## 39. What uniquely identifies an FC switch in an FC SAN?
- Area Identifier
- FC Address
- World Wide Node Name
- Domain Identifier

Justification:

Reference:

## 40. A mechanism in a Fibre Channel switch that logically segments node ports within a fabric into groups and enables communication of nodes within the group is...
- Zoning
- VLAN
- LUN masking
- Port Binding

Justification:

Reference:

## 41. What is provided by an uplink NIC used in a virtual machine network on a physical compute system running a hypervisor?
- Connectivity between a virtual switch and a physical Ethernet switch
- Connectivity between a virtual switch and physical NICs
- Inter-switch links (ISLs) between virtual switches
- Connectivity between a virtual switch and virtual NICs

Justification:

Reference:

## 42. Which statement describes the measured service characteristic of cloud computing?
- Consumers are billed based on their consumption of resources
- Cloud services are provisioned based on consumer demand
- Cloud services are created as required from resource pools
- Consumers access cloud services from anywhere over a network

Justification:

Reference:

## 43. What network virtualization technique enables two virtual LANs at two different sites to connect to each other over a WAN?
- Stretched VLAN
- Private VLAN
- Promiscuous VLAN
- Community VLAN

Justification:

Reference:

## 44. Which network virtualization technique enables a virtual LAN to be further segregated into sub-VLANs?
- Virtual Extensible LAN
- Stretched VLAN
- Virtual Private Network
- Private VLAN

Justification:

Reference:

## 45. Which of the following refers to a logical abstraction of the aggregated computing resources, such as processing power, memory capacity, storage, and network bandwidth that is managed collectively?
- Bare-metal hypervisor
- Virtual appliance
- Resource pool
- Virtual machine template

Justification:

Reference:

## 46. What is a benefit of using RAID?
- Increases the data security on a drive
- Protects data against drive failure
- Improves the data integrity on a drive
- Improves the performance of a single drive

Justification:

Reference:

## 47. Which is a consolidation of block, file, and object-based access within one storage platform?
- Flash-based storage
- Scale-out NAS
- File-based storage
- Unified Storage

Justification:

Reference:

## 48. Which cloud characteristic enables consumers to provision IT resources without any human interaction at the service provider?
- Resource Pooling
- Self-service portal
- Broad network access
- On-demand self-service

Justification:

Reference:

## 49. In a FC SAN, which FC port type does an N_Port connect to?
- F_Port
- N_Port
- G_Port
- E_Port

Justification:

Reference:

## 50. A compute system is configured to access data from a block-based storage system over a network. What must be true about the file system?
- It is managed by the storage system
- It is managed by the computer system
- It is part of the storage area network
- It is managed by the object-based storage device node

Justification:

Reference:

## 51. A technique that identifies the unused space in thin LUNs and re-assigns it to the storage pool is...
- Virtual storage reclamation
- Virtual storage rebalancing
- Virtual storage provisioning
- Multipathing

Justification:

Reference:

## 52. What enables a LUN to be presented to an application with more capacity than is physically allocated to it on the storage system?
- Virtual storage provisioning
- Virtual storage reclamation
- Virtual storage rebalancing
- Multipathing

Justification:

Reference:

## 53. Which is a benefit of server clustering?
- High security
- High availability
- Minimize memory utilization
- Maximize CPU utilization

Justification:

Reference:

## 54. Which of the following statement/s is/are true about virtual machine (VM) snapshots?
- A snapshot holds only changed blocks
- A single delta disk file is used for all the snapshots of a VM
- A snapshot provides a zero recovery point objective
- A parent virtual disk is not required for recovery from a snapshot

Justification:

Reference:

## 55. A technique that provides the ability to automatically restripe data across all the disk drives over the entire pool when new disk drives are added to the pool is...
- Virtual storage rebalancing
- Virtual storage provisioning
- Virtual storage reclamation
- Multipathing

Justification:

Reference:

## 56. What is enabled by cache tiering?
- Tiering between DRAM cache and solid state drives
- Creation of a large capacity secondary cache only using DRAM cache
- Creation of a large capacity secondary cache using hard disk drives
- Tiering between hard disk drives and DRAM cache

Justification:

Reference:

## 57. What is the manager type that provides a single management interface to manage cloud infrastructure resources and provisioning resources for services?
- Unified Manager
- Element Manager
- Application Manager
- Task Manager

Justification:

Reference:

## 58. Which network virtualization technique enables a virtual LAN to be further segregated into sub-VLANs?
- Private VLAN
- Virtual Extensible LAN
- Virtual Private Network
- Stretched VLAN

Justification:

Reference:

## 59. Select the characteristics that virtualization fulfills within cloud computing.
- Rapid Elasticity
- Resource Pooling
- Broad Network access
- Measured services

Justification:

Reference:

## 60. What is provided by an uplink NIC used in a virtual machine network on a physical compute system running a hypervisor?
- Connectivity between a virtual switch and physical NICs
- Connectivity between a virtual switch and a physical Ethernet switch
- Inter-switch links (ISLs) between virtual switches
- Connectivity between a virtual switch and virtual NICs

Justification:

Reference:

## 61. Which network virtualization technique enables two virtual LANs (VLANs) at two different sites to connect to each other over a WAN?
- Stretched VLAN
- Promiscuous VLAN
- Community VLAN
- Private VLAN

Justification:

Reference:

## 62. Which statement is true about virtual machine (VM) snapshots?
- A snapshot holds only changed blocks
- A snapshot provides a zero recovery point objective
- A single delta disk file is used for all the snapshots of a VM
- A parent virtual disk is not required for recovery from a snapshot

Justification:

Reference:

## 63. Which of the following refers to a logical abstraction of the aggregated computing resources, such as processing power, memory capacity, storage, and network bandwidth that is managed collectively?
- Bare-metal hypervisor
- Resource pool
- Virtual machine template
- Virtual appliance

Justification:

Reference:

## 64. Select all choices that are correct with the concept of virtualization.
- Enables a resource to appear larger or smaller than it actually is
- Enables multitenant environment
- Improves utilization of resources
- Virtualization cannot be applied to storage

Justification:

Reference:

