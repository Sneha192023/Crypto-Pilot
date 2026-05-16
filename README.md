# Crypto-Pilot
CryptoPilot is a modern full-stack crypto portfolio tracker built with React and Node.js. It provides real-time cryptocurrency prices, portfolio analytics, watchlists, alerts, market trends, and crypto news with a responsive dark-themed UI inspired by modern fintech platforms.
# CryptoPilot — Premium Crypto Dashboard + Admin Panel

## Quick Start

### 1. Install MongoDB
Make sure MongoDB is running locally on port 27017.
- Download: https://www.mongodb.com/try/download/community

### 2. Backend Setup
```bash
cd server
npm install
npm run seed      # Seeds dummy users + data
npm run dev       # Starts on http://localhost:5000
```

### 3. Frontend Setup
```bash
# In root directory
npm install
npm run dev       # Starts on http://localhost:5173
```

---

##  Demo Credentials

| Role  | Email             | Password  |
|-------|-------------------|-----------|
| Admin | admin@test.com    | admin123  |
| User  | user1@test.com    | 123456    |
| User  | user2@test.com    | 123456    |

---

##  Google OAuth Setup (Optional)

1. Go to https://console.cloud.google.com
2. Create a new project → APIs & Services → Credentials
3. Create OAuth 2.0 Client ID (Web application)
4. Add `http://localhost:5173` to Authorized JavaScript origins
5. Copy the Client ID

**Frontend** — edit `.env`:
```
VITE_GOOGLE_CLIENT_ID=your_client_id_here
```

**Backend** — edit `server/.env`:
```
GOOGLE_CLIENT_ID=your_client_id_here
```

---

##  Structure

```
crypto-dashboard/
├── src/
│   ├── pages/
│   │   ├── Auth.tsx              # Login + Register + Google OAuth
│   │   ├── admin/
│   │   │   ├── AdminDashboard.tsx
│   │   │   ├── AdminUsers.tsx
│   │   │   ├── AdminMarkets.tsx
│   │   │   ├── AdminPortfolios.tsx
│   │   │   ├── AdminActivity.tsx
│   │   │   └── AdminSettings.tsx
│   ├── components/
│   │   ├── admin/AdminLayout.tsx  # Sidebar layout
│   │   └── ui/NotificationPanel.tsx
│   └── store/index.ts             # Zustand store with auth
├── server/
│   ├── models/        # User, Portfolio, Market, Activity
│   ├── controllers/   # Auth, Users, Markets, Portfolios, Admin
│   ├── routes/        # REST API routes
│   ├── middleware/    # JWT auth + admin guard
│   ├── seed.js        # Database seeder
│   └── index.js       # Express server
```

---

##  Routes

| Path                  | Description              |
|-----------------------|--------------------------|
| `/`                   | Home / Landing           |
| `/auth`               | Login & Register         |
| `/dashboard`          | User Dashboard           |
| `/markets`            | Live Markets             |
| `/portfolio`          | Portfolio Tracker        |
| `/ai`                 | AI Insights              |
| `/admin`              | Admin Dashboard          |
| `/admin/users`        | User Management          |
| `/admin/markets`      | Market Management        |
| `/admin/portfolios`   | Portfolio Management     |
| `/admin/activity`     | Activity Logs            |
| `/admin/settings`     | Platform Settings        |
