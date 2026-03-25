# Record Types and Data Dictionary

This section explains the main kinds of information stored in Turndown.

## How to Read This Section

Each table uses plain-English value types:

- **ID** = a unique identifier
- **Text** = words or freeform written content
- **Number** = numeric value
- **Date** = day only
- **Date & time** = full timestamp
- **Yes / No** = true or false
- **Choice list** = one value selected from a predefined set
- **Photo / Image** = an uploaded image
- **JSON / Structured data** = machine-readable details not meant for normal manual editing

## Common Metadata on Many Records

Most records in Turndown also carry the following background fields:

| Field | Type of Value | Meaning |
|---|---|---|
| id | ID | Unique record identifier |
| createdAt | Date & time | When the record was first created |
| updatedAt | Date & time | When it was last changed |
| deletedAt | Date & time | Used for archived / soft-deleted records |

---

## Organization Records

## Company

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| displayName | Text | Yes | Public-facing company name |
| email | Text | Yes | Main contact email |
| companyType | Choice list | Yes | What kind of company this is |
| addressLine1 / addressLine2 | Text | No | Mailing or business address |
| city | Text | No | City |
| stateCode | Choice list | No | State or region code |
| postalCode | Text | No | ZIP or postal code |
| country | Text | No | Country |
| timezone | Text | No | Company’s default timezone |
| phoneNumber | Text | No | Contact phone number |
| photoUrl | Photo / Image | No | Company image or logo |

## User

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| firstName | Text | Yes | Person’s first name |
| lastName | Text | No | Person’s last name |
| email | Text | Yes | Login and contact email |
| accountType | Choice list | Yes | Role type for the account |
| companyId | ID | No | Primary company context |
| profilePhoto | Photo / Image | No | Profile image |
| phoneNumber | Text | No | Contact phone |
| preferredLanguage | Choice list | Yes | Language preference |
| status | Choice list | Yes | Active or inactive state |
| lastSignin | Date & time | No | Last successful sign-in |
| locked | Yes / No | No | Whether the account is locked |

## Company Membership

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| companyId | ID | Yes | Company the person belongs to |
| userId | ID | Yes | Person who belongs to the company |
| role | Choice list | Yes | Their role in that company |

## Person Invitation

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| companyId | ID | Yes | Company sending the invitation |
| email | Text | Yes | Invitee email |
| userId | ID | No | Existing user record, if one already exists |
| role | Choice list | Yes | Role they will receive |
| status | Choice list | Yes | Pending, accepted, declined, expired, or revoked |
| token | Text | Yes | Secure acceptance link token |
| expiresAt | Date & time | Yes | When the invitation stops working |
| acceptedAt | Date & time | No | When it was accepted |
| invitedBy | ID | Yes | Sender |

## Company Invitation

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| requesterCompanyId | ID | Yes | Company asking for the relationship |
| providerCompanyId | ID | Yes | Company being invited |
| status | Choice list | Yes | Invitation state |
| token | Text | Yes | Secure acceptance token |
| expiresAt | Date & time | Yes | Expiration time |
| acceptedAt | Date & time | No | Acceptance time |
| invitedBy | ID | Yes | Person who sent the invite |
| message | Text | No | Optional note attached to the invitation |

## Company Relationship

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| requesterCompanyId | ID | Yes | Company requesting service |
| providerCompanyId | ID | Yes | Company providing service |
| status | Choice list | Yes | Active, inactive, or suspended |
| establishedAt | Date & time | No | When the relationship became real |

---

## Place Records

## Property

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| displayName | Text | Yes | Property name shown in the app |
| addressLine1 / addressLine2 | Text | No | Street address |
| city | Text | No | City |
| stateCode | Choice list | No | State or region |
| postalCode | Text | No | Postal code |
| country | Text | No | Country |
| propertyType | Choice list | No | House, condo, cabin, and so on |
| timezone | Text | No | Property timezone |
| photoUrl | Photo / Image | No | Main property image |
| sqft | Number | No | Square footage |
| specialNotes | Text | No | Anything workers should know |
| companyId | ID | Yes | Owning or managing company |

