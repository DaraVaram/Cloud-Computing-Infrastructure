# Lecture 6: Business Continuity

**IMAGE HERE**

# What is Business Continuity?
### Definition
_BC entails **preparing** for, **responding** to, and **recovering** from service outage that adversely affects business operations._

## BC enables continuous availability of cloud services in the event of failure
- Helps to meet the required service level (OR THE SLA)

## BC involves various **proactive** and **reactive** measures

## Disaster recovery is a part of BC, which coordinates the process of restoring infrastructure, including data
- Required to support ongoing cloud services, after a disaster occurs.

## ARIEL'S NOTES:
- The business continuity overlaps with all the layers to ensure the resilience of a cloud computing data center
- Every SLA has a % of ensured availability
  
# Cloud Service Availability
_Refers to the ability of a cloud service to perform its agreed function according to business requirements and customer expectations during its specified time of operation._

Service availability (%):

$$
\mathrm{Service\ availability\ (\%)} =
\frac{\mathrm{Agreed\ service\ time} - \mathrm{Downtime}}{\mathrm{Agreed\ service\ time}}
$$

_Agreed service time is the period where the service is supposed to be available_ --> OBVIOUSLY

# Causes of Cloud Service Unavailability

- Application failure
    - For example, due to catastrophic exceptions caused by bad logic
- Data loss
- Infrastructure component failure
- Failure of dependent services
- Data center or site down
- Refreshing IT infrastructure

# Methods to Achieve Required Cloud Service Availability
- Building **resilient** cloud infrastructure facilitates meeting the required service availability
- Building resilient cloud infrastructure requires various high availability solutions
    - Implementing **fault tolerance** mechanisms
        - Deploying redundancy at both cloud infrastructure component level and site level to **avoid single point of failure**
    - Deploying data protection solutions such as **backup** and **replication**
    - Implementing automated cloud service failover --> just to clarify, cloud service failover means to switch to a backup and we want this to be done automatically; for example, network traffic can be switched in the event of a link failure
    - Architecting resilient cloud applications

# Lesson: Building Fault Tolerance Cloud Infrastructure - 1
This lesson covers the following topics:
- Avoiding single points of failure
- Key fault tolerance mechanisms

# Single Points of Failure
_Refers to **any individual component** or aspect of an infrastructure whose **failure can make the entire system** or service **unavailable**._
- Single points of failure may occur at
    - Component level (copmute, storage, and network)
    - Site or data center level 
**IMAGE HERE**

# Avoiding Single Points of Failure
- Single points of failure can be avoided by implementing fault tolerance mechanisms such as redundancy
    - Implement redundancy at component level
        - Compute
        - Storage
        - Network
- Implement multiple service availability zones
    - Avoids single points of failure at data center (site) level --> service availability zones are physically separate datacenters isolated from each other **within the same geographical region** --> helps with **high availability** and **redundancy** with services
    - Enable service failover globally
- It is important to have high availability mechanisms that enable automated service failover

# Implementing Redundancy at Component Level

**IMAGE HERE**

## How do these techniques protect **compute**?
- Clustering
    - Runs multiple servers as a coordinated group, so if one node fails, another node in the cluster continues providing the services.
- VM Live migration
    - Moves a running virtual machine from one physical host to another without downtime so workloads can continue if a host needs maintenance or fails.

## How do these tecchniques protect **network connectivity**?
- Link and switch aggregation
    - Combines multiple physical network links and/or switches into a single logical connection so traffic can automatically failover if one link or switch goes down.
- NIC teaming
    - Bonds multiple physical NICs into one logical adapter soooo if one NIC fails, another NIC maintains network connectivity
- Multipathing
    - Provides multiple independent I/O paths between servers and storage so if one path fails, data traffic can be rerouted through a different path
- In-service software upgrade
    - Allows network or system software to be upgraded on one redundant component at a time while others keep running, avoiding downtime during updates --> higher availability and uptime because the network/system software does not necessarily have to be offline

## How do these techniques protect **storage**?
- RAID
    - Spreads data across multiple disks with redundancy (mirroring or parity) so the system can tolerate one or more disk failures without losing data or acccess.
- Dynamic disk sparing
    - Keeps one or more spare disks idle so when an active disks fails, data is automatically rebuilt onto the spare, restoring redundnacy
