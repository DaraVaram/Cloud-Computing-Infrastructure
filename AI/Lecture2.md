# COE 505 – Lecture 2 Study Guide: Building the Cloud Infrastructure

This guide expands the lecture notes into a deeper, exam‑oriented walkthrough of distributed systems foundations, the cloud reference model, and build options.

## 1) Distributed Systems Essentials
- Definitions:
  - Tanenbaum: collection of autonomous computing elements that appears to users as a single coherent system.
  - Coulouris: components on networked computers coordinate only by message passing.
- Key characteristics:
  - Autonomy of nodes (physical/virtual), heterogeneity of hardware/software.
  - Illusion of a single system (transparency via middleware): location, access, migration, replication, concurrency, and failure transparency.
- Middleware role:
  - A logical layer across nodes offering common services (naming, auth, RPC/RMI, messaging, transactions). Hides distribution complexity.
- Design goals:
  - Accessibility: remote access and controlled sharing.
  - Transparency: hide distribution details from users.
  - Openness: standardized interfaces; interoperability, portability, extensibility.
  - Scalability: size, geographic, administrative. Beware of central bottlenecks; prefer decentralized algorithms; cache; partition state; avoid hotspots.

Exam edge cases:
- Partial failures and unreliable networks (CAP trade‑offs). Idempotency and retries.
- Clock issues: drift, skew; logical clocks; eventual consistency models.

## 2) Cloud Computing Reference Model (Layers)
- Physical layer: compute, storage, network devices and their operating environments.
- Virtual layer: virtualization software, resource pools, and virtual resources (VMs, virtual networks, LUNs).
- Control layer: control software (element/unified managers), provisioning, monitoring, policy.
- Orchestration layer: workflows and automation that stitch provisioning steps into services.
- Service layer: service catalog and self‑service portals.
- Cross‑layer functions: business continuity (BIA, risk, backup/replication, DR), security (policies, firewalls, IDS/IPS, AV; meet GRC).

Be able to trace a request: portal/API → orchestration → control provisioning → virtualization → physical execution.

## 3) Building the Cloud Infrastructure: Options
1) Integrating best‑of‑breed components
   - Pros: vendor choice, reuse existing assets, avoid lock‑in.
   - Cons: significant integration/compatibility testing; more staff time; complex upgrades.
   - Fit: organizations with mature engineering ops and bespoke requirements.
2) Cloud‑ready converged/hyperconverged infrastructure
   - Pros: pre‑validated stacks; faster time‑to‑value; unified management.
   - Cons: reduced flexibility; vendor coupling; cost premiums.
   - Fit: faster deployment, standardized platforms, edge/branch consistency.

## 4) Service‑Level Agreements (SLAs) and Contracts
- Define availability targets, performance SLOs, maintenance windows, support response, responsibilities.
- Legal/Business: data privacy/ownership, security and jurisdiction, DR/exit plans, penalties for breaches.
- For exam scenarios: translate SLOs to capacity plans and resilience designs (multi‑AZ, RPO/RTO, failover tests).

## 5) Reference Model Deep Dives
- Physical: DC facilities, racks, power/cooling, cabling best practices.
- Virtual: hypervisors, network/storage virtualization; resource pools; thin vs thick provisioning.
- Control: inventory discovery, pool grading (Gold/Silver/Bronze), compliance checks, dashboards.
- Orchestration: service templates, idempotent workflows, rollback/compensation logic.
- Service: catalog design, chargeback/showback, quota policies.

## 6) Sample Design Exercise
Design a private cloud for a regulated enterprise:
- Requirements: on‑prem, strict data residency, self‑service VM and storage provisioning, 99.95% availability, audit logging, and DR to secondary site (RPO 4h, RTO 8h).
- Solution sketch:
  - Physical: dual power feeds/UPS/genset; redundant spine‑leaf network; FC or iSCSI SAN.
  - Virtual: vSphere/KVM with clustered hosts; VMFS/CSV; VLANs/VSANs; thin LUNs for dev/test.
  - Control: unified manager with pool grading; Gold for OLTP (Flash+FC, RAID 1+0), Silver for general workloads, Bronze for backup.
  - Orchestration: catalog items with forms; approval workflow; IaC pipelines.
  - BC/DR: synchronous replication for Tier‑1; async for Tier‑2; quarterly failover tests; immutable backups.
  - Security: centralized IAM, MFA, network micro‑segmentation, IDS/IPS, logging to SIEM.

## 7) Practice Questions
1) Explain openness vs interoperability vs portability; give concrete examples in cloud APIs and images.
2) Show how geographical scalability challenges consistency and latency; propose mitigations for a shopping cart service.
3) Compare best‑of‑breed vs converged infrastructure given a constraint set (budget, timeline, skill).
4) Given an SLA of 99.9% monthly, compute allowable downtime and sketch monitoring/alerting to enforce it.

## 8) Quick Facts
- Middleware provides distribution transparency and common services.
- Scalability dimensions: size, geographic, administrative.
- SLAs must include availability, performance, DR/exit, and penalties; align with legal jurisdiction.
