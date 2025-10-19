# Fundamentals in Building the Cloud Infrastructure

Recall the definition of Cloud Computing: 

A Cloud is a type of **parallel** and **distributed** system consisting of a collection of **interconnected** and **virtualized** computers that are **dynamically provisioned** and presented as one or more **unified** computing resources based on **service-level agreements** established through negotiation between the service provider and consumers. - Definition by Buyya

*Interconnected: Pooled resources are a collection of intercollected resources.
*Virtualized: Multi-tenancy - virtualization enables this. 
*SLA: Negotiation between provider and consumer, essentially quality of provisioning based on the consumers' needs. 
*This Buyya guy developed the [GridSim](https://arxiv.org/abs/cs/0203019), which is the same thing as the [CloudSim](https://github.com/Cloudslab/cloudsim). 

## Introduction to Distributed System(s)
Definition 1: A distributed System is a collection of **autonomous** computing elements that appear to its users as a **single coherent system** (Tanenbaum).

Definition 2: A distributed System is one in which components located at **networked computers** **communicate** and **coordinate** their actions only by passing messages (Coulouris).

### Characteristic Features of these Definitions
There are some characteristics that can be derived from these definitions: 
1. Collection of **autonomous** entities: Meaning that they can do independent decisions and / or have their own "controllers." Each entity has the ability to behave independently from other entities. The entity can be **physical** (HW) / **virtual**.
2. Appear as a **single coherent system**: Interdependencies of operations or sub-tasks to collaborate together to execute a "primary" task. They appear to the user as a single system. This means that autonomous nodes **need** to collaborate. How, however, to establish this collaboration is the heart od developing "good" distributed systems.
3. **No assumptions** made regarding the **type** of nodes in distributed systems. What do we mean by type here? We are referring to the capability of the nodes themselves (can be something high-performance or a small edge device).
4. **No assumptions** are made concerning the way these nodes are **inter-connected**.

Basically, there are no specific requirements regarding how capable the nodes are, or how they are connected to each other. It's just a collection of entities / nodes that appear to work in unison towards a common goal. 

## Middleware and Distributed Systems
![Middleware](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/MiddlewareAndDistributedSystems.png)
To make distributed systems a reality, they are often organized to have a layer of software that is **logically** placed on top of the respective systems of the computers that are part of the system. 

- Distributed systems: Multiple computers that are inter-connected
- Look at the middleware: It aggregates resources / abstracts physical resources into logical resources. These logical resources are then managed at a software level. Resources, in this case, can be something like CPU, memory, etc...

## Design Goals
### Accessibility
We should make the resources easily accessible, meaning that they should be accessible remotely and we should be able to share them in a controlled and efficient way. 
### Transparency
The complexities are hidden from the users (doesn't this make it not transparent?) We'll need to check this with Dr. Raafat. 
| Aspect | Description |
| ------ | ----------- |
| Access | Hide differences in data representations (at a software level, like what kind of file formatting, etc...) and how the object is accessed (basically, how we process these files). |
| Location | Hide where an object is located exactly (Basically, it shouldn't matter to the consumer where exactly the data is stored, whether it's in UAE North or Central India). | 
| Migration | Hide that an object may move to another location (Moving an "object" from one data center to another without impacting performance / quality). |
| Replication | Hide that an object is replicated (for example, replication for availability / redundancy) | 
| Concurrency | Hide that an object may be shared by several independent users (again, this is multi-tenancy. Several clients can potentially use the same "object"). | 
| Failure | Hide the failure and recovery of an object (The mechanisms for recovery are hidden from the consumers, so that they don't "feel" when a failure occurs). | 

### Openness
Note: This is basically the same concept as flexibility or standardization (to enable systems to be integrated into other systems). 

A system that offers components that can easily be used by or incorporated into other systems. 
- Must interact with services from other open systems despite the underlying environments (For example, if you use VMWare or a Virtual Box, and you save them in the standardized format, you can open them in any other software. Another perspective on this is the protocols, etc... need to match).
- Must have well-defined interfaces
- Must be able to inter-operate: Two implementations of systems or components from different providers can co-exist and work together.
- Support portability: An app developed for distribued system A can be executed without modification on a different distributed system B (assuming that system B implements the same _interfaces_ as A). Then it's just plug and play.
- Extensible: Add new components or replace existing ones without affecting those components already in place (This is the same thing as modular). This applies to both HW and SW applications.

To achieve flexibility in open distributed systems, it is important that the system is organized as a collection of small, and easily replaceable or adaptable components. Again, this just means that the system should be modular. We can decompose large systems into small components that we can integrate together. 

### Scalability
Scalability can be measured along at least 3 dimensions: 
- **Size**: We can add more users / resources to the system without any noticeable loss in performance.
- **Geographical**: Users and resources _may be_ far apart and the communication delays are minimal / hardly noticeable (latency issues shouldn't be a problem)
- **Administrative**: Can still be easily managed, even if it spans many independent administrative organizations. Cloud provider (many organizations), or multiple cloud providers together, or multiple data centers by a _single_ provider.

## Cloud Infrastructure Reference Model
Definition: A **reference model** is an **abstract** framework for understanding **significant relationships** among the entities of some environment, and for the development of consistent **standards or specifications** supporting that environment. It is based on a small number of unifying concepts and may be used as a basis for **education** and **explaining standards**. It is **not directly tied** to any **standards**, **technologies**, or other concrete **implementation** details, but it does seek to provide a common semantics that can be used unambiguously across and between different implementations.

- It facilitates efficient communication of system details between stakeholders
- Provides a point of reference for system designers to extract system specifications.

Basically, it's a model. That's all there is to it. 


![ReferenceModel](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/CloudReferenceModel.png)
- Service Layer: It's an interface.
- Service Orchestration Layer: Provisions resources for you, established in a workflow, and establishes the automation of processing. This layer lays some **some plan or workflow**. The control layer just executes each process in the workflow as needed. Orchestration is the manager, it has it mapped out already, control layer does it step-by-step.
- Control Layer: There's no actual control, whatever resources are available, just provision them. This layer checks the availability of resources and creates them. Manages every single type of resource based on availability. The quality is assured through SLAs.
- Virtual Layer: Virtualization software which virtualizes the physical components (compute, storage and network)
- Phyiscal layer: The actual tangible stuff
- Two things that impact every single layer: Business Continuity and Security.
    - Business Continuity: Fault tolerance mechanisms, there are pro-active and re-active techniques. Pro-active is when you actively try to prevent faults, and then re-active is when if a fault happens, you "react" to it.
 
### Physical Layer
Foundation 
