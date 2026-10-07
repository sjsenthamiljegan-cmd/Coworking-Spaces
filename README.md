# CoWork Space – Coworking Space Booking (React + Spring Boot + MySQL)

## Structure
- `backend/`  – Spring Boot 3 (Java 17), JPA, JWT security
- `frontend/` – React 18 + Vite
- `database/schema.sql` – MySQL schema (optional; tables auto-create)

## Run
1. **MySQL**: install & start. Default config: user `root`, empty password (XAMPP default) (change in `backend/src/main/resources/application.properties`). DB `workspace_booking_db` is auto-created.
2. **Backend**: `cd backend && mvn spring-boot:run`  → http://localhost:8080
   (First run seeds demo spaces + users.)
3. **Frontend**: `cd frontend && npm install && npm run dev` → http://localhost:5173

## Demo logins
- User:  user@cowork.com / user123
- Admin: admin@cowork.com / admin123

## Flow
Register → Login → Home (search, featured, popular) → Spaces (search/filter) → Space Details → Workspace Management (Desk / Meeting Room / Private Office) → Booking (date, time, availability) → Payment (+confirmation) → Profile (edit, change password) → My Bookings (upcoming / completed / cancelled / details / cancel) → Reviews → Admin (Dashboard, Users, Spaces, Bookings, Payments, Settings)

## Main API
POST /api/auth/register, /login · GET /api/spaces, /spaces/featured, /spaces/popular, /spaces/{id}, /spaces/{id}/workspaces · GET /api/bookings/availability · POST /api/bookings · GET /api/bookings/my · PUT /api/bookings/{id}/cancel · POST /api/payments · GET/PUT /api/users/me · PUT /api/users/password · GET/POST /api/reviews · /api/admin/** (ADMIN only)
