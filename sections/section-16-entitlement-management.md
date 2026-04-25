# Section 16: Plan and implement entitlement management in Microsoft Entra

This section covers Microsoft Entra [Entitlement Management](../00-front-matter/glossary.md#entitlement-management), [access packages](../00-front-matter/glossary.md#access-package), catalogs, request policies, Terms of Use, and guest lifecycle review. The main theme is moving from scattered manual access assignments to structured, policy-governed access.

> [!NOTE]
> Entitlement Management is part of Microsoft Entra ID Governance. It is designed for controlled access to groups, Teams, SharePoint sites, enterprise applications, and other governed resources.

## 107. Plan Entitlements

### Core idea

Entitlement Management gives users access through structured access packages instead of assigning every resource manually. An access package bundles the resources a person needs for a role, project, department, or temporary business need.

### What to know

- Entitlement Management helps users request the right access without needing to know every underlying group, app, Team, or SharePoint site.
- Access packages can include groups, Teams, enterprise applications, SaaS apps, and SharePoint sites.
- Policies control who can request the package, whether approval is required, how long access lasts, and whether access is reviewed later.
- Entitlement Management can support internal users and external users from connected organizations.
- Delegation lets catalog owners or access package managers help manage access without making everyone a broad tenant administrator.

### Core objects

| Object | What it means | Memory hook |
|---|---|---|
| [Entitlement Management](../00-front-matter/glossary.md#entitlement-management) | The governance system for packaging, requesting, approving, assigning, and expiring access. | The access process |
| [Entitlement Catalog](../00-front-matter/glossary.md#entitlement-catalog) | A container that organizes related access packages and resources. | The folder |
| Access package | A bundle of resource roles users can receive or request. | The bundle |
| Access package policy | Rules for requesters, approvals, duration, review, and lifecycle behavior. | The rulebook |
| Connected organization | An external organization whose users can be allowed to request access packages. | The partner source |

### Resources that can be included

| Resource type | Example use |
|---|---|
| Microsoft Entra security groups | Assign permission or policy-based access through group membership. |
| Microsoft 365 groups and Teams | Give access to collaboration spaces and Teams-backed resources. |
| Enterprise applications and SaaS apps | Grant app assignments through the access package. |
| SharePoint sites | Grant access to project or department content. |
| Microsoft Entra roles | Govern privileged access scenarios when configured in supported governance workflows. |

### Why this matters

Large organizations often struggle with access because users do not know what to request, managers do not always know what to approve, and admins may forget to remove access later. Entitlement Management improves this by making access structured, requestable, approvable, time-limited, and reviewable.

> [!WARNING]
> An access package is not just a folder of links. It assigns resource roles. If the package includes a group, app, or SharePoint role, receiving the package can grant real access.

> [!TIP]
> Memory hook: catalog equals collection of packages; package equals collection of resources; policy equals the rules for who gets the package and for how long.

## 108. Create and configure catalogs

### Core idea

A catalog organizes related resources and access packages. It is commonly aligned to a business area, project, department, or delegated ownership boundary.

### What to know

- A catalog does not grant access by itself.
- Access packages live inside catalogs.
- Resources must be available in a catalog before they can be included in access packages.
- Catalogs can have owners so access management can be delegated to people closer to the business process.
- Catalogs can be enabled or disabled for external user requests, depending on the governance need.

### Example from the walkthrough

| Item | Example |
|---|---|
| Test user | Medical User |
| Collaboration resource | Medical Project Users Microsoft 365 group |
| Catalog | Medical Catalog |
| Purpose | Organize future medical project access packages and resources |

### Catalog workflow

| Step | Action |
|---:|---|
| 1 | Create or identify the resources that need to be governed. |
| 2 | Create a catalog for the business area, project, or function. |
| 3 | Add resources such as groups, apps, Teams, or SharePoint sites to the catalog. |
| 4 | Create access packages inside the catalog. |
| 5 | Add policies that define who can request access and under what conditions. |

### Why a Microsoft 365 group was useful

A Microsoft 365 group can be connected to collaboration resources such as Teams and SharePoint. That makes it useful for project-based access packages because receiving the package can grant access to the collaboration space and its related resources.

> [!WARNING]
> A catalog is a management container, not the access bundle users receive. The access package is what grants resource roles to the user.

> [!TIP]
> Memory hook: catalog is the shelf; access packages are the labeled boxes on the shelf.

## 109. Create and configure access packages

### Core idea

An access package is the actual governed bundle of access. It is created inside a catalog and includes resource roles such as group membership, app assignment, or SharePoint access.

### Where to create it

In the Microsoft Entra admin center, go to **ID Governance** or **Identity Governance**, open **Entitlement Management**, and create a new access package.

### Example from the walkthrough

| Setting | Example |
|---|---|
| Access package name | Medical Project Users |
| Catalog | Medical Catalog |
| Group or Team | Medical Project Users |
| Application | Adobe Identity Management |
| SharePoint resource | Site associated with the Microsoft 365 group |
| Requester scope | Specific user: Medical User |
| Approval | Not required in the walkthrough |

### Main setup areas

| Setup area | What it controls |
|---|---|
| Basics | Name, description, and catalog placement. |
| Resource roles | Groups, Teams, applications, SharePoint sites, or supported roles included in the package. |
| Requests | Who can request the package or whether only admins can assign it. |
| Approval | Whether approval is required, and whether it is single-stage or multi-stage. |
| Lifecycle | Expiration, assignment duration, access reviews, and renewal behavior. |
| Custom controls | Questions, verified ID requirements, custom extensions, or extra request information. |

### Request and approval options

| Option | When it fits |
|---|---|
| All users in the directory | Broad internal access request scenario. |
| Specific users or groups | Controlled internal audience. |
| Connected organizations | External partner access scenario. |
| Administrator direct assignment only | No self-service request flow. |
| No approval | Low-risk or lab scenario. |
| Single-stage approval | One reviewer must approve before assignment. |
| Multi-stage approval | Higher-risk access that needs multiple approvals. |

### What to verify after creation

- The access package appears in the correct catalog.
- The expected resources are listed under the package.
- Each resource has the intended role, such as member or user.
- The request policy targets the right requester population.
- Lifecycle and approval behavior match the risk level of the access.

> [!WARNING]
> Creating an access package without the right request policy can make the package unavailable, too broad, or only assignable by administrators.

> [!TIP]
> Memory hook: access package setup follows B-R-A-L: basics, resources, approvals, lifecycle.

## 110. Manage Access Requests

### Core idea

An access request is the user-facing flow where a requester asks for an access package. If the request is approved or allowed by policy, the user receives the resource roles included in the package.

### Request flow

| Step | User or admin action |
|---:|---|
| 1 | Admin copies or shares the access package request link. |
| 2 | User opens the link and signs in. |
| 3 | User selects the package and submits the request. |
| 4 | User provides required justification or answers if configured. |
| 5 | Approval happens if the policy requires it. |
| 6 | Assignment becomes active if the policy permits access. |
| 7 | User receives the package resources, such as group membership, app access, or SharePoint access. |

### Example from the walkthrough

| Before request | After request |
|---|---|
| Medical User was not a member of the Medical Project Users group. | Medical User appeared as a member after the request was processed. |
| User did not yet have the package resources. | User could see the package resources, including group, SharePoint, and application entries. |
| Admin used the request URL for testing. | Admin verified success by refreshing group membership. |

### Important distinction

| Concept | Meaning |
|---|---|
| Create an access package | Admin defines the governed bundle of access. |
| Request an access package | User asks to receive that bundle. |
| Assignment | The active result after the user is granted the package. |

### Application access note

An application can appear in an access package, but the app still needs to be correctly configured on the application side. The access package can grant assignment, but the app’s SSO, provisioning, claims, or app-specific setup may still affect the final user experience.

> [!WARNING]
> Do not assume the package worked just because the request page shows the resource. Verify the underlying assignment, such as group membership or application assignment, from the admin side.

> [!TIP]
> Memory hook: access package is the bundle; access request is how the user activates the bundle; assignment is the active granted result.

## 111. Implement and manage Terms of Use

### Core idea

[Terms of Use](../00-front-matter/glossary.md#terms-of-use) lets an organization require users to accept a legal, privacy, policy, or compliance notice before accessing resources.

### What Terms of Use is used for

| Scenario | Example |
|---|---|
| Legal acknowledgment | Non-disclosure agreement or acceptable use notice. |
| Privacy notice | Privacy or data handling acknowledgment. |
| Compliance awareness | GDPR-related or regulatory information. |
| Group-specific policy | Marketing, contractor, partner, or sensitive project agreement. |

### What can be configured

| Setting | Purpose |
|---|---|
| Name and display name | Identifies the agreement for admins and users. |
| PDF document | The actual notice or agreement users must review. |
| Language | Supports localized terms. |
| Require expand | Forces users to open or expand the document before accepting. |
| Consent on every device | Can require acceptance per device in supported scenarios. |
| Expiration or re-acceptance | Requires users to accept again after a defined period or document update. |

### Enforcement model

Creating the Terms of Use object defines the agreement, but enforcement happens through Conditional Access. A Conditional Access policy targets the users, groups, apps, or conditions and then requires the selected Terms of Use as a grant control.

### Example from the walkthrough

| Step | What happened |
|---:|---|
| 1 | A Terms of Use document was created for a marketing scenario. |
| 2 | A Conditional Access policy targeted a marketing group. |
| 3 | The policy required users in scope to accept the Terms of Use. |
| 4 | Acceptance, decline, and audit information could be reviewed afterward. |

### Monitoring and auditing

- Review who accepted or declined the Terms of Use.
- Check audit logs for Terms of Use events.
- Update the document version when the terms change.
- Require re-acceptance when the policy or document update requires it.

> [!WARNING]
> Creating Terms of Use alone does not apply it to users. Conditional Access is the enforcement mechanism.

> [!TIP]
> Memory hook: Terms of Use is the notice; Conditional Access is the checkpoint that makes users accept it.

## 112. Manage the lifecycle of external users

### Core idea

Guest access should not last forever without review. Microsoft Entra access reviews can periodically check whether external users should still have access to Microsoft 365 groups, Teams, applications, or other governed resources.

### Why this matters

- Guest users often need temporary or project-based access.
- External access can become stale if nobody reviews it.
- Access reviews create a scheduled process to confirm, remove, or renew guest access.
- Reviews support governance for external collaboration and help reduce unnecessary standing access.

### Example from the walkthrough

| Setting | Example |
|---|---|
| Review target | Teams and groups |
| Scope | All Microsoft 365 groups with guest users |
| Reviewed identities | Guest users only |
| Reviewer | Selected user |
| Recurrence | Quarterly |
| End date | No end date |
| If reviewer does not respond | Remove access |
| Auto-apply results | Enabled in the walkthrough |

### Reviewer options

| Reviewer type | When it fits |
|---|---|
| Group owners | Owners understand whether guests still need access to their group. |
| Users review their own access | Useful for attestation, but weaker for external access cleanup. |
| Managers | Useful for employee access, less reliable for guests if manager data is missing. |
| Selected users | Centralized review by a security, compliance, or project owner. |

### Review lifecycle

| Step | Governance decision |
|---:|---|
| 1 | Identify the guest access that needs periodic review. |
| 2 | Choose who should review that access. |
| 3 | Define recurrence and duration. |
| 4 | Decide what happens if reviewers approve, deny, or do not respond. |
| 5 | Decide whether review results should be automatically applied. |
| 6 | Monitor results and follow up on exceptions. |

### No-response behavior

| Choice | Effect |
|---|---|
| Remove access | Safer for stale guest access when reviewers do not respond. |
| Approve access | Less disruptive, but can preserve unnecessary access. |
| Use recommendations | Relies on available recommendation signals. |

> [!WARNING]
> Auto-apply is powerful. If reviewers deny access or fail to respond and the fallback is remove access, Microsoft Entra can automatically remove access based on that outcome.

> [!TIP]
> Memory hook: access review is the scheduled access check; guest review is the cleanup cycle for external access.

## Assignment 11: Create an Access Request Catalog and Package for Medical User

### Core idea

This assignment should document the creation of a catalog, an access package, the request flow, and the resulting assignment for a Medical User scenario.

### Evidence to document

- Catalog name and purpose.
- Resources added to the catalog.
- Access package name, description, and catalog placement.
- Resources and roles included in the package.
- Requester scope and approval settings.
- Request submission evidence with sanitized details.
- Verification that the user received the expected resource access.
- Cleanup steps if the resources are no longer needed.

### Repository note

Document the assignment in [section-16-assignment-11-access-request-catalog-package.md](../assignments/section-16-assignment-11-access-request-catalog-package.md).
