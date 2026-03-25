# Core Workflows

This section describes the main product journeys.

## 1. Create a Company and First User

```mermaid
flowchart LR
    A[Create account] --> B[Create company]
    B --> C[Choose company type]
    C --> D[Complete profile]
    D --> E[Start adding people or properties]
```

### Outcome
The business now has a home inside Turndown.

### Key records created
- user
- company
- membership between user and company

---

## 2. Invite a Team Member

```mermaid
flowchart LR
    A[Manager opens team] --> B[Enter email and role] --> C[Send invitation] --> D[Invitation accepted] --> E[User becomes company member]
```

### Outcome
A person gains access to the company with a defined role.

### Important experience details
- invitation should clearly show company name
- role should be obvious before acceptance
- pending, accepted, expired, and revoked should be visually distinct

---

## 3. Invite a Service Provider Company

```mermaid
flowchart LR
    A[Property company opens providers] --> B[Send invite] --> C[Provider reviews invite] --> D[Accept] --> E[Relationship becomes active]
```

### Outcome
Two companies become linked for service work.

### Important experience details
- “my team” and “outside provider” must not be mixed together
- pending invites and active relationships should be separate sections
- this flow is business-to-business, not person-to-person

---

## 4. Add a Property

```mermaid
flowchart LR
    A[Create property] --> B[Add address and property type] --> C[Add notes and photo] --> D[Save property] --> E[Add access details and rooms]
```

### Outcome
A property exists and is ready for room setup.

### Important experience details
- access details are part of setup, but often feel like their own step
- property photo is helpful but not always required
- special notes should be treated as important, not an afterthought

---

## 5. Add Rooms and Define Standards

```mermaid
flowchart LR
    A[Open property] --> B[Add rooms] --> C[Create or choose checklist template] --> D[Assign checklist to room] --> E[Customize room checklist if needed]
```

### Outcome
Each room has an actionable standard.

### Important experience details
- a template is reusable
- a room checklist is the version that actually governs work in that room
- one room should only have one active checklist at a time

---

## 6. Create and Run a Work Session

```mermaid
flowchart TD
    A[Create session] --> B[Assign property and worker]
    B --> C[Session starts]
    C --> D[System creates room executions]
    D --> E[Worker completes rooms]
    E --> F[Worker finishes session]
```

### Outcome
A real job is tracked from scheduled state to completion.

### Important experience details
- the worker should see a simple top-down path
- room progress should always be visible
- time data should feel automatic, not manually burdensome

---

## 7. Complete Checklist Items

```mermaid
flowchart LR
    A[Open room] --> B[See tasks in order] --> C[Complete item] --> D{Photo required?}
    D -- Yes --> E[Capture proof]
    D -- No --> F[Save completion]
    E --> F
```

### Outcome
The room’s work is documented item by item.

### Important experience details
- photo-required items need stronger visual emphasis
- skipped items should require explanation
- once an item is done, its state should be obvious and durable

---

## 8. Count or Restock Supplies

```mermaid
flowchart LR
    A[Worker checks room supplies] --> B[Enter current amount] --> C{Below threshold?}
    C -- No --> D[Save count]
    C -- Yes --> E[Flag for restock]
    E --> F[Optional order or follow-up]
```

### Outcome
Supply levels stay current and low-stock issues become visible.

### Important experience details
- current amount, target amount, and low threshold must not be visually confused
- consumables and fixed items may need different interaction patterns
- low-stock alerts should be easy for managers to scan

---

## 9. Report Damage

```mermaid
flowchart LR
    A[Worker notices issue] --> B[Open report flow] --> C[Select severity and room] --> D[Describe problem] --> E[Add photos] --> F[Submit]
```

### Outcome
The issue becomes a trackable problem instead of a forgotten text message.

### Important experience details
- severity should be chosen carefully
- room and location details matter
- before and after photos should be supported over time

---

## 10. Turn Damage Into Maintenance Work

```mermaid
flowchart LR
    A[Open damage report] --> B[Assign or escalate] --> C[Create work order] --> D[Schedule work] --> E[Complete repair] --> F[Resolve report]
```

### Outcome
The platform connects discovery to action.

### Important experience details
- not every damage report becomes a work order
- the relationship between report and work order should remain visible
- status changes need a sense of timeline and accountability

## End-to-End Example

A realistic full lifecycle looks like this:

1. A property manager creates a property.  
2. The manager adds rooms and standards.  
3. A cleaning company relationship is active.  
4. A worker is assigned to a work session.  
5. The worker completes room tasks and required photo proof.  
6. The worker notices low stock in the bathroom and updates the count.  
7. The worker finds a broken towel bar and submits a damage report.  
8. The manager reviews the issue and creates a maintenance work order.  
9. The property now has a complete operational record for that visit.

That is the product’s sweet spot.
