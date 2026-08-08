# 7. UI/UX Design

## Page Hierarchy

\`\`\`mermaid
flowchart TD
    Home[Home Page] --> Login[Login Page]
    Home --> Register[Registration Page]
    Login --> Dashboard[Dashboard]
    Register --> Dashboard
    Dashboard --> Equipment[Equipment Page]
    Dashboard --> Labor[Labor Page]
    Dashboard --> Match[Match Page]
    Dashboard --> AdminCheck{User is Admin?}
    AdminCheck -->|Yes| AdminDash[Administrator Dashboard]
    Equipment --> Match
    Labor --> Match
\`\`\`

## Component Purpose

| Page | Component | Purpose |
|---|---|---|
| Home | Navigation Bar | Access to Login/Register |
| Home | Hero Section | Introduces the platform's purpose |
| Login | Login Form | Authenticates user, issues JWT |
| Registration | Registration Form | Captures new user details |
| Dashboard | Profile Summary | Displays logged-in user's identity/role |
| Dashboard | Post Action Buttons | Entry points for new listings |
| Dashboard | Recent Listings Panel | Shows user's active listings |
| Equipment/Labor Page | Available/Required Tabs | Separates offered vs sought resources |
| Equipment/Labor Page | Listing Card | Displays listing details, links to matches |
| Match Page | Match Results List | Displays top three AI-generated matches |
| Match Page | Contact Provider Button | Initiates contact with matched listing owner |
| Match Page | Manual Search Option | Bypasses AI suggestions |
| Admin Dashboard | Users/Listings/Matches Tabs | Separates managed data types |
| Admin Dashboard | Management Table | Lists records with Resolve/Remove actions |

---
⬅️ [Previous: API Documentation](./06-api-documentation.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: Security](./08-security.md)