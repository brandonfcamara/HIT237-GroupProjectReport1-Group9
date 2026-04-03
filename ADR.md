# Architecture Decision Records

This document records significant architectural and design decisions made during the development of our Django application for Assessment 2.

---

## ADR 001: [Short decision title]

**Status:** Proposed / Accepted / Superseded

### Context
Describe the problem, requirement, or design issue that led to this decision.

Example:
We needed to decide how to model the relationship between users and bookings in our Django application. The system requires each booking to belong to one user, while each user may have multiple bookings.

### Alternatives considered

#### Option 1: Use a ForeignKey
- Simple and easy to implement
- Matches a one-to-many relationship well
- Easy to query using Django ORM
- Less suitable if the relationship becomes many-to-many later

#### Option 2: Use a ManyToManyField
- Flexible for many-to-many cases
- Useful if one booking could belong to multiple users
- Adds unnecessary complexity for the current requirements

#### Option 3: Store user details directly in the booking model without relationship design
- Fast to scaffold
- Poor object-oriented design
- Causes duplication and weak data integrity

### Decision
State the chosen approach and explain why it was selected.

Example:
We chose to use a `ForeignKey` from `Booking` to `User` because the requirement is clearly one user to many bookings. This supports data integrity, fits Django’s ORM well, and keeps the model simple and maintainable.

### Code reference
Provide exact file paths and line numbers where this decision is implemented.

Example:
- `bookings/models.py:12-24`
- `bookings/admin.py:5-14`

### Consequences
Explain the trade-offs, limitations, and impact of the decision.

Example:
This decision keeps the data model simple and readable. However, if future requirements allow shared bookings between users, the model may need to be redesigned using a many-to-many relationship or a through model.

---

## ADR 002: [Short decision title]

**Status:** Proposed / Accepted / Superseded

### Context
[Write here]

### Alternatives considered

#### Option 1
- Pro
- Pro
- Con

#### Option 2
- Pro
- Pro
- Con

#### Option 3
- Pro
- Pro
- Con

### Decision
[Write here]

### Code reference
- `path/to/file.py:line-line`

### Consequences
[Write here]

---

## ADR 003: [Short decision title]

**Status:** Proposed / Accepted / Superseded

### Context
[Write here]

### Alternatives considered

#### Option 1
- Pro
- Con

#### Option 2
- Pro
- Con

### Decision
[Write here]

### Code reference
- `path/to/file.py:line-line`

### Consequences
[Write here]
