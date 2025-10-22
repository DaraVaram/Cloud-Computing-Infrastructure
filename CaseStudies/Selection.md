# Case Study 1: Software Development Organization

## Company Profile: 
A software development organization with 5000 employees and more than 2 million customers. The organization operates two data centers at different locations, and business applications run on more than 300 physical, heterogeneous compute systems. Some of the applications are proprietary.

## Organization's Challenges: 
Coping with fast-changing customer demands is difficult, and rapid development is a challenge with the current infrastructure, which has a utilization of less than 20 percent. New application deployment takes a long time as it involves purchasing new systems, installing software, and configuring network, storage, and security.

### 1. Improve the utilization of the infrastructure resources
- Name the key technology that can contribute to this deliverable
- Describe how this can be achieved in compute, storage and networking

**Answers:**

The key technology is virtualization. Virtualization generally deals with improving the utilization of the infrastructure (compute, networking, and storage) that physically exists. In the context of the three things: 
- For compute, virtualization enables multi-tenancy, meaning that the compute systems themselves will have better utilization as they are assigned across multiple users
- For storage, we have this idea of resource pooling, which aggregates everything into one pool
- For networking, we have things like NIC teaming, link aggregation, etc...


In more details, for compute, we would have to use some sort of virtualization software such as hypervisors to allow the use of multiple VMs on a single physical compute system. We would then be able to abstract the physical hardware and map it to the created virtual hardware. Some things that fall under this are: 
- Hyper-threading (single core acts as 2 cores, recall this idea of having one car with 2 drivers that take shifts)
- Memory page sharing: Allows over-commitment of memory, eliminates redundancies, etc...
- Dynamic memory allocation
- VM load balancing

Storage utilization: We'd have to deal with things like: 
- Virtual storage provisioning (thin LUNs), that allow us to extend what's actually available and what is promised. This causes efficient utilization of the resources.
- Storage space reclamation
- Storage rebalancing
- Automated storage tiering

Network utilization: Virtual LANs
