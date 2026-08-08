# GramLink

**AI-powered village equipment and labor-sharing platform**

GramLink connects farmers, equipment owners, and laborers through a single centralized digital platform — replacing word-of-mouth, phone calls, and scattered WhatsApp groups with fast, AI-driven matching.

---

## 📌 Problem Statement

Small and marginal farmers often struggle to find affordable equipment and labor resources. Current methods — word-of-mouth communication, phone calls, and WhatsApp groups — result in:

- Loss of time
- Loss of money
- Loss of energy
- Delayed harvesting
- Underutilization of resources
- Reduced productivity

## 🎯 Objectives

- Improve equipment utilization
- Reduce costs
- Reduce search time
- Connect equipment owners with farmers
- Connect laborers with employers
- Increase productivity

## 👥 Stakeholders

- Farmers
- Equipment owners
- Laborers
- Farmers needing equipment
- Farmers needing labor

---

## ✨ Features

| Module | Description |
|---|---|
| **Equipment Availability** | Equipment owners post available equipment (tractors, harvesters, tillers, sprayers, seeders) |
| **Equipment Requirement** | Farmers post equipment needs (requirement, date, budget, duration) |
| **Labor Availability** | Laborers post their availability (labor type, availability, wage) |
| **Labor Requirement** | Farmers post labor needs (number required, work type, budget) |
| **AI Recommendation System** | Reads listings, finds similar ones, calculates similarity scores, and surfaces the top three matches |
| **Administrator Dashboard** | Manage users, manage listings, resolve requests, remove fraudulent listings |
| **Manual Search** | Users can search manually instead of relying on AI suggestions |

---

## 🏗️ Tech Stack

- **Frontend:** React
- **Backend:** Node.js, Express
- **Database:** MongoDB (MongoDB Atlas)
- **Authentication:** JWT + bcrypt
- **Image Storage:** Cloudinary

---

## 📁 Folder Structure

GramLink
│
├── client
│ ├── public
│ ├── src
│ │ ├── components
│ │ ├── pages
│ │ ├── hooks
│ │ ├── services
│ │ └── assets
│
├── server
│ ├── config
│ ├── models
│ ├── controllers
│ ├── routes
│ ├── middleware
│ └── utils
│
├── docs
│ └── GramLink_Documentation.md
│
├── uploads
└── README.md

---

## 🗄️ Database Schema (MongoDB)

**Collections:** `Users`, `Listings`, `Matches`, `Administrators`

---

- **Users → Listings:** one-to-many (`userId` FK)
- **Listings → Matches:** one-to-many, via `sourceListing` and `targetListing` FKs
- **Administrators:** oversee Users, Listings, and Matches

---

## 🔌 API Overview

| Group | Base Route |
|---|---|
| Authentication | `/api/auth` |
| Listings | `/api/listings` |
| Matches | `/api/matches` |
| Administrator | `/api/admin` |

All protected routes require a JWT in the `Authorization: Bearer <token>` header. Administrator routes additionally require an admin role.

---

## 🔐 Security

- JWT-based authentication
- Role-based authorization
- Password hashing with bcrypt
- Input validation
- CORS protection

---

## 🚀 Deployment

| Layer | Platform |
|---|---|
| Frontend | Vercel |
| Backend | Render |
| Database | MongoDB Atlas |
| Image Storage | Cloudinary |

### Environment Variables

Create a `.env` file in the `server` directory with:

MONGO_URI=
JWT_SECRET=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
CLIENT_URL=
PORT=

---

## 📄 Full Documentation

For detailed API request/response formats, ER diagrams, sequence diagrams, and UI wireframes, see [`docs/GramLink_Documentation.md`](./docs/GramLink_Documentation.md).

---

## 🏆 Built For

Smart India Hackathon (SIH)

---

## 📄 License

This project is currently under development. License to be added.