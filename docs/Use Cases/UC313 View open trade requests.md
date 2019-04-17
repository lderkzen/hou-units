# Use Case 313: View Open Trade Requests

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may view all open trade requests.

### Preconditions
- User must be logged in.
- Trade requests must have state CREATED (`NOTE10`).

### Termination Outcome
- **Success 1:** User is shown a list of all requests.

### Use Case Description
**Success 1**
1. User navigates to the `Offers & Requests` tab.
2. User checks `Requests` checkbox (`IN10`).
3. System fills page with requests (`OUT10`).

### Input Summary
- `IN10`: Filtering checkboxes

### Output Summary
- `OUT10`: `Offers & Requests` tab filled with requests with state CREATED (`NOTE10`).

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED