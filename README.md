# SafeGig

AI-powered parametric income insurance for India's gig delivery workers.

Built for Guidewire DEVTrails 2026 Hackathon by Team Codestorm.

SafeGig protects workers on platforms like Zepto, Blinkit, and Swiggy Instamart from income loss caused by extreme weather, pollution spikes, or local strikes. Instead of filing claims, payouts happen automatically when a trigger condition is met.

## The Problem

India's hyperlocal delivery ecosystem runs on gig workers, but those workers have zero income protection when things go wrong.

A monsoon can wipe out ₹1500–₹3600 in weekly earnings. A heatwave kills afternoon shifts. A pollution spike or local strike means an entire day lost. No insurance product exists today that covers this.

## What SafeGig Does

Workers pay a small weekly premium based on their risk profile. When a disruption hits their zone — heavy rain, extreme heat, hazardous AQI, or a curfew — the system detects it automatically, runs fraud checks, and triggers a payout. No paperwork, no claim forms, no waiting.

## Risk Tiers

| Tier | Weekly Premium | Coverage |
|---|---|---|
| Low | ₹29 | ₹800 |
| Standard | ₹49 | ₹1,500 |
| High | ₹79 | ₹2,500 |
| Premium | ₹89 | ₹3,500 |

## Parametric Triggers

| Trigger | Condition |
|---|---|
| Heavy Rain | Rainfall above 50 mm/hr |
| Extreme Heat | Temperature above 42°C |
| Severe Pollution | AQI above 300 |
| Curfew or Strike | Zone flagged as restricted |

## Tech Stack

Frontend is React with Tailwind CSS and Framer Motion. Backend is Node.js with Express and Supabase. ML service is Python FastAPI with inline risk scoring and fraud detection. Auth is handled via Supabase.

## How to Run

Clone the repo and set up your `.env` using `.env.example` as a reference.

Start the backend:
```bash
cd backend
npm install
node src/index.js
```

Start the frontend:
```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

Worker portal is at `/login` and `/register`. Admin portal is at `/admin/login` with credentials `admin@safegig.demo` and `SafeGig@2026`.

## Demo Flow

A worker registers and the AI computes their weekly premium based on city, hours worked, and platform. They activate a policy. The admin fires a parametric trigger — say, heavy rain in Mumbai. The system runs fraud detection and auto-generates a payout. The worker sees the claim update live on their dashboard.

## Team Codestorm

Built with the goal of protecting the workers who keep India's cities running, one delivery at a time.
