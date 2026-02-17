# 💇‍♀️ Salon & Spa Enterprise Booking System (INR)

Production-ready full-stack salon management system built with:

-   Next.js 14 (App Router)
-   Supabase (PostgreSQL + Auth + RLS)
-   Stripe (INR Payments)
-   SendGrid (Email Notifications)
-   Vercel Deployment Ready

------------------------------------------------------------------------

# 🚀 Features

## 👤 Customer

-   Register & Login
-   Browse Services
-   Book Appointments
-   Secure Stripe Payment (INR)
-   Booking Confirmation

## 👨‍💼 Staff

-   View Assigned Appointments
-   Manage Availability (extendable)

## 🛠 Admin

-   Add/Edit Services
-   Manage Staff
-   Manage Business Settings

## 🔒 Security

-   Supabase Authentication
-   Row Level Security (RLS)
-   Role-based access
-   Stripe Webhook verification

------------------------------------------------------------------------

# 🏗 Tech Stack

  Layer            Technology
  ---------------- ---------------------
  Frontend         Next.js 14
  Backend          Next.js API Routes
  Database         Supabase PostgreSQL
  Authentication   Supabase Auth
  Payments         Stripe (INR)
  Email            SendGrid
  Deployment       Vercel

------------------------------------------------------------------------

# ⚙️ Installation

## 1️⃣ Install Dependencies

``` bash
npm install
```

## 2️⃣ Configure Environment Variables

Rename `.env.example` → `.env.local`

Fill in:

    NEXT_PUBLIC_SUPABASE_URL=
    NEXT_PUBLIC_SUPABASE_ANON_KEY=
    SUPABASE_SERVICE_ROLE_KEY=

    STRIPE_SECRET_KEY=
    NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=
    STRIPE_WEBHOOK_SECRET=

    SENDGRID_API_KEY=
    NEXT_PUBLIC_SITE_URL=http://localhost:3000

------------------------------------------------------------------------

# 🗄 Supabase Setup

Run inside SQL Editor:

``` sql
create table profiles (
  id uuid primary key references auth.users(id),
  role text default 'customer',
  full_name text,
  created_at timestamp default now()
);
```

Enable RLS:

``` sql
alter table profiles enable row level security;
```

------------------------------------------------------------------------

# 💳 Stripe Setup (INR)

1.  Enable INR in Stripe dashboard
2.  Add webhook endpoint: https://yourdomain.com/api/webhook
3.  Listen for: checkout.session.completed

------------------------------------------------------------------------

# 🧪 Run Locally

``` bash
npm run dev
```

Visit: http://localhost:3000

------------------------------------------------------------------------

# 🌍 Deploy to Vercel

1.  Push to GitHub
2.  Import into Vercel
3.  Add Environment Variables
4.  Configure Stripe Webhook

------------------------------------------------------------------------

# 📈 Production Enhancements

-   Advanced RBAC policies
-   Availability time slot engine
-   Booking reminders
-   Refund & cancellation module
-   Admin analytics dashboard

------------------------------------------------------------------------

Built for scalable, production-ready salon operations 🚀
