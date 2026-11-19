# 🚛 LogixSense

**LogixSense** is a smart, AI-powered supply chain and logistics management platform built as a Progressive Web App (PWA). It enables logistics companies and drivers to track shipments in real time, detect route risks with AI, receive weather-based alerts, and monitor driver performance — all from a single, multilingual dashboard.

---

## ✨ Features

- 📦 **Shipment Management** — Create, track, and manage shipments with full CRUD support via a REST API
- 🤖 **AI Route Risk Analysis** — Integrates Groq (primary) and Gemini (fallback) APIs to analyze route risks and provide logistics insights
- 🌦️ **Real-Time Weather Alerts** — Fetches live weather data via OpenWeather API to flag weather-based route hazards
- 🗺️ **Route Optimization** — Calculates optimal routes, estimated delivery times, and time saved
- 🚨 **Disruption & Alert Tracking** — Live alerts for active route disruptions with risk scores and explanations
- 🛑 **SOS Emergency System** — Drivers can trigger SOS alerts that are logged and monitored in real time
- 📊 **Driver Scores & Trip Logs** — Tracks safety scores, eco-scores, CO₂ emissions, and fuel consumption per driver
- 🔔 **Notifications System** — In-app notifications for drivers and managers
- 🗄️ **Multi-Database Support** — Runs on Oracle DB, SQLite, or a zero-dependency embedded JSON engine (auto-detects)
- 🌍 **Multilingual UI** — Full i18n support: English, Tamil, Hindi, Kannada, Malayalam, Telugu
- 📱 **PWA / Offline Support** — Service worker for offline caching; installable on mobile devices
- 🔍 **Database Inspector** — Built-in `/api/db/tables` endpoint to inspect live table data

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML5, CSS3, JavaScript (Single-page App) |
| Backend | Node.js (built-in `http` module — zero framework) |
| AI Integration | Groq API (`groq/compound`), Google Gemini API (fallback) |
| Weather | OpenWeather API |
| Database | Oracle DB / SQLite / JSON engine (auto-fallback chain) |
| PWA | Web App Manifest, Service Worker |
| i18n | JSON locale files (en, ta, hi, kn, ml, te) |
| Deployment | Render, Netlify, Vercel, Firebase Hosting (configs included) |

---

## 📁 Folder Structure

```
LogixSense/
├── index.html              # Main SPA entry point (full app UI)
├── offline.html            # PWA offline fallback page
├── manifest.json           # PWA manifest
├── service-worker.js       # Service worker for offline caching
├── dev-server.js           # Node.js dev & production server
├── db.js                   # Database manager (Oracle / SQLite / JSON)
├── lang.js                 # i18n language switcher
├── seed.js                 # Demo data seeder
├── oracle_schema.sql       # Oracle DDL schema & seed data
├── logixsense_db.json      # Embedded JSON database store
├── .env.example            # Environment variable template
├── icons/                  # PWA app icons (SVG, 192px, 512px)
├── locales/                # i18n locale JSON files
│   ├── en.json
│   ├── ta.json
│   ├── hi.json
│   ├── kn.json
│   ├── ml.json
│   └── te.json
├── dist/                   # Production build output
├── render.yaml             # Render.com deployment config
├── vercel.json             # Vercel deployment config
├── firebase.json           # Firebase Hosting config
└── Procfile                # Heroku/Render process file
```

---

## 🚀 Installation & Running

### Prerequisites
- **Node.js** v18 or higher
- (Optional) Oracle DB or SQLite for production database usage

### 1. Clone the repository

```bash
git clone https://github.com/karthiban3333-maker/LogixSense.git
cd LogixSense
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

```bash
cp .env.example .env
```

Edit `.env` and fill in your API keys:

```env
GROQ_API_KEY=your_groq_api_key_here
OPENWEATHER_API_KEY=your_openweather_api_key_here
# PORT=8888  (optional, defaults to 8888)
```

> **API Keys (optional for demo):**
> - 🔑 Groq API key: [console.groq.com/keys](https://console.groq.com/keys)
> - 🌦️ OpenWeather API key: [openweathermap.org/api](https://openweathermap.org/api)
>
> Without keys, the app still runs with simulated AI responses and mock weather data.

### 4. Run the development server

```bash
npm run dev
```

Open your browser at **[http://localhost:8888](http://localhost:8888)**

The API endpoints are available at:
- `GET  /api/shipments` — List all shipments
- `GET  /api/alerts` — Active route alerts
- `GET  /api/stoppages` — Driver stoppages
- `GET  /api/driver-scores` — Driver performance scores
- `GET  /api/trip-logs` — Trip & CO₂ logs
- `POST /api/sos` — Trigger SOS emergency
- `POST /api/groq` — AI route analysis (Groq → Gemini fallback)
- `GET  /api/weather` — Real-time weather data
- `GET  /api/db/tables` — Database inspector

### 5. Deploy to Render (one-click)

```bash
# render.yaml is already configured — just connect your repo on render.com
```

---

## 🗄️ Database Configuration

LogixSense automatically selects the best available database engine:

| Priority | Engine | Config |
|---|---|---|
| 1 | **Oracle DB** | Set `USE_ORACLE=true`, `ORACLE_USER`, `ORACLE_PASSWORD`, `ORACLE_CONNECT_STRING` |
| 2 | **SQLite** | Install `npm install sqlite3` |
| 3 | **JSON Engine** | Zero setup — works out of the box (default) |

The Oracle schema is in [`oracle_schema.sql`](./oracle_schema.sql).

---

## 📸 Screenshots

> _Add screenshots here._

---

## 👤 Author

**Karthiban A** — [Kode Prime](https://github.com/karthiban3333-maker)

---

## 📄 License

This project is private. All rights reserved © 2026 Karthiban A — Kode Prime.
