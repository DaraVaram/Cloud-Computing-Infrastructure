## 1. List the Cloud Computing Service Models. Describe only one of them

The Cloud service models are: 
1. PaaS (Platform as a service): The consumers' resources are just the platform. Cannot manage or control the underlying cloud infrastructure including network, servers, OS, or storage. Basically, you can only create your own applications on the cloud and deploy them, nothing else. 
2. SaaS (Software as a service) The provider provides everything. The consumer can only **use** the cloud to run their own applications. The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, storage, or even individual application capabilities. You can only access the apps that are provided. Like Gmail.
3. IaaS (Infrastructure as a service) The consumer does not manage or control the underlying cloud infrastructure but has control over operating systems, storage, and deployed applications. Computational resources are provided to the consumers. You have the freedom to do whatever you want (there's some limits to this, like virtualization in a system)

## 2. List the five cloud computing characteristics discussed in class. Describe only one.

1. On-demand self-service: A consumer can unilaterally provision computing capabilities, such as server time and network storage, as needed automatically without requiring human interaction with each service provider. No human interaction between provider and consumer. 
2. Rapid elasticity: Elastically provisioned and released, in some cases automatically. 
3. Resource pooling: Multi-tenant model, with different physical and virtual resources dynamically assigned and reassigned according to consumer demand. 
4. Broad network access: Can be accessed from anywhere, at any time, regardless of the compute power of your device. 
5. Measured service: Billing. Basically, pay as you go. Automatically control and optimize resources by leveraging a metering capability.

## 3. List the cloud computing deployment models. Describe only one.

1. Public: Basically, anyone can access the cloud. IaaS, PaaS, SaaS, etc... through Azure or AWS are all part of the public cloud. 
2. Private: On-premise or external, only for the specific organization, the access levels are managed within the private cloud itself. Exclusive access. 
3. Community: Cloud that's shared between consumers that have a similar goal. Private for a group of entities only, like a chain of hospitals, or governmental entities. 
4. Hybrid: The idea of having something private and then extending to off-site during peak hours. This is just cloud bursting. 


## 4. What are the cloud computing characteristics that are provided by virtualization? Describe how the virtualization layer delivers on those characteristics.

1. Rapid Elasticity
2. Resource Pooling

## 5. Describe the NAS deployment options.

1. Traditional NAS (Scale-up): Capacity and performance of a single system is scaled by upgrading or adding more NAS components
2. Scale-out NAS: We add additional nodes to the cluster. Multiple NAS modules that act as if they're one.

## 6. What is the role of the cloud broker? [MY OWN CREATION]

The cloud broker provides cloud service brokerage. Manages the use, performance and delivery of services from the cloud. Basically acts like an intermediary between the providers and the consumers. Can aggregate multiple cloud services through the broker, not necessarily through the same vendor / provider. Gives us this flexibility. The broker provides an interface / API to access or create services. 

## 7. What are the design goals of a distributed system? [MY OWN CREATION]

1. Accessibility: The resources should be easily accessible, should be accessible remotely, and we should be able to share them in an efficient, controlled way.
2. Transparency: Complexities need to be hidden from the user. Access (hide how the objects / data is accessed, location (hide where the physical resources themselves are), migration (hide that an object may move from one place to another), failures (hide the failure and recovery of an object), etc... 
3. Openness: Same concept as flexibility or standardization. System that provides components that can be easily integrated into other systems
4. Scalability: Three dimensions: size (can add a lot of users, basically, without any loss in performance), administrative (can be easily managed even if we have a lot of resources to manage), and geographical (resources can be far apart).

## 8. Describe the components of the reference model. [MY OWN CREATION]

Service layer: service catalog, self-service portal
Service orchestration layer: orchestration software
Control layer: contains control software
Virtual layer: resource pools, virtual resources, virtualization software
Physical layer: compute, storage, network

Then business continuity (fault tolerance, back-up, replication) and security (security mechanisms, GRC) that apply to all of them. 

## 9. Describe the role of the business continuity layer. [MY OWN CREATION]

