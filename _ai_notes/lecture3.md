---
layout: lecture
title: "AI Summary - Physical Layer"
lecture_number: 3
date: 2024-01-03
collection: ai_notes
---
This guide expands the lecture into implementationâ€‘ready knowledge with checklists, comparisons, and exam prompts.

## 1) Physical Layer Overview
- Building blocks: compute systems (rack and blade), storage systems (block/file/object), and networks (computeâ€‘compute, computeâ€‘storage, interâ€‘cloud).
- Objective: reliable execution, durable storage, and performant/secure connectivity.

## 2) Compute Systems
- Components: CPU, RAM, ROM/firmware, motherboard/chipset, NIC, GPU (optional).
- Rackâ€‘mounted vs Blade:
  - Rack: flexible, standard 19" racks; easier incremental adoption; more cabling; perâ€‘server management.
  - Blade: high density; shared chassis power/cooling/networking/management; simplified cabling; great for scale, but chassis vendor lockâ€‘in.
- Hosting models: shared vs dedicated; virtualization delivers isolation with better utilization.

Sizing and HA tips:
- N+1 host redundancy for clusters; consider power/cooling headroom.
- NUMA awareness for VM sizing; pinning/affinity for latencyâ€‘sensitive workloads.

## 3) Storage Fundamentals
- Devices: Magnetic HDD (capacity, sequential throughput) vs SSD/Flash (IOPS, low latency, lower power).
- RAID techniques:
  - Striping (RAID 0): performance; no protection.
  - Mirroring (RAID 1): protection; 50% usable.
  - Parity (RAID 5/6): efficient protection; write penalty; RAID 6 tolerates 2 disk failures.
  - Nested (RAID 10): striping + mirroring; performance + protection; capacity 50% usable.
- Data access methods drive architecture:
  - Block: volumes presented to hosts as disks; filesystems built by hosts. Protocols: FC, iSCSI, FCoE.
  - File: NAS exposes files over NFS/SMB; ideal for sharing and user directories.
  - Object: flat address space with metadata; accessed via REST; great for scale/immutability (e.g., backups, logs, media).
  - Unified: arrays that serve multiple methods.

Operational practices:
- Align RAID level to workload (OLTP vs sequential analytics).
- Use thin provisioning for bursty/uncertain growth; monitor for overâ€‘commit.
- Snapshots vs clones vs backups; RPO/RTO alignment.

## 4) Networks for Cloud
- Types of communication:
  - Computeâ€‘toâ€‘compute: IP networking via switches/routers; VMs connect through NICs to access networks.
  - Computeâ€‘toâ€‘storage: SANs.
  - Interâ€‘cloud: WAN links/VPN/Direct Connect/ExpressRoute for hybrid, cloud bursting, DR.

### Fibre Channel SAN (FC)
- Block access over dedicated fabric; WWNN/WWPN identities; 24â€‘bit FC addressing; zoning for isolation.
- Fabric: domain IDs per switch; multipathing for HA; predictable latency for storage.

### IP SAN
- iSCSI: SCSI over TCP/IP; initiators (HBAs/software) and targets (arrays/gateways). Leverages existing Ethernet; security via CHAP/IPSec/VLANs.
- FCIP: encapsulate FC frames into IP to bridge FC SANs over distance; common for DR replication.

### FCoE SAN
- Converged Enhanced Ethernet carries lossless traffic for FC frames encapsulated in Ethernet; reduces adapters/cables/switches; requires DCB features (PFC, ETS) and CNAs.

Network design best practices:
- Redundant fabrics/paths; jumbo frames for iSCSI where supported; QoS for storage vs app traffic.
- Storm control and traffic shaping to prevent broadcast storms and tenant abuse.

## 5) Exam Scenarios and Calculations
- Choose RAID for given requirements: e.g., 8â€‘disk RAID 6 usable capacity? 6Ã—disk size; write penalty considerations.
- SAN protocol choice: small shop with 10GbE and IP skillset â†’ iSCSI; highâ€‘end DB latency â†’ FC.
- Multipathing policies: roundâ€‘robin vs mostâ€‘recentlyâ€‘used vs fixed; impact on load distribution.

## 6) Practice Questions
1) Compare rack vs blade systems for a 200â€‘node private cloud. Discuss power, cabling, management, and growth.
2) Select RAID levels for: (a) writeâ€‘heavy OLTP; (b) readâ€‘mostly analytics; (c) backup repository.
3) Outline the addressing and zoning concepts in FC SANs and why they matter.
4) Design an IP SAN for 100 VMs with mixed workloads on 10/25GbE; include QoS and security.

## 7) Quick Facts
- RAID 6 tolerates two disk failures; parity adds write overhead.
- iSCSI = SCSI over TCP/IP; FCIP tunnels FC over IP between SANs.
- FCoE needs lossless Ethernet and CNAs; reduces infrastructure count.
