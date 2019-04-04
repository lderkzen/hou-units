# Use Case 218: Delete an event category

### Subject Area
Events

### Actors
`Leadership Member`

### Overview
Delete an existing event category.

### Preconditions
- At least one event category must exist.
- Event category must be unused for future events, event series and event templates.

### Termination Outcome
- **Success 1:** The event category is deleted.
- **Failed 1:** The event category wasn't delete due to an error.

### Use Case Description
**Success 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Delete Event Category` for an existing event category (`IN10`).
5. User is redirected to the `Manage event categories` page and is displayed the current categories (`OUT10`), as well as the success message (`OUT20`).

**Failed 1**
1. User navigates to the `Administration` page.
2. User scrolls to the `Events` category.
3. User navigates to the `Manage event categories` page and is displayed the current categories (`OUT10`).
4. User clicks on `Delete Event Category` for an existing event category (`IN10`).
5. User is redirected to the `Manage event categories` page and is displayed the current categories (`OUT10`), as well as the error message (`OUT30`).

### Input Summary
- `IN10`: An existing event category.

### Output Summary
- `OUT10`: A list of existing event categories.
- `OUT20`: Success message for the deleted event category.
- `OUT30`: Error message that the category was not deleted, including the error reason.

### Notes
- `NOTE10`: Event categories will be flagged as `Deleted`, rather than deleted completetly. This disables future selection of the category, but allows to view the history of events and their categories.