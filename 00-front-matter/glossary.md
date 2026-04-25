# SC-300 Glossary and Acronym Cram Sheet

Use this page as a fast lookup while reviewing the section notes. Official Microsoft Learn references belong in the objective map or reference index, not inside every glossary entry.

## High-Yield Acronyms

| Acronym | Stands For | Exam Meaning |
|---|---|---|
| AD DS | Active Directory Domain Services | Traditional on-premises directory service for users, computers, groups, domains, Kerberos, LDAP, and Group Policy. |
| AU | Administrative Unit | Scopes administration over selected users, groups, or devices. Not the same as a security group. |
| B2B | Business-to-Business | External collaboration model where guests from another organization access your tenant resources. |
| BYOD | Bring Your Own Device | Personal-device scenario often tied to device registration, Conditional Access, app protection, and compliance controls. |
| CA | Conditional Access | Entra policy engine that evaluates signals and enforces allow, block, MFA, device, session, or terms-of-use controls. |
| CAE | Continuous Access Evaluation | Rechecks important session conditions more quickly, such as account disablement, password change, or risk changes. |
| CASB | Cloud Access Security Broker | Security control layer for visibility, threat detection, governance, and control over cloud app usage. |
| CBA | Certificate-Based Authentication | Passwordless authentication using X.509 certificates, often with smart cards. |
| DC | Domain Controller | AD DS server that authenticates domain users/computers and stores directory data. |
| DLP | Data Loss Prevention | Controls that detect and reduce accidental or unauthorized data exposure. |
| DMZ | Demilitarized Zone | Perimeter network used for public-facing services while protecting the internal network. |
| DNS | Domain Name System | Resolves names to IP addresses and helps domain-joined clients locate AD DS services. |
| FIDO2 | Fast IDentity Online 2 | Phishing-resistant passwordless standard used by security keys and passkeys. |
| GSA | Global Secure Access | Microsoft Entra Security Service Edge solution for Internet Access and Private Access. |
| IAM | Identity and Access Management | Broad discipline for identities, authentication, authorization, access policy, and governance. In Azure portals, IAM also commonly refers to Access Control. |
| IdP | Identity Provider | System that authenticates users or workloads and issues identity tokens or assertions. |
| JIT | Just-in-Time | Temporary access model used heavily with PIM. Access is activated only when needed. |
| KQL | Kusto Query Language | Query language for Azure Monitor, Log Analytics, Sentinel, Defender, and Entra log analysis. |
| LDAP | Lightweight Directory Access Protocol | Directory access protocol used by apps and services to query directory data. |
| MFA | Multi-Factor Authentication | Authentication with two or more factor types: know, have, or are. |
| MSA | Managed Service Account | AD DS service account type for Windows services or scheduled tasks with managed password behavior. |
| OATH | Open Authentication | Token standard used for one-time passcodes. Do not confuse with OAuth. |
| OAuth 2.0 | Open Authorization 2.0 | Authorization framework for delegated API/resource access using tokens. |
| OIDC | OpenID Connect | Identity layer on top of OAuth 2.0 used for modern app sign-in. |
| PIM | Privileged Identity Management | Entra governance feature for eligible, time-bound, approved, and audited privileged access. |
| RBAC | Role-Based Access Control | Authorization model where permissions are granted through roles at a scope. |
| SAML | Security Assertion Markup Language | Federation protocol commonly used for enterprise SSO with SaaS apps. |
| SCIM | System for Cross-domain Identity Management | Standard for automated user/group provisioning into SaaS apps. |
| SIEM | Security Information and Event Management | Central platform for collecting, correlating, and investigating security events. |
| SOAR | Security Orchestration, Automation, and Response | Automation layer for response workflows, often paired with SIEM. |
| SSE | Security Service Edge | Cloud-delivered security model that includes secure web gateway and private access patterns. |
| SSPR | Self-Service Password Reset | Lets users reset or unlock their own accounts after identity verification. |
| SWG | Secure Web Gateway | Protects web/SaaS access with filtering, inspection, and policy enforcement. |
| TAP | Temporary Access Pass | Time-limited passcode used for onboarding, recovery, or registering stronger auth methods. |
| ToU | Terms of Use | Legal or compliance notice users must accept, enforced through Conditional Access. |
| TOTP | Time-Based One-Time Password | Time-rotating one-time code used by authenticator apps or hardware/software OATH tokens. |
| UPN | User Principal Name | User sign-in name, usually formatted like an email address. |
| VPN | Virtual Private Network | Encrypted remote access method for private network resources. |
| WHfB | Windows Hello for Business | Passwordless Windows sign-in using PIN or biometrics tied to the device. |
| WS-Fed | WS-Federation | Federation protocol used in some Microsoft and enterprise identity scenarios. |

