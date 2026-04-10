Business Rules & Constraints --- Community Admin: User Onboarding & Resident Oversight
====================================================================================

* * * * *

BR-USR-REG-001 --- Registration Details
-------------------------------------

### BR-REG-001-01 --- Submission Entry

-   A user can only appear in the Registration Details tab via Self-Registration or Invitation
-   Duplicate submissions from the same Mobile No must not be allowed into the Pending queue

### BR-REG-001-02 --- Pending State

-   All new submissions must default to Pending status immediately upon receipt
-   A submission in Pending state must not be accessible to the applicant for editing
-   Only the Community Admin can action a Pending submission

### BR-REG-001-03 --- Review Pop-up Editability

-   Block/Tower and Floor are system-determined and must remain read-only in the Review pop-up
-   Only Flat/Unit and User Type may be modified by the Community Admin during review
-   All User Details fields --- Username, Mobile No, Email ID, Registered On --- must remain read-only at all times

### BR-REG-001-04 --- User Type Assignment

-   User Type must be explicitly assigned by the Community Admin before any approval can be processed
-   The system must not infer or auto-assign User Type under any circumstance
-   Valid User Type values are strictly: Owner, Tenant, Resident
-   A submission cannot transition from Pending to Approved without a User Type being set

### BR-REG-001-05 --- Approval Outcomes

-   An Approved submission must move to the History tab with status Approved
-   A Rejected submission must move to the History tab with status Rejected
-   Once moved to History, the record must be read-only and cannot be re-actioned
-   The same submission cannot be approved and rejected simultaneously

### BR-REG-001-06 --- Post-Approval Behaviour by User Type

-   If User Type = Owner: approval must immediately grant the Owner access to the application and add them to the Resident Log as Active
-   If User Type = Tenant: approval must forward a request to the corresponding Owner's Dashboard and must not grant application access until the Owner accepts
-   If User Type = Resident: approval behaviour to be confirmed --- flagged as open point

### BR-REG-001-07 --- History Tab

-   History must serve as a permanent audit trail and must not be editable
-   Both Approved and Rejected records must be visible under History
-   History records must retain the original submission data at the time of review

* * * * *

BR-USR-REG-002 --- Tenant Lease Approval (Owner Side)
---------------------------------------------------

### BR-REG-002-01 --- Request Triggering

-   A Tenant lease approval request must only appear on the Owner's Dashboard after the Community Admin has approved the Tenant's registration
-   A request must be linked to the specific Flat/Unit the Tenant is registered under
-   The Owner receiving the request must be the Owner of that Flat/Unit

### BR-REG-002-02 --- Pop-up Field Constraints

-   Tenant Name, Mobile No, and Flat/Unit must be pre-filled and read-only
-   The Owner must not be able to modify any pre-filled field
-   The Owner must enter both Lease Start Date and Lease End Date before the Accept action becomes available

### BR-REG-002-03 --- Lease Date Rules

-   Lease Start Date must be today's date or any future date --- past dates are not permitted
-   Lease End Date must always be strictly after the Lease Start Date
-   Lease End Date must be a future date --- past dates are not permitted
-   The system must validate both dates together on submission, not independently in isolation
-   A Lease End Date equal to the Lease Start Date must be rejected

### BR-REG-002-04 --- Acceptance Outcome

-   Once the Owner accepts, the Tenant's status must transition to Active
-   The Tenant must appear in the Resident Log under the Active toggle only after Owner acceptance
-   If the Owner does not act on the request, the Tenant must remain in a pending state on the Owner's Dashboard and must not gain application access
-   A rejected request by the Owner must deny the Tenant application access

* * * * *

BR-USR-RES-001 --- Resident Log
-----------------------------

### BR-RES-001-01 --- Resident Eligibility

-   Only users who have completed the full approval chain must appear in the Resident Log
-   For Owners: appearance in the log requires Community Admin approval only
-   For Tenants: appearance in the log requires Community Admin approval followed by Owner acceptance
-   Users in Pending or Rejected state must never appear in the Resident Log

### BR-RES-001-02 --- Toggle Behaviour

-   Active toggle must display only residents whose current status is Active
-   Archive toggle must display only residents whose current status is Archived
-   A resident must appear under one toggle at a time --- never both simultaneously

### BR-RES-001-03 --- Edit Constraints

-   All fields in the Edit pop-up except Status must be read-only
-   The Community Admin must not be able to modify resident identity or unit details from this screen
-   Status is the only field the Community Admin may change via the Edit action

### BR-RES-001-04 --- Status Transition Rules

-   Valid status values are strictly: Active and Archived
-   An Active resident can be set to Archived by the Community Admin
-   An Archived resident can be restored to Active by the Community Admin
-   Status changes must reflect immediately in the respective toggle view upon saving
-   The system must not allow a resident record to exist without a status value

### BR-RES-001-05 --- Data Integrity

-   Resident records must retain all original approval details regardless of status changes
-   Archiving a resident must not delete their record from the system
-   Archived residents must remain visible under the Archive toggle for audit and reference purposes
