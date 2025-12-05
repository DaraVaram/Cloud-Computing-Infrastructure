# Security

**Def. Information Security:** A term that includes a set of practices that protect infromation and information systems from **unauthorized access**, **use**, **infromation disclosure**, **disruption**, **modification**, or **destruction**.

The goal of information security is to provide: **Confidentiality, Integrity and Availability (CIA)**.

Security Mechanisms ensure **right users** have access to the **right resources** at the **right time**. 

**Def. Auditing:** Enables assessing effectiveness of the security mechanisms. 

|Term | Definition|
|------|-----|
Confidentiality | Provides **required secrecy** of information. Ensures only **authorized users** have access to the data
Integrity | Ensures **unauthorized changes** to data are **not allowed**.
Availability | Ensures **authorized users** have **reliable and timely access** to resources.
Authentication | Process to ensure **users or assets** are who they claim to be. There are two methods: single-factor and multi-factor. 
Authorization | Process of determining **access rights** of a user, device, applicaiton, or process to a service or resource. Authorization should be performed only if authentication is successful. 
Auditing | Process to evaluate the effectiveness of security enforcement mechanisms. 

![SecurityConcepts](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/SecurityConcepts.png)

**Def. Defense in Depth:** A strategy in which **multiple layers** of defesen are deployed throughout the infrastructure to help mitigate the risk of security threats in case one layer of the defesen is compromised.

This is also known as a layered approach to security. We provide service providers additional time to detect and respond to an attack, which reduces the scope of a security breach. See the below figure. 

![DefenseInDepth](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/DefenseInDepth.png)

At the top we have the perimeter security, which is the actual physical side of things. Then we go from there. The very center of the onion is the storage security. 
1. Perimeter
2. Remote Access Controls
3. Network Security
4. Compute Security
5. Storage Security

Here are some of the key security threats according to the CSA and ENISA

| Security Threat | Definition | 
| ------ | ----- | 
| Data Leakage | Occurs when an attacker gains access to a cloud consumer's confidential data. This can be gained by getting into the password database, exploiting poor application design, segregation of network traffic, encryption, or a malicious insider. How do we control this? Data encryption (both at-rest and in-transit), data shredding, MFA
| Account Hijacking | When attacker gains access to consumers' accounts. Phishing (social engineering, spoofing, etc...), installing keystroke logging malware, or a man-in-the-middle (eavesdropping on the network to capture credentials). How do we control this? MFA, IPSec, IDPS, Firewall.
| Insecure APIs | APIs are used to perform resource provisioning, configuration, monitoring and management, orchestration. They can be open or proprietary. Security of cloud depends on security of APIs. How do we control this? Design and develop APIs that follow good security practices. Do reviews. Access to APIs should be restricted to authorized users. 
| DoS Attack | Prevents legitimate users from accessing resources or services. Could be targeted against compute systems, networks or storage. The goal is to exhuast the key resources, preventing production use by legitimate consumers. 
| DDoS Attack | This is a variant of DoS. Several systems launch a coordinated DoS attack on the target. DDoS master program on a compute system, can multiply the effectiveness of DoS. How do we control this? Impose restrictions and limits on resource consumption. 
| Abuse of Cloud Services | Cloud resources can be misused to perform unauthorized activities. Cracking encryption, pirated software, etc... How do we control this? Difficult to mitigate. It's better to establish agreement with consumers. 
| Shared Technology Vulnerabilities | An attacker may explot the vulnerabilities of tools used to enable multi-tenant environments. Example is hyperjacking. How do we control this? Securing components that are part of trusted computing base. 
| Loss of Governance and Compliance | Causes: Provider outsources its services to third-parties. What is the impact? No control over third-parties, may impact commitments of the provider. Security controls of provider may change, impacting terms and conditions of the provider. Provider may not be able to supply evidence of meeting their compliance requirements. 

## Securtiy Mechanisms
Can be classified as follows: 