## Core Identity Terms

### Microsoft Entra ID

Microsoft's cloud identity and access management service. It provides users, groups, devices, authentication, roles, application access, and policy enforcement for Microsoft cloud services and integrated apps.

### Azure Active Directory

The former name for Microsoft Entra ID. Older screenshots, portals, scripts, docs, and exam wording may still say Azure AD.

### Tenant

A dedicated Microsoft cloud directory instance for an organization. It contains identities, groups, apps, devices, roles, policies, domains, and configuration.

### Directory

A structured identity store that holds objects such as users, groups, devices, applications, roles, and related settings.

### Member User

An internal user account in a Microsoft Entra tenant, usually representing an employee or organizational user.

### Guest User

An external user invited into a tenant for collaboration, usually through Microsoft Entra External ID or B2B collaboration.

### Identity Provider

A system that manages and authenticates identities. Microsoft Entra ID, AD FS, and third-party federation systems can act as identity providers.

### Authentication

The process of proving who you are through passwords, MFA, certificates, passkeys, tokens, or other methods.

### Authorization

The process of deciding what an authenticated identity is allowed to access or do.

### Single Sign-On

An authentication experience where a user signs in once and can access connected applications without repeatedly entering credentials.

### Zero Trust

A security model that assumes no implicit trust and continuously verifies identity, device, risk, location, app, and session context.

### Least Privilege

A security principle that grants only the permissions needed to perform a task, and no more.

## Microsoft Entra Administration

### Administrative Unit

A container used to scope administrative control over selected users, groups, or devices. It is for delegated administration, not normal app/resource access.

### Restricted Administrative Unit

An administrative unit that protects its members from management by broader tenant administrators unless those admins are explicitly assigned to the restricted unit.

### Microsoft Entra Role

A role used to manage Microsoft Entra, Microsoft 365, or identity administration tasks, such as User Administrator or Global Reader.

### Global Administrator

The most powerful Microsoft Entra administrator role. It should be tightly limited and protected with strong controls.

### Global Reader

A read-only role for broad tenant visibility without write permissions.

### Privileged Role Administrator

A role used to manage role assignments and privileged access configuration without granting full Global Administrator permissions.

### Security Group

A group used mainly for assigning access to resources or policies. It can include users, devices, or service principals.

### Microsoft 365 Group

A collaboration group that can provide shared Microsoft 365 resources such as mailbox, calendar, SharePoint site, Planner, and Teams.

### Dynamic Membership Group

A group whose membership is calculated automatically from user or device attributes.

### Mail-Enabled Security Group

A group that can receive email and also be used for permissions.

### Custom Security Attribute

A business-specific key-value attribute that can be assigned to supported Entra objects for filtering, automation, access decisions, or app logic.

### Custom Domain

A verified domain name owned by an organization and added to a Microsoft tenant for sign-in names, email, and cloud services.

### Company Branding

Customization of the Microsoft Entra sign-in page with organization logos, colors, layout, and sign-in text.

## Hybrid Identity and AD DS

### Active Directory Domain Services

The traditional on-premises Microsoft directory service used to manage users, computers, groups, domains, authentication, and Group Policy.

### Domain

A logical AD DS identity and management boundary, commonly aligned to an organization's DNS namespace.

### Forest

The top-level AD DS boundary that contains one or more domains and shares a common schema, configuration, and trust model.

