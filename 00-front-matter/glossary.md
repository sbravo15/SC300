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

## Domain Join

The process of connecting a Windows computer to an AD DS domain so it can authenticate with domain accounts and receive domain-based policy.

Related: [Domain](#domain), [Domain Controller](#domain-controller), [DNS](#dns)

## Forest

The top-level Active Directory Domain Services boundary that contains one or more domains and shares a common schema, configuration, and trust model.

Related: [Domain](#domain), [Active Directory Domain Services](#active-directory-domain-services)

## Global Catalog

A domain controller role that stores searchable information about objects across an AD DS forest and helps with logon and directory lookup scenarios.

Related: [Domain Controller](#domain-controller), [Forest](#forest)

## DSRM

Directory Services Restore Mode. A recovery mode for domain controllers that uses a dedicated restore password configured during domain controller promotion.

Related: [Domain Controller](#domain-controller), [Active Directory Domain Services](#active-directory-domain-services)

## NetBIOS Name

A legacy short name used for compatibility with older Windows networking and domain naming behavior.

Related: [Domain](#domain), [Active Directory Domain Services](#active-directory-domain-services)

## SYSVOL

A shared domain folder structure replicated between domain controllers and used for Group Policy and logon script data.

Related: [Domain Controller](#domain-controller), [Group Policy Object](#group-policy-object)

## SRV Record

A DNS record type that helps clients locate services, including AD DS domain controllers.

Related: [DNS](#dns), [Domain Controller](#domain-controller)

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

## Administrative Unit

A Microsoft Entra container used to scope administrative control over selected users, groups, or devices.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Least Privilege](#least-privilege), [Effective Permissions](#effective-permissions)

## Azure RBAC

Azure role-based access control. The authorization system used to manage access to Azure resources at scopes such as management group, subscription, resource group, or resource.

Related: [Role-Based Access Control](#role-based-access-control), [Azure](#azure), [Least Privilege](#least-privilege)

## Company Branding

Microsoft Entra sign-in page customization for organization logos, colors, layout, and sign-in text.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Tenant](#tenant)

## Custom Domain

A verified domain name owned by an organization and added to a Microsoft tenant for sign-in names, email, and cloud services.

Related: [Tenant](#tenant), [DNS](#dns), [Microsoft Entra ID](#microsoft-entra-id)

## Custom Security Attribute

A business-specific key-value attribute that can be defined and assigned to supported Microsoft Entra objects for filtering, access decisions, automation, or application logic.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Least Privilege](#least-privilege)

## Device Identity

A Microsoft Entra object that represents a device and can be used for access, compliance, management, and reporting decisions.

Related: [Microsoft Entra Joined Device](#microsoft-entra-joined-device), [Microsoft Entra Registered Device](#microsoft-entra-registered-device), [Microsoft Entra Hybrid Joined Device](#microsoft-entra-hybrid-joined-device)

## Dynamic Membership Group

A group whose membership is automatically calculated from user or device attributes by using membership rules.

Related: [Security Group](#security-group), [Microsoft 365 Group](#microsoft-365-group)

## Effective Permissions

The actual actions an identity can perform after role permissions, scope, and assignments are evaluated together.

Related: [Role-Based Access Control](#role-based-access-control), [Administrative Unit](#administrative-unit), [Least Privilege](#least-privilege)

## Group-Based Licensing

A licensing approach where licenses are assigned to a group so eligible members receive the license through membership.

Related: [Microsoft 365 Group](#microsoft-365-group), [Security Group](#security-group)

## Guest User

An external user invited into a tenant for collaboration, usually through Microsoft Entra B2B collaboration.

Related: [Member User](#member-user), [Microsoft Entra ID](#microsoft-entra-id)

## Mail-Enabled Security Group

A group that can be used both for email distribution and for assigning access permissions.

Related: [Security Group](#security-group), [Microsoft 365 Group](#microsoft-365-group)

## Managed Identity

An Azure-managed identity that lets an Azure resource authenticate to supported services without storing credentials in code.

Related: [Service Principal](#service-principal), [Workload Identity](#workload-identity), [Azure](#azure)

## Member User

An internal user account in a Microsoft Entra tenant, usually representing an employee or organizational user.

Related: [Guest User](#guest-user), [User Principal Name](#user-principal-name)

## Microsoft 365 Group

A collaboration group that can provide shared Microsoft 365 resources such as mailbox, calendar, SharePoint site, Planner, and Teams-backed collaboration.

Related: [Security Group](#security-group), [Dynamic Membership Group](#dynamic-membership-group)

## Microsoft Entra Hybrid Joined Device

A device joined to on-premises Active Directory and also represented in Microsoft Entra ID.

Related: [Device Identity](#device-identity), [Hybrid Identity](#hybrid-identity)

## Microsoft Entra Joined Device

A device joined directly to Microsoft Entra ID, commonly used for organization-owned cloud-managed devices.

Related: [Device Identity](#device-identity), [Microsoft Entra ID](#microsoft-entra-id)

## Microsoft Entra Registered Device

A device registered with Microsoft Entra ID, commonly used for BYOD or personal-device scenarios where the user still signs in locally or personally.

Related: [Device Identity](#device-identity), [Microsoft Entra ID](#microsoft-entra-id)

## Microsoft Graph

Microsoft's unified API for accessing and managing Microsoft cloud services and data.

Related: [Microsoft Graph PowerShell](#microsoft-graph-powershell), [Microsoft Entra ID](#microsoft-entra-id)

## Microsoft Graph PowerShell

PowerShell modules that use Microsoft Graph to manage Microsoft cloud services through Graph cmdlets.

Related: [Microsoft Graph](#microsoft-graph), [User Principal Name](#user-principal-name)

## Role-Based Access Control

An authorization model where permissions are assigned through roles rather than directly granting every permission to each user.

Related: [Privileged Identity Management](#privileged-identity-management), [Microsoft Entra ID](#microsoft-entra-id)

## Least Privilege

A security principle that grants only the permissions required to perform a task, and no more.

Related: [Role-Based Access Control](#role-based-access-control), [Privileged Identity Management](#privileged-identity-management), [Administrative Unit](#administrative-unit)

## Restricted Administrative Unit

An administrative unit that protects its members from management by broader tenant administrators unless those administrators are explicitly assigned to the restricted unit.

Related: [Administrative Unit](#administrative-unit), [Microsoft Entra ID](#microsoft-entra-id)

## Security Defaults

Baseline Microsoft Entra security settings that help protect tenants with common controls such as requiring stronger authentication for administrative access.

Related: [Microsoft Entra ID](#microsoft-entra-id), [Conditional Access](#conditional-access), [Authentication](#authentication)

## Security Group

A group used primarily for assigning access to resources or policies. In Microsoft Entra ID, security groups can include users, devices, or service principals.

Related: [Dynamic Membership Group](#dynamic-membership-group), [Mail-Enabled Security Group](#mail-enabled-security-group)

## Service Principal

The tenant-local security identity used by an application or service to access resources.

Related: [App Registration](#app-registration), [Enterprise Application](#enterprise-application), [Workload Identity](#workload-identity)

## Single Sign-On

An authentication experience where a user signs in once and can access multiple connected applications without repeatedly entering credentials.

Related: [Enterprise Application](#enterprise-application), [Microsoft Entra ID](#microsoft-entra-id)

## User Principal Name

The sign-in name for a user in Microsoft Entra ID, usually formatted like an email address.

Related: [Member User](#member-user), [Custom Domain](#custom-domain)

## Workload Identity

An identity used by software workloads, services, scripts, automations, or applications rather than by a human user.

Related: [Service Principal](#service-principal), [App Registration](#app-registration)

## B2B Collaboration

Microsoft Entra External ID capability that lets an organization invite external users into its tenant so they can access shared apps and resources with their own identities.

Related: [Guest User](#guest-user), [External Identity](#external-identity), [Cross-Tenant Access Settings](#cross-tenant-access-settings)

## B2B Direct Connect

A Microsoft Entra cross-tenant collaboration model used for direct organization-to-organization scenarios such as Teams shared channels.

Related: [Cross-Tenant Access Settings](#cross-tenant-access-settings), [Inbound Access](#inbound-access), [Outbound Access](#outbound-access)

## Cross-Tenant Access Settings

Microsoft Entra settings that control inbound and outbound collaboration, trust, and access behavior between tenants.

Related: [Tenant](#tenant), [B2B Collaboration](#b2b-collaboration), [B2B Direct Connect](#b2b-direct-connect)

## Cross-Tenant Synchronization

Microsoft Entra provisioning capability that automates creating, updating, and removing B2B collaboration users across tenants.

Related: [B2B Collaboration](#b2b-collaboration), [Tenant](#tenant), [Cross-Tenant Access Settings](#cross-tenant-access-settings)

## Email One-Time Passcode

An external identity authentication method where a guest user receives a temporary code by email to complete sign-in.

Related: [Guest User](#guest-user), [Identity Provider](#identity-provider), [B2B Collaboration](#b2b-collaboration)

## External Collaboration Settings

Microsoft Entra settings that control guest visibility, who can invite guests, self-service sign-up, guest leave behavior, and collaboration domain restrictions.

Related: [Guest User](#guest-user), [B2B Collaboration](#b2b-collaboration), [External Identity](#external-identity)

## External Identity

An identity from outside the organization that is allowed to access resources through Microsoft Entra External ID features.

Related: [Guest User](#guest-user), [B2B Collaboration](#b2b-collaboration), [Identity Provider](#identity-provider)

## Federation

An identity trust relationship where one identity provider authenticates users and another system accepts that authentication for access.

Related: [Identity Provider](#identity-provider), [SAML](#saml), [WS-Fed](#ws-fed), [OpenID Connect](#openid-connect)

## Guest Inviter

A Microsoft Entra role that allows a user to invite external guest users into the tenant without granting broader user administration rights.

Related: [Guest User](#guest-user), [B2B Collaboration](#b2b-collaboration), [Least Privilege](#least-privilege)

## Identity Provider

A system that creates, manages, and authenticates identities for users or applications.

Related: [Authentication](#authentication), [Federation](#federation), [Microsoft Entra ID](#microsoft-entra-id)

## Inbound Access

Cross-tenant access controls that determine what external users, groups, applications, or services from another tenant can do in your tenant.

Related: [Cross-Tenant Access Settings](#cross-tenant-access-settings), [Outbound Access](#outbound-access), [Tenant](#tenant)

## OpenID Connect

An identity protocol built on OAuth 2.0 that is commonly used for modern application sign-in.

Related: [Identity Provider](#identity-provider), [Federation](#federation), [Authentication](#authentication)

## Outbound Access

Cross-tenant access controls that determine what users and groups from your tenant can do in another tenant.

Related: [Cross-Tenant Access Settings](#cross-tenant-access-settings), [Inbound Access](#inbound-access), [Tenant](#tenant)

## SAML

Security Assertion Markup Language. A federation protocol commonly used for enterprise single sign-on and external identity provider integration.

Related: [Federation](#federation), [Identity Provider](#identity-provider), [Single Sign-On](#single-sign-on)

## Tenant Restrictions

Controls that restrict access to specified external tenants or applications, helping organizations limit collaboration with untrusted tenants.

Related: [Tenant](#tenant), [Cross-Tenant Access Settings](#cross-tenant-access-settings), [Outbound Access](#outbound-access)

## WS-Fed

WS-Federation. A federation protocol used in some Microsoft and enterprise identity scenarios.

Related: [Federation](#federation), [Identity Provider](#identity-provider), [SAML](#saml)

## Access Token

A signed token issued by Microsoft Entra ID that allows a client or application to access a protected API or resource.

Related: [OAuth 2.0](#oauth-20), [Refresh Token](#refresh-token), [ID Token](#id-token)

## Authentication Strength

A Conditional Access control that specifies which combinations of authentication methods are acceptable for accessing a resource.

Related: [Multi-Factor Authentication](#multi-factor-authentication), [Conditional Access](#conditional-access), [FIDO2](#fido2)

## Certificate-Based Authentication

A passwordless authentication method that uses X.509 certificates, often with smart cards, to authenticate users.

Related: [Authentication](#authentication), [Smart Card](#smart-card), [Multi-Factor Authentication](#multi-factor-authentication)

## FIDO2

A phishing-resistant passwordless authentication standard used by security keys and passkeys.

Related: [Passkey](#passkey), [Authentication Strength](#authentication-strength), [Multi-Factor Authentication](#multi-factor-authentication)

## ID Token

A signed token that tells an application who the authenticated user is.

Related: [OpenID Connect](#openid-connect), [Access Token](#access-token), [Authentication](#authentication)

## Multi-Factor Authentication

An authentication requirement that uses two or more different factor types, such as something you know, something you have, or something you are.

Related: [Authentication](#authentication), [Conditional Access](#conditional-access), [Authentication Strength](#authentication-strength)

## OATH Token

A hardware or software token that generates one-time passcodes for authentication.

Related: [Multi-Factor Authentication](#multi-factor-authentication), [TOTP](#totp), [Authentication](#authentication)

## OAuth 2.0

An authorization framework commonly used to grant delegated access to APIs and resources by using access tokens.

Related: [Access Token](#access-token), [OpenID Connect](#openid-connect), [Microsoft Graph](#microsoft-graph)

## Passkey

A passwordless credential based on FIDO2/WebAuthn that uses cryptographic keys instead of a shared password.

Related: [FIDO2](#fido2), [Authentication](#authentication), [Authentication Strength](#authentication-strength)

## Password Writeback

A hybrid identity capability that writes password changes or resets from Microsoft Entra ID back to on-premises Active Directory Domain Services.

Related: [Self-Service Password Reset](#self-service-password-reset), [Hybrid Identity](#hybrid-identity), [Microsoft Entra Connect](#microsoft-entra-connect)

## Refresh Token

A token used to request new access tokens without prompting the user to sign in again every time.

Related: [Access Token](#access-token), [OAuth 2.0](#oauth-20), [Single Sign-On](#single-sign-on)

## Self-Service Password Reset

A Microsoft Entra feature that lets users reset or unlock their own accounts after verifying their identity with approved authentication methods.

Related: [Password Writeback](#password-writeback), [Authentication](#authentication), [Multi-Factor Authentication](#multi-factor-authentication)

## Smart Card

A physical card containing a certificate or credential used for strong authentication.

Related: [Certificate-Based Authentication](#certificate-based-authentication), [Authentication](#authentication)

## Temporary Access Pass

A time-limited passcode created by an administrator to help users sign in, recover access, or register stronger authentication methods.

Related: [Self-Service Password Reset](#self-service-password-reset), [Authentication](#authentication), [FIDO2](#fido2)

## TOTP

Time-based One-Time Password. A code that changes on a time interval and is generated by an authenticator app or token.

Related: [OATH Token](#oath-token), [Multi-Factor Authentication](#multi-factor-authentication)

## Windows Hello for Business

A passwordless Windows sign-in method that uses a PIN or biometrics tied to the device and backed by asymmetric keys.

Related: [Authentication](#authentication), [FIDO2](#fido2), [Authentication Strength](#authentication-strength)
