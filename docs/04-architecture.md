# 4. System Architecture

## Folder Structure

\`\`\`
GramLink
│
├── client
│   ├── public
│   ├── src
│   │   ├── components
│   │   ├── pages
│   │   ├── hooks
│   │   ├── services
│   │   └── assets
│
├── server
│   ├── config
│   ├── models
│   ├── controllers
│   ├── routes
│   ├── middleware
│   └── utils
│
├── docs
├── uploads
└── README.md
\`\`\`

| Folder | Purpose |
|---|---|
| `client/public` | Static assets served directly by the browser |
| `client/src/components` | Reusable UI building blocks |
| `client/src/pages` | Top-level page components mapped to routes |
| `client/src/hooks` | Custom React hooks encapsulating reusable logic |
| `client/src/services` | Functions for communicating with the backend API |
| `client/src/assets` | Static resources (images, icons, fonts) |
| `server/config` | Backend configuration (DB connection, environment settings) |
| `server/models` | Mongoose schema definitions |
| `server/controllers` | Business logic for handling requests |
| `server/routes` | API endpoint definitions |
| `server/middleware` | Authentication, RBAC, and validation logic |
| `server/utils` | Helper functions (similarity scoring, hashing, formatting) |
| `uploads/` | Storage location for user-uploaded files |

## Tech Stack

- **Frontend:** React (deployed on Vercel)
- **Backend:** Node.js, Express (deployed on Render)
- **Database:** MongoDB (MongoDB Atlas)
- **Authentication:** JWT + bcrypt
- **Image Storage:** Cloudinary

---
⬅️ [Previous: Workflow](./03-workflow.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: Database Design](./05-database-design.md)