# Use Case 308: First Confirm Trade

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may confirm a transaction they have bought or replied to **or** if they are the creator.

### Preconditions
- User must be logged in.
- User must have replied or bid on a transaction **or** user must be creator of the transaction.
	- The transaction must have state ACCEPTED (`NOTE10`).

### Termination Outcome
- **Success 1:** Transaction confirmed. Waiting for the other players confirmation.
- **Success 2:** Transaction confirmed. Waiting for the other players confirmation. The other user receives a notification.

### Use Case Description
**Success 1**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. User confirms the transaction (`IN10`).
5. Confirmation registered (`OUT10`).
6. Other user sets or has set `Send Notifications for Trading` to false in `User Settings` (`OUT30`).

**Success 2**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. User confirms the transaction (`IN10`).
5. Confirmation registered (`OUT10`).
6. Other user is notified that the transaction is waiting for confirmation (`OUT20`).
7. Other user sets or has set `Send Notifications for Trading` to true in `User Settings` (`OUT30`).

### Input Summary
- `IN10`: Confirmation
	- boolean

### Output Summary
- `OUT10`: Transaction confirmed.
- `OUT20`: User receives Discord notifications.
- `OUT30`: Other User Setting: Notifications for Trading.

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED