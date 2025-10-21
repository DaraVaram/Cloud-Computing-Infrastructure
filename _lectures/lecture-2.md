---
layout: lecture
title: "Fundamentals in Building the Cloud Infrastructure"
lecture_number: 2
date: 2024-01-02
---
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
![Middleware]({{ '/figures/MiddlewareAndDistributedSystems.png' | relative_url }})
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


![ReferenceModel]({{ '/figures/CloudReferenceModel.png' | relative_url }})
Ariel's Notes: 

- Service Layer: It's an interface.
- Service Orchestration Layer: Provisions resources for you, established in a workflow, and establishes the automation of processing. This layer lays some **some plan or workflow**. The control layer just executes each process in the workflow as needed. Orchestration is the manager, it has it mapped out already, control layer does it step-by-step.
- Control Layer: There's no actual control, whatever resources are available, just provision them. This layer checks the availability of resources and creates them. Manages every single type of resource based on availability. The quality is assured through SLAs.
- Virtual Layer: Virtualization software which virtualizes the physical components (compute, storage and network)
- Phyiscal layer: The actual tangible stuff
- Two things that impact every single layer: Business Continuity and Security.
    - Business Continuity: Fault tolerance mechanisms, there are pro-active and re-active techniques. Pro-active is when you actively try to prevent faults, and then re-active is when if a fault happens, you "react" to it.
 
### Physical Layer
Foundation layer of the cloud infrastructure. 
- Specifies entities that operate at this layer (These are prime MCQ stuff):
    - Compute systems, network devices, storage devices
    - Operating environment, protocols, tools and processes.
- Functions of the physical layer:
    - Executes requests generated by virtualization and the control layer.


### Virtual Layer
Deployed **on** the physical layer
- Specifies entities that operate on this layer:
    - Virtualization software
    - Resource pools
    - Virtual resources
- Functions of this layer:
    - **Abstracts** the **physical** resources to make them **appear as virtual** resources.
    - It enables multi-tenancy, thereby improving utilization.
    - Executes the requests generated by the control layer.
 
### Control Layer
Deployed either on the virtual **or** on the physical layer. Can it be both? Yes, real deployments can mix and match. For example, the main control plane can be on physical servers for resiliency, and then the additional control plane services can be on VMs. 
- Specifies entities that operate on this layer:
    - Control software
- Functions of the control layer:
    - Enables resource config. and resource pool config. What does this mean? The control layer lets the admins group hardware capacities into logical pools, and then set rules on them (in terms of who gets how much resources). 
    - Enables resource provisioning. Provisioning = creating.
    - Executes requests generated by the service layer
    - Exposes **resources to and supports the service** layer. Control layer abstracts physical hardware, exposes virtual resources **upwards** through standard APIs. For example, the higher "service layer" components can consume those APIs without touching hardware. Basically, it acts as an intermediary between the hardware and the service.
    - Collaborates with virtualization software and enables **resource pooling** and **creating virtual resources**, **dynamic allocation of resources**, and **optimizing utilization of resources**.

### Service Orchestration Layer
- Specifies the entities that operate on this layer:
    - Orchestration software: coordinates many lower-level actions (APIs) into a repeatable workflow so entire environmnents / apps get deployed, scaled, or torn down automatically. 
- Functions of orchestration layer:
    - Provides workflows for executing automated tasks: You define a workflow, the orcehstrator executes it end-to-end without humans pressing humans. The control layer is the one that actuall does it, but the orchestration layer plans it and triggers each step. 
    - Interacts with various entities to invoke provisioning tasks: Calls provisioning APIs of lower layers to create the resources. 


How does it communicate with the control and service layer?
- With the service layer: Think about Azure self-service catalog portal, the service layer allows the user to pick a product. Clicking that triggers the orchestration (workflow or template behind the scenes).
- With the control layer: Orchestration calls the control layer's APIs which are the compute / network / storage controllers to actually allocate the VMs, volumes, and networks.

