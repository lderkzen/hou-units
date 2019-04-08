# Use Case 311: View Ongoing Transactions

### Subject Area
Trading

### Actors
`Leader` or `Officer`

### Overview
`Leader` or `Officer` may view ongoing transactions.

### Preconditions
- User must be logged in.

### Termination Outcome
**Success 1**: User is shown all ongoing transactions.

### Use Case Description
**Success 1**
1. User navigates to the `Admin Panel`.
2. User navigates to `All Ongoing Transactions` page (`OUT10`).
3. System provides all ongoing transactions (`OUT20`).

### Input Summary
No input.

### Output Summary
- `OUT10`: User is shown `All Ongoing Transactions`.
- `OUT20`: `OUT10` is filled with transaction with specific states (`NOTE10`).
	- Requests: `CREATED`, `ACCEPTED` 
	- Requests: `CREATED`, `BIDDING`, `ACCEPTED`

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED