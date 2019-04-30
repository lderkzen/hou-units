# Use Case 303: Purchase Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may purchase other `Any Guild Member`s offers.

### Preconditions
- User must be logged in.
- An offer with status `CREATED` must be available (`NOTE10`).

### Termination Outcome
- **Success 1:** Offer is instantly purchased and waiting for confirmation.
- **Failed 1:** Purchase failed. User is shown an error validation message.

### Use Case Description
**Success 1*
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT30`, `OUT40`).
4. User attempts to purchase.
5. Purchase is registered (`OUT10`).

**Failed 1**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT30`, `OUT40`).
4. User attempts to purchase.
5. User is shown validation error message (`OUT20`).

### Input Summary
No input.

### Output Summary
- `OUT10`: Purchase registered and the state is set to `PURCHASED` (`NOTE10`).
- `OUT20`: The user is shown validation error message.
- `OUT30`: Offer lifespan
- `OUT40`: Current user tokens

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, PURCHASED, COMPLETED