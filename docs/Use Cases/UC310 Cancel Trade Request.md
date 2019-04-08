# Use Case 309: Cancel Trade Request

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may cancel their request.

### Preconditions
- User must be logged in.
- User must be the creator of the request.
- The request must have state `CREATED` (`NOTE10`).

### Termination Outcome
**Success 1:** Request cancelled. User is forwarded to `My Offers & Requests` tab on the `Trading` page.

### Use Case Description
**Success 1**
1. User navigates to `My Offers & Requests` tab.
2. User opens the request.
3. User cancels request.
4. System provides that the request state is `CREATED` (`OUT10`, `NOTE10`).
5. System deletes the request (`OUT20`).
6. User is forwarded to `My Offers & Requests` tab (`OUT30`).

### Input Summary
No input.

### Output Summary
- `OUT10`: Request state.
- `OUT20`: Request cancelled.
- `OUT30`: User is forwarded to `My Offers & Requests` tab.

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, ACCEPTED, COMPLETED