# Use Case 801: Login with Discord

### Subject Area
Security

### Actors
`Unauthorized User` or `Any Guild Member`

### Overview
Any `unauthorized user` may attempt to perform a login using the Discord authentication.  
`Any guild member` will be successfully authenticated and authorized, allowing them to proceed to the main website content.

### Preconditions
- Users must have a Discord account.

### Termination Outcome
- **Success 1:** Allowed, authenticated, and forwarded to the dashboard page.
- **Failed 1:** Not allowed, authentication revoked, and forwarded to the forbidden page.
- **Failed 2:** Permissions not granted to the application, no authentication performed, and forwarded to the forbidden page.

### Use Case Description
**Success 1**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User accepts the permissions requested by the application.
5. User is authenticated by Discord (`IN10`).
6. `DiscordUserID` (`IN20`) is checked against the allowed users (`OUT10`).
7. User is allowed to access the website (`OUT20`).
8. User is forwarded to the `Dashboard` page (`OUT30`).

**Failed 1**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User accepts the permissions requested by the application.
5. User is authenticated by Discord (`IN10`).
6. `DiscordUserID` (`IN20`) is checked against the allowed users (`OUT10`).
7. User is not allowed to access the website (`OUT20`).
8. Authentication is revoked.
9. User is forwarded to the `Forbidden` page (`OUT40`).

**Failed 2**
1. User directs or is directed to the `Landing` page.
2. User clicks the `Login with Discord` button.
3. User is redirected to the Discord authentication page, asking for permissions to trust the application.
4. User denies the permissions requested by the application.
5. User is not authenticated by Discord (`IN10`).
6. User is not allowed to access the website (`OUT20`).
7. User is forwarded to the `Forbidden` page (`OUT40`).

### Input Summary
- `IN10`: Authentication provided by Discord.
- `IN20`: `DiscordUserID` provided by Discord.
    - provided by Discord after granting access to the application

### Output Summary
- `OUT10`: Allowed users, stored in the database.
- `OUT20`: Verification if the user is authorized to access the website.
- `OUT30`: Forward to the `Dashboard` page.
- `OUT40`: Forward to the `Forbidden` page.

### Notes
No additional notes to this use case.