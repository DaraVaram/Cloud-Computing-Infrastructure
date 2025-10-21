---
layout: lecture
title: "AI Summary - Virtual Layer"
lecture_number: 4
date: 2024-01-04
collection: ai_notes
---
This guide deepens the lecture with practical patterns, pitfalls, and exam questions on virtualization, resource pools, and virtual resources.

## 1) Virtualization and the Virtual Layer
- Virtualization abstracts compute, network, and storage to allow multiple instances per physical asset or aggregate many physical assets under a single logical construct.
- Benefits: utilization, cost, management simplicity, deployment speed, flexibility; enables resource pooling and rapid elasticity.
- Virtual layer entities:
  - Virtualization software (hypervisors; network/storage virtualization).
  - Resource pools (CPU, memory, storage, bandwidth, identity).
  - Virtual resources (VMs, vSwitches, VLAN/VSAN, LUNs, virtual disks/files).

## 2) Compute Virtualization: Hypervisors
- Hypervisor kernel + VMMs per VM; abstracts hardware and schedules multiple VMs.
- Types:
  - Bareâ€‘metal (Type 1): runs on hardware; high performance and isolation; suited for prod clouds (e.g., ESXi, Hyperâ€‘V, KVM). Requires certified hardware.
  - Hosted (Type 2): runs atop an OS; great for dev/test (e.g., VMware Workstation, VirtualBox).

Practical considerations:
- CPU virtualization extensions (Intel VTâ€‘x, AMDâ€‘V), nested virtualization support.
- NUMA topology awareness; CPU overcommit ratios; ballooning and swapping risks.

## 3) Network Virtualization
- Virtual switches, VLANs/Private VLANs, distributed switches across hosts.
- Softwareâ€‘defined networking (SDN) concepts: control plane decoupled; overlays (VXLAN, GRE) though not explicitly in slides, valuable to know.
- Use cases: multitenancy, microâ€‘segmentation, stretch L2 domains for VM mobility.

## 4) Storage Virtualization
- Virtual volumes/LUNs, virtual disk files (VMDK/VHDX), virtual arrays.
- Thin vs thick provisioning:
  - Thin: allocate on demand in extents; great for efficiency and unpredictable growth; may have performance variability.
  - Thick: full allocation upfront; predictable performance; consumes capacity immediately.

## 5) Resource Pools
- Logical abstraction of aggregated resources managed collectively; support dynamic allocation per demand.
- Examples:
  - CPU/memory pools across host clusters.
  - Storage pools across arrays; can form higherâ€‘level pools.
  - NIC bandwidth pools via link aggregation/NIC teaming.
- Pool grading for services (Gold/Silver/Bronze) ties to performance, media, RAID, and features (tiering, QoS).

Capacity planning tips:
- Track overcommit ratios; reserve for critical tiers; set limits/shares for fairness.
- For thin pools, monitor headroom and implement reclamation.

## 6) Virtual Machines and Artifacts
- VM hardware: vCPU, vRAM, vNICs, virtual disks; appears as physical to guest OS.
- Key files: config, virtual disk(s), memory state (suspend), snapshot deltas, logs.
- File systems: clustered hypervisor file systems enable concurrent host access and HA; shared file systems for storing VM files externally.
- VM console: local client, web console, or RDP/SSH through guest.
- VM templates and cloning: master images for consistency; patch/update via convertâ€‘toâ€‘VM â†’ update â†’ convertâ€‘toâ€‘template.
- Virtual appliances: OVFâ€‘packaged preconfigured VM(s) dedicated to functions (SaaS component, router, firewall).

## 7) Virtual Networks
- VM Network: logical L2 within a host/cluster; connects VMs and uplinks to physical network.
- VLAN (12â€‘bit ID): segment L2; membership via port/MAC/protocol/subnet/application.
- Private VLANs: isolate nodes within a VLAN (isolated/community) to scale tenants and improve security.
- Stretched VLAN: extend L2 over L3 WAN; enables VM mobility without IP change; encapsulation overhead and failure domains must be considered.
- VSANs: logical FC/FCoE fabrics; independent services and addressing; disruptions isolated per VSAN; can be stretched like VLANs.
- FCoE mapping: dedicate a VLAN per VSAN; avoid mixing regular LAN traffic.

## 8) Practice Questions
1) Compare thin and thick LUNs for a VDI deployment; include performance, capacity risk, and operational tooling.
2) Explain when a hosted hypervisor is acceptable and when bareâ€‘metal is required; include security and performance arguments.
3) Design a multiâ€‘tenant network using VLANs and PVLANs; include isolation between tenants and shared services (e.g., DNS).
4) You must extend a VM network across sites for live migration. What are stretched VLAN tradeâ€‘offs and alternatives?

## 9) Quick Facts
- Type 1 hypervisors for production; Type 2 for dev/test.
- Thin LUNs consume from pools on demand; monitor and reclaim.
- VSANs isolate FC control/data planes; map VSANs to dedicated FCoE VLANs.