### Domain Controller

A server running AD DS that stores directory data and authenticates users and computers in the domain.

### Global Catalog

A domain controller role that stores searchable information about objects across an AD DS forest.

### Group Policy Object

A centralized AD DS policy object used to apply configuration, security settings, and restrictions to domain-joined users and computers.

### SYSVOL

A shared domain folder structure replicated between domain controllers and used for Group Policy and logon scripts.

### Kerberos

The primary modern authentication protocol used in AD DS domains.

### NTLM

A legacy Microsoft authentication protocol still encountered in older compatibility scenarios.

### Microsoft Entra Connect

Synchronization tooling used to connect on-premises AD DS identities with Microsoft Entra ID.

### Hybrid Identity

An identity model connecting on-premises AD DS with Microsoft Entra ID so users can access on-premises and cloud resources with a more unified sign-in experience.

### Password Writeback

A hybrid identity capability that writes password changes or resets from Microsoft Entra ID back to on-premises AD DS.

### Domain Join

The process of connecting a Windows computer to an AD DS domain so it can authenticate with domain accounts and receive domain policies.

## External Identities

### External Identity

An identity from outside the organization that is allowed to access resources through Microsoft Entra External ID features.

### B2B Collaboration

Microsoft Entra External ID capability that lets an organization invite external users into its tenant so they can access shared apps and resources with their own identities.

### B2B Direct Connect

A cross-tenant collaboration model used for direct organization-to-organization scenarios such as Teams shared channels.

### Cross-Tenant Access Settings

Settings that control inbound and outbound collaboration, trust, and access behavior between tenants.

### Inbound Access

Controls what external users, groups, applications, or services from another tenant can do in your tenant.

### Outbound Access

Controls what users and groups from your tenant can do in another tenant.

### Cross-Tenant Synchronization

Provisioning capability that automates creating, updating, and removing B2B collaboration users across tenants.

### External Collaboration Settings

Settings that control guest visibility, who can invite guests, self-service sign-up, guest leave behavior, and collaboration domain restrictions.

### Email One-Time Passcode

An external identity authentication method where a guest receives a temporary code by email to complete sign-in.

### Guest Inviter

A Microsoft Entra role that allows inviting guest users without granting broader user administration rights.

## Authentication and Access Management

### Multi-Factor Authentication

Authentication using two or more factor types: something you know, something you have, or something you are.

### Authentication Strength

A Conditional Access control that defines which authentication methods or method combinations are acceptable for a resource.

### Certificate-Based Authentication

Passwordless authentication using X.509 certificates, often with smart cards.

### FIDO2

A phishing-resistant passwordless authentication standard used by security keys and passkeys.

### Passkey

A passwordless credential based on FIDO2/WebAuthn that uses cryptographic keys instead of a shared password.

### Windows Hello for Business

Passwordless Windows sign-in using a PIN or biometrics tied to the device and backed by asymmetric keys.

### OATH Token

A hardware or software token that generates one-time passcodes for authentication.

### Temporary Access Pass

A time-limited passcode created by an admin to help users sign in, recover access, or register stronger authentication methods.

### Self-Service Password Reset

A feature that lets users reset or unlock their own accounts after verifying identity with approved authentication methods.

### Security Defaults

Baseline Microsoft Entra security settings that help protect tenants with common controls such as requiring stronger authentication.

### Legacy Authentication

Older authentication protocols or clients that do not support modern controls such as MFA and Conditional Access in the same way modern protocols do.

### Conditional Access

Microsoft Entra policy-based access control that evaluates signals such as user, location, device, application, and risk before allowing, blocking, or requiring extra controls.

### Named Location

A Conditional Access location object representing known IP ranges or countries/regions for policy decisions.

### Grant Control

The Conditional Access result that blocks access or grants access only after requirements such as MFA, compliant device, or authentication strength are satisfied.

### Session Control

A Conditional Access control that affects the session after access is granted, such as sign-in frequency, persistent browser behavior, or app control.

### Report-Only Mode

A Conditional Access policy state that logs what a policy would have done without enforcing the result.

