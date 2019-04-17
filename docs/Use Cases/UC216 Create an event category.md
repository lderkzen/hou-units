# Use Case 216: Create an event category

### Subject Area
Events

### Actors
`Leadership Member`

### Overview
Create an event category, which will be used to group events and event series.

### Preconditions
No preconditions.

### Termination Outcome
- **Success 1:** The event category is created.
- **Success 2:** A deleted event category is re-enabled.
- **Failed 1:** The event category wasn't created due to a collision with an existing event category name.
- **Failed 2:** The event category wasn't created due to an error.

### Use Case Description
**Success 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Add Event Category` and is taken to that page.
5. User provides a new event category name (`IN10`).
6. User clicks on `Save`.
7. User is redirected to the `Manage event categories` page, being displayed the success message (`OUT20`).

**Success 2**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Add Event Category` and is taken to that page.
5. User provides an event category name (`IN10`), that was previously flagged as deleted.
6. User clicks on `Save`.
7. User is redirected to the `Manage event categories` page, being displayed the success message (`OUT20`).

**Failed 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Add Event Category` and is taken to that page.
5. User provides a new event category name (`IN10`).
6. User clicks on `Save`.
7. User is redirected to the `Add Event Category` page, being displayed the warning message (`OUT30`).

**Failed 2**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Add Event Category` and is taken to that page.
5. User provides a new event category name (`IN10`).
6. User clicks on `Save`.
7. User is redirected to the `Add Event Category` page, being displayed the error message (`OUT40`).

### Input Summary
- `IN10`: An event category name.

### Output Summary
- `OUT10`: A list of existing event categories.
- `OUT20`: Success message for the newly created event category.
- `OUT30`: Warning is displayed, that the name collides with an existing name of a different event category.
- `OUT40`: Error message that the category was not created, including the error reason.

### Notes
- `NOTE10`: Maximum event category name length is limited to 25 characters.