# Use Case 309: Assign Officer to Transaction Issue

### Subject Area
Trading

### Actors
`Officer`

### Overview
`Officers` may assign themselves to reported transaction issues.

### Preconditions
- User must be logged in.
- User must have rank `Officer` or higher in Discord.

### Termination Outcome
- **Success 1:** Officer assigned.
- **Success 2:** Officer assigned. One user is notified.
- **Success 3:** Officer assigned. Both users are notified.

### Use Case Description
**Success 1**
1. Officer navigates to the `transaction` page.
2. System shows submitted issue (`OUT10`). 
3. Officer assigns himself (`IN10`).
4. Officer registered as handler (`OUT20`).
5. Both attached users have set `Send Notifications for Trading` to false in `User Settings` (`OUT30`).

**Success 2**
1. Officer navigates to the `transaction` page.
2. System shows submitted issue (`OUT10`). 
3. Officer assigns himself (`IN10`).
4. Officer registered as handler (`OUT20`).
5. One attached user has set `Send Notifications for Trading` to true in `User Settings` (`OUT30`).
6. User will receive a notification (`OUT40`).

**Success 3**
1. Officer navigates to the `transaction` page.
2. System shows submitted issue (`OUT10`). 
3. Officer assigns himself (`IN10`).
4. Officer registered as handler (`OUT20`).
5. Both attached users have set `Send Notifications for Trading` to true in `User Settings` (`OUT30`).
6. Both users will receive a notification (`OUT50`).

### Input Summary
- `IN10`: Assign officer
	- button

### Output Summary
- `OUT10`: Submitted issue.
- `OUT20`: Officer is assigned to the issue.
- `OUT30`: User Setting: Notifications for Trading.
- `OUT40`: User receives Discord notifications.
- `OUT50`: Both users receive Discord notifications.

### Notes
No additional notes to this use case.