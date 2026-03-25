# Module Map

This section breaks the product into major modules. Each module is a self-contained area of the app with a clear job.

## 1. Authentication and Account Entry

### Purpose
Get users into the product securely and place them in the correct company context.

### Includes
- sign up
- sign in
- token/session refresh behind the scenes
- sign out
- forgot password / reset flow
- invitation acceptance flows
- “who am I” / current user state

### Design Implication
This area should feel trustworthy and low-friction. It is not where the product earns money. It is where the product either feels professional or sketchy.

---

## 2. Company and Team Management

### Purpose
Let a business define itself and manage the people and service relationships connected to it.

### Includes
- company profile
- company type
- company contact info
- internal team members
- individual invitations
- company-to-company invitations
- active provider relationships
- company switching for users with access to multiple companies

### Design Implication
This is where the org chart meets real-world service relationships. The UI needs to separate **people in my company** from **outside companies we work with**.

---

## 3. Property Management

### Purpose
Store the places being serviced and the information workers need in order to do the work correctly.

### Includes
- property list
- property detail
- address and location details
- property type
- square footage
- property photos
- special notes
- access information
- wifi and alarm details
- parking details

### Design Implication
Property pages should be a home base, not just a form. A manager should feel like everything about that location lives there.

---

## 4. Room Management

### Purpose
Break a property into meaningful work areas.

### Includes
- room list
- room detail
- room type
- room notes
- room hero photo
- room-level checklist assignment
- room-level inventory
- room-level issue context

### Design Implication
Rooms are one of the product’s strongest organizing ideas. If the design keeps everything at property level only, it loses a lot of the product’s value.

---

## 5. Checklist Standards

### Purpose
Create reusable standards for how a room should be serviced.

### Includes
- checklist templates
- template items
- item order
- required vs optional tasks
- photo-required tasks
- estimated time per item
- active/inactive templates

### Design Implication
This area should feel like building a standard operating procedure, not filling out a spreadsheet.

---

## 6. Room Checklists

### Purpose
Turn a generic template into the actual checklist used in a specific room.

### Includes
- room checklist
- room-specific checklist name
- copied items from a template
- custom items added only for that room
- one active checklist per room

### Design Implication
There is a difference between **the standard** and **the real version used in this room**. The UI should make that distinction obvious.

---

## 7. Work Sessions

### Purpose
Represent a real visit to a property for cleaning or service work.

### Includes
- scheduled date
- service provider company
- worker assigned
- status
- start time
- completion time
- total time
- notes

### Design Implication
A work session is the container for the whole job. It should feel like the top-level “job” object in the worker experience.

---

## 8. Checklist Execution

### Purpose
Track progress through room checklists during a work session.

### Includes
- room-by-room execution
- execution status
- time spent in the room
- completion notes
- item completion records
- skipped items and skip reasons
- photo proof

### Design Implication
This is the heart of the worker experience. It should be fast, focused, and impossible to get lost in.

---

## 9. Inventory

### Purpose
Track supplies and fixed items needed to keep properties operating.

### Includes
- master inventory catalog
- room-level inventory
- property-level inventory
- current level
- minimum level
- reorder point
- last checked / last restocked
- automatic reorder flag
- historical counts
- restock orders

### Design Implication
Inventory is both setup and daily workflow. Managers need structure; workers need quick adjustments without ten taps and a philosophy degree.

---

## 10. Damage Reporting

### Purpose
Capture issues discovered during work and move them toward resolution.

### Includes
- damage report
- severity
- status
- title and description
- room and property location
- estimated and actual cost
- photos
- comments
- assignee
- resolution details

### Design Implication
This area should support both urgency and clarity. A tiny scratch and a broken HVAC unit should not feel visually identical.

---

## 11. Maintenance Work Orders

### Purpose
Turn repair needs into trackable work.

### Includes
- work order number
- category
- priority
- scheduling
- assignment
- labor and materials notes
- cost summary
- completion state

### Design Implication
Maintenance work orders should feel operational, not decorative. This is where repairs become accountable.

---

## 12. Media and Documentation

### Purpose
Attach visual proof and supporting files to the right business records.

### Includes
- property images
- room images
- checklist proof images
- damage photos
- ordered image galleries
- uploader info

### Design Implication
Photos should always feel connected to context: **what is this photo of, where does it belong, and why was it taken?**

---

## 13. Subscription and Billing

### Purpose
Control access to plans, limits, and commercial features.

### Includes
- subscription plans
- monthly vs yearly pricing
- plan features
- usage caps such as property count or user count
- active or expired subscription state
- billing provider details
- subscription event history

### Design Implication
Billing may be less visible day to day, but it needs a clean administrative surface and clear upgrade messaging.
