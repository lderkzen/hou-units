# Use Case 101: View the dashboard

### Subject Area
General

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may view the dashboard, accessing the most important information.

### Preconditions
- User must be logged in.

### Termination Outcome
- **Success 1:** The dashboard is displayed.

### Use Case Description
**Success 1**
1. User navigates to the `Dashboard` page.
2. Dashboard information is displayed (`OUT10`, `OUT20`, `OUT30`, `OUT40`)

### Input Summary
No input required.

### Output Summary
- `OUT10`: List of upcoming events
- `OUT20`: List of open trade offers and requests
- `OUT30`: List of open service requests
- `OUT40`: Forecast/Burndown chart for token balance

### Notes
- `NOTE10`: The outputs will be displayed in a 2 by 2 grid.
- `NOTE20`: The list of upcoming events (`OUT10`) will be displayed in the top-left corner of the grid.
- `NOTE30`: The list of open trade offers and requests (`OUT20`) will be displayed in the bottom-left corner of the grid.
- `NOTE40`: The list of open services (`OUT30`) will be displayed in the bottom-right corner of the grid.
- `NOTE50`: The forecast/burndown chart for token balance (`OUT40`) will be displayed in the top-right corner of the grid.