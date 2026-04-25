# Section 10: Implement access management for Azure resources by using Azure roles

This section separates Microsoft Entra administration from Azure resource authorization. Microsoft Entra roles manage identity and directory administration. Azure roles manage access to Azure resources such as resource groups, virtual machines, storage accounts, databases, and Key Vaults.

> [!NOTE]
> The exam distinction is simple but important: Microsoft Entra roles control identity administration; Azure RBAC controls Azure resource access.

## 74. Create Custom Azure Roles Including Control Plane and Data Plane Permissions

### Core idea

[Azure RBAC](../00-front-matter/glossary.md#azure-rbac) is the authorization system for Azure resources. It controls who can access Azure resources, what actions they can perform, and at what scope.

### Entra roles vs Azure roles

| Role type | Used for | Example |
|---|---|---|
| Microsoft Entra roles | Identity, directory, tenant, and Microsoft 365 administration. | Global Administrator, User Administrator, Security Reader. |
| Azure roles | Azure resource access through Azure RBAC. | Owner, Contributor, Reader, Virtual Machine Contributor. |

> [!WARNING]
> Do not confuse Microsoft Entra roles with Azure RBAC roles. A user can be powerful in Entra ID but have no access to a resource group, and a user can manage Azure resources without being a tenant administrator.

### Resource groups

A resource group is a logical container for related Azure resources. Permissions can be assigned at the resource group level so the assignment applies to the resources inside that group.

Common Azure RBAC scopes:

| Scope | What it affects |
|---|---|
| Management group | Multiple subscriptions under the management group. |
| Subscription | All resource groups and resources in the subscription. |
| Resource group | All resources inside that resource group. |
| Resource | One specific Azure resource. |

### Access Control (IAM)

Access is configured through **Access Control (IAM)**.

From IAM, administrators can:

- Assign built-in roles.
- Assign custom roles.
- Review role assignments.
- Check access for a user, group, service principal, or managed identity.
- Review deny assignments.

### Custom roles

A custom role is used when built-in Azure roles do not match the exact permission set needed.

Custom roles define:

| Element | Meaning |
|---|---|
| Name | Friendly role name, such as VM Management. |
| Description | What the role is intended to allow. |
| Permissions | Allowed and excluded control plane or data plane operations. |
| Assignable scopes | Where the role can be assigned. |

Example custom role idea:

```text
VM Management
```

Possible permissions:

- Read virtual machines.
- Start or stop virtual machines.
- Update selected VM settings.
- Delete virtual machines, if intentionally allowed.

### Control plane vs data plane

| Plane | What it means | Example |
|---|---|---|
| Control plane | Managing the Azure resource itself. | Create a VM, delete a storage account, configure a Key Vault. |
| Data plane | Accessing or using the data inside the resource. | Read a secret, download a blob, connect to a database. |

Azure role definitions can include both management permissions and data permissions.

| Permission field | Purpose |
|---|---|
| Actions | Allowed control plane operations. |
| NotActions | Excluded control plane operations. |
| DataActions | Allowed data plane operations. |
| NotDataActions | Excluded data plane operations. |

> [!WARNING]
> If allowed permissions and excluded permissions conflict, the exclusion wins. In Azure role definitions, `NotActions` reduces `Actions`, and `NotDataActions` reduces `DataActions`.

> [!TIP]
> Memory hook: control plane manages the resource; data plane uses what is inside the resource.

## 75. Assign Built-In and Custom Azure Roles

### Core idea

Azure roles are assigned through IAM at a scope such as subscription, resource group, or resource. A role assignment connects three things: a security principal, a role definition, and a scope.

### Role assignment model

| Piece | Meaning |
|---|---|
| Security principal | Who receives access: user, group, service principal, or managed identity. |
| Role definition | What permissions are granted: built-in or custom role. |
| Scope | Where the permissions apply: subscription, resource group, or resource. |

### Role assignment process

To assign a role at a resource group:

1. Open the resource group.
2. Go to **Access Control (IAM)**.
3. Select **Add**.
4. Choose **Add role assignment**.
5. Select a built-in or custom role.
6. Review the role permissions if needed.
7. Select the user, group, service principal, or managed identity.
8. Select **Review + assign**.
9. Confirm the assignment appears under **Role assignments**.

### Built-in vs custom roles

| Role type | Best use |
|---|---|
| Built-in role | Microsoft-provided role already matches the job. |
| Custom role | Built-in roles are too broad or too limited for the required task. |

> [!WARNING]
> Assign roles at the smallest scope that works. A role assigned at subscription scope can affect every resource group and resource in that subscription.

> [!TIP]
> Memory hook: role assignment equals who + what role + where.

## 76. Evaluate Effective Permissions for a Set of Azure Roles

### Core idea

Effective permissions are the actual permissions an identity has after all role assignments, inherited scopes, group membership, conditions, eligible assignments, and deny assignments are considered.

### Where to check access

Open the resource group or resource, then go to:

```text
Access Control (IAM)
```

### Tools in IAM

| Tool | What it shows |
|---|---|
| View my access | Your own effective access to the selected scope. |
| Check access | Access for a specific user, group, service principal, or managed identity. |
| Role assignments | Current role assignments at that scope. |
| Deny assignments | Explicit Azure-managed deny assignments that can block access. |
| Eligible assignments | PIM-eligible access that can be activated when needed. |

### How effective permissions work

Azure RBAC is generally additive. A user can receive permissions from multiple role assignments across different scopes.

Examples:

- A user assigned **Reader** at subscription scope can read resources throughout the subscription.
- A user assigned **Contributor** at one resource group can manage resources only in that group.
- A user assigned a role through group membership receives the role through that group.
- A deny assignment can block specific actions even when a role assignment would otherwise allow them.

### Resource group vs individual resource

| Scope checked | What to expect |
|---|---|
| Resource group IAM | Shows access that applies across the group and inherited permissions from higher scopes. |
| Individual resource IAM | Shows access to that specific resource, including inherited assignments. |

> [!WARNING]
> Deny assignments can override granted permissions. Also remember that PIM eligibility is not the same as active access until the role is activated.

> [!TIP]
> Memory hook: effective permissions are what the user can actually do, not just the role you remember assigning.

## 77. Assign Azure Roles to Enable Microsoft Entra ID Login to Azure Virtual Machines

### Core idea

Microsoft Entra login to Azure virtual machines uses Azure RBAC roles to decide who can sign in to the VM and whether they sign in as a standard user or administrator.

### VM login roles

| Role | What it allows |
|---|---|
| Virtual Machine Administrator Login | Sign in to the VM with administrator privileges. |
| Virtual Machine User Login | Sign in to the VM with standard user privileges. |

### Where to assign VM login roles

1. Open the Azure virtual machine.
2. Go to **Access Control (IAM)**.
3. Select **Add role assignment**.
4. Search for **Virtual Machine Administrator Login** or **Virtual Machine User Login**.
5. Select the user or group.
6. Review and assign.

### Important requirements

Microsoft Entra-based VM sign-in depends on more than creating the VM.

Key requirements include:

- Microsoft Entra login must be enabled for the VM.
- The correct VM login role must be assigned.
- The user must be in the same tenant as the VM for supported sign-in scenarios.
- The connecting client must meet the required Microsoft Entra join, registration, or hybrid join conditions for the chosen connection method.
- Network and authentication endpoints must be reachable.

### Connection concept

Users can connect through RDP, but Microsoft Entra authentication depends on the supported configuration. The exam focus is less about every VM creation screen and more about the role-based access requirement.

> [!WARNING]
> Owner or Contributor on a VM does not automatically grant Microsoft Entra sign-in to the VM. Use **Virtual Machine Administrator Login** or **Virtual Machine User Login** for Entra-based VM sign-in.

> [!TIP]
> Memory hook: Azure RBAC can manage the VM, but VM Login roles let you sign in to the VM.

### Cleanup note

Virtual machines cost money. In a lab, deleting the resource group is a clean way to remove the VM and related resources when the exercise is finished.

## 78. Configure Azure Key Vault Role-Based Access Control and Access Policies

### Core idea

Azure Key Vault securely stores and manages secrets, keys, and certificates. Access to Key Vault must be planned carefully because it often protects credentials and encryption material used by other systems.

### What Key Vault stores

| Object type | Example |
|---|---|
| Secrets | Passwords, API keys, tokens, connection strings. |
| Keys | Encryption keys used by applications and Azure services. |
| Certificates | TLS/SSL certificates and certificate lifecycle data. |

### Why Key Vault matters

- Centralized secret management.
- Reduced hard-coded credentials.
- Secure storage for sensitive values.
- Monitoring and logging.
- Integration with services such as Azure Disk Encryption, SQL Transparent Data Encryption, and App Service.

### Key Vault access models

Key Vault supports two authorization models.

| Access model | How access is managed | Notes |
|---|---|---|
| Azure RBAC | Uses Azure IAM and role assignments. | Recommended model for stronger centralized access control. |
| Vault access policies | Permissions are configured directly in the vault. | Legacy model; can create risk if users with vault management permissions can grant themselves data access. |

> [!WARNING]
> Key Vault Contributor can manage the vault control plane, but it does not automatically grant access to read secrets, keys, or certificates. Data plane access needs the right Key Vault data role or access policy.

### Control plane vs data plane in Key Vault

| Plane | Example operations | Access control |
|---|---|---|
| Control plane | Create or delete vaults, update properties, configure settings. | Azure RBAC. |
| Data plane | Read a secret, create a key, import a certificate, decrypt with a key. | Azure RBAC for Key Vault data roles or legacy access policies. |

### Common Key Vault RBAC roles

| Role | Purpose |
|---|---|
| Key Vault Administrator | Performs all data plane operations on keys, secrets, and certificates. |
| Key Vault Reader | Reads metadata, but not sensitive secret values or key material. |
| Key Vault Secrets Officer | Manages secrets, except permissions. |
| Key Vault Secrets User | Reads secret contents. |
| Key Vault Certificates Officer | Manages certificates. |
| Key Vault Crypto Officer | Manages cryptographic keys. |

### Key Vault configuration ideas

| Setting | What to remember |
|---|---|
| Standard tier | General Key Vault usage. |
| Premium tier | Supports HSM-backed key protection. |
| Deployment options | Can allow use for VM deployment, ARM template deployment, or Azure Disk Encryption where configured. |

### Related identity and access concepts

Section 10 ties several earlier concepts together:

| Concept | What to remember |
|---|---|
| Entra ID | Stores identities such as users, groups, devices, service principals, and managed identities. |
| Security groups | Common way to assign Azure roles to sets of users or identities. |
| Administrative Units | Scope Entra administration, not Azure resource access. |
| Entra roles | Manage identity and Microsoft 365 administration. |
| Azure RBAC | Manages Azure resource permissions. |
| Key Vault | Stores secrets, keys, and certificates that must be protected with least privilege. |

> [!TIP]
> Memory hook: Key Vault control plane manages the vault; Key Vault data plane opens the vault contents.

## High-Yield Review

| Topic | What to remember |
|---|---|
| Entra roles | Identity and tenant administration. |
| Azure RBAC | Azure resource authorization. |
| Resource group | Logical container and common role assignment scope. |
| Custom role | Used when built-in roles are not precise enough. |
| Control plane | Manage the resource. |
| Data plane | Use the resource data. |
| Effective permissions | Sum of applicable grants, reduced by exclusions, conditions, deny assignments, and inactive PIM eligibility. |
| VM login roles | Required for Microsoft Entra sign-in to Azure VMs. |
| Key Vault RBAC | Recommended model for managing Key Vault access. |

> [!WARNING]
> The biggest Section 10 exam trap is mixing identity administration with Azure resource authorization. Microsoft Entra roles, Azure RBAC roles, and Key Vault data plane permissions solve different access problems.
