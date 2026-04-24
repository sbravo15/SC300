# Section 1: Introduction

This section introduces the course structure, the Microsoft cloud environment, foundational Active Directory concepts, cloud service models, the Azure AD to Microsoft Entra ID naming change, and the assignment workflow used throughout the course.

Section 1 is mainly a foundation section. It is not one of the heaviest SC-300 exam sections by itself, but it gives the background needed to understand Microsoft Entra ID, hybrid identity, cloud administration, and later hands-on assignments.

## 1. Welcome Video

The course is designed around practical learning.

The instructor focuses on:

- Real-world examples
- Visual explanations
- Hands-on demonstrations
- Simulations
- SC-300 exam objectives

The goal is not only to memorize portal steps, but to understand how Microsoft identity and cloud administration work in real environments.

## 2. Understanding the Microsoft 365 and Azure Environment

Microsoft 365, Azure, and Microsoft Entra ID are connected parts of the Microsoft cloud ecosystem.

| Service | Main idea |
|---|---|
| Azure | Microsoft’s broader cloud platform |
| Microsoft 365 | Productivity, collaboration, communication, and business services |
| Microsoft Entra ID | The shared identity layer used across Microsoft cloud services |

Different portals may manage the same backend identity objects. For example, a user created from the Microsoft 365 admin center still exists in Microsoft Entra ID.

## 3. A Solid Foundation of Active Directory Domains

Active Directory introduced centralized identity and device management for traditional on-premises environments.

Before centralized identity, early business networks were harder to manage:

- No central control
- Admins had to configure computers manually
- File sharing was harder to secure
- Users and passwords were managed inconsistently
- Scaling the environment was difficult

Active Directory helped centralize:

- User accounts
- Computer accounts
- Groups
- Authentication
- Directory access
- Policy enforcement
- Domain management

### Key Active Directory concepts

| Concept | Meaning |
|---|---|
| Active Directory Domain Services | On-premises identity and directory service |
| Domain Controller | Server running AD DS that stores and serves the directory database |
| Domain | Logical boundary for centralized identity and device management |
| Kerberos | Primary authentication protocol used in modern AD domains |
| NTLM | Legacy authentication protocol used for older compatibility scenarios |
| LDAP | Protocol used to query and access directory data |
| DNS | Name resolution system required for AD to locate domain services |
| GPO | Centralized policy configuration for domain-joined devices |

### Domain Controllers

A Domain Controller stores and provides access to the Active Directory database.

Organizations usually deploy multiple Domain Controllers for:

- Load balancing
- Redundancy
- Replication
- Authentication availability

If one Domain Controller fails, users can still authenticate through another available Domain Controller.

### DNS in Active Directory

DNS is critical in Active Directory because clients use DNS to locate domain services.

For example, when a user signs in, the computer needs to find a Domain Controller. It uses DNS to locate the correct service, then connects to a Domain Controller to authenticate.

Without working DNS, domain logons and service discovery can break.

### Group Policy Objects

Group Policy Objects are used to centrally enforce configuration on domain-joined systems.

Examples include:

- Firewall settings
- Password rules
- Lock screen policies
- Software deployment
- Security restrictions
- Antivirus configuration
- USB or device restrictions

**Memory hook:**  
Active Directory = centralized identity, authentication, DNS, and policy management for on-premises environments.

## 4. A Solid Foundation of RAS, DMZ, and Virtualization

Traditional enterprise networks used remote access, perimeter networks, and virtualization before cloud computing became the dominant model.

These concepts help explain how companies moved from on-premises infrastructure toward cloud services.

### Key concepts

| Concept | Purpose |
|---|---|
| VPN | Creates an encrypted tunnel for remote users |
| RAS / RRAS | Microsoft remote access service used for VPN and routing scenarios |
| DMZ | Perimeter network used to isolate public-facing services |
| Firewall | Controls traffic between networks or security zones |
| Hypervisor | Software layer that runs multiple virtual machines on one physical host |
| Virtualization | Allows multiple servers to run as virtual machines on shared hardware |

### Remote access

Remote users should not connect directly to internal servers through many exposed firewall ports. That increases the attack surface.

A safer approach is to use a VPN:

1. The user connects to the company VPN endpoint.
2. The connection is encrypted.
3. The user can access approved internal resources.
4. Internal systems remain protected behind the network boundary.

### DMZ / perimeter network

A DMZ is used when a company needs to host a public-facing service, such as a web server.

The goal is to avoid placing public servers directly inside the internal network.

A safer design separates:

- Internet-facing services
- Internal business systems
- Firewall boundaries between them

If the public server is compromised, the attacker should still be limited from reaching the internal network.

### Virtualization

Virtualization allows one physical host to run multiple virtual machines.

This made infrastructure more flexible because organizations could:

- Run many servers on fewer physical hosts
- Move or replicate virtual machines
- Use snapshots or checkpoints before major changes
- Share CPU, memory, and storage resources more efficiently
- Treat infrastructure as a pool of resources

**Memory hook:**  
VPN protects remote access. DMZ protects the internal network. Virtualization created the foundation for cloud infrastructure.

## 5. A Solid Foundation of Microsoft Cloud Services

Cloud services allow organizations to consume infrastructure, platforms, and applications without managing every physical component themselves.

Cloud computing builds on ideas introduced by virtualization:

- Shared resources
- Elasticity
- Centralized infrastructure
- Service-based consumption

### Cloud service models

| Model | Meaning | Microsoft example |
|---|---|---|
| IaaS | Infrastructure building blocks managed in the cloud | Azure VMs, virtual networks, storage |
| PaaS | Platform service where admins configure the service but do not manage the underlying infrastructure | Microsoft Entra ID, Intune-style management |
| SaaS | Finished application ready for users | Office for the web, Exchange Online, Teams |

### Azure vs Microsoft 365

| Area | Main role |
|---|---|
| Azure | Cloud platform for infrastructure, networking, storage, apps, and services |
| Microsoft 365 | Productivity, collaboration, communication, and business services |
| Microsoft Entra ID | Shared identity layer used across Azure and Microsoft 365 |

### Microsoft 365 service examples

Common Microsoft 365 services include:

- Exchange Online
- SharePoint Online
- Teams
- OneDrive for Business
- Microsoft 365 Apps
- Office for the web
- Intune

Some services feel like SaaS from the user perspective but require platform-style configuration from the admin perspective.

### Licensing models

| Platform | Common billing model |
|---|---|
| Azure | Usage-based billing for compute, storage, networking, and other resources |
| Microsoft 365 | Subscription licensing based on plans and assigned users |

### Hybrid identity

Many organizations do not want separate accounts for on-premises and cloud access.

Hybrid identity connects on-premises Active Directory with Microsoft Entra ID so users can have a more unified sign-in experience.

Common synchronization options include:

- Microsoft Entra Connect Sync
- Microsoft Entra Cloud Sync

Typical direction:

```text
On-premises Active Directory → Microsoft Entra ID
