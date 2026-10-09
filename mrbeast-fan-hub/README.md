# BeastMode — MrBeast Fan Hub

A playful, responsive, multi-page **unofficial fan project** inspired by challenge videos and community generosity. Not affiliated with or endorsed by MrBeast or his team.

## Features
- Three connected React routes: Home (`/`), Challenges (`/challenges`), Community (`/community`)
- Responsive mobile navigation, playful graphics, challenge cards, animated ticker
- Accessible form labels, validation, consent, loading and success/error states
- Supabase persistence, unique email constraint, Row Level Security
- Vite production build and Vercel deployment instructions

## Requirements
Node.js 18+ (20+ recommended), npm, and a Supabase project for real form persistence.

## Run locally
1. Extract the ZIP and open this folder in VS Code.
2. Run `npm install`.
3. Create a project at https://supabase.com/.
4. Open Supabase **SQL Editor** and run all of `supabase/schema.sql`.
5. Copy `.env.example` to `.env` in the project root and fill in:
   ```env
   VITE_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
   VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_OR_PUBLISHABLE_KEY
   ```
   Get the Project URL and browser-safe anon/publishable key from Supabase project settings. **Never put a service-role/secret key in frontend variables.**
6. Start the app with `npm run dev`; open the URL Vite prints (usually http://localhost:5173).

Without the environment variables, the site still runs, but the form will explain that backend configuration is missing rather than falsely claiming a signup was saved.

## Verify before submitting
- [ ] `npm install` completes.
- [ ] `npm run build` completes.
- [ ] Navigate Home → Challenges → Community.
- [ ] Direct-refresh `/challenges` and `/community`.
- [ ] Empty fields and invalid email are rejected.
- [ ] With Supabase configured, submit a signup and verify the row in Table Editor.
- [ ] Try a duplicate email and confirm duplicate handling.
- [ ] Check desktop and phone widths.

## Deploy to Vercel
1. Push the project to GitHub; do not commit `.env`.
2. Import the repo at https://vercel.com/.
3. Vite defaults: build command `npm run build`, output directory `dist`.
4. Add `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` under Vercel Project Settings → Environment Variables.
5. Redeploy and test the public URL and form.

## Database and privacy
RLS is enabled. Anonymous visitors may insert consented signup records but have no public read/update/delete policy. Email addresses are unique. The app stores signups; it does **not** send newsletter emails. For a real mailing list, add a privacy notice, retention policy, and a trusted email delivery service.

## Structure
```text
mrbeast-fan-hub/
├── index.html
├── package.json
├── vite.config.js
├── .env.example
├── README.md
├── src/ (main.jsx, App.jsx, styles.css, supabase.js)
└── supabase/schema.sql
```

## Design and branding
Yellow, blue and pink colors, bold type and graphic stickers create a playful original fan-site direction. Do not present this as an official MrBeast product or use protected logos/assets without permission.
