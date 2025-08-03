# AgeWell Financials App

A full-fledged application for tracking daily expenses and income for an old age home with individual patient logins and pages.

## Tech Stack

| Layer | Tech Recommendation | Reason |
| --- | --- | --- |
| Frontend | React (with Vite) | Fast, modular UI with component reusability |
| Backend | Node.js + Express | Scalable, RESTful APIs |
| Database | PostgreSQL or MongoDB | Relational (PostgreSQL) or flexible (MongoDB) models |
| Auth | Firebase Auth / Passport.js | Secure login and session handling |
| Hosting | GitHub (code) + Railway / Vercel | Free or low-cost deployment + Git integration |
| Admin Panel | React Admin / Custom Dashboard | Manage residents, expenses, reports |

## Core Features

### User Roles
- **Admin:** Full access to all modules
- **Resident/Family:** View their own financials only
- **Staff:** Limited input and monitoring access

### Modules
- Resident Profiles (demographics, room, medical notes)
- Daily Expenses (food, medicines, activities, utilities)
- Income Records (payments received, donations)
- Monthly Statements (auto-generated PDFs)
- Reports (summary views, filters by resident, date, category)
- Notifications (optional email/SMS alerts)
- Secure Login & Dashboard per user

## Database Schema (Simplified)

```
Users
- id
- name
- role (admin, resident, staff)
- email
- password_hash

Residents
- id
- name
- dob
- contact_info
- room_no
- guardian_user_id (FK to Users)

Expenses
- id
- resident_id (nullable)
- category
- amount
- description
- date

Income
- id
- resident_id (nullable)
- source
- amount
- notes
- date
```

## Repository Structure

```
/client        --> React frontend
/server        --> Express backend
/db            --> Prisma or SQL schema/migrations
/scripts       --> Deployment & seeding
/docs          --> Architecture, onboarding
```

## MVP Build Steps

1. **Auth System**
   - Firebase/Auth0 or Passport.js with role-based access
2. **Backend API**
   - CRUD for residents, expenses, income
   - Secure endpoints with JWT sessions
3. **Frontend UI**
   - Dashboard with summary cards
   - Resident profile pages
   - Input forms for income and expenses
   - Monthly breakdowns
4. **Admin Panel**
   - Add/update residents
   - Export CSV/PDF
   - Filter/search
5. **Deployment**
   - Frontend → Vercel
   - Backend → Railway/Render
   - DB → Supabase/PostgreSQL on Railway

## Optional Enhancements

- Export invoices as PDFs (e.g. using Puppeteer or jsPDF)
- Multi-language support (English + Hindi)
- Budget tracking and alert thresholds
- SMS/email alerts for guardians
- Audit trail for financial logs

