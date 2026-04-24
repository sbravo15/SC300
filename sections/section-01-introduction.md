# Section 1: Introduction

## Section Purpose

This section introduces the course structure, the Microsoft cloud environment, foundational Active Directory concepts, basic cloud service models, and the lab/assignment workflow used throughout the course.

## SC-300 Relevance

This section is not a heavy exam-objective section by itself, but it supports the rest of the course by explaining the identity, networking, cloud, and lab concepts needed to understand Microsoft Entra ID.

---

# 1. Welcome Video

## Core Idea

The course focuses on practical learning through real-world examples, visual explanations, hands-on demonstrations, simulations, and exam-objective coverage.

## What to Remember

- The course is designed to teach concepts in a practical order.
- Some videos may not match the official exam objective order exactly.
- Assignments and simulations are used for hands-on reinforcement.

---

# 2. Understanding the Microsoft 365 and Azure Environment

## Core Idea

Microsoft 365, Azure, and Microsoft Entra ID are connected parts of the Microsoft cloud ecosystem.

## What to Remember

- Azure is the broader cloud platform.
- Microsoft 365 provides productivity and collaboration services.
- Microsoft Entra ID is the identity layer used across Microsoft cloud services.

---

# 3. A Solid Foundation of Active Directory Domains

## Core Idea

Active Directory introduced centralized identity and device management for traditional on-premises environments.

## Key Concepts

| Concept | Meaning |
|---|---|
| Active Directory Domain Services | On-premises identity and directory service |
| Domain Controller | Server that stores and serves the AD directory database |
| Domain | Logical boundary for centralized identity and device management |
| Kerberos | Primary modern authentication protocol in AD |
| NTLM | Legacy authentication protocol |
| LDAP | Protocol used to query directory data |
| DNS | Name resolution system required for AD to work |
| GPO | Centralized policy configuration for domain-joined devices |

## Memory Hook

Active Directory = centralized identity, authentication, DNS, and policy management for on-prem environments.

---

# 4. A Solid Foundation of RAS, DMZ, and Virtualization

## Core Idea

Traditional enterprise networks used VPN/RAS for secure remote access, DMZs for public-facing services, and virtualization to reduce physical server dependency.

## Key Concepts

| Concept | Purpose |
|---|---|
| VPN / RAS / RRAS | Secure remote access into the internal network |
| DMZ | Isolated perimeter network for public-facing services |
| Firewall | Controls traffic between network zones |
| Hypervisor | Runs multiple virtual machines on one physical host |
| Virtualization | Makes infrastructure more flexible and cloud-like |

## Memory Hook

VPN protects remote access, DMZ protects internal networks, and virtualization created the foundation for cloud infrastructure.

---

# 5. A Solid Foundation of Microsoft Cloud Services

## Core Idea

Cloud services let organizations consume infrastructure, platforms, and applications without managing everything on-premises.

## Cloud Service Models

| Model | Meaning | Microsoft Example |
|---|---|---|
| IaaS | Provider rents infrastructure building blocks | Azure VMs, virtual networks, storage |
| PaaS | Provider manages platform; admins configure the service | Microsoft Entra ID, Intune-style management |
| SaaS | Finished application ready for users | Office for the web, Exchange Online, Teams |

## Azure vs Microsoft 365

| Area | Main Role |
|---|---|
| Azure | Cloud infrastructure and platform services |
| Microsoft 365 | Productivity, collaboration, and identity-connected services |
| Microsoft Entra ID | Shared identity layer used across both |

## Memory Hook

Azure gives you cloud building blocks. Microsoft 365 gives users cloud apps. Entra ID connects identities across both.

---

# 6. Azure AD Is Being Renamed to Microsoft Entra ID

## Core Idea

Azure AD is now Microsoft Entra ID, but older names may still appear in portals, documentation, videos, and exam content.

## What to Remember

| Old Name | New Name |
|---|---|
| Azure Active Directory | Microsoft Entra ID |
| Azure AD | Entra ID |
| Azure AD Premium P1/P2 | Microsoft Entra ID P1/P2 |

## Exam Trap

The exam, documentation, and portals may use both names. Treat Azure AD and Microsoft Entra ID as the same product in this context.

---

# 7. Before Beginning Your Account Lab

## Core Idea

The course uses a Microsoft 365/Azure trial tenant for hands-on practice.

## What to Remember

- Trial availability depends on region.
- Microsoft 365 E5 is preferred for broad feature coverage.
- A payment method may be required.
- Cancel the trial before being charged.
- If a trial is unavailable, simulations can still be used.

---

# 8. Creating a Trial Microsoft 365/Azure Account

## Core Idea

A lab tenant allows you to practice safely without affecting a real production environment.

## Process Overview

1. Create or use a dedicated email account.
2. Sign up for a Microsoft 365 trial.
3. Activate Microsoft 365 E5 if available.
4. Assign the license to the admin user.
5. Confirm access to the admin portals.
6. Cancel before billing if needed.

## Tenant Evidence to Add Later

1. Screenshot: Microsoft 365 admin center home page  
   - Shows successful tenant access.

2. Screenshot: Billing > Licenses  
   - Shows assigned license.

3. Screenshot: Microsoft Entra admin center overview  
   - Shows access to Entra ID.

---

# 9. Using Assignments in the Course

## Core Idea

Assignments are interactive simulations used to reinforce hands-on concepts.

## What to Remember

- Open simulations in a new tab.
- Complete the simulation.
- Return to the course page.
- Submit the post-assignment confirmation.
- Refresh if the assignment does not appear completed.

## Repository Note

Course assignments should be documented in the `/assignments` folder using your own tenant work, sanitized screenshots, and original notes.

---

# 10. Questions, Comments, and Support

## Core Idea

Microsoft cloud services change often, so official documentation and current portal experience matter.

## What to Remember

- Use Microsoft Learn as the main source of truth.
- Portal names and paths may change.
- Search official documentation when the UI differs from the course.

---

# 11. Order of Concepts Covered in the Course

## Core Idea

The course teaches topics in a learning-friendly order, not necessarily the same order as the official exam objectives.

## What to Remember

- Foundational concepts come before advanced topics.
- Some videos may cover multiple exam objectives.
- Some objectives may appear across several sections.

---

# 12. Certificate of Completion

## Core Idea

The course certificate depends on watching course videos, not completing assignments.

## What to Remember

- Assignments help learning but may not affect course completion.
- Video completion is what matters for the course certificate.
