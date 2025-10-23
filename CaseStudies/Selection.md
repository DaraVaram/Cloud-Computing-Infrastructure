# Case Study 1: Software Development Organization

## Company Profile: 
A software development organization with 5000 employees and more than 2 million customers. The organization operates two data centers at different locations, and business applications run on more than 300 physical, heterogeneous compute systems. Some of the applications are proprietary.

## Organization's Challenges: 
Coping with fast-changing customer demands is difficult, and rapid development is a challenge with the current infrastructure, which has a utilization of less than 20 percent. New application deployment takes a long time as it involves purchasing new systems, installing software, and configuring network, storage, and security.

### A. Improve the utilization of the infrastructure resources
- Name the key technology that can contribute to this deliverable
- Describe how this can be achieved in compute, storage and networking

**Answers:**

The key technology is virtualization. Virtualization generally deals with improving the utilization of the infrastructure (compute, networking, and storage) that physically exists. In the context of the three things: 
- For compute, virtualization enables multi-tenancy, meaning that the compute systems themselves will have better utilization as they are assigned across multiple users
- For storage, we have this idea of resource pooling, which aggregates everything into one pool, 
- For networking, we have things like NIC teaming, link aggregation, etc..., traffic shaping, all of that good stuff


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

Network utilization: Virtual LANs, etc...

### B. Ability to have high availability of data.
- Name and describe a technology from the physical layer that enables this deliverable. Make sure to describe how it delivers this requirement.

Here, we can do SAN and RAID. 

-------------------------
# Case Study 2

## Company profile: 
RAALI A software development organization with 5000 employees and more than 2 million customers

- Organization operates two data centers at different regions
- Business applications run on more than 300 physical compute systems
- Some of the applications are proprietary
- Infrastructure resources are heterogeneous

## Organization’s Challenges
- Coping with fast changing customers’ demands
- Rapid development and deployment are very difficult with the current infrastructure
- Utilization of the infrastructure resources is less than 20 percent
- Currently each server is utilized by a single OS and the applications are deployed on the single OS. On Average, each server resource utilization is between 20 to 30 percent
- New application deployment takes some time as it involves: Purchasing new compute server, Installing the OS and software, Configuring network and storage, Configuring security

## Help RAALI with the setup option/s that they may work on to…
A. Improve the utilization of the infrastructure resources
- Virtualization. This is because we are logically abstracting the resources. We are working with 300 compute nodes, which effects the utilization. Through virtualization, we could map these to virtual resources and add them to a resource pool, which then enables us to improve utilization

B. Ability to have high availability of data: Name and describe a technology from the physical layer that enables this deliverable. Make sure to describe how it delivers this requirement
- SAN and RAID: RAID for high availability, we can talk about mirroring, striping and parity here. SAN because they have different regions (specifically 2 data centers as mentioned in the question), so they can have a SAN to access all of the virtual storage.

C. Increase in performance in storage accessibility: Name and describe a techniques from the control layer. Make sure to describe how it delivers this
requirement
- Cache tiering: We have the secondary cache business from the SSD, it improves I/O performance
- Storage tiering: Each tier has specific pools, so they just have access to those, and this improves the performance. For the very important clients, for the higher-ups in the company, etc...

D. Accommodate increased peak workload that may occur from time to time: Name and describe one technique from the compute and another from the storage. Make sure to describe how it delivers this requirement.
- For compute, VM load balancing: go from over-utilized hypervisors to under-utilized, this is done at creation.
- For storage: Cache tiering here again. The cache allows for better accessibility, which is good for availability.

-------------------------
# Case Study 3: School Bus Management System

## Company Profile: 
A start-up company is creating a "School Bus Management System" software product. They expect request volume to grow from 10,000 requests/month in the first year to 1,000,000 requests/month in the second year, with peaks in the morning and afternoon. They are unsure about unpredictable request loads (e.g., field trip days). The database is expected to be 5TB in the first year. The company has a start-up fund of AED 20,000 and has no existing infrastructure.

## Organization's Challenges: 
The infrastructure fund is limited, and they should not pay for unused resources. They need an environment that can cope with changing customer demands and allow for rapid development. The production software must be highly available, scalable, secure, and handle unpredicted growth, as any downtime could result in losing customers.

A. Describe the different services within the cloud and which cloud service would work best for their case and why.
- IaaS: You have access to the entire stack except the underlying cloud infrastructure. Free to do whatever you want, mostly. OS, programming framework, database, and application.
- PaaS: Just have access to the application, you can only deploy and create applications
- SaaS: You can only access the application.

