# Vaultfolio — Professional Portfolio Tracker

A customer-ready investment portfolio app with **login/signup**, **Supabase cloud storage**, and **AI investment advisor**.

## What's included

- **Landing page** (`/`) — professional marketing site
- **Login / Sign up** (`/login`, `/signup`) — secure Supabase auth
- **Dashboard** (`/dashboard`) — portfolio value, charts, holdings
- **Portfolio** (`/holdings`) — card-based holdings (no delete buttons — sell via Activity)
- **Activity** (`/transactions`) — buy/sell history
- **AI Advisor** (`/advisor`) — personalized suggestions
- **Add** (`/add`) — new holdings or transactions

## Setup

### 1. Install & env

```bash
npm install
```

`.env.local`:

```env
NEXT_PUBLIC_SUPABASE_URL=https://qvgweksqenmgytnwkcws.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-publishable-or-anon-key
```

### 2. Supabase database

Run `supabase/schema.sql` in **SQL Editor** (includes user accounts + RLS).

### 3. Enable auth in Supabase

1. **Authentication → Providers → Email** — enable Email
2. For quick testing: **Authentication → Providers → Email** → turn off **Confirm email**

### 4. Run

```bash
npm run dev
```

- Home: http://localhost:3000
- Sign up → Dashboard

## Deploy (Vercel)

Add the same env vars. Set **Site URL** in Supabase Auth to your Vercel domain.

## Design notes

- No trash/delete buttons on holdings — use **Activity → Sell** to close positions professionally
- Each user sees only their own data (Row Level Security)
- Optional `OPENAI_API_KEY` for enhanced AI tips
