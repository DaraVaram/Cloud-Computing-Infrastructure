# Lecture 6: Business Continuity

![BusinessCont](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/BusinessCont.png)

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
\mathrm{Service\ availability\ } =
\frac{\mathrm{Agreed\ service\ time} - \mathrm{Downtime}}{\mathrm{Agreed\ service\ time}}
$$

_Agreed service time is the period where the service is supposed to be available_ --> OBVIOUSLY

# Causes of Cloud Service Unavailability

- Application failure
    - For example, due to catastrophic exceptions caused by bad logic (like dividing by 0)
- Data loss
- Infrastructure component failure
- Failure of dependent services
- Data center or site down
- Refreshing IT infrastructure

# Methods to Achieve Required Cloud Service Availability (CSA)
- Building **resilient** cloud infrastructure facilitates meeting the required service availability
- Building resilient cloud infrastructure requires various high availability solutions
    - Implementing **fault tolerance** mechanisms
        - Deploying redundancy at both cloud infrastructure component level and site level to **avoid single point of failure**
    - Deploying data protection solutions such as **backup** and **replication**
    - Implementing automated cloud service failover --> just to clarify, cloud service failover means to switch to a backup and we want this to be done automatically; for example, network traffic can be switched in the event of a link failure
    - Architecting resilient cloud applications


## Single Points of Failure
_Refers to **any individual component** or aspect of an infrastructure whose **failure can make the entire system** or service **unavailable**._
- Single points of failure may occur at
    - Component level (copmute, storage, and network)
    - Site or data center level 

![SinglePointFailure](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/SinglePointFailure.png)

## Avoiding Single Points of Failure
- Single points of failure can be avoided by implementing fault tolerance mechanisms such as redundancy
    - Implement redundancy at component level (clustering, SANs, link aggregation, NIC teaming, etc...)
        - Compute
        - Storage
        - Network
- Implement multiple service availability zones
    - Avoids single points of failure at data center (site) level --> service availability zones are physically separate datacenters isolated from each other **within the same geographical region** --> helps with **high availability** and **redundancy** with services
    - Enable service failover globally
- It is important to have high availability mechanisms that enable automated service failover

# Implementing Redundancy at Component Level

![ImplementingRedundancy](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ImplementingRedundancy.png)

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
 
## Compute Clustering
_A technique where **at least two compute systems** (or nodes) **work together** and are **viewed** as a **single compute system** to provide **high availability** and **load balancing**._

- Enables service failover in the event of compute system failure to another system to minimize or avoid any service outage

- Two common clustering implementations are:
    - Active/active --> ARIEL'S NOTES: Active derving requests
    - Active/passive --> ARIEL'S NOTES: waiting for a failure to happen

- Hypervisor cluster is a common clustering implementation in a cloud environment --> cluster VMs basically

## VM Live Migration

- Running services on VMs are moved from one physical compute system to another without downtime (there is some near-zero downtime).
    - Allows scheduled maintenance without any downtime
    - Facilitates load balancing

![VMLiveMigration](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/VMLiveMigration.png)

The image shows two compute systems where the first compute system has two services being migrated to the second compute system *WITHOUT** the first compute system being offline.

## Link and Switch Aggregation
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
- Link aggregation is at the **port level** (_grouping links between devices_), while switch aggregation works at the **device level** (_grouping multiple switches into one switch_). Both aim to increase bandwidth and redundancy and are often used together to aggregate links on an aggregated switch.

### What are the differences/similarities between these two and multipathing?
- Link/switch aggregation work at Layer 2 (Data Link Layer in OSI model) by aggregating physical Ethernet links into one logical connection, whereas multipathing (e.g., MPIO \[MultiPath Input Output\] for storage) keeps multiple independentg end-to-end paths for load balancing, redundancy, etc.

![LinkSwitchAggregation](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/LinkSwitchAggregation.png)

## NIC Teaming
_A link aggregation technique that groups NICs so that they appear as a single. logical NIC to the OS or hypervisor._

- Provides network traffic failover in the event of a NIC/link failure

- Distributes network traffic across NICs

- NICs within a team can be configured as active and standby

![NICTeaming](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/NICTeaming.png)

## Multipathing

