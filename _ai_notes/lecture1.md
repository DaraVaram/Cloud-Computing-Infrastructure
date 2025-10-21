---
layout: lecture
title: "AI Summary - Introduction to Cloud Computing"
lecture_number: 1
date: 2024-01-01
collection: ai_notes
---
This guide expands the lecture into an examâ€‘ready reference. It consolidates key definitions, adds context, realâ€‘world examples, and exam prompts to test mastery.

## 1) What is Cloud Computing (NIST 800â€‘145)
- Model for ubiquitous, convenient, onâ€‘demand network access to a shared pool of configurable computing resources (servers, storage, networks, apps, services) that can be rapidly provisioned and released with minimal management effort or provider interaction.
- Core idea: rent standardized IT capabilities as services over the network (utility model), instead of owning bespoke infrastructure.

Why it matters:
- Converts CapEx to OpEx, speeds experimentation, enables scale without long planning lead times.

Common pitfalls in answers:
- Forgetting â€œshared pool,â€ â€œrapid elasticity,â€ or â€œminimal provider interaction.â€

## 2) Essential Characteristics (NIST)
1. Onâ€‘demand selfâ€‘service: customers provision resources via portals/APIs without human tickets. Example: spin up a VM via AWS Console.
2. Broad network access: standard mechanisms, heterogeneous clients (mobile, tablets, laptops). Think HTTPS, REST, TLS.
3. Resource pooling: multiâ€‘tenancy and location independence; provider dynamically assigns resources. Tenants may specify coarse location (region/zone) but not rack.
4. Rapid elasticity: scale out/in quickly; appears â€œinfinite.â€ Supports workload spikes (e.g., ticket sales).
5. Measured service: metering, monitoring, and chargeback/showback. Enables billing transparency and capacity planning.

Exam cues: Be able to map scenarios to characteristics (e.g., autoscaling group â‡’ rapid elasticity; organizationâ€‘wide dashboard of usage â‡’ measured service).

## 3) Why Cloud? Trends, Economics, and Utility Vision
- Pressures: complex apps, higher availability/scalability expectations, cost constraints.
- Hyperscalers (Amazon, Microsoft, Google) built massive data centers; sell slices to customers.
- "Computer utility" vision (Kleinrock 1969): like electricity/telecom utilities; cloud is realization of the fifth utility (after water, electricity, gas, telephone).

Economic levers:
- Economies of scale, improved utilization (pooling), and demand aggregation lower unit cost.
- Risk transfer: provider manages hardware lifecycle, facility, energy, and some security.

## 4) Cloud Service Models
- IaaS: consumer controls OS, storage, deployed apps; provider manages underlying infrastructure. Examples: EC2, Azure VMs, GCP Compute Engine. Use cases: liftâ€‘andâ€‘shift, custom stacks.
- PaaS: provider offers runtime, libraries, tools; consumer deploys code. Examples: Heroku, Google App Engine, Azure App Service. Benefits: faster dev, managed scaling; tradeâ€‘off: less control over OS.
- SaaS: provider hosts full applications accessed via web/API. Examples: Salesforce, Office 365, Gmail. Benefits: zero infra mgmt; tradeâ€‘off: limited customization.

Responsibility split (highâ€‘level):
- IaaS: customer handles guest OS hardening/patching, app runtime; provider handles physical/DC/network/hypervisor.
- PaaS: provider additionally manages runtime/patching.
- SaaS: provider manages almost everything; customer manages users/config and data governance.

## 5) Deployment Models
- Public cloud: open use by general public; owned/operated by provider; offâ€‘premises from consumer perspective.
- Private cloud: exclusive to a single org; onâ€‘prem or externally hosted; cloudâ€‘like ops model (selfâ€‘service, automation) still required.
- Community cloud: shared by organizations with common concerns (mission/security/compliance). Governance shared or thirdâ€‘party.
- Hybrid cloud: composition of 2+ distinct clouds bound by tech enabling portability (e.g., cloud bursting, DR failover).

Key decision factors: data sensitivity, compliance jurisdiction, latency to plant/facility, cost model, operating model maturity.

## 6) Benefits of Cloud (Map to Business Outcomes)
- Business agility: faster provisioning, experimentation, timeâ€‘toâ€‘market.
- Cost optimization: reduced upfront CapEx; improved utilization; energy/space savings.
- Availability and resilience: design for high availability (multiâ€‘AZ/region), builtâ€‘in redundancy; fault tolerance options.
- Business continuity: simpler backup/DR (crossâ€‘region snapshots, object storage lifecycle, warm standbys).
- Flexible scaling: auto scale to demand; avoid overâ€‘provisioning.
- Accessibility and collaboration: access anywhere; shared data/services.
- Simplified infrastructure management: consumer focuses on configuration/use, not hardware lifecycle.

Risk considerations (often tested):
- Vendor lockâ€‘in, shared responsibility misunderstandings, egress costs, noisy neighbor, data residency.

## 7) Crossâ€‘Cutting Concepts to Know
- APIs and automation: selfâ€‘service implies APIâ€‘first workflows (IaC: Terraform, ARM/Bicep, Cloud Deployment Manager).
- Multiâ€‘tenancy and isolation: virtualization, vPC/VNet isolation, IAM.
- Observability and metering: logs, metrics, tracing; cost/usage reports.

## 8) Practice Questions
1) List and explain the five essential characteristics of cloud computing. Give a real example for each.
2) Contrast IaaS vs PaaS vs SaaS in terms of control, flexibility, and responsibility.
3) Choose a workload (e.g., eâ€‘commerce web app). Propose a hybrid deployment that meets HA and DR goals; justify service model choices.
4) A startup predicts variable traffic with frequent spikes. Which cloud characteristics and services help? Explain the cost implications.
5) What risks trade off against agility when moving to public cloud? How can an architect mitigate each?

## 9) Cheat Sheet
- NIST 800â€‘145 quote: remember â€œubiquitous, convenient, onâ€‘demand,â€ â€œshared pool,â€ â€œrapidly provisioned/released,â€ â€œminimal management effort.â€
- Service models: IaaS (VMs), PaaS (runtime), SaaS (app). Deployment: public/private/community/hybrid.
- Essential characteristics acronym: OB RRM (Onâ€‘demand, Broad access, Resource pooling, Rapid elasticity, Measured service).
