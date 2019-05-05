# Use Case 302: Create Trade Request

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may create a trade request with different options.

### Preconditions
- User must be logged in.

### Termination Outcome
- **Success 1:** Request created. User is forwarded to the `My Offers & Requests` tab on the `Trading` page.
- **Success 2:** Request created. User is forwarded to the `My Offers & Requests` tab on the `Trading` page, and will receive notifications
- **Failed 1:** Request not created. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success 1**
1. User navigates to the `Offer & Request Creation` page.
2. User selects `Request` option from radio button group (`IN10`).
3. User provides request information (`IN20`, `IN30`, `IN40`, `IN50`).
4. User sets or has set `Send Notifications for Trading` to false in `User Settings` (`IN60`).
5. User confirms request.
6. Request is created (`OUT10`).
7. The users tokens are taken and held temporarily. 
8. User is forwarded to `My Offer & Requests` tab (`OUT20`) and shown their request.

**Success 2**
1. User navigates to the `Offer & Request Creation` page.
2. User selects `Request` option from radio button group (`IN10`).
3. User provides request information (`IN20`, `IN30`, `IN40`, `IN50`).
4. User sets or has set `Send Notifications for Trading` to true in `User Settings` (`IN60`).
5. User confirms request.
6. Request is created (`OUT10`).
7. The users tokens are taken and held temporarily. 
8. User is forwarded to `My Offer & Requests` tab (`OUT20`) and shown their request.
9. User will receive notifications for replies via Discord (`OUT30`).

**Failed 1**
1. User navigates to the `Offers & Request Creation` page.
2. User selects `Request` option from radio button group (`IN10`).
3. User provides incomplete or invalid data for the request (`IN20`, `IN30`, `IN40`, `IN50`).
4. User confirms request.
5. User is shown validation error message (`OUT40`).

### Input Summary
- `IN10`: Offer or request
	- required, enum (`NOTE10`)
- `IN20`: Cost
	- required, integer, ranging from 1 to configured system wide maximum (possibly 1) or current user tokens (`OUT50`)
- `IN30`: Request lifespan
	- required, datetime, ranging from today + 3 hours to today + 14 days
- `IN40`: Item(s) to be requested
	- required, object, ranging from 1 to configured system wide maximum (possibly 1), allowed by ruling council (`OUT60`)
- `IN50`: Amount of each (`IN40`)
	- required, integer, ranging from 1 to configured system wide maximum
- `IN60`: User Setting: Notifications for Trading
	- boolean

### Output Summary
- `OUT10`: Request (`IN10`) is created using (`IN20`, `IN30`, `IN40`, `IN50`) and the state is set to `CREATED` (`NOTE20`).
- `OUT20`: User is forwarded to `My Offer & Requests` tab and is shown (`OUT10`).
- `OUT30`: User receives Discord notifications.
- `OUT40`: Validation error message is shown below unvalidated field(s).
- `OUT50`: Current user tokens.
- `OUT60`: Allowed items for P2P trading.

### Notes
- `NOTE10`: Enum values: UNDEFINED, OFFER, REQUEST
- `NOTE20`: Enum values: UNDEFINED, CREATED, ACCEPTED, COMPLETED