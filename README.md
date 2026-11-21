# Personal Finance Tracker

A free, KMyMoney-style personal finance tracker. Single self-contained HTML file — no build step, no server code in this repo.

## What to upload

Only one file is required:

- `index.html` — the whole tracker (accounts, transactions, categories, budgets, recurring items, reports, local profiles, and Cloud Sync)

Upload `index.html` to the root of your repo and commit it.

## Hosting

### GitHub Pages
1. Push `index.html` to your repo (root, on `main`).
2. Repo Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`.
3. Open the Pages URL it gives you.

### Netlify
Option A — drag and drop:
1. Put `index.html` in a folder by itself.
2. Drag that folder onto https://app.netlify.com/drop

Option B — connect the repo:
1. Netlify → Add new site → Import an existing project → pick this repo.
2. No build command, no publish directory change needed — publish directory is the repo root.
3. Deploy. Netlify will redeploy automatically on every push.

Yes, you can have this and the geo tool as two separate Netlify sites at the same time, even on the free plan.

## Saving your data

- By default, data saves in the browser (local storage) for the site you opened it on.
- Use **Backup & Download → Export backup** for a JSON copy, and Import to restore it on another device.
- For database sync, open the **Cloud Sync** tab in the app:
  1. Create a free project at https://supabase.com
  2. Copy-paste the SQL shown in that tab to create the `finance_tracker_data` table.
  3. Paste your Supabase Project URL + anon key into the Cloud Sync tab (stored only in your browser, never in this file).
  4. Use Test connection, then Push / Pull, or turn on Auto-sync.

Editing or re-uploading `index.html` does not delete data saved in Supabase. It also does not delete browser local storage on the same site — but a new URL, a cleared browser, or private browsing will, so keep a backup.
