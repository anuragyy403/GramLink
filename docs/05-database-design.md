# 5. Database Design

## Collections Overview

GramLink uses **MongoDB** with four core collections: **Users**, **Listings**, **Matches**, and **Administrators**.

### Users Collection

| Field | Description |
|---|---|
| `_id` | Primary Key — uniquely identifies each user |
| `name` | Full name of the registered user |
| `email` | Email address, used for identification/communication |
| `phone` | Contact number |
| `village` | Village the user belongs to — used for location-based matching |
| `profession` | User's role/occupation (e.g., Farmer) |
| `password` | Hashed password, used for authentication |

### Listings Collection

| Field | Description |
|---|---|
| `_id` | Primary Key — uniquely identifies each listing |
| `userId` | Foreign Key → Users.`_id` |
| `category` | "equipment" or "labor" |
| `type` | "available" or "required" |
| `title` | Short heading summarizing the listing |
| `description` | Detailed explanation of the listing |
| `village` | Village associated with the listing |
| `price` | Cost associated with the listing |

### Matches Collection

| Field | Description |
|---|---|
| `_id` | Primary Key — uniquely identifies each match |
| `sourceListing` | Foreign Key → Listings.`_id` (listing that triggered the match) |
| `targetListing` | Foreign Key → Listings.`_id` (listing matched against the source) |
| `similarityScore` | AI-generated score (e.g., 0.92) indicating match closeness |
| `matchStatus` | Current state of the match (e.g., "pending") |

### Administrators Collection

| Field | Description |
|---|---|
| `_id` | Primary Key — uniquely identifies each administrator |
| `name` | Administrator's name |
| `email` | Login/identification email |
| `role` | Administrator's role (e.g., "admin") |

## Primary Keys & Foreign Keys Summary

| Collection | Primary Key | Foreign Key(s) |
|---|---|---|
| Users | `_id` | — |
| Listings | `_id` | `userId` → Users.`_id` |
| Matches | `_id` | `sourceListing` → Listings.`_id`, `targetListing` → Listings.`_id` |
| Administrators | `_id` | — |

## ER Diagram

\`\`\`mermaid
erDiagram
    USERS ||--o{ LISTINGS : "creates"
    LISTINGS ||--o{ MATCHES : "appears as source in"
    LISTINGS ||--o{ MATCHES : "appears as target in"
    ADMINISTRATORS ||--o{ USERS : "manages"
    ADMINISTRATORS ||--o{ LISTINGS : "manages"
    ADMINISTRATORS ||--o{ MATCHES : "manages"

    USERS {
        string _id PK
        string name
        string email
        string phone
        string village
        string profession
        string password
    }

    LISTINGS {
        string _id PK
        string userId FK
        string category
        string type
        string title
        string description
        string village
        number price
    }

    MATCHES {
        string _id PK
        string sourceListing FK
        string targetListing FK
        number similarityScore
        string matchStatus
    }

    ADMINISTRATORS {
        string _id PK
        string name
        string email
        string role
    }
\`\`\`

## Relationships & Cardinality

| Relationship | Type | Cardinality |
|---|---|---|
| Users – Listings | Creation | One-to-Many |
| Listings – Matches (source) | Matching | One-to-Many |
| Listings – Matches (target) | Matching | One-to-Many |
| Administrators – Users/Listings/Matches | Management | One-to-Many |

---
⬅️ [Previous: System Architecture](./04-architecture.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: API Documentation](./06-api-documentation.md)