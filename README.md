# 🚚 LogixSense — Smart Supply Chain & Logistics Command Center

> **AI-powered supply chain command center and driver companion PWA providing real-time shipment tracking, predictive route risk detection, and weather hazard mitigation.**

LogixSense is an intelligent logistics and freight management platform built as an installable Progressive Web App (PWA). It bridges fleet operators, dispatch managers, and long-haul drivers on a single multilingual dashboard — optimizing delivery schedules, analyzing road disruption risks with LLMs, monitoring live weather hazards, and tracking driver safety and sustainability metrics.

---

## 📖 About the Project

### 🎯 Problem Statement
Commercial freight networks face rampant supply chain bottlenecks due to unexpected transit delays, sudden severe weather disruptions, sub-optimal routing, and fragmented communication between drivers and depot managers. Most fleet management systems require expensive proprietary telematics hardware and lack intelligent, predictive risk forecasting.

### 💡 The Solution
LogixSense provides an accessible, hardware-free Progressive Web App operating across mobile and desktop. Powered by Groq and Google Gemini AI, it evaluates active shipment routes against live weather telemetry, calculates estimated delay risks, recommends alternative routes, and tracks driver safety and carbon footprints. With automatic multi-database failover (Oracle DB, SQLite, or local JSON) and complete offline capabilities, logistics operations remain resilient anywhere.

### 🌟 Core Value Proposition
- **Predictive AI Route Risk Intelligence**: Real-time risk scoring and mitigation advice evaluating road disruptions and live weather hazards.
- **Hardware-Free PWA Deployment**: Works on any smartphone or tablet with service workers and offline caching.
- **Multilingual Driver Inclusivity**: Native interface support for 6 regional Indian languages (English, Tamil, Hindi, Kannada, Malayalam, Telugu).
- **Flexible Database Architecture**: Auto-detects and seamlessly adapts to Oracle Enterprise DB, local SQLite, or lightweight zero-dependency JSON.

---

## ✨ Features

- 📦 **Shipment Management** — End-to-end shipment lifecycle tracking (Pending, In Transit, Delivered, Delayed) with full CRUD REST APIs.
- 🤖 **AI Route Risk Analysis** — Evaluates route waypoints using Groq LLM (with Gemini fallback) to produce real-time hazard assessments and time-saved metrics.
- 🌦️ **Real-Time Weather Alerts** — Live OpenWeather telemetry integration flagging thunderstorms, heavy precipitation, and visibility hazards.
- 🗺️ **Interactive Route Optimization** — Visual route mapping, waypoint inspection, and dynamic detour recommendations.
- 🛑 **SOS Emergency System** — Immediate driver panic trigger logging instant distress alerts for fleet operations dispatch.
- 📊 **Driver Safety & Eco-Scoring** — Calculates safety compliance scores, eco-efficiency ratings, fuel economy, and estimated CO₂ emissions.
- 🌐 **Multilingual UI (i18n)** — Full localization across English, Tamil, Hindi, Kannada, Malayalam, and Telugu.
- 📱 **Progressive Web App (PWA)** — Offline service worker caching, installable on Android and iOS devices.
- 🗄️ **Multi-Database Auto-Fallback** — Autonomous connection hierarchy: Oracle DB → SQLite → Zero-dependency JSON storage engine.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend Framework** | Vanilla HTML5, Modern CSS3, JavaScript (SPA architecture) |
| **PWA & Offline** | Web App Manifest, Service Worker caching, Offline fallback |
| **Backend Runtime** | Node.js (Zero-dependency built-in `http` server) |
| **AI Integration** | Groq API (`llama-3.3-70b-versatile`) + Google Gemini API |
| **Weather Telemetry** | OpenWeatherMap REST API |
| **Databases** | Oracle DB / SQLite3 / Embedded JSON engine (Auto-detect) |
| **Internationalization** | Custom client-side i18n engine (`locales/*.json`) |

---

## 📁 Folder Structure

```
LogixSense/
├── dist/                       # Static build and bundled resources
├── icons/                      # PWA icons and logos
├── lang/                       # Legacy translation dictionaries
├── locales/                    # Modular JSON locale definitions (en, ta, hi, kn, ml, te)
├── db.js                       # Multi-database abstraction layer (Oracle, SQLite, JSON)
├── dev-server.js               # Lightweight Node.js HTTP server & API router
├── index.html                  # Main single-page application dashboard
├── lang.js                     # Client-side i18n localization engine
├── logixsense_db.json          # Embedded JSON database
├── manifest.json               # Progressive Web App manifest
├── oracle_schema.sql           # Oracle database enterprise DDL schema
├── package.json                # Project scripts
├── seed.js                     # Database seeding utility
├── service-worker.js           # PWA offline asset caching worker
└── README.md                   # Project documentation
```

---

## 🚀 How to Install and Run

### Prerequisites
- [Node.js](https://nodejs.org/) (v18+)

### 1. Clone the Repository
```bash
git clone https://github.com/karthiban3333-maker/LogixSense.git
cd LogixSense
```

### 2. Configure Environment Variables
Copy `.env.example` to `.env`:
```bash
cp .env.example .env
```
Provide your Groq, Gemini, or OpenWeather credentials (optional; runs in demo mode out of the box).

### 3. Start the Server
```bash
npm start
```
Open `http://localhost:3000` in your browser.

---

## 📸 Screenshots

> _Add screenshots here._

---

## 📄 License

This project is private. All rights reserved © 2026 Karthiban A — Kode Prime.

---

## 👨‍💻 Author

**Karthiban A** — [Kode Prime](https://github.com/karthiban3333-maker)