- Enables a compute system to use multiple paths for transferring data to a LUN (Logical Unit Number)

- Enables failover by redirecting I/O from a failed path to another active path

- Performs load balancing by distributing I/O across active paths
    - Standby paths become active if one or more active paths fail
 
![MultiPath](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/MultiPath.png)

## Storage Resiliency Using Mirrored LUN
- Mirrored LUN is created using virtualization appliance
    - Each I/O to the LUN is mirrored to the LUNs on the storage system
    - Mirrored LUN is continuously available to the compute system
        - Even if one of the storage systems is unavailable due to failure

Is there a benefit of distributed traffic here?
- With mirrored LUNs, the host sees a single virtual LUN while a virtualization appliance (or storage software) actually writes each I/O to two backend LUNs on different storage systems; if the configuration is “active-active” or allows both sides to serve reads, read traffic can be spread across both arrays for better throughput, but writes must always go to both sides and be acknowledged, so write performance is limited by latency and the slower side—meaning any traffic-distribution benefit is mostly on reads and is secondary to the primary goal of redundancy and high availability.

- What is going on in the image?
- The host sees one LUN, a virtualization appliance mirrors all I/Os to two backend LUNs on two separate storage systems, providing continuous availability (and potentially read (not necessarily write) load-balancing) even if one storage system fails.

![StorageRes](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/StorageRes.png)

## Service Availability Zones
- A service availability zone is a location with its own set of resources and isolated from other zones
    - A zone can be a part of a data center or may even be comprised of the whole data center
    - Enables running mulitple service instances within and across zones to survive data center or site failures.
    - In the event of outage, the service should seamlessly failover across zones. 
 
- Zones within a particular region are typically connected through low latency network. This enables faster cloud service failover.


## Automated Service Failover Across Zoness
- Ensures robust and consistent failover
- Enables to meet stringent service levels. Reduces recovery time objective (RTO) --> How long it takes to recover from a failure.
- Automated failover process primarily depends on:
    - Replication across zones
    - Live migration with stretched cluster (zones in different remote locations)
    - Reliable network infrastructure between zones.
 
- Zones can be configured as active/passive and active/active.

**Active/Passive:** 
![ActivePassive](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ActivePassive.png)
We have the replication on standby, not running. In the event of failure, failover happens automatically, standby activates and becomes operational. Replication happens only one way. Only storage.

**Active/Active:**
![ActiveActive](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ActiveActive.png)
Both are running at the same time. The other system has the same services. Both have different services, but then replicate the storage. All the services migrate to the other. Replication happens both ways. Only storage. 


## Data protection overview
- Protecting critical data ensures availability of services.
    - Seamless server failover requires the availability of data
- Businesses also implement data protection solutions in order to comply with GRC.
- Individual services and associated datasets have different business values, require different data protection strategies
- Two common: Backup and replication.

**Def. Backup:** An additional copy of production data, created and retained for the sole purpose of recovering lost or corrupted data. 

- Recovery point objective (RPO) and time (RTO) are the primary considerations in selecting and implementing a specific backup strategy.
    - RPO specifies the time interval between two backups. It's the frequency of backups
    - RTO relates to the time taken to recover data from a backup
        - RTO influences the type of backup target that should be used
     
- To implement successful backup and recovery, service providers need to evaluate the backup methods along with their recovery considerations and retention requirements.

Data is an asset. 

## Guest-Level backup

![GuestLevelBackup](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/GuestLevelBackup.png)

Backup agent is installed on each VM
- Performs file-level backup and recovery
- Does not backup the VM configuration files. Because they are the image.
- Performing backup on multiple VMs on a compute system may consume more resources and lead to resource contention.
    - Impacts performance of applications running on VMs
 
This is time-consuming. If we have a high RTO then it's okay. Otherwise it's not feasible. We have a backup agent per VM. 


## Image-Level Backup
Snapshot of an image. Creates a copy of the entire virtual disk and configuration data associated with a particular VM. 
- Backup is saved as a single entity called a VM image.
    - Provides VM-image level and file-level recovery
    - No backup agent is required inside the VM to backup
    - Backup processing is offloaded from VMs to a proxy server.
 

## Drivers for Optimizing Backup

