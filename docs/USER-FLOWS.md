# User flows

## Platform boundary

The public website and teacher workspace are React clients. Laravel APIs own validation, authorization, domain rules, email, media, and persistence; the Laravel admin console gives operations staff a controlled interface over the same application services.

```mermaid
flowchart LR
    Website[React public website] --> API[Laravel APIs]
    Teacher[React teacher workspace] --> API
    Admin[Laravel admin console] --> Core[Laravel application services]
    API --> Core
    Core --> Data[(Database and protected media)]
    Core --> Mail[Email and queued notifications]
```

## 1. Course enrollment

```mermaid
sequenceDiagram
    actor Visitor
    participant Site as React website
    participant API as Laravel API
    participant Mail as Laravel mail
    participant Ops as Laravel admin console

    Visitor->>Site: Explore programs and levels
    Site->>API: Request published courses and schedules
    API-->>Site: Return eligible options
    Visitor->>Site: Select class and enter details
    Site->>API: Submit enrollment with consent
    API->>API: Validate availability, consent, and duplicate submissions
    API-->>Site: Return submission confirmation
    API->>Ops: Add enrollment to review queue
    Ops->>API: Confirm, schedule, or request follow-up
    API->>Mail: Send status and next-step email
    Mail-->>Visitor: Deliver confirmation or follow-up
```

## 2. Teacher class operations

```mermaid
flowchart TD
    Login[Teacher signs in to React workspace] --> Dashboard[Assigned schedule]
    Dashboard --> Class[Open class]
    Class --> Attendance[Record attendance]
    Class --> Notes[Add class notes]
    Class --> Progress[Update student progress]
    Attendance --> Save[Validate and save]
    Notes --> Save
    Progress --> Save
    Save --> API[Laravel API]
    API --> Summary[Updated class summary]
```

## 3. Verified showcase voting

```mermaid
sequenceDiagram
    actor Visitor
    participant Showcase
    participant Verify as Verification service
    participant Review as Moderation

    Visitor->>Showcase: Browse event projects
    Visitor->>Showcase: Choose a project and submit vote
    Showcase->>Verify: Send one-time verification code
    Visitor->>Verify: Confirm code
    Verify->>Showcase: Mark ballot verified
    Showcase->>Review: Queue eligible ballot
    Review-->>Showcase: Approve or reject
    Showcase-->>Visitor: Show public results when enabled
```

## 4. Camp registration

```mermaid
flowchart LR
    Sessions[Browse available sessions] --> Cart[Select one or more weeks]
    Cart --> Details[Contact and camper details]
    Details --> Medical[Required care information]
    Medical --> Policies[Policy acknowledgements]
    Policies --> Review[Review registration]
    Review --> Submit[Submit request]
    Submit --> Reference[Receive confirmation reference]
    Reference --> Followup[Staff availability and payment follow-up]
```
