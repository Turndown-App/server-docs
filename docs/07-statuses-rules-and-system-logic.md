# Statuses, Rules, and System Logic

This section lists the important predefined values and product rules that shape the app.

## Account and Company Choices

## User Account Types

| Value | Plain-English Meaning |
|---|---|
| Turndown Admin | Platform-level administrator |
| Account Admin | Company-level administrator |
| Property Manager | Manages properties and operations |
| Maintainer | Performs repair or maintenance work |
| Cleaner | Performs cleaning work |
| Guest | Restricted or limited-access user |

## Company Types

| Value | Meaning |
|---|---|
| Property Management | Owns or manages properties |
| Maintenance | Provides maintenance services |
| Cleaner | Provides cleaning services |
| Other | Fallback business type |

## User Status

| Value | Meaning |
|---|---|
| Active | Can use the account normally |
| Inactive | Account exists but is not active |

## Language Choices

The system currently models:
- English
- German
- Spanish
- French

## Property and Room Choices

## Property Types

The system already supports a broad property list, including:

- house
- apartment
- condo
- townhouse
- villa
- cabin
- cottage
- bungalow
- farmhouse
- ranch
- loft
- studio
- duplex
- triplex
- penthouse
- chalet
- castle
- beach house
- houseboat
- yurt
- treehouse
- other

## Room Types

The system currently supports:

- bedroom
- bathroom
- kitchen
- living room
- dining room
- office
- garage
- laundry room
- basement
- attic
- balcony
- porch
- garden
- other

## Work and Checklist Statuses

## Work Session Status

| Status | Meaning |
|---|---|
| Pending | Planned but not started |
| In Progress | Currently being worked |
| Completed | Finished successfully |
| Cancelled | No longer happening |

## Checklist Execution Status

| Status | Meaning |
|---|---|
| Pending | Not started |
| In Progress | Being worked right now |
| Completed | Finished |
| Skipped | Intentionally not completed |

## Invitation and Relationship Statuses

## Invitation Status

| Status | Meaning |
|---|---|
| Pending | Waiting for action |
| Accepted | Accepted |
| Expired | Timed out |
| Revoked | Withdrawn |
| Declined | Rejected |

## Company Relationship Status

| Status | Meaning |
|---|---|
| Active | Usable relationship |
| Inactive | Exists but not currently active |
| Suspended | Temporarily blocked |

## Damage and Issue Statuses

## Damage Severity

| Severity | Meaning |
|---|---|
| Minor | Small issue, limited impact |
| Moderate | Noticeable issue, manageable impact |
| Severe | Major issue affecting use or quality |
| Critical | Immediate or high-risk issue |

## Damage Status

| Status | Meaning |
|---|---|
| Open | Newly reported and unresolved |
| In Review | Being assessed |
| Resolved | Closed with a documented resolution |
| Escalated | Sent upward for additional action |

## Inventory Statuses

## Inventory Item Type

| Type | Meaning |
|---|---|
| Consumable | Gets used up, such as pods or paper towels |
| Fixed | Stays in place, such as equipment or a durable item |

## Restock Order Status

| Status | Meaning |
|---|---|
| Pending | Not yet placed or still being prepared |
| Ordered | Submitted to supplier |
| Shipped | On the way |
| Received | Delivered and received |

## Image Attachment Types

Images can belong to several kinds of records, including:

- user profile
- property
- company
- checklist item proof
- property room
- maintenance ticket
- cleaning report
- work report
- platform default / placeholder

## Product Rules That Matter for UX

### One active checklist per room
A room can only have one active room checklist at a time.

**Design implication:**  
The UI should make “activate” and “replace current checklist” explicit.

### Item completion is unique within a room execution
A checklist item can only be completed once during a single room execution.

**Design implication:**  
A done item should not look tappable in the same way as an undone item.

### A completed work session must have a completion time
The system expects finish time to exist when a session is completed.

**Design implication:**  
Completion should feel like a final action with confirmation.

### In-progress and completed sessions require a start time
A session cannot honestly be “in progress” without having started.

**Design implication:**  
There should be a clear “start job” moment.

### Resolved damage requires a resolution timestamp
The system expects a resolved issue to include the time it was resolved.

**Design implication:**  
Closing an issue should likely ask for at least minimal resolution detail.

### Only one pending invitation per target
The system avoids duplicate pending invites for:
- the same person into the same company
- the same company-to-company invitation pair

**Design implication:**  
Pending invites should be easy to spot so people do not keep sending duplicates.

### A company cannot invite itself
Because apparently the backend also believes in boundaries.

### A company cannot have a relationship with itself
Same logic, less drama.

### Some records are soft-deleted
Many records are not immediately destroyed. They are marked as deleted first.

**Design implication:**  
The product may need:
- archive states
- restore flows
- inactive badges
- separate “hidden vs deleted” behavior

### Time is automatically calculated in some places
The backend calculates:
- total session time
- time spent per room execution
- consumed and final inventory amounts

**Design implication:**  
The UI should display these values clearly, but not force users to do manual math.

## Permission-Oriented Design Notes

The current platform model strongly suggests these UI needs:

- show the active company clearly
- explain why an action is unavailable
- separate read-only from editable states
- avoid mixing internal staff with outside providers
- preserve room context throughout work execution
