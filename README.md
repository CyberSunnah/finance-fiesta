# Personal Finance Tracker

A free, KMyMoney-style personal finance tracker. Single self-contained HTML file — no build step, no server code in this repo.

## What is in this repo

- `index.html` — the whole tracker (accounts, transactions, categories, budgets, recurring items, reports, local profiles, Cloud Sync, and Forecast)
- `README.md` — this file

## Features

- Accounts (chequing, savings, credit cards, cash, investments, loans) with live balances and net worth
- Transaction ledger with categories, cleared/pending flags, search and account/month filters
- Transfers between accounts
- Monthly budgets with progress bars
- Recurring transactions with one-tap posting
- Reports with a six-month cash-flow chart, plus CSV export
- Local profiles (e.g. Household, Side business), each with its own data — saved automatically in the browser
- **Forecast tab:** balance projection for a timeframe you pick (30/60/90 days, 6 or 12 months, or custom dates), and a pay-to-pay view showing every recurring expense between this payday and the next, the total spoken for, and what is left over
- **Cloud Sync tab:** Supabase sync, so data lives in a database separate from this file

## Saving your data

- By default, data saves in the browser (local storage) for the site you opened it on.
- Use **Backup & Download → Export backup** for a JSON copy, and Import to restore it on another device.
- For database sync, open the **Cloud Sync** tab in the app. It has the SQL to create the `finance_tracker_data` table, and fields for your Supabase Project URL + publishable (anon) key.
- This copy of `index.html` has the Supabase Project URL and publishable key baked in near the top of the file (`BAKED_SUPABASE_URL` / `BAKED_SUPABASE_KEY`), so any browser that opens the site connects automatically, with auto-sync on. Never put the secret / service_role key in this file.
- Editing or re-uploading `index.html` does not delete data saved in Supabase. It also does not delete browser local storage on the same site — but a new URL, a cleared browser, or private browsing will, so keep a backup.

## Hosting

### Netlify Drop (simplest, free, no repo connection needed)
1. Put `index.html` in a folder by itself.
2. Drag that folder onto https://app.netlify.com/drop
3. Re-drag the folder whenever this file is updated.

### Netlify, Git-connected
1. Netlify → Add new site → Import an existing project → GitHub → pick this repo.
2. No build command, publish directory is the repo root.
3. Netlify redeploys automatically on every push to `main`.

Note: on Netlify's free plan, Git-connected deploys from a private repo can be restricted — that is why this repo is currently public. If you make it private again, use Netlify Drop instead, or another free host that allows private repos (e.g. Cloudflare Pages).

### GitHub Pages
1. Push `index.html` to the repo root on `main`.
2. Repo Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`.
3. Open the Pages URL it gives you.
