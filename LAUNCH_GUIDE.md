# 🚀 Step-by-Step Launch Playbook: From Zero to First Paying Customers

Your **VoiceBill MVP** (`/home/user/voicebill-mvp`) is already configured with 1-click deployment files (`render.yaml`, `railway.json`, `.gitignore`, `.env.example`, `/health` check) and zero-code payment link redirects (`?upgraded=1`).

Follow these **6 simple steps** in exact order. You can complete Steps 1–4 **today in under 45 minutes** for **$0 upfront**.

---

## STEP 1: Download Your Code & Put It on GitHub (10 Minutes · $0)
Hosting platforms deploy directly from a private GitHub repository so every future change updates automatically.

1. Create a free account at **[github.com](https://github.com)** (if you don't have one) and click **New Repository**:
   * **Repository name:** `voicebill-saas`
   * **Visibility:** **Private** (keep your source code private!)
   * Click **Create repository**.
2. Download the `voicebill-mvp` folder from your workspace here onto your computer (or upload the files directly via GitHub's **"uploading an existing file"** link—just skip `node_modules`).
3. If using Terminal/Git on your computer, run:
   ```bash
   cd voicebill-mvp
   git init
   git add .
   git commit -m "Initial VoiceBill MVP launch"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/voicebill-saas.git
   git push -u origin main
   ```

---

## STEP 2: Put the App Live on the Internet (10 Minutes · $0 to $5/mo)
Pick **Option A (Render — Free to start)** or **Option B (Railway — $5/mo, super fast + persistent storage)**.

### Option A: Render.com (Best $0 Free Start)
1. Sign up at **[render.com](https://render.com)** using **"Continue with GitHub"**.
2. Click **New +** → **Blueprint** (or **Web Service**) and select your `voicebill-saas` repository.
3. Render automatically reads the `render.yaml` file I added for you:
   * **Build Command:** `npm install`
   * **Start Command:** `npm start`
4. Click **Deploy Web Service**.
5. In ~90 seconds, you get a live public HTTPS link like `https://voicebill-saas.onrender.com`!
   *(Tip: Once you get your first 2 paying users, upgrade Render to the $7/mo Starter plan + attach a $1 Persistent Disk mounted at `/data` with env var `DATA_DIR=/data` so your server never sleeps).*

### Option B: Railway.app (Fastest Always-On Hosting)
1. Sign up at **[railway.app](https://railway.app)** with GitHub.
2. Click **New Project** → **Deploy from GitHub repo** → choose `voicebill-saas`.
3. Right-click your service card → **Add Volume** → mount path `/data`, and add variable `DATA_DIR=/data`.
4. Go to **Settings → Networking → Generate Domain** to get your live HTTPS URL immediately.

---

## STEP 3: Connect Real Payments So Money Hits Your Bank Account (15 Minutes)
Your app is **already wired** to accept real checkout links without writing payment API code! Here is the easiest setup for **both Global ($ USD) and India (₹ INR)**—even as an individual solo founder without a registered corporation:

### A. Taking Global USD Payments ($19/mo) — *Works from India or Anywhere*
Use a **Merchant of Record (MoR)** like **[Dodo Payments](https://dodopayments.com)**, **[Lemon Squeezy](https://lemonsqueezy.com)**, or **[Polar.sh](https://polar.sh)** (or **Stripe Payment Links** if you're in a Stripe-supported country):
* **Why MoR is easiest:** You can sign up as an **individual** with just your ID/PAN + bank account, they handle global sales tax/VAT automatically, and pay straight to your local bank account!
1. Create a Product called **`VoiceBill Pro`** priced at **`$19 / month`** (or a **`$49 Lifetime Early-Bird Deal`**—lifetime deals sell *extremely* fast in week 1!).
2. In the product's **Confirmation / Redirect URL after purchase**, enter:
   ```text
   https://YOUR-LIVE-APP-URL.com/?upgraded=1
   ```
3. Copy the Checkout URL they give you.

### B. Taking India INR / UPI Payments (₹699/mo)
1. Sign up on **[Razorpay](https://razorpay.com)** (or **Cashfree**).
2. Go to **Payment Links / Payment Pages** (or **Subscriptions**) → Create **`VoiceBill Pro — ₹699/month`** (supports UPI Autopay, GPay, PhonePe, Cards).
3. Set the **Redirect URL after payment** to:
   ```text
   https://YOUR-LIVE-APP-URL.com/?upgraded=1
   ```
4. Copy the Razorpay link.

### C. Paste Both Links into Your Hosting Dashboard
In Render or Railway → **Environment Variables**, add:
* `PRO_STRIPE_LINK` = `https://checkout.dodopayments.com/...` *(your Global USD link)*
* `PRO_RAZORPAY_LINK` = `https://rzp.io/l/...` *(your India INR link)*

Click **Save**. Your app will auto-restart, and now clicking **"Activate Pro Plan"** sends Global users to USD checkout and Indian users to UPI/INR checkout, then unlocks Pro automatically upon payment!

---

## STEP 4: Connect a Clean Custom Domain (Optional · 10 Minutes · ~$9/yr)
A real domain increases buyer trust 3×.
1. Buy a `.com`, `.co`, or `.app` domain on **Cloudflare Registrar**, **Porkbun**, or **Namecheap** (e.g., `getvoicebill.com`, `quickvoicebill.com`, `speakbill.app` — ~$9/year).
2. In Render or Railway → **Settings → Custom Domains** → type your domain.
3. Copy the `CNAME` record shown and paste it into your domain registrar's DNS settings. Free SSL (`https://`) activates automatically in 5 minutes.

---

## STEP 5: Get Your First 10 Paying Customers in 14 Days ($0 Ad Budget)
Do **not** run paid Facebook/Google ads first. Use direct outreach + short demo videos where business owners already hang out:

### Channel 1: The 20-Second Screen Recording DM (Highest Conversion)
Record a 20-second screen video on your phone/laptop showing:
1. Tapping a voice prompt in **VoiceBill**.
2. Watching the branded GST / Stripe invoice + scannable UPI QR appear in 2 seconds.
3. Clicking **Send on WhatsApp**.

**Send 20 messages/day** on Instagram DM, LinkedIn, or WhatsApp to **one niche at a time** (Interior Designers, Modular Kitchen Contractors, Freelance Web/Video Agencies, Salons/Clinics, Event Photographers):

> **Copy-Paste Outreach Script:**
> *"Hey [Name]! Saw your recent [interior/design/photography] work—looks great. Quick question: do you still type client quotes & GST/deposit bills manually? I built a tiny tool where you speak a 15-second voice note and it instantly generates a branded quote + 50% advance UPI QR / payment link ready to send on WhatsApp. Mind if I send you a free link to try on your next client quote?"*

### Channel 2: Short-Form Organic Reels / Shorts / Reddit
Post 3 short videos a week with the hook:
* *"POV: Your client asks for an itemized quote while you're driving / on-site — watch me send a branded invoice + payment QR in 14 seconds using just my voice."*
* Post in `r/freelance`, `r/smallbusiness`, `r/sweatystartup`, IndieHackers, and local business Facebook/WhatsApp groups.

### Channel 3: Early-Bird Cash Injection Trick ("First 25 Founders Deal")
Need cash in Week 1 instead of waiting for monthly renewals?
* Offer the **first 20 customers** a **$49 (or ₹2,499) 1-Year / Founding Member Pass** instead of $19/mo.
* **20 buyers × $49 = $980 (~₹82,000) upfront cash** in your first two weeks, which funds everything else!

---

## STEP 6: When You Hit 15–20 Paying Users (Scale-Up Upgrade)
Right now, this MVP intentionally skips complicated signup walls so users experience the magic in 5 seconds. Once 10–20 strangers are paying you, take one weekend to add multi-tenant accounts:
1. Add **Clerk** or **Supabase Auth** ("Continue with Google / Magic Link") so each business has its own private workspace (`user_id` column).
2. Move storage from `db.json` to **Supabase Free Postgres** (`500MB free`).
3. Optional: Plug in **OpenAI `gpt-4o-mini` / Whisper API** (~$0.001 per invoice) so users can speak in **Hindi, Hinglish, Spanish, French, or Arabic** and still output clean invoices!