How does it differ from the control layer?
- Orchestration is what and in what order, meaning that it encodes multi-step workflow orders. Governs sequencing, approvals and error handling.
- Control layer says "how" and "where." It exposes APIs to create / manage the actual virtual resources. Applies scheduling, placement, quotas and policies on hardware.

### Service Layer
Consumers interact and consume cloud resources via this layer. 

- Specifies the entities that operate at this layer: 
    - Service catalog
    - Self-service portal

- Functions of the service layer:
    - Stores information about cloud services in service catalogs and presents them to the consumers
    - Enables consumers to access and manage cloud services via a self-service portal


### Cross-Layer Functions: Business Continuity
- Specifies adoption of measures to mitigate the impact of down-time

| Measures | Description | 
| ------- | ------- | 
| Proactive | <ul><li>Business impact analysis</li><li>Risk assessment</li><li>Technology solutions deployment (backup and replication)</li></ul> |
| Reactive | <ul><li>Disaster recovery</li><li>Disaster restart </li></ul> |

- Enables ensuring the availability of services in-line with the SLA
- **Supports all the layers** to provide uninterrupted services.

Basically, this layer responds to interruptions in the workflow / service. If anything happens that can disrupt it across all layers, then the business continuity layer steps in to mitigate. 

### Security Layer
- Specifies the adoption of: 
    - Administrative mechanisms: (1) Security and personnel policies (2) Standard procedures to direct safe execution of operations.
    - Technical mechanisms: (1) Firewall (2) Intrusion **detection** and **prevention** systems (3) Anti-virus
- Deploys security mechanisms to meet GRC requirements (Governance, Risk, and Compliance)
- Supports all the layers to provide secure services

Basically, it provides security across all layers. All the firewall stuff, the anti-viruses, potential intrusions / attacks, etc... are all expected to be handled / mitigated in this layer.

## Solutions for Building Cloud Infrastructure
There are two solutions for building cloud infrastructure: 
1. Integrating best-of-breed cloud infrastructure components
- Built my integrating multi-vendor infrastructure components. Basically, you take everything that's the best in the market for that particular domain. Frankenstein it all together.
- Enables repurposing the existing infrastructure components.
- Requires spending significant time of IT staff time on:
    - Evaluating individual and disparate HW components
    - Installing and integrating infrastructure components
    - Testing HW, MW, and SW
    - Checking compatibility of all components
- Enables organizations to choose and switch vendors easily

It's doable, but not straightforward (According to Ariel's notes). You pick each component / service from the vendor you like best and integrate them yourself. This maximizes choice and specialization, but you have to do the setup yourself. For example, if you want to build a private cloud. Why would you choose this method?
- Flexibility and avoiding lock-in: You can swap components, negotiate pricing, etc...
- Specialize performance / features. You can pick the best of whatever you want for your use-case.

2. Cloud-ready converged infrastructure
![CloudReady]({{ '/figures/CloudReady.png' | relative_url }})

You buy a pre-validated stack that bundles compute, storage, networking and management as **one fully-engineered system**. You have less freedom, but at the same time much more convenience since you don't have to set up and patch things together yourself. Quicker deployment, this-just-works guarantee, etc...
- Keep in mind that if you go with this, you'd have to get it from one single vendor. You can't mix and match there, so there's a potential issue with vendor lock-in.

## Service-level Agreement (SLA) and Legal Contract
Definition: A **contract** negotiated between a **provider** and a **consumer** that specifies various parameters and metrics such as **cost**, **service availability**, maintenance schedules, **performance levels**, service desk response time, and consumer's and provider's responsibilities.

There are certain key things that **need to be included** in a legal contract: 
- Business-level policies such as **data privacy**, **data ownership**, **security** and **jurisdiction**.
- Availability and performance metrics
- Disaster recovery plans, exit plans, and penalties for not meeting SLA
- How unexpected incidents and potentially prolonged service outage will be handled.
