# 🛵 Suraksha360
**AI-Powered Parametric Income Insurance for India's Gig Workers**

*Built for Guidewire DEVTrails 2026*

---

## 1. What is Suraksha360? (The Requirement & Strategy)

**The Problem:** 
Gig workers (like Swiggy and Zomato delivery partners) in India rely entirely on daily earnings. But when extreme weather (heavy rain, heatwaves) or city-wide issues (severe pollution, curfews) happen, they physically cannot work. During these times, they lose 20–30% of their monthly income, with zero safety net.

**Our Solution:** 
Suraksha360 is a simple, automated income insurance platform. Workers pay a tiny weekly premium. If a major disruption hits their delivery zone, our system detects it and instantly pays out a portion of their lost income for that day. 
- No paperwork. 
- No manual claims. 
- Instant UPI transfer.

### Real-World Scenarios
- **Raju (Mumbai, Monsoon):** A Red Alert for flooding is declared. Roads are closed. Suraksha360 automatically detects the IMD alert for his zone and credits his day's lost earnings directly to his UPI.
- **Vikram (Delhi, Heatwave):** The temperature hits 47°C. It's unsafe to ride. Our system reads the weather API, sees the extreme heat threshold is crossed, and triggers an automated payout.
- **Pradeep (Bangalore, Strike):** A sudden transport strike locks down his area. Our system cross-checks local news APIs and his GPS inactivity to verify he can't work, filing an instant claim without him doing anything.

### How it Works (The Workflow)
1. **Sign Up:** The worker registers on our app and links their UPI ID.
2. **Subscription:** They choose a low-cost, weekly insurance plan.
3. **Monitoring:** Our system constantly checks Weather, AQI, and News APIs in the background.
4. **Trigger:** An extreme event (like heavy rain) crosses our predefined limit.
5. **Validation:** Our AI quickly checks for fraud (e.g., GPS spoofing).
6. **Payout:** Money is sent instantly to the worker's bank account.

---

## 2. Premiums, Triggers, & Platform

### Weekly Premium Model
Gig workers earn weekly, so we charge weekly. Plans auto-renew and can be canceled anytime.
- **Basic (₹19/week):** Covers Rain & Heat.
- **Standard (₹35/week):** Covers Rain, Heat, Pollution (AQI), and Curfews.
- **Pro (₹55/week):** Covers all events with extended protection hours.

### Parametric Triggers (When do we pay?)
We don't wait for workers to complain. We pay out automatically when official APIs hit specific numbers:
* **Rain / Flood:** Over 64mm of rain in a day (via OpenWeatherMap API).
* **Extreme Heat:** Temperatures over 42°C for 3+ hours.
* **Severe Air Pollution:** AQI levels crossing 300 (via CPCB API).
* **Curfews / Strikes:** Verified local area lockdowns (via NewsAPI).

### Why a Web Platform (PWA)?
We are building this as a **Progressive Web App (PWA)** instead of a heavy Android or iOS mobile app. 
- **Easy Access:** Workers can open it on any basic smartphone browser.
- **Low Data:** It saves precious mobile data and phone storage space.
- **Fast:** We can build and update it much faster during the hackathon. Workers can still "Add to Home Screen" so it feels exactly like a real app.

---

## 3. How We Use AI & ML

We use Artificial Intelligence to solve two massive insurance problems:

* **Dynamic Premium Pricing:** Every Sunday, our AI (XGBoost) looks at the 7-day weather forecast, the worker's city zone, and their past claims. If they live in a safe zone with clear weather, their premium for next week drops. If a major monsoon is coming, it slightly adjusts to cover the increased risk.
* **Fraud Detection:** To prevent fake claims, our AI (Isolation Forest) works behind the scenes. It checks if a worker is using fake GPS apps to pretend they are in a flooded zone, or if multiple accounts are trying to claim from the exact same phone. 

---

## 4. Tech Stack & Development Plan

### What We Are Using
* **Frontend:** Next.js 14 and Tailwind CSS (Simple, fast UI).
* **Backend & Database:** Next.js API routes connecting to Supabase (PostgreSQL).
* **AI Engine:** Python and FastAPI to run our ML models.
* **Payments:** Razorpay Sandbox for testing premium deductions.

### How We Will Build It
1. **Phase 1 (Ideation - Complete):** Formulate the core idea, define the API triggers, write this Idea Document, and choose our tech stack.
2. **Phase 2 (Building Core App):** Create the Web App. Build the screens for workers to sign up and choose a plan. Build the background system that monitors live Weather APIs to trigger mock payouts.
3. **Phase 3 (AI & Polish):** Connect our Python AI models for fraud detection and dynamic pricing. Polish the UI, deploy the app live, and film our final demo video!

---

## 5. What We DO NOT Cover
To keep the system fast and completely automated, Suraksha360 only covers **income lost due to external disruptions** (weather, strikes, curfews).
* We **do not** cover vehicle repairs or petrol.
* We **do not** cover health, accident, or life insurance.
