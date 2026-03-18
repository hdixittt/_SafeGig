# SafeGig

AI-powered parametric income insurance for India's gig delivery workers.

Guidewire DEVTrails 2026 Hackathon. Team Codestorm. Persona: Grocery and Q-Commerce delivery partners on Zepto and Blinkit.

## The Problem

India's 10-minute delivery ecosystem runs on the backs of gig workers. These workers earn ₹500 to ₹900 a day, operating entirely outdoors with zero income protection. When external disruptions strike — a flash flood, a heatwave, severe pollution, or a sudden curfew — they simply stop earning. No recourse. No safety net. No fallback.

A Blinkit delivery partner in Chennai can lose 3 to 4 working days during a single monsoon week. That's ₹1,500 to ₹3,600 gone, with no way to recover it.

SafeGig exists to fix that.

## What SafeGig Does

SafeGig is an AI-enabled parametric income insurance platform built exclusively for grocery and Q-commerce delivery partners on Zepto, Blinkit, and Swiggy Instamart.

Workers pay a small weekly premium based on their risk profile. When a disruption hits their zone — heavy rain, extreme heat, hazardous AQI, or a curfew — the system detects it automatically, runs fraud checks, and triggers a payout. No claim forms. No waiting periods. No ambiguity. When a trigger fires, SafeGig pays.

## Who It's Built For

The typical SafeGig user earns ₹600 to ₹900 a day and works 8 to 12 hours, 6 to 7 days a week. They operate in hyperlocal urban pockets across Mumbai, Bengaluru, Delhi, and Hyderabad. Their biggest risks are heavy rain, extreme heat, AQI spikes, and local curfews or strikes. They prefer weekly micro-payments over monthly premiums and pay via UPI.

## Real Scenarios

Ravi is a Blinkit partner in Andheri, Mumbai. Rainfall hits 65mm per hour. SafeGig's weather trigger fires automatically. Ravi gets a notification: "You're covered today. ₹450 payout initiated." He doesn't file anything. He just gets paid.

Priya operates in Dwarka, Delhi. The temperature hits 45°C, past SafeGig's 42°C threshold. The system detects her active policy, validates her zone, and auto-initiates a partial payout for lost afternoon hours.

Later in November, AQI crosses 300 in Priya's zone. SafeGig triggers a pollution disruption payout. Fraud detection confirms her GPS was stationary in her home zone during peak hours. Payout approved instantly.

In Bengaluru, a sudden strike closes access roads to a Zepto dark store. SafeGig's social disruption module flags the zone as impacted. All active partners in that pin code receive automated coverage.

## How It Works

A worker registers and the AI computes their weekly premium based on their city, pin code, platform, and weekly hours. They activate a policy. Real-time monitoring begins. When a parametric trigger fires in their zone, the AI fraud check runs and the claim is auto-approved. The payout hits their UPI within minutes. Their dashboard updates with the claim status.

## Weekly Premium Tiers

Low risk workers pay ₹29 per week for up to ₹800 in coverage. Standard risk is ₹49 per week for up to ₹1,500. High risk is ₹79 per week for up to ₹2,500. Premium tier is ₹89 per week for up to ₹3,500 in coverage.

Premiums are calculated fresh each week using a risk score based on the worker's pin code risk history, how often that zone has triggered claims in the past 6 months, their average weekly active hours, the current season, and the baseline AQI for their delivery zone.

## Parametric Triggers

Heavy rainfall above 50mm per hour triggers a payout of 60 to 100 percent of daily covered income. Extreme heat above 42°C triggers 40 to 70 percent. Severe pollution with AQI above 300 triggers 50 to 80 percent. A curfew or strike flagging a zone as inaccessible triggers 80 to 100 percent.

Coverage is strictly for loss of income. SafeGig does not cover health, life, accidents, or vehicle repair.

## AI and ML

The weekly premium is calculated by a Gradient Boosted Regressor trained on pin code risk scores, seasonal factors, platform tenure, and historical claim frequency. It runs as a Python FastAPI microservice called by the backend every Monday at policy renewal.

Fraud detection uses an Isolation Forest model that monitors GPS location during claimed disruptions, activity pattern anomalies, duplicate claim attempts, and claim velocity. A fraud score above 0.75 flags the claim for manual review. Below that, it auto-approves.

Claim summaries are generated using the Google Gemini API, producing plain-language notifications in Hindi or English. For example: "Your claim for ₹450 has been approved. Heavy rainfall of 67mm per hour was recorded in your zone on 14 July between 10am and 4pm. Payout will reach your UPI in 2 minutes."

## Tech Stack

The frontend is React with Vite, Tailwind CSS, and Framer Motion. The backend is Node.js with Express and Supabase for the database and auth. The ML service is Python FastAPI with scikit-learn and XGBoost. External APIs used are OpenWeatherMap for weather triggers, AQICN for pollution monitoring, Razorpay in sandbox mode for payout simulation, and Google Gemini for NLP summaries.

## How to Run

Clone the repo and copy `.env.example` to `backend/.env`, then fill in your Supabase credentials.

Start the backend:

```
cd backend
npm install
node src/index.js
```

Start the frontend:

```
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser. Worker portal is at `/login` and `/register`. Admin portal is at `/admin/login` using `admin@safegig.demo` and `SafeGig@2026`.

## Repository Structure

```
safegig/
  frontend/       React web app
  backend/        Node.js Express REST API
  ml-service/     Python FastAPI for risk scoring and fraud detection
  README.md
```

## Team Codestorm

Guidewire DEVTrails 2026. University Hackathon.

Built for India's 10 million gig workers who keep our cities fed, one delivery at a time.
