# Virtual Layer
This lecture talks about the virtual layer in significantly more detail than in [Lecture 2](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/Lecture-2.md).

![VirtualLayer](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/VirtualLayer.png)

Virtual layer is related to the elasticity and resource pooling. Recall the characteristics of the cloud: 
- Self-service
- **Elasticity** - Virtual layer focus
- **Resource Pooling** - Virtual layer focus
- **Multi-tenancy** - Virtual layer focus

## Introduction to Virtualization
Definition: Refers to the **logical abstraction** of **physical resources**, such as compute, network, and storage that enables a single hardware resource to support multiple concurrent instances of systems or multiple hardware resources to support single instance of system.

This is an enabler technology. No virtualization means that there is no cloud at all.

Virtualization allows resources to appear larger or smaller than they actually are. How? By turning them into logical units. This applies to both compute and storage. Imagine you have 6 machines with 2 CPU cores each. If you wrap them together and virtualize, your system appears to have 12 CPU cores now. Similar idea for storage as well. 

Enables a multi-tenant environment, improving utilization of physical resources.
- Parallel users of the same computer at the same time (as an example). This is the general philosophy.

### Benefits of Virtualization
- Optimizes **utilization** of IT resources
- Reduces **cost** and **management** complexity
- Reduces **deployment time**
- Increases **flexibility**

### Overview of the Virtual Layer
**Virtualized** compute, network and storage forms the virtual layer. This enables fulfilling two characteristics of cloud infrastructure: 
- Resource pooling
- Rapid elasticity

Multi-tenancy is not necessarily in-line with resource pooling. You can have a multi-tenant system without the need to pool resources, etc... Think about having the same compute node, with different ```conda``` environments on it. This is basically the same thing as virtualizing the machine. Everyone can have their own ```conda``` environment, but on the same machine (an A100). You **can** incorporate resource pooling (multiple A100s as part of a cluster), and allow rapid elasticity (adding more storage to the A100 cluster). 

_Do you need virtualization for multi-tenancy?_ You do not always need virtualization for multi-tenancy, as other methods like application-level and database-level isolation are also common. Virtualization is one method, especially useful when strong isolation is required, while application-level isolation is often used for cost-effective SaaS applications.

Specifices the entities operating at this layer: 
- Virtualization software
- Resource pools
- Virtual resources

```mermaid
flowchart LR
    A[**Step 1:** Deploy virtualization software on:<br/>• Compute systems<br/>• Network devices<br/>• Storage devices] --> 
    B[**Step 2:** Create resource pools:<br/>• Processing power & memory<br/>• Network bandwidth<br/>• Storage]
    B --> 
    C[**Step 3:** Create virtual resources:<br/>• Virtual machines<br/>• Virtual networks<br/>• LUNs]
    C --> 
    D((Virtual resources are packaged<br/>and offered as services))

```

### Compute Virtualization Software: Hypervisor
Definition: Software that is installed on a compute system and **enables multiple OSs** to run **concurrently** on a physical compute system.

Hypervisor Kernel: 
- Provides functionality similar to OS kernel
- Designed to run multiple VMs concurrently

Virtual Machine Manager (VMM): 
- Abstracts hardware
- Each VM is assigned a VMM
- Each VMM gets a share of physical resources.

This is summarized pretty well in the figure below: 

![hypervisorvmm](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/Hypervisor.png)

We can see that the VMM and is part of the hypervisor. The hypervisor **does not only manage the compute**. It manages the entire hardware that it's installed on. Otherwise, it wouldn't be able to virtualize that particular hardware. If you want to virtualize storage, you will need to hypervise the storage. 

| Types of Hypervisors | Description |
| ------ | ------- |
|Bare-metal | <ul><li>Installed on a bare-metal HW</li><li> Requires certified HW</li><li> Suitable for enterprise data centers and cloud infrastructure </li></ul>
| Hosted | <ul><li>Installed as an application on an OS </li><li> Relies on OS running on physical machine(s) for device support </li><li>Suitable for development testing and training purposes.</li></ul>

Hosted: would be something like having a virtual box and then installing Linux onto your PC using that virtual box. That's what hosted is. 

Bare metal: The hypervisor will be installed directly onto the machine prior to any OS. There's no OS in between the hypervisor and the machine. It's as if it's the OS, and now, on top of this, you can have multiple VMs installed. There are some minimum requirements for installation. The figure in the last section is an example of bare-metal. Example: ESXI. 
- To access bare-metal hypervisor: You have an IP address, use the console to create VM

If you have hosted, then there would be a **layer of OS** between the physical resources and the hypervisor. 


