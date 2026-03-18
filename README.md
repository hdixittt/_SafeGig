# SafeGig — AI-Powered Parametric Income Insurance for India's Gig Workers

> Guidewire DEVTrails 2026 Hackathon | Team: Codestorm

SafeGig protects India's gig delivery workers (Zepto, Blinkit, Swiggy Instamart) from income loss caused by external disruptions — extreme weather, pollution spikes, or local strikes — using parametric triggers and AI automation for instant payouts without claim filing.

---

## Problem Statement

India's hyperlocal delivery ecosystem powers 10-minute grocery delivery, but gig workers face severe income volatility:

| Event | Income Loss |
|---|---|
| Monsoon disruption | ₹1500 – ₹3600/week |
| Heatwave | Lost afternoon working hours |
| Pollution spike | Reduced deliveries |
| Local strike | Entire shift lost |

No insurance product currently protects daily gig income.

---

## Solution

SafeGig provides AI-powered parametric income insurance:
- Weekly micro-insurance premiums
- Automatic disruption detection
- AI-based fraud prevention
- Instant payout simulation
- Worker-friendly dashboard

**No paperwork. No claim forms. No waiting.**

---

## Risk Tiers & Premiums

| Risk Tier | Weekly Premium | Coverage |
|---|---|---|
| Low | ₹29 | ₹800 |
| Standard | ₹49 | ₹1500 |
| High | ₹79 | ₹2500 |
| Premium | ₹89 | ₹3500 |

---

## Parametric Triggers

| Trigger | Condition | Data Source |
|---|---|---|
| Heavy Rain | Rainfall > 50 mm/hr | Weather API |
| Extreme Heat | Temperature > 42°C | Weather API |
| Severe Pollution | AQI > 300 | AQI API |
| Curfew / Strike | Zone restricted | News / Mock API |

---

## Tech Stack

**Frontend:** React.js, Tailwind CSS, Chart.js, Axios  
**Backend:** Node.js + Express, JWT Auth  
**ML Service:** Python FastAPI, XGBoost, Isolation Forest, Gemini API  
**Infra:** Supabase, Vercel, Render, GitHub Actions

---

## How to Run

```bash
git clone https://github.com/your-repo/safegig.git
cd safegig
```

**Backend:**
```bash
cd backend
npm install
npm start
```

**ML Service:**
```bash
cd ml-service
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

---

## Demo Flow

1. Worker registers
2. AI calculates weekly premium
3. Policy activated
4. Admin triggers disruption (rain/heat/AQI)
5. Fraud detection runs
6. Payout automatically generated
7. Dashboard updates claim status

---

## Team Codestorm — Guidewire DEVTrails 2026

*Built with the vision of protecting the workers who keep India's cities running — one delivery at a time.*