### What If

A Conditional Access troubleshooting tool that simulates whether policies would apply under selected user, app, device, location, and risk conditions.

### Terms of Use

A legal or compliance agreement users can be required to accept through Conditional Access before accessing resources.

## Identity Protection

### Identity Protection

Microsoft Entra features that detect, investigate, and respond to user and sign-in risk.

### User Risk

The likelihood that a user account itself is compromised.

### Sign-In Risk

The likelihood that a specific sign-in attempt is suspicious or compromised.

### Risk Detection

A signal or event that contributes to user risk or sign-in risk.

### Risky User

A user account that Microsoft Entra evaluates as potentially compromised.

### Risky Sign-In

A specific sign-in attempt that Microsoft Entra evaluates as suspicious.

### Leaked Credentials

Credentials found in a known breach, dump, or threat intelligence source.

### Password Spray

An attack where an adversary tries one or a few common passwords against many accounts.

## Azure Roles and Resource Access

### Azure RBAC

Azure role-based access control for managing permissions to Azure resources at scopes such as management group, subscription, resource group, or resource.

### Role Assignment

A binding that grants a security principal a role at a specific scope.

### Scope

The boundary where an Azure RBAC assignment applies, such as management group, subscription, resource group, or resource.

### Effective Permissions

The actual actions an identity can perform after role permissions, scope, deny assignments, and assignments are evaluated together.

### Control Plane

The management layer used to create, configure, update, or delete Azure resources.

### Data Plane

The access layer used to read, write, or use data inside an Azure resource, such as reading a secret or accessing storage data.

### Deny Assignment

An Azure assignment that explicitly blocks specific actions, even when role assignments would otherwise grant access.

### Custom Azure Role

An Azure RBAC role definition created when built-in roles do not provide the exact permissions needed.

### Resource Group

A logical Azure container used to organize related resources and apply management, lifecycle, and access controls.

### Key Vault

An Azure service used to securely store and manage secrets, keys, and certificates.

### Key Vault Access Policy

A legacy vault-level authorization model that grants permissions to keys, secrets, or certificates directly inside the vault.

## Global Secure Access

### Global Secure Access

Microsoft Entra's Security Service Edge solution for identity-centric access to internet destinations, Microsoft services, and private applications.

### Microsoft Entra Internet Access

Global Secure Access capability that helps secure user access to internet and SaaS destinations through identity-aware controls.

### Microsoft Entra Private Access

Global Secure Access capability that provides Zero Trust access to private applications and internal resources without broad traditional VPN access.

### Traffic Forwarding Profile

A Global Secure Access configuration that determines which traffic is acquired, forwarded, or bypassed for assigned users or groups.

### Secure Web Gateway

A security service that protects web and SaaS access by applying filtering, inspection, and access controls.

### Security Service Edge

A cloud-delivered security model that combines secure web gateway, private access, and cloud access controls near users and apps.

### Web Content Filtering

A policy capability for allowing or blocking web access based on categories, domains, or security risk.

### Remote Network Connectivity

A Global Secure Access capability for connecting branch or remote networks without installing the client on every device.

## Workload Identities and App Registrations

### Workload Identity

An identity used by software workloads, services, scripts, automations, or applications rather than by a human user.

### Managed Identity

An Azure-managed identity that lets an Azure resource authenticate to supported services without storing credentials in code.

### System-Assigned Managed Identity

A managed identity created for one Azure resource whose lifecycle is tied to that resource.

### User-Assigned Managed Identity

A standalone managed identity created as an Azure resource that can be assigned to one or more supported Azure resources.

### Service Principal

The tenant-local security identity used by an application or service to access resources.

### Managed Service Account

An AD DS service account type designed for Windows services or scheduled tasks with managed password behavior.

### Standard User Account

A normal human user account used for interactive sign-in and user-driven work.

### App Registration

The Microsoft Entra object that defines an application's identity configuration, such as application ID, redirect URIs, API permissions, certificates, secrets, and authentication settings.

### Enterprise Application

The tenant representation of an application instance, used to manage access, assignment, SSO, provisioning, and application-specific settings.

