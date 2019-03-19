# Use Case 801: Provide interface to accept allowed members information

### Subject Area
Web API

### Actors
`Discord bot`

### Overview
The Discord bot will push a list of allowed members to the API.

### Preconditions
The bot instance must be authenticated and authorized.

### Termination Outcome
- **Success 1:** The API will respond a success.
- **Failed 1:** The API fails to respond.

### Use Case Description
**Success 1**
1. Bot pushes a list of allowed members (`IN10`) to the endpoint for allowed members
2. API returns HTTP200 (`OUT10`) in the response header

**Failed 1**
1. Bot pushes a list of allowed members (`IN10`) to the endpoint for allowed members
2. API returns a **none** HTTP200 (`OUT10`) in the response header

### Input Summary
- `IN10`: A complete list of all currently allowed members to access the system
    - required, list of `DiscordUserID`

### Output Summary
- `OUT10`: Response HTTP status code

### Notes
Currently no nodes to this use case.