# UC307: Cancel Trade Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may cancel their offer.

### Preconditions
- User must be logged in.
- User must be the creator of the offer.
- The offer must have state `CREATED` (`NOTE10`).

### Termination Outcome
**Success 1:** Offer cancelled. User is forwarded to `My Offers & Requests` tab on the `Trading` page.

### Use Case Description
**Success 1**
1. User navigates to `My Offers & Requests` tab.
2. User opens the offer.
3. User cancels offer.
4. System provides that the offer state is `CREATED` (`OUT10`, `NOTE10`).
5. System deletes the offer (`OUT20`).
6. User is forwarded to `My Offers & Requests` tab (`OUT30`).

### Input Summary
No input.

### Output Summary
- `OUT10`: Offer state.
- `OUT20`: Offer cancelled.
- `OUT30`: User is forwarded to `My Offers & Requests` tab.

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED