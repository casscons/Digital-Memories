# Digital Memories Edmonton
### *Their faces still want to be seen, their voices still want to be heard.*

**digitalmemories.ca** · Professional VHS, 8mm Film & Tape Digitization · Edmonton & Red Deer, Alberta

---

## About This Site

This is the complete single-file website for **Digital Memories Edmonton** — a full-featured business web application built as one self-contained `index.html` file. No frameworks, no build tools, no server required. Upload and go.

---

## What's Inside

### Customer Features
- **Instant Quote** — customer snaps a photo of their tapes; AI identifies and counts every item and builds a side-by-side Standard vs Premium quote in seconds
- **Manual Entry** — +/− counter for each media type if camera isn't available
- **3-Decision Quote Flow** — Accept (logs job immediately), Think About It (saves quote, texts reminder in 1 week), or No Thanks (clean exit, nothing stored)
- **Booking Workflow** — 6-step guided process: delivery method → package → scheduling → customer details → review → payment
- **Scheduling** — customers propose 3 preferred pickup/drop-off dates and times; staff confirms one
- **Check My Progress** — customers look up their order by first name + phone number; see every tape and reel as its own checkbox with real-time completion status
- **Get My Files** — password-protected digital download section; Google Drive link with 30-day expiry from payment date
- **Live AI Chat** — 24/7 assistant powered by Claude API; knows all pricing, formats, policies, and speaks plainly for senior customers
- **Services, Pricing, Contact** tabs with full service descriptions and transparent pricing

### Staff Features (Password Protected)
- **Staff Login** — Rene and Jack each have separate logins; passwords changeable in-panel
- **Order Dashboard** — all bookings listed with status badges
- **Intake Photo** — staff photographs received items; AI auto-generates the work order checklist from the photo
- **Work Order Checklist** — one checkbox per individual tape/reel; checking them off updates the customer's progress page in real-time
- **Schedule Confirmation** — staff clicks one of the customer's 3 proposed times to confirm it; customer sees confirmation immediately
- **Payment Confirmation** — logs e-transfer reference or Square transaction number
- **Digital Download Setup** — staff pastes Google Drive sharing URL + sets customer password; 30-day timer starts automatically
- **Staff Notes** — any note added is visible to the customer on their progress page
- **Receipt Generation** — printable official receipt generated on payment confirmation

### Business Details Baked In
- **Edmonton drop-off / pickup:** 6535 – 168 Avenue NW, Edmonton, AB T5Y 3X9
- **Red Deer drop-off:** 11 Dobler Avenue, Red Deer, AB T4R 1X6
- **E-transfer:** hello@digitalmemories.ca (auto-deposit enabled)
- **Phone:** (780) 555-0192
- **Rush orders:** +25% surcharge, 48hr turnaround
- **Senior discount:** 10% off any order

---

## Pricing Model (Jeet Video Edmonton Aligned)

| Format | Standard | Premium |
|--------|----------|---------|
| VHS / S-VHS / Betamax | $35/tape | $45/tape |
| Hi8 / Video8 / Digital8 | $32/tape | $42/tape |
| MiniDV / DVCAM | $28/tape | $36/tape |
| 8mm / Super 8 reel | $37/reel | $52/reel |
| 16mm film reel | $60/reel | $80/reel |
| Audio cassette | $20/tape | $28/tape |
| Reel-to-reel audio | $50/reel | $65/reel |
| Film cleaning (one-time) | $15 | Included |
| USB drive | $15 optional | Included |
| Pickup + return delivery | $25 + $25 | $25 + $25 |
| Rush (48hr) | +25% | +25% |

---

## Deployment

### This repo → digitalmemories.ca

This site lives at `github.com/casscons/Digital-Memories` and is served via GitHub Pages.

**To publish or update:**

1. Upload/replace `index.html` in this repo (drag and drop on the main repo page)
2. Also upload `README.md` (this file) and `CNAME`

**To enable GitHub Pages (first time only):**
1. Go to **Settings → Pages**
2. Under **Branch** → change from `None` to `main` → click **Save**
3. The **Custom domain** field will appear → type `digitalmemories.ca` → Save

**DNS setup at your domain registrar:**

Add these 4 A records pointing to GitHub Pages:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
And a CNAME record: `www` → `casscons.github.io`

GitHub will automatically create the `CNAME` file in this repo when you save the custom domain in Settings.

---

## Files in This Repo

| File | Purpose |
|------|---------|
| `index.html` | The entire website — all HTML, CSS, and JavaScript in one file |
| `README.md` | This file |
| `CNAME` | Contains `digitalmemories.ca` — tells GitHub Pages which domain to serve |

---

## Staff Login

Access via the **Staff Login** link in the footer, or click the logo 5 times quickly.

| Username | Default Password | Role |
|----------|-----------------|------|
| Rene | Rene | Owner |
| Jack | Jack | Staff |

Passwords can be changed inside the Staff Panel under **My Settings**. Changes persist in the browser's local storage.

---

## AI & Data

- **Quote photo analysis** — Claude API (claude-sonnet-4) identifies media types from customer photos
- **Intake photo analysis** — Claude API creates the work order checklist from the staff intake photo
- **Live chat** — Claude API with full pricing, services, and brand voice baked into the system prompt
- **Order storage** — browser `window.storage` (persistent key-value store provided by the Claude.ai artifact environment). Orders are stored as `booking:{ref}` keys.
- **No backend required** — everything runs client-side

> **Note:** Order data persists in the browser storage of whoever is viewing the site. For a production deployment, replace `window.storage` calls with a proper backend (Supabase, Firebase, etc.) so all staff share the same order data.

---

## Updating Content

All editable content is in `index.html`. Key locations:

| What to change | Search for |
|----------------|------------|
| Phone number | `(780) 555-0192` |
| Email address | `hello@digitalmemories.ca` |
| Edmonton address | `6535 – 168 Avenue NW` |
| Red Deer address | `11 Dobler Avenue` |
| Pricing | `CFG.PRICES` in the `<script>` section |
| Staff passwords (reset) | `DEFAULT_USERS` in the `<script>` section |
| Chat system prompt | `CHAT_SYS` variable in the `<script>` section |
| AI API model | `claude-sonnet-4-20250514` |

---

## Two Websites, One GitHub Account

| Site | Repo | Live URL |
|------|------|----------|
| CASS Consulting Group | `casscons/casscons.github.io` | casscons.github.io |
| Digital Memories | `casscons/Digital-Memories` | digitalmemories.ca |

Both run from the same `casscons` GitHub account. No extra accounts needed.

---

*Built for Digital Memories Edmonton · © 2025*
