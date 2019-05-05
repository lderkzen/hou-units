# Use Case 314: View Own Trade History

### Subject Area
Trading

### Actors
Any Guild Member

### Overview
`Any Guild Member` may view their own trade history.

### Preconditions
- User must be logged in.

### Termination Outcome
**Success 1**: User is shown all past transactions.

### Use Case Description
**Success 1**:
1. User navigates to `Transaction History` page.
2. System provides all past transactions (`OUT10`).

### Input Summary
No input.

### Output Summary
- `OUT10`: User is shown `Trasaction History` (`NOTE20`)

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, PURCHASED, COMPLETED
- `NOTE20`: Transactions considered history (`NOTE10`)
	- Requests: COMPLETED
	- Offers: COMPLETED
