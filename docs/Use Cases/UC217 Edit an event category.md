# Use Case 217: Edit an event category

### Subject Area
Events

### Actors
`Leadership Member`

### Overview
Edit the name of an existing event category.

### Preconditions
- At least one event category must exist.

### Termination Outcome
- **Success 1:** The event category is renamed.
- **Failed 1:** The new name collides with a different event category name.
- **Failed 2:** The renamed event category wasn't saved due to an error.

### Use Case Description
**Success 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Edit Event Category` for an existing event category (`IN10`) and is taken to that page.
5. User is displayed the current event category name (`OUT20`).
5. User provides a new event category name (`IN20`).
6. User clicks on `Save`.
7. User is redirected to the `Manage event categories` page, being displayed the success message (`OUT30`).

**Failed 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Edit Event Category` for an existing event category (`IN10`) and is taken to that page.
5. User is displayed the current event category name (`OUT20`).
6. User provides a new event category name (`IN20`).
7. User clicks on `Save`.
8. User is redirected to the `Edit Event Category` page, being displayed the warning message (`OUT40`).

**Failed 2**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Edit Event Category` for an existing event category (`IN10`) and is taken to that page.
5. User is displayed the current event category name (`OUT20`).
6. User provides a new event category name (`IN20`).
7. User clicks on `Save`.
8. User is redirected to the `Edit Event Category` page, being displayed the error message (`OUT50`).

### Input Summary
- `IN10`: An existing event category.
- `IN20`: An event category name.

### Output Summary
- `OUT10`: A list of existing event categories.
- `OUT20`: The current event category name.
- `OUT30`: Success message for the renamed event category.
- `OUT40`: Warning is displayed, that the name collides with an existing name of a different event category.
- `OUT50`: Error message that the category was not renamed, including the error reason.

### Notes
- `NOTE10`: Maximum event category name length is limited to 25 characters.