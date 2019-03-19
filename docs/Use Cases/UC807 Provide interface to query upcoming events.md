# Use Case 807: Provide interface to query upcoming events

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will query the API for upcoming events within the next hour, to present those events in a Discord text channel.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond with upcoming events.
- **Success 2:** The API will respond with no upcoming events.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot queries the endpoint for upcoming events within the next hour
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns the list of upcoming events starting within the next hour in the response body (`OUT20`)

**Success 2**
1. Bot queries the endpoint for upcoming events within the next hour
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns an empty response body

**Failed 1**
1. Bot queries the endpoint for upcoming events within the next hour
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
No input required.

### Output Summary
- `OUT10`: Response HTTP status code
- `OUT20`: A list of upcoming events starting within the next hour

### Notes
Currently no nodes to this use case.