## Property Access Information

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| propertyId | ID | Yes | Property this belongs to |
| entryInstructions | Text | No | How to get in |
| accessCode | Text | No | Door or lock code |
| wifiName | Text | No | Network name |
| wifiPassword | Text | No | Network password |
| alarmCode | Text | No | Alarm code |
| parkingInfo | Text | No | Parking instructions |
| specialNotes | Text | No | Other arrival or entry notes |

## Room

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| displayName | Text | Yes | Room name |
| roomType | Choice list | No | Bedroom, bathroom, kitchen, and so on |
| heroPhoto | Photo / Image | No | Main photo for the room |
| propertyId | ID | Yes | Property this room belongs to |
| checklistTemplateId | ID | No | Default checklist template attached to the room |
| description | Text | No | Basic description |
| specialNotes | Text | No | Special instructions for this room |

---

## Standards and Execution Records

## Checklist Template

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| name | Text | Yes | Template name |
| description | Text | No | What the template is for |
| companyId | ID | Yes | Company that owns the template |
| createdBy | ID | Yes | Creator |
| isActive | Yes / No | No | Whether the template can currently be used |

## Checklist Template Item

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| templateId | ID | Yes | Parent template |
| title | Text | Yes | Task name |
| description | Text | No | Task details |
| displayOrder | Number | Yes | Order shown to the worker |
| requiresPhoto | Yes / No | No | Whether proof photo is required |
| isRequired | Yes / No | No | Whether the task must be completed |
| estimatedTimeMinutes | Number | No | Expected time for the task |

## Room Checklist

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| roomId | ID | Yes | Room this checklist is for |
| templateId | ID | No | Template it came from |
| name | Text | Yes | Checklist name shown in the room |
| isActive | Yes / No | No | Whether this is the live checklist for that room |

## Room Checklist Item

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| roomChecklistId | ID | Yes | Parent room checklist |
| templateItemId | ID | No | Original template item, if copied from a template |
| title | Text | Yes | Task name |
| description | Text | No | Task details |
| displayOrder | Number | Yes | Order inside the room checklist |
| requiresPhoto | Yes / No | No | Whether the worker must add photo proof |
| isRequired | Yes / No | No | Whether the task must be done |
| isCustom | Yes / No | No | Whether the task exists only in this room |
| estimatedTimeMinutes | Number | No | Expected time |

## Work Session

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| propertyId | ID | Yes | Property being serviced |
| serviceProviderCompanyId | ID | Yes | Company performing the work |
| performedBy | ID | Yes | Worker assigned to the job |
| status | Choice list | Yes | Pending, in progress, completed, or cancelled |
| scheduledDate | Date | No | Planned service date |
| startedAt | Date & time | No | Actual start time |
| completedAt | Date & time | No | Actual finish time |
| totalTimeMinutes | Number | No | Final total time spent |
| notes | Text | No | Session-level notes |

## Checklist Execution

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| workSessionId | ID | Yes | Parent work session |
| roomChecklistId | ID | Yes | Checklist being executed |
| roomId | ID | Yes | Room being worked on |
| workerId | ID | Yes | Worker performing the room |
| status | Choice list | Yes | Pending, in progress, completed, or skipped |
| startedAt | Date & time | No | Start time for that room |
| completedAt | Date & time | No | Finish time for that room |
| timeSpentMinutes | Number | No | Total room time |
| notes | Text | No | Room-level notes |

## Checklist Item Completion

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| checklistExecutionId | ID | Yes | Parent room execution |
| roomChecklistItemId | ID | Yes | Task being completed |
| completedBy | ID | Yes | Worker who marked it done |
| completedAt | Date & time | Yes | Completion time |
| photoId | ID | No | Linked proof photo |
| notes | Text | No | Notes about this completion |
| skipped | Yes / No | No | Whether the item was skipped |
| skipReason | Text | No | Why it was skipped |

---

## Inventory Records

## Inventory Item

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| companyId | ID | Yes | Company that owns the item definition |
| name | Text | Yes | Item name |
| description | Text | No | What it is |
| itemType | Choice list | Yes | Consumable or fixed item |
| unit | Choice list | Yes | Count, rolls, boxes, bottles, and so on |
| unitCustom | Text | No | Custom unit label |
| minimumLevel | Number | No | Lowest acceptable amount |
| reorderLevel | Number | No | Level that should trigger reorder attention |
| maximumLevel | Number | No | Full target level |
| costPerUnit | Number | No | Unit cost |
| supplierInfo | Text | No | Vendor or supplier details |
| sku | Text | No | Stock code |
| barcode | Text | No | Barcode value |

