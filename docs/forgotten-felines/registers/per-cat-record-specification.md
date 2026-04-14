# Per-Cat Record Specification — "Current Cats" System

**Forgotten Felines Cat Rescue — Charity No. 1181190**

**Version:** 1.0
**Last Reviewed:** 2026-04-14
**Next Review Due:** 2027-04-14
**Owner:** Fostering Coordinator (with Trustee oversight)
**ADCH Standards addressed:** 76 (records for all animals), 77 (personal data), 78 (records as part of written procedures)

---

## 1. Purpose

ADCH Minimum Welfare Operational Standard 76 requires that "the organisation shall keep records for all animals for which it is responsible, including description, date of arrival and departure, believed age, vet history, behavioural assessments, name and address of the new owner/keeper, and a record of what details were passed to the new owner."

This document is the specification for Forgotten Felines' per-cat record system — the **"Current Cats"** system referenced across the animal-care policy suite. It defines the mandatory fields, access control, retention, and data-handling approach. It is the evidence document an ADCH assessor will expect to see alongside the actual system (a Google Sheet, Airtable base, or equivalent).

This specification does not replace the operational system itself — it defines what that system must contain. The system is built by the Fostering Coordinator against this specification and maintained on an ongoing basis.

---

## 2. Record scope

A per-cat record is opened for **every cat that enters Forgotten Felines' legal care**, from the moment of acceptance (stray intake, surrender, transfer, or born-in-care) until the record is closed (adoption, transfer out, death, or feral release).

One record per cat. For a litter of kittens, each kitten has its own record cross-referenced to the queen and littermates.

---

## 3. Mandatory fields

These fields must exist in the Current Cats system for every cat. Fields are grouped by when they are typically populated.

### 3.1 Identification (on intake)

| Field | Type | Notes |
|---|---|---|
| Unique ID | Text | Auto-generated, never re-used |
| Name (First Name) | Text | Used on vet invoices with Fosterer's Surname |
| Description | Text | Breed, colour, markings, distinguishing features |
| Sex | Enum | Male / Female / Unknown |
| Neutered status on intake | Enum | Neutered / Entire / Unknown |
| Believed age on intake | Text | Age band (kitten / young / adult / senior) + best estimate in months/years |
| Weight on intake | Number | kg |
| Photo(s) | Attachment(s) | At least one identifying photo on intake |

### 3.2 Intake details

| Field | Type | Notes |
|---|---|---|
| Intake date | Date | |
| Intake source | Enum + text | Stray / Surrender / Transfer / Born in care / Feral — with free-text detail |
| Intake source reference | Text | Household name, stray location, transferring organisation |
| Receiving fosterer | Text | From Roles and Responsibilities Register |
| Receiving foster home | Text | Reference to Foster Home Register entry |
| Surrender form on file (if surrendered) | Boolean + file reference | |
| Stray holding period start (if stray) | Date | For Standard 2 / relinquishment policy 7-day rule |
| Unregistered microchip trigger (if applicable) | Date | For 28-day extended hold rule |

### 3.3 Veterinary and health

| Field | Type | Notes |
|---|---|---|
| Microchip scan on intake | Enum + text | Chip found / No chip / Not yet scanned — with chip number |
| Microchip number | Text | |
| Microchip database | Text | |
| Microchip registration date | Date | Forgotten Felines listed as keeper until adoption |
| Microchip transfer to adopter date | Date | Held back until neuter proof for early-adopted kittens |
| Health & welfare assessment — lay | Date + assessor + outcome | Initial assessment within 72 hours |
| Health & welfare assessment — vet | Date + practice + outcome | Within 72 hours per Standard 3 |
| Vaccination history | Structured | Product, dose, date, nominated practice |
| Parasite treatment history | Structured | Product, dose, date |
| Neutering date | Date | |
| FIV result | Enum | Positive / Negative / Not tested |
| FeLV result | Enum | Positive / Negative / Not tested |
| Ongoing medical conditions | Text | |
| Current medications | Text | |
| Nominated practice holding clinical records | Text | Reference to Named Veterinary Practices Register |

### 3.4 Behavioural

| Field | Type | Notes |
|---|---|---|
| Temperament notes | Text | Friendly, nervous, shy, fearful, feral, etc. |
| Triggers and preferences | Text | |
| Cohabitation notes | Text | Suitable with other cats? Dogs? Children? |
| Behavioural incidents | Structured log | Date, description, action taken |
| Behavioural support contact involvement | Text | If Standard 55 behaviourist consulted |

### 3.5 Placement history

| Field | Type | Notes |
|---|---|---|
| Placements | Structured log | Foster home, start date, end date, reason for move |
| Daily care log reference | Link / attachment | Fosterer's day-to-day observations |
| Isolation start and end dates | Date range | Per Cat Isolation on Arrival Policy |

### 3.6 Incidents

| Field | Type | Notes |
|---|---|---|
| Incidents log | Structured | Date, type (illness, injury, escape, refusal to eat, near-miss), actions, outcome |
| Escape log | Structured | Cross-reference to Escape of a Cat Policy recording |

### 3.7 Fit to Home and Adoption

