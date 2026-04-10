
# Requirements Traceability Matrix — Community Admin: User Onboarding & Resident Oversight

---

## How to Read This Matrix

Each row represents a Functional Requirement. The columns trace every User Story, Acceptance Criteria, and Business Rule linked to that FR.

---

## FR-USR-REG-001 — Registration Details

| FR ID | Description | User Story IDs | Acceptance Criteria | Business Rule IDs |
|-------|-------------|----------------|--------------------|--------------------|
| FR-USR-REG-001 | View all registration submissions in a table | US-REG-001-01 | Table must display: Block/Tower, Floor, Flat/Unit, Full Name, Mobile No, Email ID, Invited By, Registered On, Action | BR-REG-001-01 |
| FR-USR-REG-001 | Filter submissions by Pending | US-REG-001-02 | Pending toggle must display only submissions awaiting review | BR-REG-001-02 |
| FR-USR-REG-001 | Filter submissions by History | US-REG-001-03 | History toggle must display all finalised submissions — Approved and Rejected — for audit purposes | BR-REG-001-07 |
| FR-USR-REG-001 | Open review pop-up for a pending submission | US-REG-001-04 | Clicking Review must open a pop-up pre-filled with the applicant's registration data | BR-REG-001-02, BR-REG-001-03 |
| FR-USR-REG-001 | Edit Flat/Unit in review pop-up | US-REG-001-05 | Flat/Unit must be editable by the Community Admin; Block/Tower and Floor must be read-only | BR-REG-001-03 |
| FR-USR-REG-001 | Assign User Type before approval | US-REG-001-06, US-REG-001-07 | User Type must be mandatory — Owner, Tenant, or Resident; Admin must not be able to approve without selecting a User Type | BR-REG-001-04 |
| FR-USR-REG-001 | Approve a registration submission | US-REG-001-08 | Approved submissions must move to History with Approved status | BR-REG-001-05, BR-REG-001-06 |
| FR-USR-REG-001 | Reject a registration submission | US-REG-001-09 | Rejected submissions must move to History with Rejected status | BR-REG-001-05 |
| FR-USR-REG-001 | Move actioned submissions to History automatically | US-REG-001-10 | Once moved to History, the record must be read-only and cannot be re-actioned | BR-REG-001-05, BR-REG-001-07 |

---

## FR-USR-REG-002 — Tenant Lease Approval (Owner Side)

| FR ID | Description | User Story IDs | Acceptance Criteria | Business Rule IDs |
|-------|-------------|----------------|--------------------|--------------------|
| FR-USR-REG-002 | Tenant request appears on Owner Dashboard after Community Admin approval | US-REG-002-01 | Approved Tenant request must appear on the Owner's Dashboard | BR-REG-002-01 |
| FR-USR-REG-002 | Owner views pre-filled Tenant details in pop-up | US-REG-002-02 | Pop-up must display Tenant Name, Mobile No, and Flat/Unit as read-only | BR-REG-002-01, BR-REG-002-02 |
| FR-USR-REG-002 | Owner enters Lease Start Date | US-REG-002-03, US-REG-002-04 | Lease Start Date must be today or a future date; past dates must be rejected | BR-REG-002-03 |
| FR-USR-REG-002 | Owner enters Lease End Date | US-REG-002-03, US-REG-002-05 | Lease End Date must always be after Lease Start Date; past dates must be rejected | BR-REG-002-03 |
| FR-USR-REG-002 | Accept action requires both dates to be entered | US-REG-002-06 | Owner must not be able to accept without entering both date fields | BR-REG-002-02, BR-REG-002-03 |
| FR-USR-REG-002 | Tenant status becomes Active after Owner acceptance | US-REG-002-07 | Once accepted, Tenant status must be confirmed as Active and reflected in the Resident Log | BR-REG-002-04 |

---

## FR-USR-RES-001 — Resident Log

| FR ID | Description | User Story IDs | Acceptance Criteria | Business Rule IDs |
|-------|-------------|----------------|--------------------|--------------------|
| FR-USR-RES-001 | View all approved residents in a table | US-RES-001-01 | Table must display: Block/Tower, Floor, Flat/Unit, User Name, Mobile No, Email ID, User Type, Active On, Status, Action | BR-RES-001-01 |
| FR-USR-RES-001 | Filter residents by Active status | US-RES-001-02 | Active toggle must display only residents with Active status | BR-RES-001-02 |
| FR-USR-RES-001 | Filter residents by Archive status | US-RES-001-03 | Archive toggle must display only residents with Archived status | BR-RES-001-02 |
| FR-USR-RES-001 | Only fully approved residents appear in the log | US-RES-001-01 | Owners appear upon Community Admin approval; Tenants appear only after Community Admin approval and Owner acceptance | BR-RES-001-01 |
| FR-USR-RES-001 | Open edit pop-up for a resident record | US-RES-001-04 | Clicking Edit must open a pop-up pre-filled with the resident's details | BR-RES-001-03 |
| FR-USR-RES-001 | Only Status is editable in the edit pop-up | US-RES-001-05 | All fields except Status must be read-only | BR-RES-001-03 |
| FR-USR-RES-001 | Set resident status to Archived | US-RES-001-06 | Status must be editable via dropdown — Active or Archived; changes must save successfully | BR-RES-001-04, BR-RES-001-05 |
| FR-USR-RES-001 | Restore Archived resident to Active | US-RES-001-07 | An Archived resident can be restored to Active by the Community Admin | BR-RES-001-04 |
| FR-USR-RES-001 | Status changes reflect immediately in toggle view | US-RES-001-08 | Changes must be saved successfully on confirmation and reflect in the correct toggle immediately | BR-RES-001-04 |

---

*End of Traceability Matrix — Community Admin: User Onboarding & Resident Oversight*
