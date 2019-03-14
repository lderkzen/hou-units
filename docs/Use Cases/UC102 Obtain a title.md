# Use Case 102: Obtain a title

### Subject Area
General

### Actors
`Any Guild Member`

### Overview
`Any Guild Member` may obtain a title, being displayed on the Discord profile card.

### Preconditions
- User does not own a title.

### Termination Outcome
- **Success 1:** User obtains the selected title.
- **Failed 1:** User has insufficient tokens to obtain the selected title.

### Use Case Description
**Success 1**
1. User navigates to the `Profile` page
2. User is displayed the current token balance (`OUT20`) in the navigation bar
3. User goes to the `Title` section, where all available titles are displayed (`OUT10`)
4. User selects a title (`IN10`) which is cheap enough to obtain
5. User confirms the purchase
6. User is shown the success message (`OUT30`)

**Failed 1**
1. User navigates to the `Profile` page
2. User is displayed the current token balance (`OUT20`) in the navigation bar
3. User goes to the `Title` section, where all available titles are displayed (`OUT10`)
4. User selects a title (`IN10`) which is to expensive to obtain
5. User confirms the purchase
6. User is shown the failure message (`OUT40`)

### Input Summary
- `IN10`: Title selected by the user

### Output Summary
- `OUT10`: List of available titles and their prices
- `OUT20`: Current token balance
- `OUT30`: Success message, title is obtained
- `OUT40`: Failure message, title is *not* obtained

### Notes
- `NOTE10`: Titles will decay the same way as everything else in the system.