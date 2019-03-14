# Use Case 805: Provide interface to query new trade issues

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will query the API for new trade issues since the last query time, to present those new trade issues in a Discord text channel.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond with new trade issues.
- **Success 2:** The API will respond with no new trade issues.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot queries the endpoint for new trade issues after the last query time (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns the list of new trade issues in the response body (`OUT20`)

**Success 2**
1. Bot queries the endpoint for new trade issues after the last query time (`IN10`)
2. API returns HTTP200 (`OUT10`) in the response header
3. API returns an empty response body

**Failed 1**
1. Bot queries the endpoint for new trade issues after the last query time (`IN10`)
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: Last query time
    - required, `DATETIME`

### Output Summary
- `OUT10`: Response HTTP status code
- `OUT20`: A list of new trade issues filed after the last query time

### Notes
Currently no nodes to this use case.