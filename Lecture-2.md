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
