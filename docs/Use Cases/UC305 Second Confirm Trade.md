# Use Case 305: Second Confirm Trade

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may set a transaction to `COMPLETED` (`NOTE10`) if they have bought or replied to it **or** if they are the creator.

### Preconditions
- User must be logged in.
- User must have replied or bid on a transaction **or** user must be creator of the transaction.
	- The transaction must have state `ACCEPTED` or `PURCHASED` (`NOTE10`).
- Another player must have confirmed the transaction first.

### Termination Outcome
- **Success 1:** Transaction confirmed to be finished and `COMPLETED` (`NOTE10`). Tokens are transferred.
- **Success 2:** Transaction confirmed to be finished and `COMPLETED` (`NOTE10`). Tokens are transferred. Other user receives a notification.

### Use Case Description
**Success 1**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. User confirms the transaction (`IN10`).
5. Other user has already confirmed the transaction (`OUT50`).
6. Confirmation registered and tokens transferred (`OUT20`).
7. Other user sets or has set `Send Notifications for Trading` to false in `User Settings` (`OUT40`).

**Success 2**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. User confirms the transaction (`IN10`).
5. Other user has already confirmed the transaction (`OUT50`).
6. Confirmation registered and tokens transferred (`OUT20`).
7. Other user sets or has set `Send Notifications for Trading` to true in `User Settings` (`OUT40`).
8. Other user is notified that the transaction has been `COMPLETED` (`NOTE10`,`OUT30`).

### Input Summary
- `IN10`: Confirmation
	- boolean

### Output Summary
- `OUT10`: Transaction confirmed.
- `OUT20`: Transaction confirmed. The state is set to `COMPLETED`. Tokens transferred.
- `OUT30`: User receives Discord notifications.
- `OUT40`: Other User Setting: Notifications for Trading
- `OUT50`: Other users confirmation

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, PURCHASED, COMPLETED