### Redirect URI

The application URL where Microsoft Entra sends the authentication response after sign-in.

### API Permission

A permission requested by an app registration that allows an application to access an API such as Microsoft Graph.

### Delegated Permission

An API permission that allows an application to act on behalf of a signed-in user.

### Application Permission

An API permission that allows an application to act as itself without a signed-in user.

### Admin Consent

Consent granted by an administrator allowing an application to access permissions users cannot approve on their own.

### User Consent

Consent granted by a user allowing an application to access data or permissions the organization permits users to approve.

### Claim

A piece of information included in a token, such as a user attribute, app role, tenant, or permission value.

### App Role

An application-defined role assigned to users, groups, or service principals to control app-specific authorization.

### Access Token

A signed token issued by Microsoft Entra ID that allows a client or application to access a protected API or resource.

### ID Token

A signed token that tells an application who the authenticated user is.

### Refresh Token

A token used to request new access tokens without prompting the user to sign in again every time.

### OAuth 2.0

An authorization framework commonly used to grant delegated access to APIs and resources by using access tokens.

### OpenID Connect

An identity protocol built on OAuth 2.0 and commonly used for modern application sign-in.

### SAML

A federation protocol commonly used for enterprise single sign-on and external identity provider integration.

### Federation

An identity trust relationship where one identity provider authenticates users and another system accepts that authentication for access.

## Enterprise Applications

### Application Proxy

Microsoft Entra feature that publishes internal web applications securely through a cloud service and on-premises connector.

### Application Proxy Connector

A Windows Server component installed inside the corporate network that connects internal web apps to the Microsoft Entra Application Proxy cloud service.

### Automatic Provisioning

Automated creation, update, and removal of users or groups in a target application from Microsoft Entra ID.

### SCIM

A standard often used for automated user and group provisioning between identity providers and SaaS applications.

### App Collection

A My Apps grouping that organizes related enterprise applications for assigned users and groups.

## Defender for Cloud Apps

### Microsoft Defender for Cloud Apps

Microsoft's cloud app security broker capability for discovering cloud app usage, monitoring SaaS activity, governing connected apps, applying policies, and controlling supported sessions.

### Cloud Discovery

Capability that analyzes traffic and log data to identify cloud apps, users, IP addresses, traffic volume, and app risk.

### Cloud App Catalog

Defender for Cloud Apps database that evaluates cloud applications by risk, security, compliance, legal, and operational characteristics.

### Sanctioned App

A cloud application that an organization has approved for use.

### Unsanctioned App

A cloud application that an organization has marked as disallowed or not approved for business use.

### App Connector

An integration that connects Defender for Cloud Apps to supported cloud apps through APIs.

### Conditional Access App Control

A Defender for Cloud Apps capability that applies real-time access and session controls to supported cloud application sessions.

### Access Policy

In Defender for Cloud Apps, a policy that controls whether a user can enter a cloud app session.

### Session Policy

In Defender for Cloud Apps, a policy that controls or monitors what users can do inside a cloud app session after access is granted.

### File Policy

A policy that monitors or governs cloud file activity, sharing, sensitivity, ownership, or exposure conditions.

### OAuth App Policy

A policy that monitors or alerts on OAuth-connected applications based on filters such as publisher, permissions, or app behavior.

### Shadow IT

Use of applications, cloud services, or technology outside approved organizational governance or IT visibility.

### Data Exfiltration

Unauthorized movement, copying, downloading, or sharing of organizational data outside approved boundaries.

### Log Collector

A component or service used to collect logs from supported network devices or sources and forward them for Cloud Discovery analysis.

### Snapshot Report

A Cloud Discovery report generated from a specific uploaded or collected set of traffic logs.

## Identity Governance

### Entitlement Management

Microsoft Entra ID Governance capability used to package and manage access to groups, applications, Teams, and SharePoint sites through catalogs, access packages, policies, and approvals.

### Entitlement Catalog

A container that organizes related resources and access packages, often by project, department, or delegated ownership boundary.

### Access Package

