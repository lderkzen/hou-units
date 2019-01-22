# Use Case 303: Make Bid On Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may make make a bid on any other `Any Guild Member`s offer.

### Preconditions
- User must be logged in.
- An offer must be available.

### Termination Outcome
- **Success 1:** Bid made.
- **Success 2:** Bid made. Offer is instantly accepted and waiting for confirmation.
- **Success 3:** Bid made. User will receive notifications.
- **Success 4:** Bid made. Offer is instantly accepted and waiting for confirmation. User will receive notifications.
- **Failed 1:** Bid not made. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success 1**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT50`, `OUT60`, `OUT70`, `OUT80`).
4. User provides a bid (`IN10`).
5. User sets or has set `Send Notifications for Trading` to false in `User Settings` (`IN20`).
6. User sends bid.
7. Bid is registered (`OUT10`).

**Success 2**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT50`, `OUT60`, `OUT70`, `OUT80`).
4. User sets or has set `Send Notifications for Trading` to false in `User Settings` (`IN20`).
5. User confirms instant buy.
6. Bid is registered (`OUT20`).
7. User will receive a notification once the offer is confirmed finished by the supplier (`OUT30`).

**Success 3**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT50`, `OUT60`, `OUT70`, `OUT80`).
4. User provides a bid (`IN10`).
5. User sets or has set `Send Notifications for Trading` to true in `User Settings` (`IN20`).
6. User sends bid.
7. Bid is registered (`OUT10`).
8. User will receive notifications if a higher bid is made (`OUT30`).

**Success 4**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT50`, `OUT60`, `OUT70`, `OUT80`).
4. User sets or has set `Send Notifications for Trading` to true in `User Settings` (`IN20`).
5. User confirms instant buy.
6. Bid is registered (`OUT20`).
7. User will receive a notification once the offer is confirmed by the supplier (`OUT30`).

**Failed 1**
1. User navigates to the `Offers & Requests` tab.
2. User navigates to an offer.
3. System provides (`OUT50`, `OUT60`, `OUT70`, `OUT80`).
4. User provides invalid or incomplete data for the bid (`IN10`).
5. User sends bid.
6. User is shown validation error message (`OUT40`).

### Input Summary
- `IN10`: Bid
	- required, integer, ranging from the current bid (`OUT50`) to the instant sale price (`OUT60`) or current tokens (`OUT80`), before offer lifespan has passed (`OUT70`)
- `IN20`: User Setting: Notifcations for Trading
	- boolean

### Output Summary
- `OUT10`: Bid is registered using (`IN10`) and the state is set to `BIDDING` (`NOTE10`).
- `OUT20`: Bid is registered using (`IN10`) and the state is set to `ACCEPTED` (`NOTE10`).
- `OUT30`: User receives Discord notifications.
- `OUT40`: Validation error message is shown below unvalidated field(s).
- `OUT50`: Current highest bid
- `OUT60`: Instant sale price
- `OUT70`: Offer lifespan
- `OUT80`: Current user tokens

### Notes
- `NOTE10`: Enum values: UNDEFINED, CREATED, BIDDING, ACCEPTED, COMPLETED