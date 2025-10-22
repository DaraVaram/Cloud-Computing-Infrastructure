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
- Service orchestration layer ✅

## 2. Which RAID level provides the highest level of data protection among the options by using dual distributed parity, allowing it to withstand the failure of two simultaneous disk drives?
- RAID 6 ✅

## 3. A cloud provider wants to implement a storage area network (SAN) that leverages their existing, robust IP network infrastructure and is widely used for disaster recovery solutions. Which SAN protocol would be the most suitable choice?
- iSCSI ✅

From the available options, this is the only one that is an IP SAN protocol. 


## 4. What is the key difference between a bare-metal hypervisor and a hosted hypervisor?
- A bare-metal hypervisor is installed directly on the hardware, and the hosted hypervisor is installed on an application or OS. ✅

## 5. Which compute resource management technique allows a single physical processor to appear as two logical processor cores to an operating system, enabling two threads to be scheduled simultaneously?
- Hyperthreading ✅

## 6. In a software-defined approach to infrastructure management, what is the primary function of the controller?
- To separate management functions from the infrastructure components and enable centralized, automated and policy-driven management ✅

## 7. A storage administrator creates a 10 TB Logical Unit Number (LUN) for an application but wants to avoid allocating the full 10 TB of physical disk space immediately. Which storage provisioning technology allows this?
- Thin LUN ✅

## 8. What is the primary purpose of a Virtual SAN (VSAN) in a Fibre Channel fabric?
- To create a logical fabric on a physical SAN, enabling communication between a group of nodes independent of their location ✅

## 9. Which of the following is NOT one of the five essential characteristics of cloud computing as defined by NIST?
- Simplified infrastructure management ✅

## 10. When building a cloud infrastructure, an organization chooses to integrate multi-vendor components, repurposing some of their existing hardware. What is a significant drawback of this 'best-of-breed' approach?
- Requires a significant amount of IT staff time for evaluation, integration and checking for compatibility. ✅

## 11. In Platform as a Service (PaaS), what does the consumer manage and control?
- Only the deployed applications and their hosting environment configuration settings. ✅

## 12. What is the primary function of a Converged Network Adapter (CNA) in an FCoE SAN?
- To provide functionality of both FC HBA and NIC in a single device ✅

## 13. An externally-hosted private cloud is characterized by which of the following arrangements?
- Implementation is out-sourced to a provider, but the infrastructure is for the exclusive use of a single organization ✅

## 14. Which distributed system design goal ensures that an application developed for one system can run without modification on another system that implements the same interfaces?
- Portability ✅

## 15. A unified manager in the control layer is creating resource pools and categorizing them as 'Gold', 'Silver', and 'Bronze' based on performance and protection levels. What is the primary purpose of this activity?
- To create a variety of services with different QoS levels and pricings for consumers. ✅

## 16. In a virtualized environment, what is the role of a VM Template?
- To create a master copy of a VM with a standardized configuration for deployment of new VMs ✅

## 17. Which network traffic management technique queues excess packets for later transmission when the traffic rate exceeds a pre-configured limit on an interface?
- Traffic shaping

## 18. What distinguishes an object-based storage system from a file-based storage system?
- Object-based uses a flat, non-hierarchical address space to store the data ✅

## 19. In the context of RAID techniques, what is the primary purpose of 'mirroring'?
- Store an exact copy of the data on a separate drive. Redundancy ✅

## 20. The vision of 'Computer Utilities', proposed by Leonard Kleinrock in 1969, is an early conceptualization of which modern technology?
- Cloud computing, duh ✅

## 21. What is a primary advantage of a blade compute system over a rack-mounted compute system?
- Its modular design increases compute density and scalability within a smaller footprint ✅

## 22. A hypervisor needs to reclaim memory from VMs when physical memory becomes scarce. It uses an agent in the guest OS to request memory pages, which are then returned to the hypervisor's memory pool. What is this technique called?
- Dynamic memory allocation. Don't get confused because memory page is mentioned here. ✅

## 23. Which of the following describes the 'control layer' in the cloud computing reference model?
- Includes software tools responsible for managing the cloud infrastructure and provisioning resources ✅

## 24. The 'rapid elasticity' characteristic of cloud computing provides what key advantage to the consumer?
- The ability to scale outward and inward commensurate with demand, appearing unlimited. ✅

## 25. A Community Cloud deployment model is distinct from a Private Cloud because it is:
- Provisioned for exclusive use by consumers from organizations that have shared concerns. ✅

## 26. What is the function of a Cloud Services Brokerage (CSB)?
- Acts as an intermediary that adds value to cloud services on behalf of the consumers ✅

## 27. Which resource management technique helps achieve higher overall storage pool performance by restriping data across all disk drives in the pool when new drives are added?
- Storage pool rebalancing ✅
 
## 28. A 'Stretched VLAN' provides a unique capability for cloud environments. What is its primary function?
- Enables layer 2 communication between nodes in different physical locations through a layer 3 WAN ✅

## 29. In the NIST definition of cloud computing, what does 'multi-tenant model' refer to?
- Provider's compute resources are pooled to serve multiple consumers ✅

## 30. Which of these is a key benefit of using 'Automated Storage Tiering'?
- It stores the right data on the right tier to meet service levels and optimize the cost. ✅

