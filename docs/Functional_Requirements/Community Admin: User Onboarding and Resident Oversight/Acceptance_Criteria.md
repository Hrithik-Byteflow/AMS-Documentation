Acceptance Criteria --- Community Admin: User Onboarding & Resident Oversight
===========================================================================

* * * * *

FR-USR-REG-001 --- Registration Details
-------------------------------------

### Acceptance Criteria

#### General

-   Only Community Admin must be able to access the Registration Details tab
-   Table must display: Block/Tower, Floor, Flat/Unit, Full Name, Mobile No, Email ID, Invited By, Registered On, and Action columns
-   Submissions must appear via Self-Registration or Invitation only

#### Pending Toggle

-   Must filter and display only submissions awaiting Community Admin review
-   Action column must display a Review button for each pending entry

#### History Toggle

-   Must filter and display all submissions with a finalised status
-   Approved and Rejected submissions must both appear here
-   Records in History must be read-only and serve as an audit trail

#### Review Pop-up

-   Clicking Review must open a pop-up pre-filled with the applicant's registration data
-   Community Details must display Block/Tower and Floor as read-only
-   Flat/Unit must be editable by the Community Admin
-   User Details must display Username, Mobile No, Email ID, and Registered On as read-only
-   User Type must be editable and mandatory --- must be set to Owner, Tenant, or Resident before approval
-   Admin must not be able to approve without selecting a User Type
-   Admin must be able to Approve or Reject the submission
-   Approved submissions must move to History with Approved status
-   Rejected submissions must move to History with Rejected status
-   Approved Owner submissions must grant the Owner access to the application
-   Approved Tenant submissions must trigger a request on the Owner's Dashboard for acceptance

* * * * *

FR-USR-REG-002 --- Tenant Lease Approval (Owner Side)
---------------------------------------------------

### Acceptance Criteria

-   Approved Tenant request must appear on the Owner's Dashboard
-   Owner must be able to open the request via a pop-up
-   Pop-up must display Tenant Name, Mobile No, and Flat/Unit as read-only
-   Owner must enter Lease Start Date and Lease End Date before accepting
-   Lease Start Date must be today or a future date
-   Lease End Date must always be after the Lease Start Date
-   Owner must not be able to accept without entering both date fields
-   Once accepted, the Tenant's status must be confirmed as Active and reflected in the Resident Log

* * * * *

FR-USR-RES-001 --- Resident Log
-----------------------------

### Acceptance Criteria

#### General

-   Only Community Admin must be able to access the Resident Log tab
-   Table must display: Block/Tower, Floor, Flat/Unit, User Name, Mobile No, Email ID, User Type, Active On, Status, and Action columns
-   Only residents who have completed the full verification and approval chain must appear in the Resident Log
-   Owners appear in the log upon Community Admin approval
-   Tenants appear in the log only after Community Admin approval followed by Owner acceptance

#### Active Toggle

-   Must filter and display only residents with Active status

#### Archive Toggle

-   Must filter and display only residents with Archived status

#### Edit Action

-   Community Admin must be able to click the Edit icon in the Action column
-   Clicking Edit must open a pop-up pre-filled with the resident's details
-   All fields except Status must be read-only
-   Status must be editable via a dropdown --- Active or Archived
-   Changes must be saved successfully on confirmation

* * * * *

