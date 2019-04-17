# Use Case 312: View Open Trade Offers

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may view all open trade offers.

### Preconditions
- User must be logged in.
- Trade offers must have state CREATED or BIDDING (`NOTE10`).

### Termination Outcome
- **Success 1:** User is shown a list of all offers.

### Use Case Description
**Success 1**
1. User navigates to the `Offers & Requests` tab.
2. User checks `Offers` checkbox (`IN10`).
3. System fills page with offers (`OUT10`).

### Input Summary
- `IN10`: Filtering checkboxes

### Output Summary
- `OUT10`: `Offers & Requests` tab filled with offers with state CREATED or BIDDING (`NOTE10`).

### Notes
- `NOTE10`: Enum values
	- Offers: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED