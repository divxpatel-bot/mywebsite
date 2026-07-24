# The Assertion

A static blog for QA engineers and testers, focused on testing AI/LLM-powered products. Plain HTML/CSS/JS — no build step, no framework, no database. Open source under the MIT License (see `LICENSE`).

Live structure:
```
index.html              → homepage (post list, tools, sponsored slot)
about.html
advertise.html          → sponsorship / paid listing packages
privacy-policy.html
posts/
  testing-ai-products-field-guide.html
  llm-bug-patterns.html
  non-deterministic-test-cases.html
css/style.css
js/script.js
```

## Run it locally
No build tools needed. Either:
- Open `index.html` directly in a browser, or
- Serve it properly (recommended, avoids relative-path quirks):
  ```
  cd the-assertion
  python3 -m http.server 8000
  ```
  then visit `http://localhost:8000`

## Deploy it (free)
**Option A — GitHub Pages** (fits well since the project is already open source):
1. Create a repo, e.g. `the-assertion`, and push this folder to it.
2. Repo → Settings → Pages → set source to the `main` branch, root folder.
3. Your site goes live at `https://YOUR_USERNAME.github.io/the-assertion/`.

**Option B — Netlify** (if you want a custom domain more easily):
1. Drag-and-drop this folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect the GitHub repo for auto-deploys on push.

Either way, once you have a repo, replace every `YOUR_USERNAME` placeholder in the footer links across all pages with your actual GitHub username.

## Adding a new post
1. Copy an existing file in `posts/` as a starting point.
2. Update the `<title>`, meta description, badges/tags, and body content.
3. Add a card for it to the "Recent posts" list in `index.html`.
Keep posts genuinely useful and specific — thin, padded posts are the #1 reason AdSense applications get rejected (see below).

## Turning on monetization

### 1. Display ads (Google AdSense)
- Apply at [google.com/adsense](https://www.google.com/adsense). No official minimum traffic is required, but in practice you'll have a much better shot with:
  - 15–20+ genuinely useful posts (800+ words each) — this site currently ships with 3, treat that as a starting point, not the finish line
  - A working Privacy Policy page (already included) and an About page (already included)
  - A live, custom domain rather than a raw `github.io` subdomain (a $10–15/year domain from Namecheap or a `.in` registrar helps approval odds and looks more credible to sponsors too)
- Once approved, paste your AdSense script into the `<head>` of every page (a commented placeholder is already left in `index.html`) and replace the placeholder `<div>` ad slots in `index.html` and each post with your real `<ins class="adsbygoogle">` ad units.
- Realistic expectation: AdSense income is a function of traffic. At low traffic (a few hundred visits/month) this will earn very little — it compounds slowly as posts rank on Google and get shared. Don't count on it as a fast income source.

### 2. Affiliate links
- The homepage "Test environment" section is already structured for this — each `.stack-item` has a placeholder or real link.
- Programs worth checking for a QA/testing niche:
  - **Udemy affiliate program** — open to individuals, no website required, commission on course sales via your referral link.
  - **Amazon Associates (India)** — for QA/testing books if you ever review any.
  - Most dedicated QA tool vendors (BrowserStack, etc.) run partner/reseller programs aimed at businesses rather than a simple per-signup affiliate link for individual bloggers — check each vendor's own partner page before assuming a commission structure.
- Always disclose affiliate links (already done in `index.html` via the `.disclosure` box) — this is both good practice and a legal requirement in most jurisdictions.

### 3. Paid listings (directory / sponsored post / job listing)
- Packages and starter pricing are on `advertise.html` — adjust the numbers once you have a sense of real traffic.
- For accepting payment **without building a backend**, use a payment link tool rather than Stripe: Stripe is currently invite-only for new India-based accounts, which makes it impractical to set up quickly. **Razorpay Payment Links** (or Instamojo/Cashfree as alternatives) work well for this — create a link from the dashboard, no code or website integration required, supports UPI/cards/netbanking. Replace the placeholder button on `advertise.html` with your real link.
- Manually add/remove sponsor entries by editing the relevant HTML section — no CMS needed at this scale.

## A realistic note on income
A brand-new site with three posts and no traffic will not generate meaningful income on day one — that's true of every monetization method above. The two things that actually move the needle over time are (1) publishing consistently so there's enough content for AdSense approval and for Google to have something to rank, and (2) sharing posts where QA people already are (LinkedIn, r/QualityAssurance, testing-focused Slack/Discord communities) rather than waiting for organic search traffic alone. In the short term, this project is arguably worth more as a visible, well-executed portfolio piece in a job search than as an income stream — both things can be true at once.

## License
MIT — see `LICENSE`. Free to use, modify, and redistribute.
