# Functional Requirement Document (FRD)

## Module 5.3 – Community Admin: User Onboarding & Resident Oversight

* * * * *

1\. Purpose
-----------

This document defines the functional, validation, and error-handling requirements for the Community Admin --- User Onboarding & Resident Oversight module of the Apartment/Community Management System. It covers the Registration Details and Resident Log tabs accessible exclusively to the Community Admin, as well as the Tenant Lease Approval flow on the Owner's side.

* * * * *

2\. Scope
---------

### In Scope

-   Registration Details tab --- filtering, reviewing, approving, and rejecting user registration submissions
-   Resident Log tab --- viewing, filtering, and editing resident status
-   Tenant Lease Approval --- Owner-side date entry and acceptance flow



### Out of Scope

-   User self-registration and tenant invitation flows
-   Billing and payment management
-   Gate access and visitor management
-   Amenity booking and service requests

* * * * *

3\. Roles
---------

| Role | Responsibility |
| --- | --- |
| Community Admin | Reviews registrations, assigns User Type, approves or rejects submissions, manages resident records, configures user roles |
| Owner | Receives tenant approval request on dashboard, enters lease dates, accepts tenant |

* * * * *

4\. Functional Requirements
---------------------------

* * * * *

### FR-USR-REG-001 --- Registration Details

#### Description

Provides the Community Admin with a tabular view of all user registration submissions. The admin filters by Pending or History, reviews each submission, assigns a User Type, and approves or rejects accordingly.

* * * * *

#### Tab Structure

| Column | Description |
| --- | --- |
| Block/Tower | Block or tower of the applicant's unit |
| Floor | Floor number of the applicant's unit |
| Flat/Unit | Unit number of the applicant |
| Full Name | Full name of the applicant |
| Mobile No | Registered mobile number |
| Email ID | Registered email address |
| Invited By | Owner who sent the invitation, if applicable |
| Registered On | Date of registration submission |
| Action | Review button for pending submissions |

* * * * *

#### Toggle Filters

| Toggle | Behaviour |
| --- | --- |
| Pending | Displays all submissions awaiting Community Admin review |
| History | Displays all finalised submissions --- Approved and Rejected --- for audit purposes |

* * * * *

#### Review Pop-up --- Fields

| Section | Field | Editable | Notes |
| --- | --- | --- | --- |
| Community Details | Block/Tower | No | Read-only |
| Community Details | Floor | No | Read-only |
| Community Details | Flat/Unit | Yes | Editable by Community Admin |
| User Details | Username | No | Read-only |
| User Details | Mobile No | No | Read-only |
| User Details | Email ID | No | Read-only |
| User Details | Registered On | No | Read-only |
| User Details | User Type | Yes | Mandatory --- Owner, Tenant, or Resident |

* * * * *

#### Input Fields & Field-Level Validations --- Review Pop-up

| Field Name | Mandatory | Data Type | Editable | Acceptable Values | Validation Rules |
| --- | --- | --- | --- | --- | --- |
| Block/Tower | --- | String | No | Pre-filled | Read-only |
| Floor | --- | String / Integer | No | Pre-filled | Read-only |
| Flat/Unit | Yes | String | Yes | Existing units in community | Must be a valid unit within the community |
| Username | --- | String | No | Pre-filled | Read-only |
| Mobile No | --- | Numeric String | No | Pre-filled | Read-only |
| Email ID | --- | String | No | Pre-filled | Read-only |
| Registered On | --- | Date | No | Pre-filled | Read-only |
| User Type | Yes | Enum | Yes | Owner, Tenant, Resident | Mandatory before approval |

* * * * *

#### Error Handling --- Review Pop-up

##### Flat/Unit

| Field | Scenario | Error Message | Type | Location |
| --- | --- | --- | --- | --- |
| Flat/Unit | Field cleared or left blank | Flat/Unit is mandatory. | Inline | Below Field |
| Flat/Unit | Invalid or non-existent unit | Please select a valid Flat/Unit within this Community. | Popup | Centre of Screen |

##### User Type

| Field | Scenario | Error Message | Type | Location |
| --- | --- | --- | --- | --- |
| User Type | No selection made before Approve | User Type is mandatory. Please select a User Type before approving. | Inline | Below Field |
| User Type | Invalid value (tampered request) | Invalid User Type selected. | Popup | Centre of Screen |
| User Type | Value outside allowed list | User Type must be one of the following: Owner, Tenant, or Resident. | Inline | Below Field |

##### System-Level Errors

| Scenario | Error Message | Type | Location |
| --- | --- | --- | --- |
| Approval attempted with validation errors | Please correct the highlighted errors before submitting. | Popup | Centre of Screen |
| Server validation failure | Unable to process the request. Please try again. | Popup | Centre of Screen |
| Database constraint violation | Data validation failed. Please verify the entered details. | Popup | Centre of Screen |
| Unauthorized access attempt | You are not authorized to perform this action. | Popup | Centre of Screen |

* * * * *

### FR-USR-RES-001 --- Resident Log

#### Description

