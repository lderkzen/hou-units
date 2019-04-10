# Use Case 306: Report Transaction Issue

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may report an issue on a transaction.

### Preconditions
- The user must be logged in.
- The transaction must have state `ACCEPTED` or `COMPLETED` (`NOTE10`).
- The user must be participating in the transaction.

### Termination Outcome
- **Success 1:** Issue reported. Officers have been notified. User forwarded to the transaction on the `My Bids` tab.
- **Failed 1:** Issue not reported. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success 1**
1. User navigates to the `My Bids` tab.
2. User opens a transaction.
3. User clicks `Report Issue`.
4. User provides (`IN10`, `IN20`).
5. User reports issue.
6. Issue is registered (`OUT10`). 
7. Officers receive a discord notification, including a transaction link (`OUT50`), for an unassigned issue (`OUT40`).
8. User is forwarded to the `My Bids` tab with the transaction opened (`OUT20`).


**Failed 1**
1. User navigates to the `My Bids` tab.
2. User opens a transaction.
3. User clicks `Report Issue`.
4. User provides (`IN10`, `IN20`).
5. User reports issue.
6. User is shown validation error message (`OUT30`).

### Input Summary
- `IN10`: Type of issue
	- required, string (`NOTE20`)
- `IN20`: Short description
	- required, string, max string length 255

### Output Summary
- `OUT10`: Issue is registered using (`IN10`, `IN20`).
- `OUT20`: User is forwarded to `My Bids` tab and is shown the transaction.
- `OUT30`: Validation error message is shown below unvalidated field(s).
- `OUT40`: Officer channel receives Discord notification.
- `OUT50`: Transaction link for the registered issue at (`OUT10`).

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, ACCEPTED, COMPLETED
- `NOTE20`: Preset strings, selected from selection box.
	- "Other user does not respond"
	- "The items were not transferred"
	- "I didn't receive the tokens" - Only when `COMPLETED` (`NOTE10`)