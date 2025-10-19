# Introduction to Cloud Computing
Cloud Computing works with **distributed systems**. 

Classical Computing: 
- You can buy and own hardware, system software, applications, etc... to meet peak needs.
- You would have to set it up, manage it, configure, test, and only then would you be able to manage it.
- This would be a process that is cyclic, around 18 months in time, and would cost a fortune.

## Cloud Computing: 
- The perception back in the day was that cloud had zero security, because it's on a public domain. However, this is not the case: people just need to be more informed on what the cloud is.
- The key difference here is that all you need to do is subscribe and then you can immediately use the service.
- Is this cheaper? Not necessarily. It depends on your use-case. This is based entirely on QoS (quality of service). Every asset is a service.
- It's definitely more convenient to use.

## The Cloud Computing Phenomena: 
- The adoption of Cloud Computing is much more widespread in organizations.
- Seen as a leading technology by businesses to drive optimization and innovation.
- In short, if you need computing power, just use the cloud!

## What's new?
- The illusion of infinite computing resources. The caveat here is that it's not really infinite, it's bounded by what physically exists in the infrastructure of, for example, a particular data center or server. This **eliminates** the need to plan too far ahead for provision. This aids in this illusion that there's an infinite amount of compute in this pool of resources.
- **Elimination of up-front commitment**: You can start small, provision as much as you need as you go / when you need it. If necessary, you can scale up / scale out at a later stage. This also gives you the ability to pay for exactly what you need, when you need it.


## Why is it hot?
- We generally need more compute, there's a higher demand for resource availability, since there's more complex tasks to be ran.
- Higher demand for scalability, and we need to cut costs as the scale increases. There's a lot of people, energy and infrastructure needed if you want to take a classical computing approach, but with the cloud, you just need to have access to the cloud. That's pretty much it.
- Companies like Google, Amazon, and Microsoft have their own large data centers. They offer pay-as-you-go plans, allowing customers to have access to Virtual Machines (VMs) where they can do their ''stuff''.

There's some details here regarding the history. In 1969, some guy said:

"As of now, computer networks are still in their infancy, but as they grow up and become sophisticated, we will probably see the spread of **computer utilities**, which, like present electric and telephone utilities, will service individual homes and offices across the country."

This notion of computer utilities: He envisioned back then that we'd be able to pay for using computers without having to set it up ourselves, much like our electrical / telephone systems. This would be a _pay-for-use_ service. We have essential utiliies (like water, gas, electricty, telephone, etc...), so why not computers as well? That's exactly what Cloud Computing aims to provide.

![Cloud Computing: The 5th utility!](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/Cloud%20Computing%20(5th%20Utility).png)

