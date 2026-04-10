## 1. Owner Registration Lifecycle

```mermaid
flowchart TD
    A([Owner Submits Self-Registration]) --> B[Status: Pending]
    B --> C{Community Admin Reviews\nRegistration Details tab}
    C -->|User Type = Owner\nApprove| D[Status: Approved\nMoved to History]
    C -->|Reject| E[Status: Rejected\nMoved to History]
    D --> F[Owner Gains Access\nto Application]
    F --> G[Owner Appears in\nResident Log as Active]
```

## 2. Tenant Registration Lifecycle

```mermaid
flowchart TD
    A([Tenant Submits via Invitation Link]) --> B[Status: Pending\nRegistration Details tab]
    B --> C{Community Admin Reviews\nAssigns User Type = Tenant}
    C -->|Reject| D[Status: Rejected\nMoved to History]
    C -->|Approve| E[Status: Approved\nMoved to History]
    E --> F[Request Forwarded to\nOwner Dashboard]
    F --> G{Owner Reviews\nTenant Request}
    G -->|Reject| H[Tenant Access Denied]
    G -->|Accept + Enter\nLease Start and End Date| I[Tenant Status: Active]
    I --> J[Tenant Appears in\nResident Log as Active]
```

## 3. Registration Details Tab — Admin Review Flow

```mermaid
flowchart TD
    A([Submission Arrives\nSelf-Registration or Invitation]) --> B[Appears in Pending Toggle]
    B --> C[Community Admin Clicks\nReview in Action Column]
    C --> D[Review Pop-up Opens\nPre-filled Data]
    D --> E{Admin Sets\nFlat/Unit and User Type}
    E -->|User Type not set| F[Validation Error\nCannot Approve]
    F --> E
    E -->|Approve| G[Moved to History\nStatus: Approved]
    E -->|Reject| H[Moved to History\nStatus: Rejected]
    G -->|User Type = Owner| I[Owner Access Granted]
    G -->|User Type = Tenant| J[Forwarded to Owner Dashboard]
```

## 4. Resident Log Lifecycle

```mermaid
flowchart TD
    A([Resident Fully Approved]) --> B[Appears in Resident Log\nActive Toggle]
    B --> C{Community Admin\nEdits Status}
    C -->|Set to Archived| D[Moved to Archive Toggle\nStatus: Inactive]
    D --> E{Community Admin\nEdits Status}
    E -->|Set to Active| B
```

## 5. Tenant Lease Approval — Owner Side

```mermaid
flowchart TD
    A([Community Admin Approves Tenant]) --> B[Request Appears on\nOwner Dashboard]
    B --> C[Owner Opens Request Pop-up]
    C --> D[Read-only: Tenant Name\nMobile No, Flat/Unit]
    D --> E{Owner Enters\nLease Start Date}
    E -->|Past date| F[Validation Error:\nMust be today or future]
    F --> E
    E -->|Valid date| G{Owner Enters\nLease End Date}
    G -->|Before or same\nas Start Date| H[Validation Error:\nMust be after Start Date]
    H --> G
    G -->|Valid date| I[Owner Clicks Accept]
    I --> J[Tenant Status: Active\nAppears in Resident Log]
```

