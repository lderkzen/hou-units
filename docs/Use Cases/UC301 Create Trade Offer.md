	# Use Case 301: Create Trade Offer

### Subject Area
Trading

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may create a trade offer with different options.

### Preconditions
- User must be logged in.

### Termination Outcome
- **Success 1:** Offer created. User is forwarded to the `My Offers & Requests` tab on the `Trading` page.
- **Success 2:** Offer created. User is forwarded to the `My Offers & Requests` tab on the `Trading` page, and will receive notifications.
- **Failed 1:** Offer not created. Error validation message shown under fields which didn't pass validation.

### Use Case Description
**Success 1**
1. User navigates to the `Offer & Request Creation` page.
2. User selects `Offer` option from radio button group (`IN10`).
3. User provides offer information (`IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`).
4. User sets or has set `Send Notifications for Trading` to false in `User Settings` (`IN80`).
4. User confirms offer.
5. Offer is created (`OUT10`).
6. User is forwarded to `My Offers & Requests` tab (`OUT20`) and shown their offer.

**Success 2**
1. User navigates to the `Offer & Request Creation` page.
2. User selects `Offer` option from radio button group (`IN10`).
3. User provides offer information (`IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`).
4. User sets or has set `Send Notifications for Trading` to true in `User Settings` (`IN80`).
5. User confirms offer.
6. Offer is created (`OUT10`).
7. User is forwarded to `My Offers & Requests` tab (`OUT20`) and shown their offer.
8. User will receive notifications for new offers via Discord (`OUT30`).

**Failed 1**
1. User navigates to the `Offer & Request Creation` page.
2. User selects `Offer` option from radio button group (`IN10`).
3. User provides incomplete or invalid data for the offer (`IN20`, `IN30`, `IN40`, `IN50`, `IN60`).
4. User confirms offer.
5. User is shown validation error message (`OUT40`).

### Input Summary
- `IN10`: Offer or request
    - required, enum (`NOTE10`)
- `IN20`: Minimum price
    - required, integer, ranging from 1 to configured system wide maximum
- `IN30`: Instant sale price
    - required, integer, ranging from (`IN10`) to double of (`IN10`)
- `IN40`: Offer lifespan
    - required, datetime, ranging from today + 3 hours to today + 14 days
- `IN50`: Item(s) to be offered
    - required, object, ranging from 1 to configured system wide maximum (possibly 1), allowed by ruling council (`OUT50`)
- `IN60`: Amount of each (`IN40`)
    - required, integer, ranging from 1 to configured system wide maximum
- `IN70`: Image link
    - string
- `IN80`: User Setting: Notifications for Trading
    - boolean

### Output Summary
- `OUT10`: Offer (`IN10`) is created using (`IN20`, `IN30`, `IN40`, `IN50`, `IN60`, `IN70`) and the state is set to `CREATED` (`NOTE20`).
- `OUT20`: User forwarded to `My Offers & Requests` tab and is shown (`OUT10`).
- `OUT30`: User receives Discord notifications.
- `OUT40`: Validation error message is shown below unvalidated field(s).
- `OUT50`: Allowed items for P2P trading.

### Notes
- `NOTE10`: Enum values: UNDEFINED, OFFER, REQUEST
- `NOTE20`: Enum values: UNDEFINED, CREATED, PURCHASED, COMPLETED