| Mechanism | Description | 
| ---- | ---- |
| Administrative | Security and personnel polciies or standard procedures to direct the safe execution of various operations. 
| Technical | Usually implemented through tools or devices deployed on computer systems, networks or storage. 

Technical security mechanisms must be deployed at the compute level, network level and storage level. 

**Def. Identity and Access Management:** A process of managing consumers' identities, and their authentication and authorization to access cloud resources. 

Cloud providers deploy both traditional and new authentication and authorization mechanisms. 

**Network Monitoring and Analysis:** A proactive measure to detect and prevent network failure or performance problems. Mechanisms used to monitor, detect and prevent attacks are: Firewall, IDPS, and network analysis / forensics systems. 

**Def. Firewall:** A security mechanism designed to examine data packets traversing a network and compare them to a set of **filtering rules**.
- Can be deployed at compute, network or storage level
- Can be physical or virtual
- Uses various parameters for traffic filtering. Examples are source address, destination address, port numbers and protocols.

**Def. Intrusion Detection and Prevention Systems:** A security tool that automates the process of detecting and preventing events that can compromise the confidentiality, integrity or availability of IT resources.
- Signature-based detection technique: Scans for signatures to detect an intrusion. This is only useful for known threats.
- Anomaly-based detection technique; Scans and analyzes events to detect if they are statistically different from normal events. You can use this to detect various events. Examples: Multiple login failures, excessive process failures, excessive network BW consumed by an activity.

Types of implementations: 

| IDPS Implementation | Description | 
| ----- | ----- | 
| Compute system-based | Analyzes activity such as system logs and running processes. IDPS software is susceptible to attacks. 
| Network-based | Monitors and analyzes traffic, network devices, protocol, and application protocol behavior. Deployed in the form of application or software on compute system. Usually isolated from malicious applications on compute systems. 
| Hypervisor-based | Monitors for anomalies in a hypervisor. Detection policies are typically kernel-specific. 

**Def. Adaptive Security:** A mechanism that integrates with the cloud service providers' standalone mechanisms such as IDPS and firewalls and uses heuristics to learn user behavior to detect fraudulent activities. 

The goal here is to identify and block anomalies. Parameters to learn about a user are: 
- Behavioral profile
- Device-related profile
- Type of web browser being used
- Plugins used in a browser

**Virtual LAN and SAN:**
- Ensure security by providing isolation over shared infrastructure
- Restricting communication among different consumers
- Zoning provides additional level of security within a VSAN.

**Securing Hypervisor and Management Server:**
- Compromsiing a hypervisor or management server places all the VMs at risk.
- Control measures:
    - Install security-critical hypervisor updates
    - Harden hypervisor using specifications provided by CIS and DISA. Restrict core functionality to selected administrators
    - Encrypt network traffic when managing remotely.
    - Deploy firewall between management system and the rest of the network
    - Rotate or delete log files when they reach a certain size
 
**Def. Data Encryption:** A cryptographic technique in which data is encoded and made indecipherable to eavesdroppers or hackers. 
- Enables securing data in-flight / in-transit and at-rest.
- Provides protection from threats, such as data tampering, media theft, and sniffing attacks.
- Data encryption mechanism can be deployed at compute, network or storage levels.
- Data should be encrypted as close to its origin as possible.

**Def. Data Shredding:** A process of deleting data or residual representations (sometimes called remanence) of data and making it unrecoverable. 
- Techniques for shredding data stored on tapes:
    - Overwriting tapes with invalid data
    - Degaussing media
    - Destroying tapes
- On disks and flash drives: use shredding algorithms
- You also want to shred all copies of data including backups and replicas.

## Governance, Risk and Compliance (GRC)

**Def. GRC:** A term encompassing processes that help an organization to snure that their acts are ethically correct and in accordance with their risk appetite (the risk level an organization chooses to accept), internal policies and external regulations. 

GRC work together to enforce policies and minimize risks. 
- Governance is the authority for making the policies
- Risk management invovles identifying resources that should not be accessed by certain users to preserve CIA
