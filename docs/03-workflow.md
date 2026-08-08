# 3. Workflow

## Textual Workflow

A user begins by opening the GramLink application and registering or logging in. Once authenticated, the user selects a category relevant to their need: **Equipment Available**, **Equipment Required**, **Labor Available**, or **Labor Required**. The user then fills in the corresponding form for that category.

The submitted data is stored in the database. The system then executes the **matching algorithm**, which generates similarity scores by comparing the new listing against existing listings. Based on these scores, the platform displays the **top three matches** to the user. The user can then contact the relevant provider, and the request is resolved.

## System Workflow

\`\`\`mermaid
flowchart TD
    A[User opens the application] --> B[Register or Log in]
    B --> C[Select a category]
    C --> C1[Equipment Available]
    C --> C2[Equipment Required]
    C --> C3[Labor Available]
    C --> C4[Labor Required]
    C1 --> D[Fill in the form]
    C2 --> D
    C3 --> D
    C4 --> D
    D --> E[Store data in the database]
    E --> F[Execute the matching algorithm]
    F --> G[Generate similarity scores]
    G --> H[Display the top three matches]
    H --> I[Contact the provider]
    I --> J[Resolve the request]
\`\`\`

## User Journey

| Stage | User Action | System Response |
|---|---|---|
| 1. Entry | Opens the GramLink app | Loads home/login screen |
| 2. Authentication | Registers or logs in | Validates credentials, grants access |
| 3. Category Selection | Chooses Equipment/Labor, Available/Required | Loads the relevant form |
| 4. Listing Submission | Fills and submits the form | Stores listing in the database |
| 5. Matching | — | Runs matching algorithm, generates similarity scores |
| 6. Results | Views suggested matches | Displays top three matches |
| 7. Action | Contacts the provider | Connects the two parties |
| 8. Resolution | Confirms/completes the exchange | Marks the request as resolved |

## Sequence Diagram

\`\`\`mermaid
sequenceDiagram
    participant U as User
    participant F as Frontend (React)
    participant B as Backend (Express)
    participant DB as Database (MongoDB)
    participant AI as AI Recommendation Engine

    U->>F: Open app / Register or Login
    F->>B: Auth request
    B->>DB: Validate credentials
    DB-->>B: User verified
    B-->>F: Auth success
    F-->>U: Access granted

    U->>F: Select category & fill form
    F->>B: Submit listing data
    B->>DB: Store listing
    DB-->>B: Listing saved

    B->>AI: Trigger matching algorithm
    AI->>DB: Fetch existing listings
    DB-->>AI: Return listings
    AI-->>B: Similarity scores
    B-->>F: Top three matches
    F-->>U: Display matches

    U->>F: Contact provider
    F->>B: Update match status
    B->>DB: Mark request as resolved
    DB-->>B: Confirmation
    B-->>F: Resolution confirmed
    F-->>U: Request resolved
\`\`\`

---
⬅️ [Previous: Features & Scope](./02-features-scope.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: System Architecture](./04-architecture.md)