### Network Virtualization Software
Abstracts physical **network** resources to create virtual resources. This allows VMs to talk to each other, and also isolates the traffic. 
- Virtual LAN / Virtual SAN
- Virtual Switch

Network virtualization software can be: 
- Built into the operating environment of a **network device**
- Installed on an independent **compute system**
    - Fundamental component for deploying software-defined component.
- Hypervisor's capability


### Storage Virtualization Software
Abstracts physical **storage** resources to create virtual resources. 
- Virtual volumes
- Virtual disk files
- Virtual arrays


Storage virtualization software can be (This is the exact same thing as above, just switch network with storage): 
- Built into the operating environment of a **storage device**
- Installed on an independent **compute system**
    - Fundamental component for deploying software-defined component.
- Hypervisor's capability

**Example:**

If you have a server that has compute, storage and network, you can virtualize all of it. The two ways of doing this is either we virtualize the entire thing and all of its components on an independent compute system, or we can just do the Azure thing which is where we get a virtual disk that's already virtualized and use that immediately. This is what we mean by it being built into the operating environment of a storage device. 


## Resource Pooling
Definition: A **logical abstraction of the aggregated computing resources**, such as  processing power, memory capacity, storage, and network bandwidth that are managed collectively. **Very important:** Everything before this, we abstract / virtualize first, and then aggregate. For resource pooling, we have a pool of resources that are not inherently abstracted together. So then we aggregate them and _then_ we virtualize again. 

You have separate hard drives. Now, you put the hard drives in a box to "abstract" them, and then you put them into a bigger box to aggregate and virtualize. Abstracting the abstracted resources. You can increase the size of the resource pool as well. Then, you can assign the resources based on the users' needs. 

![ResourcePool](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ResourcePool.png)

Cloud services obtain computing resources from the resource pool. They are **sized** according to **service requirements**.
- Resources are **dynamically allocated** as per consumer demand

Another example: 

![ExampleResourcePool](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ResourcePoolExample.png)

Each one of the resources here has their own hypervisor, meaning that it's already virtualized. Now, we group them together and virtualize again, and then you create virtual machines. You connect them to each other. This aggregation method is a software (hypervisor), or it could be a networking thing. They are networked together for sure.

![StorageBlockBased](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/StoragePooling.png)

This is an example for a block-based storage system. This is only for one system. We are pooling resources into a single storage system. In this example, there is no computer. It's just storage drives pooled together. We obviously need the storage controllers (something has to manage it), but it's not a computer. If we want to extend this across storage systems: 

![StorageBlockBased2](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/StoragePooling2.png)

We have a higher level of abstraction, where we are basically pooling the resource pools of storage. 

### Network Pooling

![NetworkPooling](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/NetworkPooling.png)

This is what happens when you do network pooling. This pool has three NICs. We are pooling the bandwidth (technically the NICs). Then, you allocate to the consumers based on how much they need / want. This is called **teaming** the NICs. 

## Virtual Machines (VMs)
Definition: A logical compute system that, like a physical compute system, runs an OS and applications.

This is **created by a hypervisor and is installed on a physical compute system**. This hypervisor can be either bare-metal or hosted, but the VM is installed specifically on top of the hypervisor. It comprises of the virtual HW, such as virtual processor, memory, storage, and network resources. 
- **Appears as a physical compute system** to the guest OS
- Hypervisor **maps** the virtual HW to the physical HW
- Provider provisions the VMs to consumers for deploying applications
    - VMs on the same **compute system** or **cluster** run in **isolation**. Basically, the people that are using different VMs on the same compute system / cluster will not feel the impact of the others on that cluster. This is unless you network them with each other.
 
### VM Files
From the hypervisor's perspective, the VM is a discrete set of files.

| Files | Description | 
| ---- | ----- |
| Confirguation File | <ul><li>Stores information such as the VM name, BIOS information, the guest OS type, and memory size</li></ul> | 
| Virtual Disk File | <ul><li>This stores the contents of the VM's disk drive</li></ul> | 
| Memory State File | <ul><li>This stores the memory contents of a VM in a **suspended** state </li></ul> | 
| Snapshot File | <ul><li>Stores the VM settings and virtual disk of a VM </li></ul> | 
| Log File | <ul><li>Keeps a log of the VM's activity and is typically used in troubleshooting </li></ul> |

### File system to manage VM Files
Hypervisor's native file system: 
- Clusted file system deployed on local or external storage
- Enables **multiple hypervisors** to **perform concurrent reads and writes**
- Enables high availability to protect against hypervisor or compute system failures

Shared File system: 
- Enables storing VM files on remote file servers or NAS devices

![FileSystemManager](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/FileSystemManageVMs.png)

In this figure, you can see that...
