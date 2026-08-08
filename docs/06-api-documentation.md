# 6. API Documentation

**Authentication:** JWT (JSON Web Token). Successful login returns a token, sent in subsequent requests as `Authorization: Bearer <token>`. Passwords are hashed with **bcrypt**.

## Authentication APIs

| Endpoint | Method | Auth | Description | Status Codes |
|---|---|---|---|---|
| `/api/auth/register` | POST | No | Registers a new user | 201, 400, 409 |
| `/api/auth/login` | POST | No | Authenticates a user, returns JWT | 200, 400, 401 |
| `/api/auth/profile` | GET | Yes | Retrieves logged-in user's profile | 200, 401 |
| `/api/auth/profile` | PUT | Yes | Updates logged-in user's profile | 200, 400, 401 |

## Listing APIs

| Endpoint | Method | Auth | Description | Status Codes |
|---|---|---|---|---|
| `/api/listings` | POST | Yes | Creates a new listing | 201, 400, 401 |
| `/api/listings` | GET | Yes | Retrieves all listings | 200, 401 |
| `/api/listings/:id` | GET | Yes | Retrieves a single listing | 200, 401, 404 |
| `/api/listings/:id` | PUT | Yes | Updates a listing (owner only) | 200, 400, 401, 403, 404 |
| `/api/listings/:id` | DELETE | Yes | Deletes a listing (owner only) | 200, 401, 403, 404 |

## Matching APIs

| Endpoint | Method | Auth | Description | Status Codes |
|---|---|---|---|---|
| `/api/matches` | POST | Yes | Triggers the AI recommendation engine | 201, 400, 401, 404 |
| `/api/matches` | GET | Yes | Retrieves all matches for the user | 200, 401 |
| `/api/matches/:id` | GET | Yes | Retrieves a single match | 200, 401, 404 |
| `/api/matches/:id` | DELETE | Yes | Deletes/dismisses a match | 200, 401, 404 |

## Administrator APIs
*(Require JWT + Admin role)*

| Endpoint | Method | Auth | Description | Status Codes |
|---|---|---|---|---|
| `/api/admin/users` | GET | Admin | Retrieves all users | 200, 401, 403 |
| `/api/admin/listings` | GET | Admin | Retrieves all listings | 200, 401, 403 |
| `/api/admin/matches` | GET | Admin | Retrieves all matches | 200, 401, 403 |
| `/api/admin/resolve/:id` | PUT | Admin | Marks a request as resolved | 200, 401, 403, 404 |
| `/api/admin/delete/:id` | DELETE | Admin | Removes a fraudulent record | 200, 401, 403, 404 |

## Status Code Reference

| Code | Meaning |
|---|---|
| 200 OK | Request succeeded |
| 201 Created | Resource created successfully |
| 400 Bad Request | Malformed or missing fields |
| 401 Unauthorized | No valid JWT provided |
| 403 Forbidden | Authenticated user lacks permission |
| 404 Not Found | Requested resource does not exist |

---
⬅️ [Previous: Database Design](./05-database-design.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: UI/UX Design](./07-ui-ux-design.md)