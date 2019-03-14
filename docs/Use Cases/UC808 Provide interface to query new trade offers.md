# Use Case 808: Provide interface to query new trade offers

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will query the API for new trade offers since the last query time, to present those new trade offers in a Discord text channel.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond with new trade offers.
- **Success 2:** The API will respond with no new trade offers.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot queries the endpoint for newly created trade offers after the last query time (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns the list of newly created trade offers in the response body (`OUT20`)

**Success 2**
1. Bot queries the endpoint for newly created trade offers after the last query time (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns an empty response body

**Failed 1**
1. Bot queries the endpoint for newly created trade offers after the last query time (`IN10`)
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: Last query time
    - required, `DATETIME`

### Output Summary
- `OUT10`: Response HTTP status code
- `OUT20`: A list of trade offers created after the last query time

### Notes
Currently no nodes to this use case.