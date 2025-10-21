# COE 505 – Lecture 1 Study Guide: Cloud Computing Overview

This guide expands the lecture into an exam‑ready reference. It consolidates key definitions, adds context, real‑world examples, and exam prompts to test mastery.

## 1) What is Cloud Computing (NIST 800‑145)
- Model for ubiquitous, convenient, on‑demand network access to a shared pool of configurable computing resources (servers, storage, networks, apps, services) that can be rapidly provisioned and released with minimal management effort or provider interaction.
- Core idea: rent standardized IT capabilities as services over the network (utility model), instead of owning bespoke infrastructure.

Why it matters:
- Converts CapEx to OpEx, speeds experimentation, enables scale without long planning lead times.

Common pitfalls in answers:
- Forgetting “shared pool,” “rapid elasticity,” or “minimal provider interaction.”

## 2) Essential Characteristics (NIST)
1. On‑demand self‑service: customers provision resources via portals/APIs without human tickets. Example: spin up a VM via AWS Console.
2. Broad network access: standard mechanisms, heterogeneous clients (mobile, tablets, laptops). Think HTTPS, REST, TLS.
3. Resource pooling: multi‑tenancy and location independence; provider dynamically assigns resources. Tenants may specify coarse location (region/zone) but not rack.
4. Rapid elasticity: scale out/in quickly; appears “infinite.” Supports workload spikes (e.g., ticket sales).
5. Measured service: metering, monitoring, and chargeback/showback. Enables billing transparency and capacity planning.

Exam cues: Be able to map scenarios to characteristics (e.g., autoscaling group ⇒ rapid elasticity; organization‑wide dashboard of usage ⇒ measured service).

## 3) Why Cloud? Trends, Economics, and Utility Vision
- Pressures: complex apps, higher availability/scalability expectations, cost constraints.
- Hyperscalers (Amazon, Microsoft, Google) built massive data centers; sell slices to customers.
- "Computer utility" vision (Kleinrock 1969): like electricity/telecom utilities; cloud is realization of the fifth utility (after water, electricity, gas, telephone).

Economic levers:
- Economies of scale, improved utilization (pooling), and demand aggregation lower unit cost.
- Risk transfer: provider manages hardware lifecycle, facility, energy, and some security.

## 4) Cloud Service Models
- IaaS: consumer controls OS, storage, deployed apps; provider manages underlying infrastructure. Examples: EC2, Azure VMs, GCP Compute Engine. Use cases: lift‑and‑shift, custom stacks.
- PaaS: provider offers runtime, libraries, tools; consumer deploys code. Examples: Heroku, Google App Engine, Azure App Service. Benefits: faster dev, managed scaling; trade‑off: less control over OS.
- SaaS: provider hosts full applications accessed via web/API. Examples: Salesforce, Office 365, Gmail. Benefits: zero infra mgmt; trade‑off: limited customization.

Responsibility split (high‑level):
- IaaS: customer handles guest OS hardening/patching, app runtime; provider handles physical/DC/network/hypervisor.
- PaaS: provider additionally manages runtime/patching.
- SaaS: provider manages almost everything; customer manages users/config and data governance.

## 5) Deployment Models
- Public cloud: open use by general public; owned/operated by provider; off‑premises from consumer perspective.
- Private cloud: exclusive to a single org; on‑prem or externally hosted; cloud‑like ops model (self‑service, automation) still required.
- Community cloud: shared by organizations with common concerns (mission/security/compliance). Governance shared or third‑party.
- Hybrid cloud: composition of 2+ distinct clouds bound by tech enabling portability (e.g., cloud bursting, DR failover).

Key decision factors: data sensitivity, compliance jurisdiction, latency to plant/facility, cost model, operating model maturity.

## 6) Benefits of Cloud (Map to Business Outcomes)
- Business agility: faster provisioning, experimentation, time‑to‑market.
- Cost optimization: reduced upfront CapEx; improved utilization; energy/space savings.
- Availability and resilience: design for high availability (multi‑AZ/region), built‑in redundancy; fault tolerance options.
- Business continuity: simpler backup/DR (cross‑region snapshots, object storage lifecycle, warm standbys).
- Flexible scaling: auto scale to demand; avoid over‑provisioning.
- Accessibility and collaboration: access anywhere; shared data/services.
- Simplified infrastructure management: consumer focuses on configuration/use, not hardware lifecycle.

Risk considerations (often tested):
- Vendor lock‑in, shared responsibility misunderstandings, egress costs, noisy neighbor, data residency.

## 7) Cross‑Cutting Concepts to Know
- APIs and automation: self‑service implies API‑first workflows (IaC: Terraform, ARM/Bicep, Cloud Deployment Manager).
- Multi‑tenancy and isolation: virtualization, vPC/VNet isolation, IAM.
- Observability and metering: logs, metrics, tracing; cost/usage reports.

## 8) Practice Questions
1) List and explain the five essential characteristics of cloud computing. Give a real example for each.
2) Contrast IaaS vs PaaS vs SaaS in terms of control, flexibility, and responsibility.
3) Choose a workload (e.g., e‑commerce web app). Propose a hybrid deployment that meets HA and DR goals; justify service model choices.
4) A startup predicts variable traffic with frequent spikes. Which cloud characteristics and services help? Explain the cost implications.
5) What risks trade off against agility when moving to public cloud? How can an architect mitigate each?

## 9) Cheat Sheet
- NIST 800‑145 quote: remember “ubiquitous, convenient, on‑demand,” “shared pool,” “rapidly provisioned/released,” “minimal management effort.”
- Service models: IaaS (VMs), PaaS (runtime), SaaS (app). Deployment: public/private/community/hybrid.
- Essential characteristics acronym: OB RRM (On‑demand, Broad access, Resource pooling, Rapid elasticity, Measured service).