| Field | Type | Notes |
|---|---|---|
| FTH status | Boolean + date | Set when nominated vet confirms Fit to Home |
| FTH approved by | Text | Nominated vet name |
| Rehoming listing date | Date | When added to website / social media |
| Adoption form reference | Text | Link to signed Google form |
| Adopter name | Text | |
| Adopter address | Text | With proof of address captured (Standard 71) |
| Adopter phone | Text | |
| Adopter email | Text | |
| Landlord permission on file (if applicable) | Boolean + file reference | |
| Proof of address on file | Boolean + file reference | Mandatory |
| Home visit date and outcome | Date + text | In-person or virtual |
| Adoption date | Date | |
| Adoption donation received | Boolean + amount | |
| Follow-up contact date and outcome | Date + text | |

### 3.8 Handover record (Standard 76)

This is the explicit "record of what details were passed to the new owner" required by Standard 76.

| Field | Type | Notes |
|---|---|---|
| Care advice pack given | Boolean + date | |
| Medical notes provided | Boolean | |
| Vaccination card provided | Boolean | |
| Microchip details provided | Boolean | |
| Diet information provided | Boolean | |
| Behavioural notes provided | Boolean | |
| Vet details of nominated practice provided | Boolean | |
| Settling-in advice provided | Boolean | |
| Return procedure explained | Boolean | |
| Adopter signature on care advice pack | Boolean + date | |

### 3.9 Departure (record closure)

| Field | Type | Notes |
|---|---|---|
| Departure reason | Enum | Adoption / Transfer / Death / Euthanasia / Feral release / Returned to owner |
| Departure date | Date | |
| Departure notes | Text | |
| Record closed by | Text | Coordinator who closed the record |
| Record closed on | Date | |

---

## 4. Access control (Standard 77)

The Current Cats system holds personal data about adopters and must be handled per the Data Retention Policy, Privacy Notice, and Record of Processing Activities.

### 4.1 Who can access what

| Role | Access level | Notes |
|---|---|---|
| **Fostering Coordinators** | Full read/write | Structural edits (intake, closure, adopter details) |
| **Fosterers** | Read/write on their own cats' daily care log; read on cat's identification and health fields | No access to adopter personal data |
| **Vet Liaison** | Full read; write on veterinary history, isolation, post-mortem fields | |
| **Trustees** | Full read | Write access only when acting as Foster Coordinator |
| **Data Protection Lead** (Sam Mathias) | Full read; responsible for subject access requests and breach response | |
| **Adopters** | No direct access | Receive their handover record at adoption |

### 4.2 Security

- The system must be password-protected with unique credentials per user.
- Credentials must not be shared.
- The system must be backed up at least weekly.
- Access is revoked immediately when a volunteer leaves or changes role.
- Any suspected data breach is handled under the Data Breach Response Procedure.

---

## 5. Retention (Standard 77)

- **Active records** are retained for the duration of the cat's time in Forgotten Felines' care.
- **Closed records** are retained in line with the Data Retention Policy — currently 12 months after departure for adoption-related personal data, and longer where required for welfare or regulatory reasons.
- **Deceased cats** — core clinical and circumstance-of-death information is retained beyond the standard retention period for welfare oversight purposes.
- **Feral release** records are retained long enough to support Standard 50 evidence (typically 2 years).

Medical records held by nominated vets are retained by the practices under their own obligations and are available to Forgotten Felines on request.

---

## 6. Integration with other systems

| System | Relationship |
|---|---|
| Foster Home Register | Per-cat record references the Foster Home Register entry by ID |
| Named Veterinary Practices Register | Per-cat record references the nominated practice that holds clinical records |
| Fosterer Training Record | Receiving fosterer is cross-checked for current training |
| Adoption form (Google form) | Adoption form submission triggers record update |
| Roles and Responsibilities Register | Coordinator and Vet Liaison names are pulled from this register |

---

## 7. Implementation guidance

The Current Cats system is typically implemented as a **Google Sheet** (single sheet with one row per cat and tabbed sub-sheets for structured logs), but may be built in any system that supports:

- Structured fields matching Section 3
- Password-protected access control
- Audit trail of changes (who changed what, when)
- Backup and restore
- Export for subject access requests

The Fostering Coordinator confirms that the live system matches this specification at the annual review.

---

## 8. Review

This specification is reviewed at least annually by the Fostering Coordinator and Data Protection Lead, with Trustee sign-off. A review is also triggered by:

- A change in ADCH standards
- A change in the live system technology
- A data breach or access-control incident
- A change in retention legal basis

### Review log

| Review date | Reviewed by | Trustee sign-off | Changes made | Next review due |
|---|---|---|---|---|
| 2026-04-14 | _[Fostering Coordinator / Data Protection Lead]_ | _[Trustee]_ | Specification created | 2027-04-14 |

---

## 9. Related Documents

- Cat Intake and Medical Care Policy
- Fostering Policy
- Foster Home Assessment Checklist
- Named Veterinary Practices Register
- Data Retention Policy
- Privacy Notice
- Record of Processing Activities
- Data Breach Response Procedure
- Roles and Responsibilities Register

---

*This specification is reviewed at least annually, or sooner if ADCH standards, data-protection legislation, or the live system design changes.*