_Small little side note:_ Cloud Computing used to be called Grid Computing (See the paper ["Economic-based modelling for resource scheduling in grid computing (2012)"](https://ieeexplore.ieee.org/abstract/document/6221877) by Dr. Raafat.

## Now, we ask the real question: **What is Cloud Computing?**
- _A model for enabling **ubiquitous**, **convenient**, **on-demand** network access to a **shared pool** of configurable computing resources, (e.g., servers, storage, networks, applications, and services) that can be **rapidly provisioned** and released with **minimal management effort** or **service provider interaction**._
- A cloud is a collection of network-accessible IT resources, which consists of shared pools of HW / SW resources deployed in **data centers**.
- The cloud model enables consumers to hire a providers' IT resources as a **service**.
- Cloud Computing is not managed by humans. It's managed by systems (the control and the orchestration layers - we'll get to this later)
- Multi-tenancy: Multiple users using / sharing resources at the same time.

 What are the essential **cloud characteristics**? This is how we will answer case-study based questions in exams. If a system does not have all 5 of these, then it cannot be defined as a cloud computing system. 
 - On-demand self-service
 - Broad network access
 - Resource pooling
 - Rapid elasticity
 - Measured service

Let's go into the details of each one of these. 

| Characteristic | Definition | Discussion |
|--------|--------|--------|
| On-demand self-service | A consumer can **unilaterally provision computing capabilities**, such as server time and network storage, as needed automatically without requiring human interaction with each service provider. | Consumers use a web-based self-service portal (think about Azure) to view the service catalog and request cloud-related services. This enables consumers to provision these services in a simple, flexible manner. This whole thing means there's no human intervention. There's no one guy that builds it for you. Because of this, there's little to no delay in the provisioning of resources, it's provided **when and as required**. Reduces the time needed to provision new or additional IT resources. Let's define provisioning: Related to the actual **building** of the system that you need. 
| Broad network access | Capabilities are available over the network and accessed through standard mechanisms that promote use by heterogeneous thin or thick client platforms, (e.g., mobile phones, tablets, laptops, and workstations). | Consumers access cloud services on **any** client or end-point device from **anywhere** over a network. The standard mechanisms here **should** support the use of heterogenous client platforms. This means that we can use any device we want as long as that device can connect to the network. 
| Resource pooling | The provider’s computing resources are pooled to serve multiple consumers using a **multi-tenant model**, with different **physical** and **virtual** resources dynamically assigned and reassigned **according to consumer demand**. There is a sense of **location independence** in that the customer generally has no control or knowledge over the **exact location** of the provided resources but may be able to specify location at a **higher level of abstraction** (e.g., country, state, or datacenter). Examples of resources include storage, processing, memory, and network bandwidth.| How we saw this in Azure was through the regions and the zones. This allows us to improve resource utilization, and allows flexibility provision. Also allows us to reclaim resources as necessary. The resource pooling is specifically what allows multi-tenancy through the aggregation of pooled resources. 
|Rapid elasticity | Capabilities can be **elastically provisioned** and **released**, in some cases **automatically**, to scale rapidly outward and inward commensurate with demand. To the consumer, the capabilities available for provisioning often **appear to be unlimited** and can be appropriated in any quantity at any time.| Consumers can adapt variations in workloads and maintain performance. They may be able to avoid excessive costs from the over-provision of resources. You basically get what you need at that moment. **Rapid elasticity** in particular allows the capability to scale-up or scale-out based on demand.  <ul><li> Scale-up: upgrading the machine itself, e.g., from 2 CPUs to 4 CPUs.</li><li>Scale-out: Adding more machines. For example, if your CPU util. reaches 90%, another resource will automatically be provisioned.</li></ul> All of this would be under the service-level agreement between the consumer and the provider. This contract **guarantees** a certain level of quality of resources and services. Also, better fault tolerance --> better availability. |
| Measured service | Cloud systems automatically **control** and **optimize** resource use by leveraging a **metering capability** at some level of abstraction appropriate to the type of service (e.g., storage, processing, bandwidth, and active user accounts). Resource usage can be monitored, controlled, and reported, providing transparency for both the provider and consumer of the utilized service.| This enables the billing of cloud services. Monitoring the resources can help providers determine the capacity of the services and planning ahead.|



## What are the benefits of using Cloud Computing?
(From Ariel's notes on the slides): 
- Scalability
- Pay-as-you-go
- Computational power
- No need to hire people to manage the computational resources (you may just need to hire one "cloud expert"), because the software manages the data center anyway.
- Physical space on-site is not required, because you don't have the resources yourself. This is the case unless you host your own data center on-site. On this note, consider the **hybrid approach**: You have your own data center (or within the region, at least), and then you if need _more_ resources, you can provision more from the cloud.

### Cloud Computing Benefits: 
| Benefit | Description |
| ------- | ----------- |
|Business Agility | <ul><li> Enables quick resource provisioning </li><li> Facilitates "innovation" </li> <li> Reduces time-to-market (basically the amount of time it takes for a product to be conceived and then made available for use) </li></ul> |
|Reduces IT Costs | <ul><li> Reduces up-front capital spending </li><li> Improves resource utilization (better resource util. --> less spending on resources) </li> <li> Reduces energy and space consumption </li></ul> |
|High Availability | <ul><li> Ensures resource availability based on consumer requirements </li><li> Enables fault tolerance </li> </ul> |
| Business Continuity | <ul><li> Reduces impact of downtime (because on high availability) </li><li> Example: cloud-based backups (if you lose the data locally, you can still get it back from the cloud). </li> </ul> |
| Flexible Scaling | <ul><li> Enables scaling of resources to meet the demand </li><li> Unilateral* and automatic resource scaling </li> </ul> |
| Flexibility of Access | <ul><li> Enables access to services from **anywhere**</li><li> Eliminates dependency on a **specific** end-point device. You can access it from anywhere, regardless of the device.  </li> </ul> |

*Unilateral: The user doesn't need to communicate to the provider at all. It's self-service at the end of the day.
