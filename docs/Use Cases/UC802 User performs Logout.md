# Use Case 801: User Performs Logout

### Subject Area
Security

### Actors
`Any Guild Member`

### Overview
`Any guild member` will be successfully logged out, redirecting them to the landing page.

### Preconditions
- Users must be logged in.
- User must be on a page with the nav bar.

### Termination Outcome
- **Success:** Logged in user is logged out and redirected to the landing page.

### Use Case Description
**Success**
1. User opens the user menu dropdown upon clicking the user icon on the nav bar.
2. The user menu dropdown opens.
3. User clicks on "Logout".
4. User is logged out.
5. User is redirected to the landing page (`OUT10`).
6. User shown a message about the logout (`OUT20`).

### Input Summary
No input.

### Output Summary
- `OUT10`: Forward to the `Landing` page.
- `OUT20`: Message about successful logout.

### Notes
No additional notes to this use case.