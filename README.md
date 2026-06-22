# PGB HR Dashboard

**PGB Group Human Resource Information System**  
Single-file HR dashboard with role-based access, monthly report encoding, EOS monitoring, and AI-generated insights.

---

## Live URL

```
https://jeiare01-lab.github.io/pgb-hr-dashboard/
```

---

## Stack

| Layer | Technology |
|---|---|
| Frontend | Single-file HTML/JS — no framework |
| Data | In-memory (encoded directly in the browser) |
| AI | Anthropic Claude Sonnet (browser-direct) |
| Hosting | GitHub Pages |
| Backend | None required |

---

## File Structure

```
pgb-hr-dashboard/
└── public/
    └── index.html    ← entire app (HTML + CSS + JS, ~320KB)
```

---

## Setup

### 1. Add your API key
Open `public/index.html` and find this line near the bottom of the `<script>` block:

```js
const ANTHROPIC_KEY = 'PASTE_YOUR_KEY_HERE';
```

Replace with your Anthropic API key (`sk-ant-...`).

### 2. Enable GitHub Pages
Go to **Settings → Pages**
- Source: Deploy from a branch
- Branch: `main`
- Folder: `/public`
- Save

### 3. Access the dashboard
Navigate to your GitHub Pages URL. The dashboard loads immediately — no server, no database.

---

## Access / Passcodes

| Role | Passcode | Access Level |
|---|---|---|
| CHRO | *(no passcode)* | Full executive view |
| HR Executive | `view123` | Full executive view |
| HR Strategic Partner | `view123` | Full executive view |
| HR Business Partner | `approve123` | Executive + SBU monitoring |
| HR Operations / CoE / SD / OH&W | `encode123` | Encoder tabs |

> To change passcodes, edit the `const ROLES = {...}` block in `index.html`.

---

## Tab Overview

### Viewer Tabs (Executive access)
| Tab | Description |
|---|---|
| Executive Summary | Live-scraped KPIs from all encoder tabs |
| HR EOS Monitoring | Q2 2026 Rocks with interactive status tracking |
| Data Analysis & Rec. | Deep analysis mirroring Executive Summary |
| Risk & Mitigations | ✦ AI-generated risk register |
| Trends & Patterns | ✦ AI-detected patterns + static charts |
| Actionable Items | ✦ AI-generated priority action plan |
| SBU Monitoring | Per-SBU workforce snapshots |

### Encoder Tabs (Operations access)
| Tab | Description |
|---|---|
| HR Operations | Headcount, diversity, attrition, PRF — May 2026 |
| Centre of Excellence | EE report, wellness, L&D — Jan–Jun 2026 |
| Service Delivery | Timekeeping, tardiness, benefits, SD concerns — May 2026 |
| Health & Wellbeing | Medical insurance, OPD, WRA, illnesses — April 2026 |

---

## AI Features

The **Risk & Mitigations**, **Trends & Patterns**, and **Actionable Items** tabs use Claude Sonnet to generate analysis from live encoded data.

- Click **✦ Generate** on any of the three tabs
- AI reads all encoded data across all tabs in real time
- Results render as structured HTML with colored cards
- Click **↻ Regenerate** to refresh with latest data

> AI calls go directly from the browser to `api.anthropic.com`. The API key is embedded in the HTML — keep the repo **private**.

---

## Monthly Update Workflow

Each month:
1. Log in as **HR Operations / CoE / SD / OH&W** (`encode123`)
2. Update data in the four encoder tabs
3. Switch to Executive Summary → click **↻ Refresh**
4. Navigate to Risk / Trends / Actions → click **✦ Generate**
5. Share the GitHub Pages URL with the CHRO and HR Executive team

---

## Report Period

| Tab | Current Data |
|---|---|
| HR Operations | May 2026 |
| Centre of Excellence | Jan–Jun 2026 |
| Service Delivery | May 2026 |
| Health & Wellbeing | April 2026 |

---

*Built for PGB Group · Central Visayas, Philippines · 2026*
