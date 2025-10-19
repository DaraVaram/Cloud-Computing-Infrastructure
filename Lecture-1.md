# Introduction to Cloud Computing
Cloud Computing works with **distributed systems**. 

Classical Computing: 
- You can buy and own hardware, system software, applications, etc... to meet peak needs.
- You would have to set it up, manage it, configure, test, and only then would you be able to manage it.
- This would be a process that is cyclic, around 18 months in time, and would cost a fortune.

Cloud Computing: 
- The perception back in the day was that cloud had zero security, because it's on a public domain. However, this is not the case: people just need to be more informed on what the cloud is.
- The key difference here is that all you need to do is subscribe and then you can immediately use the service.
- Is this cheaper? Not necessarily. It depends on your use-case. This is based entirely on QoS (quality of service). Every asset is a service.
- It's definitely more convenient to use.

The Cloud Computing Phenomena: 
- The adoption of Cloud Computing is much more widespread in organizations.
- Seen as a leading technology by businesses to drive optimization and innovation.
- In short, if you need computing power, just use the cloud!

What's new?
- The illusion of infinite computing resources. The caveat here is that it's not really infinite, it's bounded by what physically exists in the infrastructure of, for example, a particular data center or server. This **eliminates** the need to plan too far ahead for provision. This aids in this illusion that there's an infinite amount of compute in this pool of resources.
- **Elimination of up-front commitment**: You can start small, provision as much as you need as you go / when you need it. If necessary, you can scale up / scale out at a later stage. This also gives you the ability to pay for exactly what you need, when you need it.


Why is it hot?
- We generally need more compute, there's a higher demand for resource availability, since there's more complex tasks to be ran.
- Higher demand for scalability, and we need to cut costs as the scale increases. There's a lot of people, energy and infrastructure needed if you want to take a classical computing approach, but with the cloud, you just need to have access to the cloud. That's pretty much it.
- Companies like Google, Amazon, and Microsoft have their own large data centers. They offer pay-as-you-go plans, allowing customers to have access to Virtual Machines (VMs) where they can do their ''stuff''.

There's some details here regarding the history. In 1969, some guy said:

"As of now, computer networks are still in their infancy, but as they grow up and become sophisticated, we will probably see the spread of **computer utilities**, which, like present electric and telephone utilities, will service individual homes and offices across the country."

This notion of computer utilities: He envisioned back then that we'd be able to pay for using computers without having to set it up ourselves, much like our electrical / telephone systems. This would be a _pay-for-use_ service. We have essential utiliies (like water, gas, electricty, telephone, etc...), so why not computers as well? That's exactly what Cloud Computing aims to provide.

![Cloud Computing: The 5th utility!](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/Cloud%20Computing%20(5th%20Utility).png)

_Small little side note:_ Cloud Computing used to be called Grid Computing (See the paper ["Economic-based modelling for resource scheduling in grid computing (2012)"](https://ieeexplore.ieee.org/abstract/document/6221877) by Dr. Raafat.

Now, we ask the real question: **What is Cloud Computing?**
- _A model for enabling **ubiquitous**, **convenient**, **on-demand** network access to a **shared pool** of configurable computing resources, (e.g., servers, storage, networks, applications, and services) that can be **rapidly provisioned** and released with **minimal management effort** or **service provider interaction**._
- A cloud is a collection of network-accessible IT resources, which consists of shared pools of HW / SW resources deployed in **data centers**.
- The cloud model enables consumers to hire a providers' IT resources as a **service**.
- Cloud Computing is not managed by humans. It's managed by systems (the control and the orchestration layers - we'll get to this later)
- Multi-tenancy: Multiple users using / sharing resources at the same time.

 
