# Open Product Decisions and Assumptions

This section calls out places where the current system model is clear enough to design around, but not fully opinionated yet.

These are not bugs. They are product decisions that should be made intentionally.

## 1. What is the true home screen for managers?

The system supports dashboard-style information, but it does not fully define the exact manager landing-page layout yet.

### Choices to make
- alert-driven dashboard
- portfolio summary dashboard
- jobs-first operations dashboard
- blended dashboard with quick actions

## 2. Is scheduling simple or calendar-heavy?

Work sessions already support scheduled dates, but the overall planning model is still fairly lean.

### Choices to make
- list-first scheduling
- calendar-first scheduling
- drag-and-drop dispatching
- recurring service patterns

## 3. How should company switching behave?

The data model strongly suggests multi-company access, but the ideal company switcher pattern is still a product choice.

### Questions
- global switcher in header?
- account picker on entry?
- sticky last-used company?
- show company-specific permissions before switching?

## 4. How visible should provider-company relationships be?

Company-to-company relationships are a major capability, but many property operations apps bury this kind of concept.

### Choices to make
- dedicated “Providers” section
- combine with team management
- relationship cards on company profile
- active vs pending vs suspended split

## 5. How should cleaning and maintenance differ in the worker experience?

The system supports both kinds of work, but the current mobile structure is still more clearly cleaning-oriented.

### Choices to make
- one worker app with mode-specific jobs
- separate job detail templates for cleaning vs maintenance
- separate navigation for maintenance workers
- severity / priority emphasis for maintenance

## 6. What belongs on mobile vs web long term?

The backend is broader than the current mobile UI.

### Likely web-heavy areas
- large-scale checklist building
- inventory administration
- advanced reporting
- billing and subscription management
- broad company administration

### Likely mobile-heavy areas
- active job execution
- property access details
- room-by-room completion
- proof capture
- issue reporting

## 7. What are the strongest empty states?

This product has a lot of first-run setup moments:
- no company yet
- no properties yet
- no rooms yet
- no checklist templates yet
- no active providers yet
- no jobs assigned yet
- no damage reports yet

A full product design should decide whether these feel instructional, operational, or promotional.

## 8. How much offline behavior should be exposed?

The mobile project mentions offline support as a product need, but the best user-facing behavior is still a design choice.

### Questions
- show offline banners?
- queue actions silently?
- allow image capture before upload completes?
- show sync conflicts explicitly or quietly?

## 9. What should happen after a job is completed?

The system records rich end-of-job data, but the post-completion experience could go several ways.

### Choices to make
- completion summary
- shareable proof packet
- open-issues recap
- restock warning recap
- next-job handoff

## 10. How should billing surface inside the product?

Subscription data exists, but the ideal user-facing billing experience is not deeply defined yet.

### Choices to make
- simple plan page
- stronger upgrade gating
- usage meter by properties / users
- billing alerts in settings vs dashboard

## Working Assumptions That Are Safe Today

These assumptions are well supported by the current product model:

1. **Mobile is the primary operational surface today.**
2. **Property managers need more context than cleaners.**
3. **Rooms are core objects, not decorative sub-items.**
4. **Photos are required for quality control in multiple flows.**
5. **Service-provider companies are first-class citizens in the business model.**
6. **A complete design must include inventory and issue handling, not only cleaning checklists.**

## Final Guidance for Any Full Product Design

If the goal is to design Turndown as a complete platform, the design should include all of the following layers:

- onboarding and company setup
- internal team management
- outside provider relationships
- property and room structure
- operational standards
- live job execution
- issue escalation
- supply tracking
- history and proof
- billing / account administration

Anything less will look cleaner on paper, but it will quietly ignore what the product actually does. And the backend will sit there judging everyone.
