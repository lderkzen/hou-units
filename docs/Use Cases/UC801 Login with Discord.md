# Use Case 801: Login with Discord

### Subject Area
Security

### Actors
`Unauthorized User` or `Any Guild Member`

### Overview
Any `unauthorized user` may attempt to perform a login using the Discord authentication.  
`Any guild member` will be successfully authenticated and authorized, allowing them to proceed to the main website content.

### Preconditions
Users must have a Discord account.

### Termination Outcome
- **Success:** Allowed, authenticated, and forwarded to the dashboard page.
- **Failed 1:** Not allowed, authentication revoked, and forwarded to the forbidden page.
- **Failed 2:** Permissions not granted to the application, no authentication performed, and forwarded to the forbidden page.

### Use Case Description
**Success**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User accepts the permissions requested by the application.
5. User is authenticated by Discord (`IN20`).
6. `DiscordUserID` (`IN30`) is checked against the allowed users (`IN10`).
7. User is allowed to access the website (`OUT10`).
8. User is forwarded to the `Dashboard` page (`OUT20`).

**Failed 1**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User accepts the permissions requested by the application.
5. User is authenticated by Discord (`IN20`).
6. `DiscordUserID` (`IN30`) is checked against the allowed users (`IN10`).
7. User is not allowed to access the website (`OUT10`).
8. Authentication is revoked.
9. User is forwarded to the `Forbidden` page (`OUT30`).

**Failed 2**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User denies the permissions requested by the application.
5. User is not authenticated by Discord (`IN20`).
6. User is not allowed to access the website (`OUT10`).
7. User is forwarded to the `Forbidden` page (`OUT30`).

### Input Summary
#### Mandatory
- `IN10`: Allowed users, stored in the database.
- `IN20`: Authentication provided by Discord.
- `IN30`: `DiscordUserID` provided by Discord.

### Output Summary
- `OUT10`: Verification if the user is authorized to access the website.
- `OUT20`: Forward to the `Dashboard` page.
- `OUT30`: Forward to the `Forbidden` page.

### Notes
No additional notes to this use case.