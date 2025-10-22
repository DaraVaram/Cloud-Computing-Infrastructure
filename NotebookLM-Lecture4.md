## 1. An administrator needs to deploy a hypervisor for a development and testing environment on their existing workstation operating system. Which type of hypervisor is most suitable for this purpose?
- Hosted hypervisor ✅

## 2. What is the primary function of a resource pool in a cloud computing reference model?
- To logically abstract and aggregate physical computing resources for collective management. ✅

## 3. Which specific VM file contains information such as the VM's name, BIOS settings, and memory size?
- Configuration file ✅

## 4. A cloud provider needs to provision storage for a client whose space consumption is difficult to forecast. To maximize storage utilization and cost-efficiency, which type of LUN is the best choice?
- Thin LUN ✅

## 5. What is the function of a Virtual Machine Manager (VMM) within a hypervisor?
- It abstracts the physical hardware and is assigned to an individual VM ✅

Justification: VMM is assigned to a single VM

## 6. A network administrator needs to enable Layer 2 communication for a group of VMs across two geographically separate data centers connected by a Layer 3 WAN. Which type of virtual network would achieve this?
- Stretched VLANs ✅

## 7. What is a virtual appliance?
- A pre-configured VM with a guest OS and an application for a specific function ✅

An example of this would be a firewall. 

## 8. In the context of a VM network, which component functions as an Inter-Switch Link (ISL) between a virtual switch and a physical Ethernet switch?
- Uplink NIC ✅

## 9. Which of the following is a key benefit of virtualization that involves creating a multitenant environment?
- It optimizes the utilization of IT resources ✅

## 10. What is the correct sequence of steps in the virtualization process?
- Deploy virtualization software, create resource pools, create virtual resources ✅

Why? Because first you have to install the software on the physical devices, then, aggregate the resources into a pool, then you can carve out the virtual resources from this pool. 

## 11. Which two cloud infrastructure characteristics are directly enabled by the virtual layer?
- Resource pooling and rapid elasticity ✅

## 12. When configuring a Fibre Channel over Ethernet (FCoE) SAN, what is a key consideration for mapping VLANs to VSANs?
- Each VSAN should be mapped to a dedicated VLAN ✅

Justification: The mapping determines which VLAN carries a VSAN traffic. Mapping considerations:

- Configure a dedicated VLAN for each VSAN
- VLANs configured for VSANs should not carry regular LAN traffic 
