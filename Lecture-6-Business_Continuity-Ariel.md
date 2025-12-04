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
    - 
    -  