Provides the Community Admin with a complete view of all Active and Archived residents. Owners appear after Community Admin approval. Tenants appear only after Community Admin approval and Owner acceptance. The Community Admin can update resident status via the Edit action.

* * * * *

#### Tab Structure

| Column | Description |
| --- | --- |
| Block/Tower | Block or tower of the resident's unit |
| Floor | Floor number of the resident's unit |
| Flat/Unit | Unit number of the resident |
| User Name | Full name of the resident |
| Mobile No | Registered mobile number |
| Email ID | Registered email address |
| User Type | Owner or Tenant |
| Active On | Date the resident was activated |
| Status | Active or Archived |
| Action | Edit icon for modifying resident status |

* * * * *

#### Toggle Filters

| Toggle | Behaviour |
| --- | --- |
| Active | Displays only residents with Active status |
| Archive | Displays only residents with Archived status |

* * * * *

#### Input Fields & Field-Level Validations --- Edit Resident Pop-up

| Field Name | Mandatory | Data Type | Editable | Acceptable Values | Validation Rules |
| --- | --- | --- | --- | --- | --- |
| Block/Tower | --- | String | No | Pre-filled | Read-only |
| Floor | --- | String / Integer | No | Pre-filled | Read-only |
| Flat/Unit | --- | String | No | Pre-filled | Read-only |
| User Name | --- | String | No | Pre-filled | Read-only |
| Mobile No | --- | Numeric String | No | Pre-filled | Read-only |
| Email ID | --- | String | No | Pre-filled | Read-only |
| User Type | --- | Enum | No | Pre-filled | Read-only |
| Active On | --- | Date | No | Pre-filled | Read-only |
| Status | Yes | Enum | Yes | Active, Archived | Mandatory selection |

* * * * *

#### Error Handling --- Edit Resident Pop-up

##### Status

| Field | Scenario | Error Message | Type | Location |
| --- | --- | --- | --- | --- |
| Status | No selection made | Status is mandatory. | Inline | Below Field |
| Status | Invalid value (tampered request) | Invalid Status selected. | Popup | Centre of Screen |
| Status | Value outside allowed list | Status must be either Active or Archived. | Inline | Below Field |

##### System-Level Errors

| Scenario | Error Message | Type | Location |
| --- | --- | --- | --- |
| Save attempted with invalid status | Please correct the highlighted errors before saving. | Popup | Centre of Screen |
| Server validation failure | Unable to process the req


### FR-USR-REG-001 --- Tenant Lease Approval (Owner Side)

#### Description

Once the Community Admin approves a Tenant registration, a request is forwarded to the relevant Owner's Dashboard. The Owner must enter lease dates and accept the request before the Tenant gains Active status in the Resident Log.

* * * * *

#### Lease Approval Pop-up --- Fields

| Field | Editable | Notes |
| --- | --- | --- |
| Tenant Name | No | Read-only, pre-filled |
| Mobile No | No | Read-only, pre-filled |
| Flat/Unit | No | Read-only, pre-filled |
| Lease Start Date | Yes | Must be today or a future date |
| Lease End Date | Yes | Must be after Lease Start Date |

* * * * *

#### Input Fields & Field-Level Validations --- Lease Approval

| Field Name | Mandatory | Data Type | Editable | Acceptable Values | Validation Rules |
| --- | --- | --- | --- | --- | --- |
| Tenant Name | --- | String | No | Pre-filled | Read-only |
| Mobile No | --- | Numeric String | No | Pre-filled | Read-only |
| Flat/Unit | --- | String | No | Pre-filled | Read-only |
| Lease Start Date | Yes | Date | Yes | Today or future date | Cannot be a past date |
| Lease End Date | Yes | Date | Yes | Any future date | Must be after Lease Start Date |

* * * * *

#### Error Handling --- Lease Approval

##### Lease Start Date

| Field | Scenario | Error Message | Type | Location |
| --- | --- | --- | --- | --- |
| Lease Start Date | Field left blank | Lease Start Date is mandatory. | Inline | Below Field |
| Lease Start Date | Invalid date format | Please enter a valid date. | Inline | Below Field |
| Lease Start Date | Past date entered | Lease Start Date must be today or a future date. | Inline | Below Field |

##### Lease End Date

| Field | Scenario | Error Message | Type | Location |
| --- | --- | --- | --- | --- |
| Lease End Date | Field left blank | Lease End Date is mandatory. | Inline | Below Field |
| Lease End Date | Invalid date format | Please enter a valid date. | Inline | Below Field |
| Lease End Date | Same as or before Lease Start Date | Lease End Date must be after the Lease Start Date. | Inline | Below Field |
| Lease End Date | Past date entered | Lease End Date must be a future date. | Inline | Below Field |

##### System-Level Errors

| Scenario | Error Message | Type | Location |
| --- | --- | --- | --- |
| Accept attempted without both dates | Please enter both Lease Start Date and Lease End Date before accepting. | Popup | Centre of Screen |
| Server validation failure | Unable to process the request. Please try again. | Popup | Centre of Screen |
| Unauthorized access attempt | You are not authorized to perform this action. | Popup | Centre of Screen |

* * * * *
