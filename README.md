# RESET — Private Habit Tracker

A public-facing website with private, account-scoped habit records. No leaderboards, public profiles, public activity feeds, or shared habit records.

## Features
- Email/password sign-up and sign-in
- Daily check-ins: no porn, no masturbation, no smoking, exercise, study, sleep and hydration
- Private notes, streak count, logged-day count, monthly count and 30-day calendar
- Export your own records as JSON
- Responsive mobile-first interface

## Privacy architecture
Supabase Auth identifies each user. PostgreSQL Row Level Security (RLS) restricts every row to its owner using auth.uid() = user_id. The browser uses only the Supabase project URL and publishable/anon key. Never put a service-role or secret key in this repository. Review supabase/schema.sql before launch. No analytics or advertising scripts are included.

## Setup — phone only
1. Create a free project at https://supabase.com/dashboard.
2. In Supabase, open SQL Editor, paste all of supabase/schema.sql and run it.
3. Open Project Settings → API (or API Keys). Copy the Project URL and publishable/anon public key.
4. In this GitHub repository, open config.js, tap the pencil icon, replace YOUR_SUPABASE_PROJECT_URL and YOUR_SUPABASE_ANON_KEY, then commit.
5. In Supabase Authentication → URL Configuration, set Site URL to https://s-hasil.github.io/reset-habit-tracker/ and add the same URL to Redirect URLs.
6. In GitHub, open Settings → Pages, choose Deploy from a branch, select main and /(root), then Save. Wait for deployment. The website address will be https://s-hasil.github.io/reset-habit-tracker/.

## Important
- Do not turn off RLS or create permissive public policies.
- Never share your Supabase password or service-role/secret key.
- Email confirmation may be enabled by default; users must confirm their email if required.
- Anyone can inspect the website source and public client configuration. They cannot read another user's habit records when the RLS policies are correctly installed.
- This starter has not undergone an independent security audit. Review security settings before collecting sensitive information at scale.
