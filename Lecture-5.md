# Control Layer
Definition: Includes software tools that are responsible for **managing** and **controlling** the underlying cloud infrastructure and **enables provisioning of IT resources** for creating cloud services. 

![ControlLayer](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ControlLayer.png)

The control can be deployed on top of the virtual layer or on top of the physical layer. It receives requests from the service and orchestration layers, and then provisions the required resources to fulfill the service requests. Key functions of the control layer are: 
- Resource configuration
- Resource provisioning
- Monitoring resources

It's in between. It takes requests from above, and makes sure that the resources below are able to provide. It's the **line manager** of the cloud stack.

## Control Software
This lives inside the control layer. Ties together the underlying resources and works in conjunction with virtualization software to enable: 
- Resource **pooling** (It does not do the actual resource pooling, it just "sends the green flag" to go ahead. The virtual layer is what actually does it)
- **Dynamic** allocation of resources for services
- Optimizing **utilization** and the operation of resources

This provides a **complete view** of all the resources in the cloud environment. 
- Enables **centralized management** of IT resources.

There's 2 types of control software: 
1. Element manager
2. Unified manager


## Element Manager
Infrastructure component vendors may provide the element managers as built-in _or_ external software. It is required to manage infrastructure compoenents independently. There is going to be a question on the exam about this. It is a amanger for a specific resource, such as compute, storage, or network.  

![ElementManager](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/ElementManager.png)

What does the figure tell us? We have three different EMs, they each go through an API, and then they handle whatever it is that they're supposed to handle. Keep in mind that this is in the control layer. We **get access** to the virtual layer through the API. 

### Key tasks performed by the EM
1. Enables performing **initial component configurations** and allows modifications to it. For example, installing guest OS, configuring zoning, security settings, VLANs, RAID, etc...
2. Allows **expanding** resource capacity (detects newly added resources and adds them to an **existing pool**)
3. Monitors the infrastucture component for performance, availability, capacity and security.

## Unifed Manager (UM)
Provides a **single management interface** for configuring and provisioning resources for applications and services. We no longer have a breakdown into specific elements / resources. It's all-in-one inclusive. 

![UnifiedManager](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/UnifiedManager.png)

To coordinate the different EMs together, we have the UM on top, which communicates with the EMs using API. The unified manager manages the element managers. It's sort of like a delegation thing. 

- Exposes APIs that can be integrated with the orchestration layer (to the layer above) to **automate service provisioning**. You will get a request from orchestration layer. The UM gets it, talks to the designated EM through APIs, which then takes the request to the layers underneath.
- Enables **adding or removing infrastructure** resources to an **already-provisioned** service
- Performance **compliance checks** during resource configurations
- Provides a **dashboard** showing **resource configurations** and **utilization**. This could be a trick question, because someone might think that having a dashboard means it's in the service layer.
    - Allows administrator to perform monitoring, reporting, and root-cause analysis.
