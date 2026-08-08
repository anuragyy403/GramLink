# 8. Security

## Authentication — JWT
On successful login, the server issues a signed JWT. The client sends it via the `Authorization: Bearer <token>` header on protected requests. Invalid/missing/expired tokens return `401 Unauthorized`.

## Authorization — Role-Based Access Control
Users can only manage their own listings. Administrator-only endpoints check role after authentication; unauthorized access returns `403 Forbidden`.

## Password Hashing — bcrypt
Passwords are hashed with bcrypt before storage and never persisted in plain text.

## Input Validation
All incoming data is validated for required fields, correct types, and expected formats before reaching the database. Invalid input returns `400 Bad Request`.

## CORS Protection
Configured on the Express backend to restrict which domains (e.g., the deployed frontend) can access the API.

## Rate Limiting
Restricts requests per client within a time window (e.g., on `/api/auth/login`) to mitigate brute-force attempts. Excess requests return `429 Too Many Requests`.

---
⬅️ [Previous: UI/UX Design](./07-ui-ux-design.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: Deployment Architecture](./09-deployment.md)