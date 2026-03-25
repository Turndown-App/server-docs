# Screen Inventory

This section inventories the product surfaces implied by the current mobile app structure and backend capabilities.

## Shared Entry and Global Screens

| Area | Screen / View | Purpose | Key Actions | Important States |
|---|---|---|---|---|
| Auth | Sign In | Enter existing account | sign in, switch to sign up, forgot password | loading, bad credentials, rate-limited |
| Auth | Sign Up | Create a new account | register, choose account type | validation, duplicate email |
| Auth | Forgot Password | Recover access | request reset | success confirmation, expired/reset unavailable |
| Global | App Shell | Decide what navigation to show | load session, restore user, choose company context | splash/loading, unauthenticated, session expired |
| Global | Settings | Personal and app settings | profile edits, sign out, language/preferences | unsaved changes, signed out |

## Property Manager Experience

### Dashboard and Overview

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Dashboard | High-level control center | properties, jobs, open issues, supply concerns | open module, filter by company, act on alerts |
| Company Summary | View current company | company profile, team count, active relationships | edit company, invite people, invite provider company |

### Company and Team

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Team List | See internal members | people, roles, status | invite user, open profile, remove or change access |
| User Invitation Flow | Bring in a teammate | email, role, expiration | send invite, revoke invite |
| Provider Relationship List | See outside service companies | pending invites, active relationships, suspended links | invite company, view invite, suspend or reactivate |
| Company Switcher | Change business context | companies the user belongs to | switch active company |

### Properties

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Property List | Portfolio overview | name, location, type, photo, status cues | create property, search, open property |
| Create Property | Add a new property | form fields and property basics | save, cancel |
| Property Overview | Home for one property | summary, notes, photos, access snapshot | edit property, open rooms, open jobs |
| Property Access Information | Store how to enter and operate the property | entry instructions, codes, wifi, parking, alarms | edit access details |
| Property Notes / History | Capture context over time | notes, job history, issue history | add note, filter history |

### Rooms

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Room List | View rooms in a property | room name, type, hero photo, checklist state | add room, reorder mentally, open room |
| Room Detail | Manage one room | room notes, assigned checklist, room inventory, room issues | edit room, open checklist, update inventory |
| Create / Edit Room | Define a room | title, type, notes, photo | save, cancel |

### Standards and Checklists

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Checklist Template List | Manage reusable standards | template name, active state, item count | create template, duplicate, archive |
| Checklist Template Detail | Build template | list of tasks with order and requirements | add item, reorder, edit item |
| Room Checklist Detail | See checklist actually used in one room | inherited items, custom items | activate/deactivate, customize items |

### Jobs and Operations

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Job List / Work Sessions | Track upcoming and active jobs | scheduled date, property, assigned worker/company, status | create session, reassign, open session |
| Job Detail | Monitor one job | progress by room, timestamps, notes, proofs | start, complete, cancel, review issues |
| Checklist Execution Monitor | Watch room-level progress | room statuses, time spent, skipped items | inspect room details |
| Damage Reports | Review problems found during work | title, severity, status, assignee | assign, change status, open photos |
| Maintenance Work Orders | Track repair work | priority, category, schedule, costs | create order, assign, schedule, complete |

### Inventory

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Inventory Catalog | Manage standard items | item type, unit, reorder settings | create item, edit item |
| Room Inventory | Track supplies in one room | current level, par level, notes | count, restock, flag reorder |
| Property Inventory | Track shared property supplies | current level, reorder state | count, restock, create restock order |
| Restock Orders | Follow supply replenishment | order status, expected delivery, totals | create order, mark received |

## Cleaner / Maintenance Experience

### Primary Navigation

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| My Jobs | See current assignments | date, property, status, urgency | open job, start job |
| Schedule | Calendar-style view of work | upcoming sessions by date | open day, open job |
| History | Review completed work | completed jobs, durations, issues raised | open past session |
| Settings | Personal settings | profile, session, preferences | sign out, edit profile |

### Worker Job Flow

| Screen / View | Purpose | Main Information | Primary Actions |
|---|---|---|---|
| Job Home | Single-job landing page | property, access info, schedule, notes | start session, open rooms, report issue |
| Property Access Card | Quick operational details | entry instructions, codes, wifi, parking | copy or reveal details |
| Room Progress List | Show rooms that need service | room status and completion state | open next room |
| Room Checklist Execution | Complete tasks in that room | item list, required photos, notes | complete item, skip item, add proof |
| Item Proof Capture | Attach evidence | photo, notes | retake, save |
| Supply Count / Restock | Update what is low | counted amount, restock amount, notes | save count, flag issue |
| Report Damage | Escalate a problem | severity, title, description, photos | submit report |
| Complete Session | Finish the visit | summary, time spent, unresolved issues | complete session |

## Shared States Every Major Screen Should Consider

| State | Why It Matters |
|---|---|
| Empty | First-time setup is common in this product |
| Loading | Data-rich screens will almost always have a loading phase |
| Offline / weak connection | Workers may be in properties with bad service |
| Permission blocked | Company context and role can hide actions |
| Partial completion | A session or checklist may be started but not finished |
| Error with retry | Network and token issues will happen |
| Archived / inactive | Templates, relationships, and records can be inactive without being gone |

## Recommended Grouping for Navigation

### Property Manager tabs
A clean structure would likely group into:

- Dashboard
- Properties
- Jobs
- Team / Company
- Settings

### Cleaner tabs
A clean structure would likely group into:

- Jobs
- Schedule
- History
- Settings

## Web Surface

The web app is still early, but the backend strongly suggests the web experience should eventually own heavier administrative work such as:

- company administration
- complex property setup
- checklist building
- inventory administration
- reporting and billing

That does not mean mobile cannot do these things. It just means the future product likely has a “power surface” somewhere, and web is the obvious candidate.
