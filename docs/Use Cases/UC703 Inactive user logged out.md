# Use Case 801: Inactive user logged out

### Subject Area
Security

### Actors
`Any Guild Member`

### Overview
`Any guild member` will be automatically logged out, if he didn't visit the site for too long.

### Preconditions
- Users must be logged in.
- User must not be logged in for 14 days.

### Termination Outcome
- **Success:** Logged in user is logged out and redirected to the landing page.

### Use Case Description
**Success**
1. User opens any page of the website.
2. User is logged out.
3. User is redirected to the landing page (`OUT10`).
4. User shown a message about the logout (`OUT20`).

### Input Summary
No input.

### Output Summary
- `OUT10`: Forward to the `Landing` page.
- `OUT20`: Message about automatic logout.

### Notes
No additional notes to this use case.