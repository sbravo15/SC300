# SC-300 Glossary

This glossary defines recurring identity, access, cloud, and administration terms used throughout the SC-300 study guide. Entries are intentionally concise so section notes can link here without turning the glossary into a full lesson.

## Active Directory Domain Services

The traditional on-premises Microsoft directory service used to manage users, computers, groups, authentication, and policy for domain-joined Windows environments.

Related: [Domain](#domain), [Domain Controller](#domain-controller), [Group Policy Object](#group-policy-object), [Microsoft Entra ID](#microsoft-entra-id)

## Azure

Microsoft's cloud platform for infrastructure, platforms, applications, networking, storage, security, and management services.

Related: [IaaS](#iaas), [PaaS](#paas), [Microsoft Entra ID](#microsoft-entra-id)

## Azure Active Directory

The former name for Microsoft Entra ID. Older documentation, screenshots, portals, and exam wording may still use Azure AD or Azure Active Directory.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Tenant](#tenant)

## Cloud-First

An approach where new identity, device, application, and management designs start with cloud services instead of assuming a traditional on-premises domain is required.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Microsoft 365](#microsoft-365), [Intune](#intune)

## Directory

A structured identity store that holds objects such as users, groups, devices, applications, and related settings.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Microsoft Entra ID](#microsoft-entra-id), [Tenant](#tenant)

## DMZ

A perimeter network used to host public-facing services while limiting their access to the internal private network.

Related: [Firewall](#firewall), [VPN](#vpn)

## DNS

Domain Name System. A name-resolution service that maps hostnames to IP addresses and is required for Active Directory clients to locate domain services.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Domain Controller](#domain-controller)

## Domain

A logical identity and management boundary in Active Directory Domain Services, commonly aligned to an organization's DNS namespace.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Domain Controller](#domain-controller)

## Domain Controller

A server running Active Directory Domain Services that stores a copy of the directory database and authenticates users and computers in the domain.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Kerberos](#kerberos), [DNS](#dns)

## Enterprise Application

The Microsoft Entra representation of an application instance in a tenant, commonly used to manage access, assignment, single sign-on, and application-specific settings.

Related: [App Registration](#app-registration), [Service Principal](#service-principal), [Single Sign-On](#single-sign-on)

## Firewall

A network security control that permits or blocks traffic between networks, hosts, or security zones based on rules.

Related: [DMZ](#dmz), [VPN](#vpn)

## Group Policy Object

A centralized Active Directory policy object used to apply configuration, security settings, and restrictions to domain-joined users and computers.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Domain Controller](#domain-controller)

## Hybrid Identity

An identity model that connects on-premises Active Directory with Microsoft Entra ID so users can access both on-premises and cloud resources with a more unified sign-in experience.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Microsoft Entra Connect](#microsoft-entra-connect), [Microsoft Entra ID](#microsoft-entra-id)

## Hypervisor

The software layer that allows multiple virtual machines to run on a physical host.

Related: [Virtualization](#virtualization), [IaaS](#iaas)

## IaaS

Infrastructure as a Service. A cloud model where the provider offers infrastructure building blocks such as virtual machines, storage, networking, and firewalls.

Related: [Azure](#azure), [Virtualization](#virtualization), [PaaS](#paas), [SaaS](#saas)

## Intune

Microsoft's cloud-based endpoint management service for managing devices, applications, compliance settings, and related controls.

Related: [Microsoft 365](#microsoft-365), [Microsoft Entra ID](#microsoft-entra-id)

## Kerberos

The primary modern authentication protocol used in Active Directory domains.

Related: [Active Directory Domain Services](#active-directory-domain-services), [Domain Controller](#domain-controller), [NTLM](#ntlm)

## LDAP

Lightweight Directory Access Protocol. A protocol used by applications and services to query and access directory data.

Related: [Directory](#directory), [Active Directory Domain Services](#active-directory-domain-services)

## Microsoft 365

Microsoft's cloud productivity and collaboration service family, including services such as Exchange Online, SharePoint Online, Teams, OneDrive for Business, Office apps, and Intune.

Related: [Microsoft Entra ID](#microsoft-entra-id), [SaaS](#saas), [PaaS](#paas)

## Microsoft Entra Connect

The Microsoft synchronization tool used to connect on-premises Active Directory identities with Microsoft Entra ID.

Related: [Hybrid Identity](#hybrid-identity), [Active Directory Domain Services](#active-directory-domain-services), [Microsoft Entra ID](#microsoft-entra-id)

## Microsoft Entra ID

Microsoft's cloud identity and access management service. It provides users, groups, authentication, roles, application access, and policy enforcement for Microsoft cloud services and many integrated applications.

Related: [Azure Active Directory](#azure-active-directory), [Tenant](#tenant), [Conditional Access](#conditional-access)

## NTLM

A legacy Microsoft authentication protocol still encountered in older compatibility scenarios.

Related: [Kerberos](#kerberos), [Active Directory Domain Services](#active-directory-domain-services)

## PaaS

Platform as a Service. A cloud model where the provider manages the underlying infrastructure while administrators configure and manage the platform or service.

Related: [IaaS](#iaas), [SaaS](#saas), [Microsoft Entra ID](#microsoft-entra-id)

## RAS/RRAS

Remote Access Service / Routing and Remote Access Service. Microsoft remote access technologies used for routing and VPN scenarios.

Related: [VPN](#vpn), [Firewall](#firewall)

## SaaS

Software as a Service. A cloud model where users consume a finished application without managing the underlying infrastructure or platform.

Related: [Microsoft 365](#microsoft-365), [IaaS](#iaas), [PaaS](#paas)

## Tenant

A dedicated Microsoft cloud directory instance for an organization. A tenant contains identities, groups, applications, roles, policies, and configuration for Microsoft Entra ID and related cloud services.

Related: [Directory](#directory), [Microsoft Entra ID](#microsoft-entra-id), [Microsoft 365](#microsoft-365)

## Virtualization

The abstraction of physical compute resources so multiple virtual machines can run on shared hardware.

Related: [Hypervisor](#hypervisor), [IaaS](#iaas)

## VPN

Virtual Private Network. An encrypted connection that allows remote users or networks to access private resources more securely.

Related: [RAS/RRAS](#rasrras), [Firewall](#firewall), [DMZ](#dmz)

## App Registration

The Microsoft Entra object that defines an application's identity configuration, such as application ID, redirect URIs, API permissions, certificates, secrets, and authentication settings.

Related: [Enterprise Application](#enterprise-application), [Service Principal](#service-principal), [Workload Identity](#workload-identity)

## Conditional Access

Microsoft Entra policy-based access control that evaluates signals such as user, location, device, application, and risk before allowing, blocking, or requiring additional controls for access.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Authentication](#authentication), [Identity Protection](#identity-protection)

## Authentication

The process of proving an identity, usually through credentials, multifactor authentication, certificates, or other verification methods.

Related: [Kerberos](#kerberos), [Microsoft Entra ID](#microsoft-entra-id), [Conditional Access](#conditional-access)

## Identity Protection

Microsoft Entra features that detect, investigate, and respond to user and sign-in risk.

Related: [Conditional Access](#conditional-access), [Microsoft Entra ID](#microsoft-entra-id)

## Privileged Identity Management

Microsoft Entra ID Governance capability for managing, approving, activating, and auditing privileged role access.

Related: [Role-Based Access Control](#role-based-access-control), [Identity Governance](#identity-governance)

## Identity Governance

Microsoft Entra capabilities for governing access over time, including entitlement management, access reviews, lifecycle workflows, and privileged access controls.

Related: [Entitlement Management](#entitlement-management), [Access Review](#access-review), [Privileged Identity Management](#privileged-identity-management)

## Entitlement Management

Microsoft Entra ID Governance capability used to package and manage access to groups, applications, and SharePoint sites through catalogs, access packages, policies, and approvals.

Related: [Identity Governance](#identity-governance), [Access Review](#access-review)

## Access Review

A Microsoft Entra governance process for periodically reviewing whether users, guests, or privileged identities should keep access.

Related: [Identity Governance](#identity-governance), [Entitlement Management](#entitlement-management)

## Role-Based Access Control

An authorization model where permissions are assigned through roles rather than directly granting every permission to each user.

Related: [Privileged Identity Management](#privileged-identity-management), [Microsoft Entra ID](#microsoft-entra-id)

## Service Principal

The tenant-local security identity used by an application or service to access resources.

Related: [App Registration](#app-registration), [Enterprise Application](#enterprise-application), [Workload Identity](#workload-identity)

## Single Sign-On

An authentication experience where a user signs in once and can access multiple connected applications without repeatedly entering credentials.

Related: [Enterprise Application](#enterprise-application), [Microsoft Entra ID](#microsoft-entra-id)

## Workload Identity

An identity used by software workloads, services, scripts, automations, or applications rather than by a human user.

Related: [Service Principal](#service-principal), [App Registration](#app-registration)