- Configuring redundnat storage system components
    - Duplicates critical storage parts (e.g., controllers, power supplies, fans, interconnects)  so the failure of any single component does not interrupt access to stored data
 
# Compute Clustering
_A technique where **at least two compute systems** (or nodes) **work together** and are **viewed** as a **single compute system** to provide **high availability** and **load balancing**._

- Enables service failover in the event of compute system failure to another system to minimize or avoid any service outage

- Two common clustering implementations are:
    - Active/active --> ARIEL'S NOTES: Active derving requests
    - Active/passive --> ARIEL'S NOTES: waiting for a failure to happen

- Hypervisor cluster is a common clustering implementation in a cloud environment --> cluster VMs basically

# VM Live Migration

- Running services on VMs are moved from one physical compute system to another without downtime
    - Allows scheduled maintenance without any downtime
    - Facilitates load balancing

**IMAGE HERE**

The image shows two compute systems where the first compute system has two services being migrated to the second compute system *WITHOUT** the first compute system being offline.

# Link and Switch Aggregation
- Link aggregation
    - Combined links between two seitches and also between a switch and a node
    - Enables network traffic failover in the event of a link failure in the aggregation --> when you need to hit a word count
    - Enables distribution of network traffic across links in the aggregation

### NOT NEEDED::: What is the difference between link aggregation and trunking?
- Link aggregation combines multiple physical links into one logical link, whereas trunking aggregates VLAns as one logical link

- Switch aggregation
    - Provides fault tolerance against switch and link failures --> Does link aggregation also protect against switch failure? Normal link aggregation involves bundling links into a **single switch**, so it only protects against port/cable failure.
    - Improves node performance by providing more active paths and bandwidth --> what does providing more active paths and bandwidth mean and how does it do these things? So, this means that a node can use many physical uplinks at the same time to the aggregated switches, for load balancing traffic across the links resulting in the effective bandwidth to be the sum of the bandwidths

### What are the differences/similarities between switch and link aggregation?
- Link aggregation is at the **port level** (_grouping links between devices_), while switch aggregation works at tge **device level** (_grouping multiple switches into one switch_). Both do aim to increase bandwidth and redundancy and are often used together to aggregate links on an aggregated switch.

### What are the differences/similarities between these two and multipathing?
- Link/switch aggregation work at Layer 2 (Data Link Layer in OSI model) by aggregating physical Ethernet links into one logical connection, whereas multipathing (e.g., MPIO [MultiPath Input Output] for storage) keeps multiple independentg end-to-end paths for load balancing, redundancy, etc.

**IMAGE HERE**

# NIC Teaming
_A link aggregation technique that groups NICs so that they appear as a single. logical NIC to the OS or hypervisor._

- Provides network traffic failover in the event of a NIC/link failure

- Distributes network traffic across NICs

- NICs within a team can be configured as active and standby

**IMAGE HERE**

# Multipathing

- Enables a compute system to use multiple paths for transferring data to a LUN (Logical Unit Number)

- Enables failover by redirecting I/O from a failed path to another active path

- Performs load balancing by distributing I/O across active paths
    - Standby paths become active if one or more active paths fail

# Storage Resiliency Using Mirrored LUN
- Mirrored LUN is created using virtualization appliance
    - Each I/O to the LUN is mirrored to the LUNs on the storage system
    - Mirrored LUN is continuously available to the compute system
        - Even if one of the storage systems is unavailable due to failure

Is there a benefit of distributed traffic here?
- With mirrored LUNs, the host sees a single virtual LUN while a virtualization appliance (or storage software) actually writes each I/O to two backend LUNs on different storage systems; if the configuration is “active-active” or allows both sides to serve reads, read traffic can be spread across both arrays for better throughput, but writes must always go to both sides and be acknowledged, so write performance is limited by latency and the slower side—meaning any traffic-distribution benefit is mostly on reads and is secondary to the primary goal of redundancy and high availability.

- What is going on in the image?
- The host sees one LUN, a virtualization appliance mirrors all I/Os to two backend LUNs on two separate storage systems, providing continuous availability (and potentially read (not necessarily write) load-balancing) even if one storage system fails.

**IMAGE HERE**

# Service Availability Zones
- A service availability zone is a location with its own set of resources and isolated from other zones
    - A zone can be a part of a data center or may even be comprised of the whole data center
