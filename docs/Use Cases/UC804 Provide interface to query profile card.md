# Use Case 804: Provide interface to query profile card

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will query the API to return the current profile card information for a specific member, to present this information in a Discord text channel.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond a success and the current profile card information.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot queries the endpoint for the current profile card information of a specific user (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns the current profile card information in the response body (`OUT20`)

**Failed 1**
1. Bot queries the endpoint for the current profile card information of a specific user (`IN10`)
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: A member that queries the current profile card information
    - required, `DiscordUserID`

### Output Summary
- `OUT10`: Response HTTP status code
- `OUT20`: The current profile card information
    - `DiscordUserID`
    - `BackgroundColor`
    - `LadderPosition`
    - `CurrentPoints`
    - `CurrentRank`
    - `Title`

### Notes
Currently no nodes to this use case.