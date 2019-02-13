# Use Case 304: Reply to Request

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may reply to any other `Any Guild Member`s request.

### Preconditions
- User must be logged in.
- A request must be available.

### Termination Outcome
- **Success 1:** Replied to request. Request accepted and waiting for confirmation.
- **Success 2:** Replied to request. Request accepted and waiting for confirmation. User will receive notifications.

### Use Case Description
**Success 1**
1. User navigates to the `Offer & Requests` tab.
2. User navigates to a request.
3. User sets or has set `Send Notifications for Trading` to false in `User Settings` (`IN10`).
4. User confirms request.
5. Request reply is registered (`OUT10`).

**Success 2**
1. User navigates to the `Offer & Requests` tab.
2. User navigates to a request.
3. User sets or has set `Send Notifications for Trading` to true in `User Settings` (`IN10`).
4. User confirms request.
5. Reply is registered (`OUT10`).
6. User will receive a notification once the request is confirmed by the requester (`OUT20`).

### Input Summary
- `IN10`: User Setting: Notifications for Trading
	- boolean
	
### Output Summary
- `OUT10`: Reply registered. The state is set to `ACCEPTED` (`NOTE10`).
- `OUT20`: User receives Discord notifications.

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, ACCEPTED, COMPLETED