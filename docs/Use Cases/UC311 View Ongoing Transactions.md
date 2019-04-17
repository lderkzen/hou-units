# Use Case 311: View Ongoing Transactions

### Subject Area
Trading

### Actors
`Leader` or `Officer`

### Overview
`Leader` or `Officer` may view ongoing transactions of all `Any Guild Member`.

### Preconditions
- User must be logged in.

### Termination Outcome
**Success 1**: User is shown all ongoing transactions of all `Any Guild Member`.

### Use Case Description
**Success 1**
1. User navigates to the `Admin Panel`.
2. User navigates to `All Ongoing Transactions` page.
3. System provides all ongoing transactions (`OUT10`).

### Input Summary
No input.

### Output Summary
- `OUT10`: User is shown `All Ongoing Transactions` (`NOTE20`).
	
### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED
- `NOTE20`: Transactions considered ongoing (`NOTE10`)
	- Requests: `CREATED`, `ACCEPTED` 
	- Offers: `CREATED`, `BIDDING`, `ACCEPTED`