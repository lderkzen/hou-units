# Use Case 803: Provide interface to query current token balance

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will query the API to return the current token balance for a specific member, to present this balance in a Discord text channel.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond a success and the current balance.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot queries the endpoint for the current token balance of a specific user (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns the current token balance in the response body (`OUT20`)

**Failed 1**
1. Bot queries the endpoint for the current token balance of a specific user (`IN10`)
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: A member that queries the current token balance
    - required, `DiscordUserID`

### Output Summary
- `OUT10`: Response HTTP status code
- `OUT20`: The current token balance

### Notes
Currently no nodes to this use case.