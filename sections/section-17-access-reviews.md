# Section 17: Plan, implement, and manage access reviews in Microsoft Entra

This section focuses on Microsoft Entra [Access Reviews](../00-front-matter/glossary.md#access-review): how to plan them, create them, configure reviewers and recurrence, apply decisions, and avoid accidental access removal.

> [!NOTE]
> Access Reviews are part of Microsoft Entra ID Governance. They help verify whether users, guests, privileged users, and group or application members should still keep access over time.

## 113. Plan, create, configure, and manage Access Reviews in Entra ID

### Core idea

Access Reviews periodically check whether users should still have access to a resource. They are especially useful because identity access changes constantly as people join, leave, change teams, finish projects, or retain access longer than they should.

### Why access reviews matter

Over time, users can accumulate unnecessary access through old group memberships, project access, exception lists, privileged roles, or guest invitations. If nobody reviews that access, it becomes a security and audit risk.

| Access risk | Why it matters |
|---|---|
| Stale access | Users keep access after a project, role, or business need ends. |
| Guest sprawl | External users remain in groups or Teams long after collaboration ends. |
| Privilege accumulation | Users retain powerful roles or memberships that are no longer justified. |
| Reused groups | A group may be repurposed while old members remain. |
| Policy exception drift | Exception lists grow and stop reflecting the original business need. |
| Audit findings | Organizations may be unable to prove access is periodically reviewed. |

### Common review targets

| Target | Example |
|---|---|
| Microsoft 365 groups and Teams | Review members or guest users in a collaboration group. |
| Security groups | Review access granted through group membership. |
| Enterprise applications | Review users assigned to a business application. |
| Guest users | Confirm external users still have a business need. |
| Privileged access | Review role assignments through Privileged Identity Management. |
| Access package assignments | Review whether users should keep an entitlement assignment. |

> [!WARNING]
> Access Reviews can remove real access. If auto-apply is enabled, deny decisions or no-response fallback behavior can change group memberships, app assignments, or guest access.

### Walkthrough scenario

| Area | Example setting |
|---|---|
| Portal path | Microsoft Entra admin center -> Identity Governance -> Access Reviews -> New access review |
| Review target | Teams and groups |
| Resource | Selected Microsoft 365 group |
| Example group | Access Review Demo |
| Review scope | Guest users only |
| Reviewer | Selected user |
| Recurrence | Quarterly |
| Duration | Defined number of days |
| End condition | Based on review schedule settings |

### Review planning decisions

| Planning question | Why it matters |
|---|---|
| What access should be reviewed? | Determines whether the review targets groups, apps, roles, guests, or package assignments. |
| Who should be reviewed? | Scope can include everyone, guests only, inactive users, or selected users depending on the review type. |
| Who should review? | The reviewer should understand whether continued access is justified. |
| How often should it recur? | Sensitive or external access usually needs a recurring schedule. |
| What happens if reviewers do not respond? | No-response behavior can preserve access, remove access, approve access, or follow recommendations. |
| Should results auto-apply? | Auto-apply reduces manual cleanup but increases the impact of mistakes. |

### Reviewer options

| Reviewer option | Best fit |
|---|---|
| Group owner | Good for groups or Teams where the owner understands membership. |
| Selected users or groups | Good for centralized security, compliance, or project-owner review. |
| Users review their own access | Useful for attestation, but weaker for sensitive access decisions. |
| Managers of users | Useful when manager data is reliable and managers understand role need. |
| Multi-stage reviewers | Useful when higher-risk access needs sequential review or escalation. |

### Recurrence and duration

| Setting | Meaning |
|---|---|
| Duration | How long reviewers have to make decisions. |
| Recurrence | How often the review repeats, such as monthly, quarterly, or annually. |
| Start date | When the review series begins. |
| End condition | Whether the review never ends, ends on a date, or ends after a number of occurrences. |

### Important behavior settings

| Setting | What it does | Exam note |
|---|---|---|
| Auto apply results to resource | Applies review decisions automatically when the review completes. | Can remove access automatically. |
| If reviewers do not respond | Defines fallback behavior for undecided items. | Risky when paired with auto-apply. |
| Decision helpers | Shows recommendations such as inactivity-based guidance. | Helps reviewers, but does not replace judgment. |
| Justification required | Requires reviewers to explain decisions. | Useful for auditability. |
| Email notifications | Notifies reviewers when the review starts. | If disabled, reviewers still need to know a review is waiting. |
| Reminders | Sends reminder messages during the review window. | Helps prevent no-response outcomes. |

### No-response behavior

| Option | Result |
|---|---|
| No change | Access remains unchanged if nobody reviews. |
| Remove access | Access can be removed if no reviewer responds. |
| Approve access | Access can be kept even without reviewer action. |
| Take recommendations | Microsoft Entra recommendations are applied for undecided items. |

> [!WARNING]
> The dangerous combination is auto-apply plus remove access or take recommendations when reviewers do not respond. That can remove users automatically because a reviewer missed the review.

### Denied guest user actions

For guest users, access review completion can do more than remove a group or application assignment. Depending on configuration, denied guests can have membership removed from the resource, be blocked from signing in for a period, or eventually be removed from the tenant.

| Denied guest action | Meaning |
|---|---|
| Remove membership from resource | Removes the guest from the reviewed group, Team, or application assignment. |
| Block sign-in for 30 days | Temporarily blocks the guest before later cleanup. |
| Remove guest from tenant | Removes the external user object after the configured lifecycle behavior. |

### Managing an existing access review

After a review is created, you can manage:

- Reviewers.
- Current review settings.
- Future series settings.
- Review history.
- Scheduled review instances.
- Decisions and results.
- Audit logs.
- Reminders and notifications.

### Current vs series settings

| Area | Meaning |
|---|---|
| Current review | Changes affect the review instance already running. |
| Review series | Changes affect future recurrences. |

This distinction matters for recurring reviews. Updating only the current review does not necessarily change future review behavior.

### Comprehension checkpoints

| Question | Answer |
|---|---|
| What is the purpose of an Access Review? | To periodically verify whether users should still have access to a resource. |
| Why are Access Reviews important for security? | They reduce stale, excessive, guest, privileged, and unmanaged access over time. |
| What can be reviewed? | Groups, Teams, applications, guests, role assignments, and access package assignments depending on the review type. |
| Who can review access? | Group owners, selected users or groups, users themselves, managers, or multi-stage reviewers. |
| What does recurrence mean? | How often the review repeats, such as quarterly. |
| What does auto-apply mean? | Review decisions are enforced automatically after completion. |
| What happens if reviewers do not respond? | The configured fallback action applies, such as no change, remove access, approve access, or take recommendations. |
| What can happen to denied guests? | Their resource membership can be removed, sign-in can be blocked, or they can be removed from the tenant based on configuration. |

> [!TIP]
> Memory hook: Access Review equals recurring access check. The goal is to remove stale or excessive access before it becomes an incident.

## Section 17 Exam Traps

| Trap | Correct understanding |
|---|---|
| Access Reviews only apply to guest users. | They can review guests, employees, groups, apps, roles, and package assignments depending on configuration. |
| Creating a review automatically removes access immediately. | Access changes happen only after decisions are applied manually or automatically. |
| Recommendations are final decisions. | Recommendations help reviewers decide; they are only applied automatically if configured. |
| No-response behavior is harmless. | It can remove or approve access if paired with auto-apply. |
| Current and series settings are the same. | Current settings affect an active instance; series settings affect future recurrences. |