## Room Inventory

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| roomId | ID | Yes | Room where the item is tracked |
| inventoryItemId | ID | Yes | Standard inventory item |
| currentLevel | Number | Yes | Current amount on hand |
| minimumLevel | Number | No | Lowest acceptable level for this room |
| maximumLevel | Number | No | Maximum target for this room |
| parLevel | Number | No | Preferred stocked amount |
| lastRestockedAt | Date & time | No | Most recent restock time |
| lastRestockedBy | ID | No | Person who restocked |
| lastCheckedAt | Date & time | No | Most recent count time |
| lastCheckedBy | ID | No | Person who counted |
| autoReorder | Yes / No | No | Whether this item should auto-trigger reorder behavior |
| locationNotes | Text | No | Where it is stored or any extra notes |

## Property Inventory

Same shape as room inventory, but tied to the full property instead of a single room.

## Inventory Count

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| checklistExecutionId | ID | Yes | Room execution where count was taken |
| roomInventoryId | ID | Yes | Inventory slot being counted |
| previousLevel | Number | Yes | Amount before the count |
| countedLevel | Number | Yes | Amount actually found |
| consumedAmount | Number | Automatic | How much appears to have been used |
| restockedAmount | Number | No | Amount added during restock |
| finalLevel | Number | Automatic | New resulting amount |
| countedBy | ID | Yes | Person who counted |
| countedAt | Date & time | Yes | When the count happened |
| needsRestock | Yes / No | No | Whether follow-up is needed |
| notes | Text | No | Additional explanation |

## Restock Order

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| companyId | ID | Yes | Company placing the order |
| orderNumber | Text | No | Human-readable order reference |
| status | Choice list | No | Pending, ordered, shipped, or received |
| totalItems | Number | No | Number of line items |
| totalCost | Number | No | Total cost |
| orderedBy | ID | No | Person who placed the order |
| orderedAt | Date & time | No | When it was ordered |
| expectedDelivery | Date | No | Expected arrival |
| receivedBy | ID | No | Person who marked receipt |
| receivedAt | Date & time | No | When it was received |
| supplierInfo | Text | No | Vendor details |
| notes | Text | No | Extra context |

## Restock Order Item

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| orderId | ID | Yes | Parent order |
| inventoryItemId | ID | Yes | Item being ordered |
| roomInventoryId | ID | No | Room inventory target, if room-specific |
| propertyInventoryId | ID | No | Property inventory target, if property-level |
| quantityOrdered | Number | Yes | Amount ordered |
| quantityReceived | Number | No | Amount received |
| unitCost | Number | No | Cost per unit |
| totalCost | Number | No | Total line cost |

---

## Issue and Maintenance Records

## Damage Report

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| propertyId | ID | Yes | Property where the issue exists |
| roomId | ID | Yes | Room where the issue exists |
| workSessionId | ID | No | Session during which it was found |
| reportedBy | ID | Yes | Person who reported it |
| reportedAt | Date & time | No | When it was reported |
| severity | Choice list | Yes | Minor through critical |
| status | Choice list | Yes | Open, in review, resolved, escalated |
| title | Text | Yes | Short issue headline |
| description | Text | Yes | Full issue explanation |
| locationDetails | Text | No | Exact placement details |
| estimatedCost | Number | No | Early cost estimate |
| actualCost | Number | No | Final cost |
| assignedTo | ID | No | Person responsible |
| assignedAt | Date & time | No | Assignment time |
| resolvedAt | Date & time | No | Resolution time |
| resolvedBy | ID | No | Who resolved it |
| resolutionNotes | Text | No | What was done |
| requiresProfessional | Yes / No | No | Whether outside expertise is needed |
| vendorInfo | Text | No | Vendor details |
| insuranceClaimNumber | Text | No | Insurance claim reference |
| isTenantResponsible | Yes / No | No | Whether tenant is responsible |
| tenantChargeAmount | Number | No | Charge passed to tenant |

