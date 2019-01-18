# Use Case 301: Create Trade Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may create a trade offer with different options.

### Preconditions
User must be logged in.

### Termination Outcome
- **Success:** Offer created. User is forwarded to the `My Offers & Requests` tab on the `Trading` page.
- **Failed 1:** Offer not created. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success**
1. User directs to the `Offer & Request Creation` page.
2. User selects `Offer` option from radio button group.
3. User provides (`IN10`, `IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`, `IN80`).
4. User confirms offer.
5. Offer is created (`OUT10`).
6. User forwarded to `My Offers & Requests` tab (`OUT20`) and shown their offer.

**Failed 1**
1. User directs to the `Offer & Request Creation` page.
2. User selects `Offer` option from radio button group.
3. User provides invalid data for (`IN10`, `IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`, `IN80`).
4. User confirms offer.
5. User is shown validation error message (`OUT30`).

### Input Summary
- `IN10`: Offer or request				| required, enum (`NOTE10`)
- `IN20`: Minimum price 				| required, integer, ranging from 1 to infinite.
- `IN30`: Instant sale price 			| required, integer, ranging from (`IN10`) to double of (`IN10`).
- `IN40`: Offer lifespan 				| required, datetime, ranging from today + 3 hours to today + 14 days.
- `IN50`: Item(s) to be offered 		| required, object, ranging from 1 to 5.
- `IN60`: Amount of each (`IN40`) 		| required, integer, ranging from 1 to infinite.
- `IN70`: Image link					| string
- `IN80`: Receive notifications			| boolean

### Output Summary
- `OUT10`: Offer is created using (`IN10`, `IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`).
- `OUT20`: User forwarded to `My Offers & Requests` tab and is shown (`OUT10`).
- `OUT30`: User receives notifications per (`IN80`).
- `OUT40`: Validation error message is shown below unvalidated field(s).

### Notes
- `NOTE10`: Enum values: OFFER, REQUEST