They do not have any infrastructure. They also do not have any money, so ideally, you'd want to go with PaaS so you have control over the application, but do not have the extra management / administrative responsibilities. 

B. Describe the cloud deployment models and which one works best for their case and why.
- Private (external / on-premise)
- Public
- Community
- Hybrid

The best option for them would be the public cloud: First of all, they do not have the infrastructure, so it would have to be externally hosted. They're doing this for a single school, not a variety, so it cannot be community either, and they do not have the funding to go for a private cloud. Therefore, the best option for them would be the public cloud. Since they do not know how to deal with increased workloads, public also works best because they can automatically provision more resources once they hit a certain threshold. 

Public is pay-as-you-go, scalability, high availability, etc...

C. Let the organization know how they can set up their product to be highly available and to scale based on demand without having to pay for resources that are not used.
- Virtual storage provisioning: Thin LUNs so you pay as you go for the data / storage
- You can scale through a variety of methods, built into the cloud characteristics, you can provision more resources automatically, use Azure

--------------------------------
# Case Study 4: AAAD Inc. Health Services

## Company profile: 
AAAD Inc. is a start-up creating a system to provide health services to the elderly using data from wearable sensors. This data will be stored on the cloud. The system will be used by the elderly, their relatives, and the healthcare community (doctors, nurses). They expect rapid growth from 100,000 requests in the first two months to 900,000,000 requests per month within the following five months, with unpredictable peaks. The database is expected to contain 10TB of data in the first year. They have an AED 10,000 start-up fund.

## Organization's Challenges: 
The deployment fund is limited, and they cannot pay for unused resources. They are interested in deploying the software directly without managing servers. The application must be highly available, scalable, and secure to handle unpredicted growth, as downtime is not an option.

A. Name and describe the adequate cloud service model that would work best for their case and why.
- PaaS, because they don't have money. They don't want to manage things, they're only interested in deploying the software. So it can't be SaaS or IaaS. 

B. Name and describe the cloud deployment model that would work best for their case and why.
- Public, because they don't want to manage anything. Cost efficient (pay-as-you-go), allows for scalability, etc...

C. Let AAAD know how they can set up their product to be highly available and to scale based on demand without paying for resources that are not used.
- Measured service, rapid elasticity, just use Azure again. 

D. A consultant suggested a "cloud-ready converged infrastructure." Help the team understand what this is and if this opinion is valid for their case and why.
- Cloud-ready infrastructure: pre-configured, already set up, ready to go and use whenever you want, etc...
- This opinion is not valid, because they don't want to physically own anything, they don't have the money, and they also don't want to manage anything.

----------------------------------
# Case Study 5: RAALI Content Management

## Company Profile: 
RAALI is an on-demand content management organization with 1 million customers. They operate two data centers with heterogeneous infrastructure. Each server is utilized by a single OS, and average resource utilization is between 20 to 30 percent.

## Organization's Challenges: 
Coping with fast-changing customer demands and rapid deployment is difficult. New application deployment is slow, involving purchasing new hardware, installing software, and configuring the environment.

A. Tell RAALI how they can transform their data center to a cloud-based data center to serve their operations requirements.
- They need to virtualize things! Create resource pools using virtualization software, provision them to the clients and administration as needed. Should improve resource utilization.
- Instead of a single OS, doing it through VMs is probably a good idea, so it doesn't affect all the users
- Automated resource provisiong, automated storage tiering, cache tiering, etc...

B. What is the name of the software that is installed on a compute system and enables multiple OSs to run concurrently? Describe the two main components that exist in that software.
- Hypervisor:
    - Hypervisor kernel: like the OS kernel, it's designed to run VMs concurrently
    - VMMs: Per VM, abstracts the physical resources
 
C. Describe a storage technique from the virtualization layer that enables creating storage volumes based on host demand. Explain how this technique can help RAALI. 
- Virtual storage provisioning through thin LUNs. How does this help RAALI?
    - You show more than what's physically there. Expands and decreases as needed.
    - Simplified storage management, cheaper
 
D. Describe a way that allows RAALI to serve requests that require proprietary software with specific VM capabilities in a minimal amount of time.
- VM appliance: For a specific function. Simplifies the delivery, it's only for that application, installation is easier for VM appliances. The word proprietary software, so it's can't be VM template
