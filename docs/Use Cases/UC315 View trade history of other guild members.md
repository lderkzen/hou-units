# Use Case 315: View Trade History of Other Guild Member

### Subject Area
Trading

### Actors
`Leader` or `Officer`

### Overview
`Leader` or `Officer` may view trade history of `Any Guild Member`.

### Preconditions
- User must be logged in.

### Termination Outcome
**Success 1**: User is shown all past transaction of selected `Any Guild Member`.

### Use Case Description
**Success 1**:
1. User navigates to the `Any Guild Member` profile page.
2. User navigates to `Transaction History` page.
3. System provides all past transactions (`OUT10`).

### Input Summary
No input.

### Output Summary
- `OUT10`: User is shown `Transaction History` (`NOTE20`)

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, PURCHASED, COMPLETED
- `NOTE20`: Transactions considered history (`NOTE10`)
	- Requests: COMPLETED
	- Offers: COMPLETED