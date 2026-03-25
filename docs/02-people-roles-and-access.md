# People, Roles, and Access

## People and Organizations

Turndown separates **people** from **companies**.

- A **person** is an individual user account.
- A **company** is the business context they work inside.
- A person can belong to one or more companies.
- A company can invite both individual people and other companies.

This matters because the platform is designed for real service relationships, not just one internal team.

## Company Types

A company can be one of these types:

| Company Type | Meaning |
|---|---|
| Property Management | Owns or manages the rental properties |
| Cleaner | Provides cleaning services |
| Maintenance | Provides repair or maintenance services |
| Other | A fallback category for service partners that do not fit the main buckets |

## Account Types

Turndown currently models these account types:

| Account Type | Meaning |
|---|---|
| Turndown Admin | Platform-level administrator |
| Account Admin | Business-level administrator |
| Property Manager | Oversees properties, people, and work quality |
| Maintainer | Performs repair or maintenance work |
| Cleaner | Performs cleaning or turnover work |
| Guest | Limited access user, likely temporary or restricted |

## How Access Works

The product has three overlapping ideas of access:

### 1. Primary company
A user may have a main company associated with their account.

### 2. Memberships
A user can also belong to one or more companies through a membership record.

### 3. Role inside that company
A user’s permissions are shaped by the role they have in that company.

In plain English: **who you are is not enough; the company context matters too**.

## Invitations

The system supports two different invitation models.

### Person-to-company invitation
A company can invite an individual by email into the company.

This is used for:

- inviting a cleaner
- inviting a maintenance person
- inviting a manager
- bringing in a teammate who does not have an account yet

### Company-to-company invitation
One company can invite another company into a service relationship.

This is used for:

- property company inviting a cleaning company
- property company inviting a maintenance company
- any service-provider relationship where work will move across company boundaries

## Relationship Model

After a company invitation is accepted, the relationship becomes an active connection between:

- a **requesting company**
- a **provider company**

That means Turndown is designed to support a business hiring another business, not only direct employee management.

## Invitation Lifecycle

| Status | Meaning |
|---|---|
| Pending | Sent but not acted on yet |
| Accepted | Accepted successfully |
| Declined | Explicitly turned down |
| Expired | Timed out before action |
| Revoked | Withdrawn by the sender |

## Relationship Lifecycle

| Status | Meaning |
|---|---|
| Active | Relationship is live and usable |
| Inactive | Relationship exists but is not currently in use |
| Suspended | Relationship is temporarily blocked or restricted |

## What Each Role Likely Needs to See

### Property Manager
Should see:

- company information
- team roster
- service-provider relationships
- all properties
- room setup
- standards and checklist setup
- work sessions
- issue review
- supply problems
- history and trends

### Cleaner
Should see:

- assigned jobs
- today’s schedule
- property access details
- room checklists
- required photo steps
- issue reporting
- supply levels relevant to the job
- own work history

### Maintainer
Should see:

- assigned issues or work orders
- property and room context
- damage details
- before and after photos
- scheduling details
- completion notes

### Account Admin
Should see:

- company settings
- users and invitations
- subscription and billing status
- relationship management
- company-wide configuration

## Access Philosophy

The system strongly suggests this product rule:

> The same person may look powerful in one company and limited in another.

That means the UI should always make the **current company context** visible. Otherwise users will think the app is broken when it is really showing a different permission scope. Classic multi-tenant fun.
