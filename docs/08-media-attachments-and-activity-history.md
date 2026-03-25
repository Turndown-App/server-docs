# Media, Attachments, and Activity History

Turndown is not just a forms product. It is also a documentation product.

Photos, timestamps, comments, and histories are part of how trust is built inside the system.

## Where Images Can Appear

The current product model supports images on several kinds of records:

- user profiles
- companies
- properties
- rooms
- checklist item completions
- work reports
- cleaning reports
- maintenance tickets / issue records

## Why Images Matter

Photos serve different jobs depending on context.

### Reference photos
Used to show what a place or room looks like.

Examples:
- property cover photo
- room hero photo
- company image

### Proof photos
Used to prove a task was completed.

Examples:
- required photo after cleaning a bathroom
- proof image attached to a checklist item

### Incident photos
Used to document a problem.

Examples:
- broken fixture
- damage before repair
- repair result after completion

## Image Attributes That Matter

Each image can carry more than just the file itself.

| Attribute | Meaning |
|---|---|
| file name | Original uploaded file name |
| file type | Kind of image file |
| file size | File weight |
| width / height | Basic dimensions |
| display order | Position in a gallery |
| category | Optional grouping label |
| uploaded by | Who added it |
| public or protected | Whether access is open or restricted |

## Gallery Behavior

Because images have display order, the product should support a stable gallery order for record types that can hold multiple images.

This matters especially for:

- property photo sets
- room photo sets
- damage before/after galleries
- task proof sequences

## Before and After Patterns

Damage reporting already models “before” and “after” image behavior.

That means the UI should likely support:
- a clearly labeled before state
- a clearly labeled after state
- side-by-side comparison or grouped galleries
- a visible repair timeline

## Comments and Conversation

Damage reports support comments, including internal-only comments.

That means issue management is not just status-based. It also has a conversation layer.

### Design implications
- show author and timestamp on each comment
- distinguish internal notes from wider-visible notes
- keep comment entry simple and fast

## Status History

Damage reports also keep a status history with:

- previous status
- new status
- who changed it
- why it changed
- when it changed

This means the product has a real timeline pattern available.

## Recommended Timeline Uses

A timeline pattern would fit well for:

- damage report lifecycle
- maintenance work order lifecycle
- work session history
- invitation history
- subscription events

## Protected Information

Some media and operational details are sensitive.

Examples:
- lock codes
- alarm codes
- wifi passwords
- private issue photos
- worker documentation tied to a property

The product should therefore assume that some information needs stronger privacy treatment, not just nice typography.

## Activity History Beyond Photos

Even when there is no photo, Turndown keeps useful history such as:

- sign-in history
- invitation acceptance timestamps
- last checked inventory timestamps
- last restocked timestamps
- work start and finish times
- status change times
- plan and subscription event timestamps

## What This Means for the Product

The app should not treat “history” as a boring appendix page.

History is how managers answer:
- Did the worker actually do the job?
- When was this room last serviced?
- When did this issue become serious?
- Who changed this?
- When did supplies start running low?

A strong product surface for Turndown should include timeline, proof, and history patterns early, not bolt them on later.
