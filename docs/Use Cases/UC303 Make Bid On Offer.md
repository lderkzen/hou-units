# Use Case 303: Make Bid On Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may make make a bid on any other `Any Guild Member`s offer.

### Preconditions
- User must be logged in.
- An offer must be available.

### Termination Outcome
- **Success 1:** Bid made.
- **Success 2:** Bid made. Offer is instantly accepted and waiting for confirmation.
- **Failed 1:** Bid not made. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success 1**
1. User navigates to the `Offer & Requests` tab.
2. User navigates to an offer.
3. System provides (`IN10`, `IN20`, `IN30`)
4. User provides a bid (`IN40`).
5. User sends bid.
6. Bid is registered (`OUT10`).
7. User will receive notifications if a higher bid is made (`OUT30`).

**Success 2**
1. User navigates to the `Offer & Requests` tab.
2. User navigates to an offer.
3. System provides (`IN10`, `IN20`, `IN30`)
4. User confirms instant buy.
5. Bid is registered (`OUT20`).
6. User will receive a notification once the offer is confirmed finished by the supplier (`OUT30`).

**Failed 1**
1. User navigates to the `Offer & Requests` tab.
2. User navigates to an offer.
3. System provides (`IN10`, `IN20`, `IN30`)
4. User provides invalid or incomplete data for the bid (`IN40`).
5. User sends bid.
6. User is shown validation error message (`OUT40`).

### Input Summary
- `IN10`: Current highest bid
- `IN20`: Instant sale price
- `IN30`: Offer lifespan
- `IN40`: Bid
	- required, integer, ranging from the current bid (`IN10`) to the instant sale price (`IN20`), before offer lifespan (`IN30`)

### Output Summary
- `OUT10`: Bid is registered using (`IN40`).
- `OUT20`: Bid is registered using (`IN40`) and the state is set to `ACCEPTED` (`NOTE10`).
- `OUT30`: User receives Discord notifications.
- `OUT40`: Validation error message is shown below unvalidated field(s).

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, ACCEPTED, COMPLETED