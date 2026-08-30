# Barker Digital Portal

Static site — no build step. Just commit and deploy as-is (Vercel, Netlify, anything that serves static files).

## One-time setup before it works

**Create yourself a login.** The portal is gated behind Supabase Auth so only you can see it.
1. Go to https://supabase.com/dashboard/project/faybcsknnbifjyqqiqej/auth/users
2. Click "Add user" → "Create new user"
3. Enter your email + a password, tick "Auto Confirm User"
4. That's it — no API keys, this is just your login for the portal itself.

The Supabase URL and public key are already embedded in `index.html` — they're safe to be public (that's what "publishable" key means), all the real protection is server-side via Row Level Security, which only lets logged-in requests touch the data.

## What's in here
- `index.html` — the whole app (login + overview + clients + projects + finances + tasks)
- `assets/` — your logo (black + cream versions)

## Database
Project: `portal-dashboard` in your Barker Digital Supabase org.
Tables: `clients`, `projects`, `finances`, `email_threads`, `project_tasks`.
`email_threads` is the table the Cowork automation will update — see the dashboard README for the scheduled task prompt.
