# VoiceBill — free voice bill maker for Indian shops

### 👉 [Try it free — no signup needed](https://voicebill-saas.onrender.com/free-bill)

Speak your items ("do kilo chawal 150, ek lifebuoy 45") and get a GST bill
with a UPI QR in about 30 seconds. Free bill maker, no account required.

---
# VoiceBill MVP — Speak a 15s Note, Send a Paid Invoice

VoiceBill is a full-stack Micro-SaaS MVP built for **solo founders who want fast recurring revenue** across **Global ($ USD / Stripe)** and **India (₹ INR / Dynamic UPI QR + GST)** markets.

## Why This Idea Wins on Monetization
1. **Sells a Painkiller Tied Directly to Cash:** Freelancers, contractors, interior designers, agencies, clinics, photographers, and field technicians hate typing invoices at night and chasing late payments.
2. **Works Globally & Locally Out of the Box:**
   - **Global Mode (`USD` / `EUR` / `GBP`):** Generates itemized quotes & tax invoices with Deposit %, Stripe payment links, and client checkout QR codes.
   - **India Mode (`INR`):** Generates GST-compliant invoices (`CGST + SGST` + `GSTIN`), **real NPCI-compliant scannable Dynamic UPI QR codes (`upi://pay?...` pre-filled with exact ₹ amount)**, Advance % calculation, and 1-tap WhatsApp reminders.
3. **Built-In Viral Loop ($0 CAC):** Free users can send up to 5 bills/month carrying a *"Powered by VoiceBill — Create yours in 15s"* badge on every client link (`/p/:id`), turning every client into a lead.
4. **Zero API Cost Required to Launch:** Uses browser Web Speech dictation + a deterministic NLP extraction engine (`src/parser.js`) so your gross margin stays **85%+** even before adding optional LLM APIs.

---

## Project Structure
```text
voicebill-mvp/
├── package.json          # Express + QRCode dependencies
├── data/
│   └── db.json           # Persistent document & settings store (auto-created)
├── src/
│   ├── server.js         # REST API, Dynamic SVG QR generator, CSV export, Client Portal route
│   ├── parser.js         # Voice & natural-language quote/invoice extraction engine
│   └── store.js          # Financial math (Subtotal, Discount, CGST/SGST/Tax, Deposit, Balance)
└── public/
    ├── index.html        # Workspace UI (Pipeline, Voice AI Studio, Clients, Settings, SaaS Paywall)
    ├── portal.html       # Public Client E-Signature & Instant Payment Portal (/p/:id)
    ├── styles.css        # Modern fintech stylesheet + clean A4/Letter @media print PDF rules
    └── app.js            # Frontend state, Web Speech mic integration, WhatsApp chaser generator
```

## Run Locally or Deploy in 2 Minutes
```bash
cd voicebill-mvp
npm install
npm start
# Runs on http://0.0.0.0:3000
```
Deploy directly to **Railway**, **Render**, or **Fly.io** (`Build: npm install`, `Start: npm start`).

---

## 14-Day Playbook to Get Your First 10 Paying Users ($190/mo or ₹7,000+/mo)
1. **Days 1–2 (Connect Your Checkout):** Create a Stripe Payment Link ($19/mo) and/or Razorpay Subscription Link (₹699/mo) and link it to the **Activate Pro Plan** button in `public/index.html`.
2. **Days 3–7 (Direct Niche Outreach):** Pick **one** high-ticket service vertical first (e.g., *Interior Designers & Modular Kitchen Contractors*, *Web/Marketing Freelancers*, or *Wedding Photographers*).
3. **Send a 20-Second Loom / Screen Recording on WhatsApp or LinkedIn:**
   > *"Hey [Name], saw your recent project! Built a tiny tool where you speak a 15-second voice note after a client call and it instantly creates a branded GST/Tax quote with a 50% advance UPI QR / Stripe link + 1-tap WhatsApp follow-ups. Want free Pro access for 14 days to test on your next quote?"*
4. **Days 8–14 (Close & Retain):** Once a business sends 3–5 client quotes through VoiceBill and collects their first deposit, switching cost kicks in (61% monthly retention in Business apps).
