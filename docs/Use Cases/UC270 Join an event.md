# Use Case 270: Join an event

### Subject Area
Events

### Actors
`Any Guild Member`

### Overview
Sign up for an upcoming event.

### Preconditions
- Event must start in the future.
- Event must be open for registration.
- User may not be blacklisted from joining events.
- User may not be the event creator.
- The event roster and waiting list are not full.

### Termination Outcome
- **Success 1:** Dashboard: User is signed up and put into the roster.
- **Success 2:** Dashboard: User is signed up and put into the waiting list.
- **Success 3:** Upcoming Events: User is signed up and put into the roster.
- **Success 4:** Upcoming Events: User is signed up and put into the waiting list.
- **Success 5:** Event: User is signed up and put into the roster.
- **Success 6:** Event: User is signed up and put into the waiting list.
- **Failed 1:** Dashboard: Signing up failed due to a technical error.
- **Failed 2:** Upcoming Events: Signing up failed due to a technical error.
- **Failed 3:** Event: Signing up failed due to a technical error.

### Use Case Description
**Success 1**
1. User navigates to the `Dashboard` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is displayed a `JOINED` indicator (`OUT50`) for the signed up event.

**Success 2**
1. User navigates to the `Dashboard` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is displayed a `WAIT` indicator (`OUT60`) for the signed up event.

**Success 3**
1. User navigates to the `Upcoming Events` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is displayed a `JOINED` indicator (`OUT50`) for the signed up event.

**Success 4**
1. User navigates to the `Upcoming Events` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is displayed a `WAIT` indicator (`OUT60`) for the signed up event.

**Success 5**
1. User navigates to the page of a specific `Event`.
2. User is displayed an indicator about the available slots for the event (`OUT30` and `OUT40`).
3. User signs up for the event (`IN10`) with his primary class (`OUT20`).
4. User is redirected to the same `Event` page and displayed a "added to roster" message (`OUT50`) for the signed up event.

**Success 6**
1. User navigates to the page of a specific `Event`.
2. User is displayed an indicator about the available slots for the event (`OUT30` and `OUT40`).
3. User signs up for the event (`IN10`) with his primary class (`OUT20`).
4. User is redirected to the same `Event` page and displayed a "added to waiting list" message (`OUT50`) for the signed up event.

**Failed 1**
1. User navigates to the `Dashboard` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is redirected to the `Event` page and displayed an error message (`OUT70`) for the signed up event.

**Failed 2**
1. User navigates to the `Upcoming Events` page.
2. User is displayed a list of upcoming events (`OUT20`), as well as an indicator about the available slots for each event (`OUT30` and `OUT40`).
3. User signs up for an event (`IN10`) with his primary class (`OUT20`).
4. User is redirected to the `Event` page and displayed an error message (`OUT70`) for the signed up event.

**Failed 3**
1. User navigates to the page of a specific `Event`.
2. User is displayed an indicator about the available slots for the event (`OUT30` and `OUT40`).
3. User signs up for the event (`IN10`) with his primary class (`OUT20`).
4. User is redirected to the same `Event` page and displayed an error message (`OUT70`) for the signed up event.

### Input Summary
- `IN10`: Sign up request for an upcoming event.

### Output Summary
- `OUT10`: List of upcoming events.
- `OUT20`: The users primary class.
- `OUT30`: Indicator, how many slots are available in the roster.
- `OUT40`: Indicator, how many slots are available in the waiting list.
- `OUT50`: Success message or indicator, that the user is signed up and put into the roster.
- `OUT60`: Success message or indicator, that the user is signed up and put into the waiting list.
- `OUT70`: Error message that the signing up failed, including the error reason.

### Notes
- `NOTE10`: If the event roster and waiting list have class restricitons (e.g. 5 mages in the roster, 3 mages in the waiting list), `OUT30` and `OUT40` will indicate the available slots for the users primary class (`OUT20`), instead of the complete number of available slots.