## Damage Report Photo

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| damageReportId | ID | Yes | Report this photo belongs to |
| photoId | ID | Yes | Image record |
| caption | Text | No | Photo caption |
| isBeforePhoto | Yes / No | No | Before-repair vs after-repair marker |
| displayOrder | Number | No | Order in gallery |
| uploadedBy | ID | No | Who added it |

## Damage Report Comment

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| damageReportId | ID | Yes | Parent issue |
| userId | ID | Yes | Comment author |
| comment | Text | Yes | Comment text |
| isInternal | Yes / No | No | Internal note visibility flag |

## Damage Status History

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| damageReportId | ID | Yes | Parent issue |
| previousStatus | Choice list | No | Prior status |
| newStatus | Choice list | Yes | New status |
| changedBy | ID | Yes | Person who changed it |
| reason | Text | No | Why the status changed |
| createdAt | Date & time | No | When it changed |

## Maintenance Work Order

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| damageReportId | ID | No | Linked issue, if one exists |
| propertyId | ID | Yes | Property |
| roomId | ID | No | Room |
| workOrderNumber | Text | No | Human-readable work order code |
| priority | Choice list | No | Urgency level |
| category | Text | No | Plumbing, electrical, HVAC, and so on |
| assignedTo | ID | No | Person doing the work |
| assignedAt | Date & time | No | When assigned |
| scheduledDate | Date | No | Target date |
| scheduledTimeStart | Text | No | Planned start time |
| scheduledTimeEnd | Text | No | Planned end time |
| startedAt | Date & time | No | Actual start time |
| completedAt | Date & time | No | Actual completion time |
| completedBy | ID | No | Who completed the work |
| description | Text | Yes | Work requested |
| workPerformed | Text | No | What was actually done |
| materialsUsed | Text | No | Materials summary |
| laborHours | Number | No | Hours spent |
| laborCost | Number | No | Labor total |
| materialsCost | Number | No | Materials total |
| totalCost | Number | No | Full job total |
| status | Choice list | No | Pending through completed |

---

## Media Records

## Image

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| entityType | Choice list | Yes | What kind of record the image belongs to |
| entityId | ID | Yes | Specific record the image belongs to |
| fileName | Text | Yes | Original file name |
| mimeType | Text | Yes | File type |
| fileSizeBytes | Number | No | File size |
| width | Number | No | Image width |
| height | Number | No | Image height |
| isPublic | Yes / No | Yes | Whether the image is openly viewable |
| category | Text | No | Optional grouping label |
| displayOrder | Number | Yes | Position among other images |
| uploadedBy | ID | No | Person who uploaded it |

---

## Commercial Records

## Subscription Plan

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| name | Text | Yes | Plan name |
| description | Text | No | Plan summary |
| priceMonthly | Number | No | Monthly price |
| priceYearly | Number | No | Yearly price |
| features | JSON / Structured data | No | Feature list for the plan |
| maxProperties | Number | No | Property cap |
| maxUsers | Number | No | User cap |
| isActive | Yes / No | No | Whether the plan is available |

## User Subscription

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| userId | ID | Yes | Subscriber |
| planId | ID | Yes | Plan chosen |
| status | Text | Yes | Billing state |
| billingPeriod | Text | Yes | Monthly or yearly |
| currentPeriodStart | Date & time | Yes | Billing period start |
| currentPeriodEnd | Date & time | Yes | Billing period end |
| provider | Text | Yes | Billing provider |
| providerSubscriptionId | Text | Yes | External subscription reference |
| cancelAtPeriodEnd | Yes / No | No | Whether cancellation is scheduled |

## Subscription Event

| Field | Type of Value | Required | Meaning |
|---|---|---:|---|
| subscriptionId | ID | No | Subscription affected |
| userId | ID | Yes | User affected |
| eventType | Text | Yes | Created, renewed, cancelled, expired, and so on |
| provider | Text | Yes | Billing provider |
| providerEventId | Text | No | Provider event reference |
| eventData | JSON / Structured data | No | Raw event details |

## Data Dictionary Summary

Turndown’s information model centers on these chains:

- **company → people**
- **company → properties → rooms**
- **company → checklist standards**
- **property → work session → room execution → item completion**
- **room / property → inventory**
- **work session → damage report → maintenance work order**
- **many record types → images and history**

That is the core shape of the product.
