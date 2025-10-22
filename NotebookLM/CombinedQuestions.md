# Medium Difficulty

## 1. According to the NIST definition, which of the following is considered an essential characteristic of cloud computing that allows consumers to provision resources like server time and network storage without human interaction with the provider?
- On-demand self service ✅

## 2. In the context of the Cloud Computing Reference Model, which layer is responsible for abstracting physical resources to create entities like virtual machines, virtual networks, and LUNs?
- Virtual layer ✅

## 3. Which cloud service model provides the consumer with the capability to deploy their own applications using programming languages and tools supported by the provider, but does not give them control over the underlying infrastructure like servers and operating systems?
- PaaS ✅

## 4. A financial services company needs to build a cloud for its exclusive use to meet strict security and compliance requirements. It will be owned and operated by a third party and exist off-premises. Which deployment model does this describe?
- Off-premise private cloud ✅

## 5. What is the primary function of a software-defined controller in a modern cloud infrastructure?
- To abstract management functions from infrastructure components and centralize the control via software ✅

## 6. Which RAID technique improves performance by spreading data across multiple drives but offers no protection against drive failure?
- RAID 0 / Striping ✅

## 7. A hypervisor needs to optimize physical memory usage when multiple VMs are running the same operating system. Which technique allows it to eliminate redundant copies of memory pages?
- Memory sharing ✅

## 8. What is the key advantage of a blade compute system over a traditional rack-mounted system?
- Its modular design increases compute density and scalability within a smaller footprint ✅

## 9. Which storage system architecture is designed to store file data as self-contained items that include user data, metadata, and a unique identifier in a flat address space?
- Object-based storage (this is flat, non-hierarchical). File-based is the Google Drive example ✅

## 10. In a Fibre Channel over Ethernet (FCoE) SAN, what is the role of a Converged Network Adapter (CNA)?
- To provide the functionality of both a standard NIC and FC HBA in a single device ✅

## 11. What is a VM template primarily used for in a cloud environment?
- To create a master copy of a VM with a standardized configuration for deployment of new VMs ✅

## 12. Which network traffic management technique ensures that business-critical applications receive consistent service levels by prioritizing their packets over less critical traffic?
- Quality of Service (QoS) ✅

## 13. What is the defining characteristic of a 'thin LUN' created from a storage pool?
- It does not require physical storage to be allocated upfront and consumes space from the pool only as data is written. ✅

## 14. In a distributed system, what does the design goal of 'transparency' refer to?
- The complexities of the distributed nature of the system are hidden from the users ✅

## 15. A cloud provider uses a technique to establish a hierarchy of different storage types (e.g., Flash, FC, SATA) and automatically moves data between them based on access frequency to meet service levels and optimize costs. What is this technique called?
- Automated storage tiering ✅

# Hard Difficulty

## 1. In the context of the Cloud Computing Reference Model, which layer is responsible for providing workflows to execute automated tasks and interacting with various entities to invoke provisioning?
- Service orchestration layer

## 2. Which RAID level provides the highest level of data protection among the options by using dual distributed parity, allowing it to withstand the failure of two simultaneous disk drives?
- RAID 6

## 3. A cloud provider wants to implement a storage area network (SAN) that leverages their existing, robust IP network infrastructure and is widely used for disaster recovery solutions. Which SAN protocol would be the most suitable choice?
- iSCSI

From the available options, this is the only one that is an IP SAN protocol. 


## 4. What is the key difference between a bare-metal hypervisor and a hosted hypervisor?
- A bare-metal hypervisor is installed directly on the hardware, and the hosted hypervisor is installed on an application or OS.

## 5. Which compute resource management technique allows a single physical processor to appear as two logical processor cores to an operating system, enabling two threads to be scheduled simultaneously?
- Hyperthreading

## 6. In a software-defined approach to infrastructure management, what is the primary function of the controller?
- To separate management functions from the infrastructure components and enable centralized, automated and policy-driven management

## 7. A storage administrator creates a 10 TB Logical Unit Number (LUN) for an application but wants to avoid allocating the full 10 TB of physical disk space immediately. Which storage provisioning technology allows this?
- Thin LUN

## 8. What is the primary purpose of a Virtual SAN (VSAN) in a Fibre Channel fabric?
- To create a logical fabric on a physical SAN, enabling communication between a group of nodes independent of their location

## 9. Which of the following is NOT one of the five essential characteristics of cloud computing as defined by NIST?
- Simplified infrastructure management

## 10. When building a cloud infrastructure, an organization chooses to integrate multi-vendor components, repurposing some of their existing hardware. What is a significant drawback of this 'best-of-breed' approach?
- Requires a significant amount of IT staff time for evaluation, integration and checking for compatibility.

## 11. In Platform as a Service (PaaS), what does the consumer manage and control?
- Only the deployed applications and their hosting environment configuration settings. 
