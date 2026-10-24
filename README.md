# 🏥 CareNow Health — Chandigarh Tricity

**Healthcare & Live Queue Tracker for Chandigarh, Mohali and Panchkula**

CareNow Health is a single-page web app that helps people in the Chandigarh Tricity find the right hospital or clinic, check live OPD queues, get sequential token slips, and issue emergency casualty tokens, all from a phone-friendly interface.

🔗 **Live Demo:** https://endrift894.github.io/Carenow/
---

## ✨ Features

### 🩺 OPD Queues & Sequential Slips
- Live queue tracking with **"Now Serving #N"** counters
- **Sequential OPD token slips** (#1, #2, #3…) by department
- **Printable / downloadable slips** (Print or Save as PDF, or download as HTML)
- Crowd-sourced **"Report live queue"** form (people in line, line speed)
- **"Report false claim"** option so wrong data can be flagged and audited
- Auto-cleanup of stale data after 24 hours

### 📍 Near Me (within 10 km)
- Uses browser geolocation and the **Haversine formula** to sort facilities by distance
- Filters for nearby hospitals and clinics

### 🚑 Emergency Casualty Triage
- Instant **emergency token** (Priority 1 – Trauma to Priority 3)
- 24x7 trauma centers: PGIMER, GMCH-32, Fortis, Max, AIMS Mohali and more
- **1-tap SOS** for **108 (Ambulance)** and **112 (Unified Emergency)**
- Printable pre-alert triage slip with patient details, ETA and chief complaint

### 🏢 Facility Directory
- **30+ facilities** across Govt hospitals, private hospitals and evening clinics
- Timings, fees, contact numbers, doctor lists with speciality and hours
- Category ribbons (Govt / Private / Clinic)

### ☁️ Live Sync
- **Supabase** backend for token storage and real-time updates
- Automatic **localStorage fallback** if Supabase is unavailable
- Mobile bottom navigation bar with large touch targets for stressful situations

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript (single file, no build step) |
| Backend / DB | [Supabase](https://supabase.com) (Postgres + Realtime) |
| Storage fallback | Browser `localStorage` |
| Location | Browser Geolocation API + Haversine distance |
| Printing | `window.print()` via hidden iframe |

---

## 🚀 Getting Started

No installation needed.

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

# 2. Open the app
# Just open index.html in your browser
# or serve it locally:
npx serve .
```

### Optional: connect your own Supabase

1. Create a project at [supabase.com](https://supabase.com)
2. Create these tables:

   **`emergency_tokens`**
   `token_id, hospital_name, patient_name, patient_phone, severity, chief_complaint, arrival_eta, created_at`

   **`visitor_logs`**
   `visitor_name, page_visited, created_at`

3. In `index.html`, replace the values of `SUPABASE_URL` and `SUPABASE_ANON_KEY` with your own.
4. Enable Realtime on the `emergency_tokens` table.

> 🔒 Only ever use the **anon/public** key in frontend code, and turn on Row Level Security (RLS) policies on your tables.

---

## 📁 Project Structure

```
.
├── index.html      # Entire app (HTML + CSS + JS)
└── README.md
```

---

## 📱 Screens

_Add screenshots here:_

| Home Gateway | OPD Radar | Emergency Token |
|---|---|---|
| ![home](screenshots/home.png) | ![opd](screenshots/opd.png) | ![emergency](screenshots/emergency.png) |

---

## ⚠️ Disclaimer

This is a community/demo project. Queue numbers, timings and fees may be crowd-sourced or approximate and may not reflect real-time hospital data. **In a medical emergency, always call 108 or 112 immediately.** This app does not replace professional medical advice.

---

## 🗺️ Roadmap

- [ ] Real hospital API integrations for official queue data
- [ ] Hindi / Punjabi language support
- [ ] PWA support (installable, offline mode)
- [ ] More facilities across the Tricity
- [ ] Admin dashboard for hospitals to update queues

---

## 🤝 Contributing

Pull requests are welcome! To add or correct a facility, edit the `places` array in `index.html` and open a PR.

## 📄 License

MIT License. Free to use and modify. _(Change this if you prefer another license.)_

## 👤 Author

**Endrift** — [GitHub](https://github.com/your-username)