A policy-governed bundle of resource roles that can be requested, approved, assigned, expired, and reviewed as a unit.

### Access Package Policy

Rules defining who can request or receive an access package, whether approval is required, how long access lasts, and whether lifecycle controls apply.

### Access Package Assignment

The active grant that results when an identity receives an access package and its included resource roles.

### Access Request

A self-service or admin-driven request for an access package assignment.

### Connected Organization

An external organization represented in entitlement management so its users can request access packages.

### Access Review

A governance process for periodically reviewing whether users, guests, or privileged identities should keep access.

### Auto-Apply Access Review Results

An access review setting that automatically applies decisions to the target resource when the review completes.

### Decision Helper

An access review recommendation signal that helps reviewers decide whether access should be approved or denied.

### Multi-Stage Access Review

An access review design where two or more reviewer stages make decisions sequentially.

### Privileged Identity Management

Microsoft Entra ID Governance capability for managing, approving, activating, and auditing privileged role access.

### Eligible Assignment

A privileged role assignment that allows a user to activate the role when needed, usually after MFA, justification, approval, or time limits.

### Active Assignment

A privileged role assignment that is currently usable without a separate activation step.

### Just-in-Time Access

An access model where privileged permissions are granted only when needed and only for a limited period.

### Privilege Bracketing

A security practice that grants elevated access for a defined task or time window and removes that access afterward.

### Emergency Access Account

A highly protected break-glass administrator account used to regain tenant access if normal administrative sign-in is disrupted.

## Monitoring, Logs, and Reporting

### Sign-In Logs

Microsoft Entra logs that record authentication activity, including success, failure, device details, Conditional Access results, and client app details.

### Audit Logs

Microsoft Entra logs that record administrative and directory changes, including who performed an action, what changed, and whether it succeeded.

### Provisioning Logs

Microsoft Entra logs that track automated user, group, and identity synchronization activity between connected systems.

### Diagnostic Settings

Configuration that routes selected logs and metrics to destinations such as Log Analytics, Storage, Event Hubs, or partner solutions.

### Log Analytics Workspace

An Azure Monitor workspace used to collect, store, query, and analyze log data with Kusto Query Language.

### Event Hubs

Azure event streaming service often used to send logs to external monitoring, SIEM, or analytics pipelines.

### Kusto Query Language

Microsoft query language used to search, filter, summarize, and analyze log and telemetry data.

### Workbook

An interactive Azure Monitor or Microsoft Entra dashboard that combines queries, charts, parameters, text, and visual reports.

### Identity Secure Score

A Microsoft Entra posture score that measures identity security configuration against Microsoft recommendations.

## Cloud and Network Basics

### Azure

Microsoft's cloud platform for infrastructure, platforms, applications, networking, storage, security, and management services.

### Microsoft 365

Microsoft's cloud productivity and collaboration service family, including Exchange Online, SharePoint Online, Teams, OneDrive for Business, Office apps, and Intune.

### Intune

Microsoft's cloud-based endpoint management service for devices, applications, compliance settings, and related controls.

### Microsoft Graph

Microsoft's unified API for accessing and managing Microsoft cloud services and data.

### IaaS

Infrastructure as a Service. Cloud infrastructure building blocks such as virtual machines, storage, networking, and firewalls.

### PaaS

Platform as a Service. The provider manages infrastructure while administrators configure the platform or service.

### SaaS

Software as a Service. Users consume a finished application without managing the underlying infrastructure or platform.

### Virtualization

The abstraction of physical compute resources so multiple virtual machines can run on shared hardware.

### Hypervisor

The software layer that allows multiple virtual machines to run on a physical host.

### Firewall

A network security control that permits or blocks traffic between networks, hosts, or security zones based on rules.

### VPN

An encrypted connection that allows remote users or networks to access private resources more securely.

### DMZ

A perimeter network used to host public-facing services while limiting their access to the internal private network.

### DNS

Name-resolution service that maps hostnames to IP addresses and is required for AD DS clients to locate domain services.

### SRV Record

A DNS record type that helps clients locate services, including AD DS domain controllers.