![DriversForOptimizing](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/DriversForOptimizing.png)

1. Limited budget
2. Limited backup window
3. Network bandwidth constraint
4. Longer retention period (you need to keep data for longer periods


## Data Deduplication

![Deduplication](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/Deduplication.png)

Def.: The process of detecting and identifying the unique data segments within a given set of data to eliminate redundancy. 

Deduplication process: 
- Chunk the dataset
- Identify duplicate chunks
- Eliminate the redundant chunks.

If you want redundancy, take an additional copy of the **dedpulicated segments**.

Granularity Levels: 
- File-level dedup:
    - Detects and removes redundant copies of identical files
    - Only one copy of the file is stored; subsequent copies are replaced with a pointer to the original file. Does not address the problem of duplicate content inside the files
- Sub-file level dedup:
    - Breaks files down into smaller segments
    - Detects redundant data within and across files
    - Two methods:
         - Fixed-length. Issue: small change in a block results in a shift that happens.
         - Variable-length: A change that happens in a block will be contained within the block.
     
**Source-based dedup**: 
- Eliminates redundant data at the source / backup client
- Client sends only new and unique segments across the network
- Reduces storage and network BW requirements
- Increases overhead on the backup client

At the VM level. It's the compute that generates the files. 

**Target-based dedup**: 
- Offloads dedup process from the backup client to the storage system
- Data is dedupped at target either in-line or post-process.
    - In-line: As the data comes in, identify, dedup, then store the dedup data
    - Post-process: Data is already in the storage system, then we dedup.
 

## Replication
Def.: Process of creating an exact copy / replica of the data for ensuring availability of the services. 

- Replica copies are used to restore and restart services if data loss occurs. Based on the SLA for the service being offered, data can be replicated to one or more locations.
- Can be classified as local replication (snapshot and mirroring), and remote replication (can be sync or async).
- Helps with high availability, usually done on production data.


**Local Replication (Snapshot)**: 
- A virtual copy of a set of files or volume as they appear in a particular PIT (point in time)
    - Provides the ability to restore the files or volumes if there is data loss of corruption.
 
- VM snapshot is a common snapshot technique that preserves the state and data of a VM at a specific PIT.
    - When a snapshot is created, a child virtual disk (delta disk file) is created from the base image (parent virtual disk)
    - Successive snapshots generate a new child virtual disk from the previous child virtual disk
    - Snapshots hold only changed blocks.
 
**Remote Replication (Sync.)**

 ![RemoteReplication](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/RemoteReplication.png)

 - Write is committed to both the source and the remote replica before it is ACKed to the compute system
 - Ensures that the source and replica have identical data at all times. Near-zero RPO. For each write, it happens to the replica as well, but this causes a delay for writing. 

**Remote Replication (Async.)**
![AsyncRemoteReplication](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/AsyncRemoteReplication.png)

- Write is committed to the source and immediately ACKed to the compute system.
    - Data is buffered at the source and transmitted to the remote site later.
    - Replica is behind the source by a finite amount (finite RPO)
 
Replication happens between storage systems. 

## Replication Usecase: DRaaS (disaster recovery as a service)
- Service provider offers resources to enable consumers to run their IT services in the event of a disaster.
    - Resources at the service provider location can be dedicated to the consumer or they can be shared.
 
- Replication is a key technique used by the service provider in order to offer DRaaS to the consumers
- Service provider should design, implement and document a DRaaS solution specific to a customer's infrastructure.

![DRaaS](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/DRaaS.png)

**Normal production operation:**
- IT services run at the consumer's production data center
- Replication occurs from the consumer's production environment to the service provider's data center over the network
    - Data is usually encrypted while replicating to the provider's location.
 
In the provider side, the VM instances are not allocated yet. Because they're at the consumer production data center. 


**Business Disruption**
- Business operations failover to the provider's infrastructure in the event of a disaster at the consumer's data center.
    - Users at the consumer organization are re-directed to the cloud
 
- Typically, VM instances are created from a pool of compute
    - Connect replicated storage to each of the newly activated VMs


![DRaaSBusinessDisruption](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/DRaaSBusinessDisruption.png)

Now, the VM instances are booted up and we connect the replicated storage to the newly activated VMs. 
