# COE 505 – Lecture 5 Study Guide: Control Layer and Resource Management

This guide elaborates the control layer, software‑defined management, and key resource management techniques, with exam‑style prompts and design patterns.

## 1) Control Layer Overview
- Purpose: manage and control the underlying cloud infrastructure; provision IT resources to fulfill service requests from service/orchestration layers.
- Functions: resource configuration, provisioning, monitoring; inventory discovery and policy enforcement.
- Deployment: atop virtual or physical layers.

## 2) Control Software Types
- Element Manager: per‑component tools (array GUIs/CLIs, switch managers, hypervisor host clients). Tasks: initial config (OS install, zoning, VLANs, RAID), expand capacity, monitor perf/availability/capacity/security.
- Unified Manager: single pane across components; API exposure for orchestration; service lifecycle (add/remove resources); compliance checks; dashboards and RCA tooling.

Provisioning phases (with unified manager):
1) Resource discovery (compute, network, storage inventory and mappings; QoS, zones, pools).
2) Resource pool management (including grading pools: Gold/Silver/Bronze with media/RAID/tiering mix and cost).
3) Resource provisioning (allocate per service templates; create instances with policy‑driven configuration).

## 3) Software‑Defined Approach
- Decouple control from underlying devices; central controller abstracts and pools compute/storage/network.
- Benefits: uniform policy application, rapid provisioning, programmable interfaces (northbound APIs), and centralized governance.

Controller key functions:
- Discover/aggregate resources; apply policies; expose APIs to request resources as services.

## 4) Resource Management Models
- Relative allocation: proportions via shares/weights; fair distribution when contention occurs.
- Absolute allocation: lower/upper bounds (reservations/limits) to guarantee minimums and cap maximums.

Policy design tips:
- Reserve for latency‑critical tiers; cap noisy tenants; mix shares with limits for fairness and protection.

## 5) Compute Optimizations
- Hyper‑threading: exposes two logical cores per physical core to keep execution units busy; improves throughput but not 2×; watch for SMT‑unfriendly workloads.
- Memory page sharing (TPS/KSM): deduplicate identical guest pages; enables memory overcommit; sensitive to security considerations (side‑channels) and workload similarity.
- Dynamic memory (ballooning, hot‑add): reclaim pages from guests under pressure and reassign; avoid swap‑induced latency by setting reasonable reservations.
- VM load balancing across hypervisors (DRS‑like): placement at power‑on; continuous monitoring and live migration to even load.

## 6) Storage Optimizations
- Virtual storage provisioning (thin vs thick): efficiency vs predictability; align to workload and monitoring maturity.
- Storage space reclamation for thin LUNs:
  - Zero‑extent reclamation (detect all‑zero extents) and API‑based reclaim (report unused ranges from file systems/VMs).
- Storage pool rebalancing: restripe across drives when expanding pools; yields better parallelism and uniform utilization.
- Automated storage tiering: policy‑driven data movement across media (Flash/FC/SATA); intra‑array and inter‑array; base policy on access heat, file type, SLA.
- Cache tiering: SSD as secondary cache behind DRAM to absorb reads; boosts peak performance transparently.
- Dynamic VM load balancing across storage volumes: intelligent placement and ongoing rebalancing using I/O telemetry.

## 7) Network Traffic Management
- Balance client workload across nodes (load balancers; L4/7 policies; health checks; sticky sessions when needed).
- Quality of Service (QoS):
  - IntServ: per‑flow reservation; precise but complex/scales poorly.
  - DiffServ: mark and classify traffic; scalable class‑based prioritization.
- Traffic shaping: enforce rate limits; queue excess; protects business‑critical traffic and prevents congestion.
- Link aggregation (LACP): bundle links for bandwidth and redundancy; hash‑based distribution.
- NIC teaming: distribute VM/host traffic across NICs; failover on NIC/link loss.
- Multipathing: multiple storage I/O paths for load balance and failover; path selection policies.

## 8) Vendor Solutions (Awareness)
- EMC/Dell examples: Unisphere (storage management), UIM (Vblock/VSPEX), ViPR/ViPR SRM (software‑defined storage mgmt and analytics), FAST VP (sub‑LUN tiering), XtremSF/XtremSW Cache (server‑flash cache), PowerPath/VE (advanced multipathing).

## 9) Practice Questions
1) Given mixed workloads, propose pool grading (Gold/Silver/Bronze) and map applications to each with justification.
2) Your thin‑provisioned pool is nearing 80% used; outline immediate actions and long‑term policy changes.
3) Compare IntServ vs DiffServ for a multi‑tenant cloud; which would you deploy and why?
4) Diagnose a latency spike: which telemetry would you collect from compute, storage, and network before moving VMs?

## 10) Quick Facts
- Provisioning phases: discover → pool/grade → provision by template.
- Thin: efficiency with monitoring; thick: predictability.
- QoS: DiffServ scales; IntServ precise but complex.
- Always design for N+1 and multiple paths; enforce caps to contain noisy neighbors.
