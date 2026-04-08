# Clinic Platform — Database Schema

Entity-relationship schema for a clinic management platform covering patients, doctors, appointments, consultations, diagnostics, reports, and payments.

## Entities

| Entity | Description |
|---|---|---|
| `patient` | Registered patients with personal and contact info |
| `specialty` | Medical specialties assigned to doctors |
| `doctor` | Licensed doctors linked to a specialty |
| `appointment` | Scheduled bookings between patient and doctor |
| `consultation` | Actual clinical visit resulting from an appointment |
| `diagnostic_test` | Tests ordered during a consultation |
| `report` | Findings generated from a diagnostic test |
| `payment` | Payments tied to an appointment or consultation |

## Relationships

- One **patient** books many **appointments**
- One **doctor** attends many **appointments**
- One **appointment** results in at most one **consultation** (zero if cancelled/no-show)
- One **consultation** prescribes many **diagnostic tests**
- One **diagnostic test** generates one **report**
- One **patient** makes many **payments**
- Payments link optionally to an **appointment** or a **consultation**

## Key Design Decisions

- `appointment` and `consultation` are separate — a booking does not guarantee a visit
- `specialty` is a standalone entity, not a plain text field on `doctor`
- `diagnostic_test` belongs to `consultation`, preserving clinical context
- `report.reviewed_by` is a FK back to `doctor`
- `payment` holds nullable FKs to both `appointment` and `consultation` to support pre-visit and post-visit billing models
