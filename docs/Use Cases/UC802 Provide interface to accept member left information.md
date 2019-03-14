# Use Case 802: Provide interface to accept member left information

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
When a member left, the Discord bot will push a single notification to the API.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond a success.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot pushes a member left notification (`IN10`) to the endpoint for member left handling
2. API returns HTTP200 (`OUT10`) in the response header

**Failed 1**
1. Bot pushes a member left notification (`IN10`) to the endpoint for member left handling
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: A member that is no longer allowed to access the system
    - required, `DiscordUserID`

### Output Summary
- `OUT10`: Response HTTP status code

### Notes
Currently no nodes to this use case.