# PGB HR Dashboard

PGB Group Human Resource Information System — single-file HR Dashboard with role-based access, encoder tabs, AI-generated insights, and live data flow to executive views.

## Stack
- **Frontend**: Single-file HTML/JS (no framework)
- **API Proxy**: Vercel Serverless Function (`/api/claude.js`)
- **AI**: Anthropic Claude Sonnet (Risk, Trends, Actions tabs)
- **Hosting**: Vercel

## Project Structure
```
pgb-hr-dashboard/
├── public/
│   └── index.html        # Full dashboard (318KB)
├── api/
│   └── claude.js         # Anthropic API proxy
├── vercel.json           # Routing config
└── package.json
```

## Deployment

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Initial deploy"
git remote add origin https://github.com/YOUR_USERNAME/pgb-hr-dashboard.git
git push -u origin main
```

### 2. Connect to Vercel
1. Go to [vercel.com](https://vercel.com) → **Add New Project**
2. Import your GitHub repo `pgb-hr-dashboard`
3. Framework: **Other** — no changes needed
4. Click **Deploy**

### 3. Set Environment Variables
In Vercel dashboard → **Settings → Environment Variables**:

| Key | Value |
|-----|-------|
| `ANTHROPIC_API_KEY` | `sk-ant-...` |
| `DASHBOARD_SECRET` | `PGB-DASH-2026` |

Then **Redeploy** from the Vercel dashboard.

## Access / Passcodes

| Role | Passcode |
|------|----------|
| CHRO | *(no passcode)* |
| HR Executive / Strategic Partner | `view123` |
| HR Business Partner | `approve123` |
| HR Operations / CoE / SD / OH&W | `encode123` |

> Change passcodes in `public/index.html` under the `const ROLES = {...}` block before deploying.

## AI Features
The **Risk & Mitigations**, **Trends & Patterns**, and **Actionable Items** tabs generate AI analysis by clicking **✦ Generate**. This calls `/api/claude` which proxies to Anthropic — the API key is never exposed to the browser.
