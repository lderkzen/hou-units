# Use Case 305: Confirm Transaction

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may confirm a transaction that they have bought or replied to **or** that they have created.

### Preconditions
- User must be logged in.
- User must have replied or bid on a transaction **or** user must be creator of the transaction.
	- The transaction must have state ACCEPTED (`NOTE10`).

### Termination Outcome
- **Success 1:** Transaction confirmed to be finished. Waiting for the other players confirmation.
- **Success 2:** Transaction confirmed to be finished. Waiting for the other players confirmation. The other user receives a notification.
- **Success 3:** Transaction confirmed to be finished. Tokens are wired.
- **Success 4:** Transaction confirmed to be finished. Tokens are wired. Both users receive a notification.

### Use Case Description
**Success 1**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. Other user sets or has set `Send Notifications for Trading` to false in `User Settings` (`OUT40`).
5. User confirms the transaction (`IN10`).
6. Confirmation registered (`OUT10`).

**Success 2**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. Other user sets or has set `Send Notifications for Trading` to true in `User Settings` (`OUT40`).
5. User confirms the transaction (`IN10`).
6. Confirmation registered (`OUT10`).
7. Other user is notified that the transaction is waiting for confirmation (`OUT30`).

**Success 3**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. Other user sets or has set `Send Notifications for Trading` to false in `User Settings` (`OUT40`).
5. User confirms the transaction (`IN10`).
6. Other user has already confirmed the transaction (`OUT50`).
7. Confirmation registered (`OUT20`).

**Success 4**
1. User navigates to `My Offers & Requests` tab.
2. User opens a transaction.
3. User trades / has traded the items in-game.
4. Both users set or have set `Send Notifications for Trading` to true in `User Settings` (`OUT40`).
5. User confirms the transaction (`IN10`).
6. Other user has already confirmed the transaction (`OUT50`).
7. Confirmation registered (`OUT20`).
8. Both users are notified that the transaction has been completed (`OUT30`).

### Input Summary
- `IN10`: Confirmation
	- boolean

### Output Summary
- `OUT10`: Transaction confirmed to be finished.
- `OUT20`: Transaction confirmed to be finished. The state is set to `COMPLETED`.
- `OUT30`: User receives Discord notifications.
- `OUT40`: Other User Setting: Notifications for Trading
- `OUT50`: Other users confirmation

### Notes
- `NOTE10`: Enum values
	- Requests: UNDEFINED, CREATED, ACCEPTED, COMPLETED
	- Offers: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED