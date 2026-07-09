# Sotechxy — Launch Roadmap (Idea → Market-Ready)

> The full sequence to take Sotechxy from a live homepage to a robust, safe,
> revenue-ready business. Ordered smart-first: each stage builds on the last,
> and nothing paid or risky is added before it's needed.
> Companion to PROJECT_BRIEF.md. Last updated: 2026-07-08.

Legend: [x] done · [~] in progress · [ ] not started

---

## STAGE 0 — Foundation ✅ (mostly done)

- [x] Brand identity locked (name, colors, tagline, voice)
- [x] Domain owned + secured (sotechxy.com, privacy on, 2FA on Namecheap)
- [x] Storefront homepage designed and built (index.html)
- [x] Website in its own GitHub repo (public)
- [x] Published live for free on GitHub Pages
- [x] Custom domain connected (live at www.sotechxy.com)
- [x] Enforce HTTPS (site serves over GitHub Pages TLS — confirm padlock in browser)

**Exit criteria:** sotechxy.com loads the site over https:// with a padlock.

> **Polish shipped 2026-07-08:** self-hosted Outfit font (OFL, commercial-safe) for
> wordmark + H1; enlarged nav logo; interactive layer (scroll reveals, hero + stats
> count-up, magnetic buttons, 3D card tilt, cursor glow, nav scroll-spy — all pure
> CSS/JS, reduced-motion aware); brand name capitalized to "Sotechxy" everywhere;
> hero buttons wired to sections; favicon + Apple icon + Open Graph/Twitter share card.

---

## STAGE 1 — Make the site trustworthy & complete (content)

A store people will pay at must feel real and safe before money is involved.

- [x] "How it works" section (3 simple steps: pick → follow wizard → done)
- [ ] Real template detail pages (what each does, what it costs to run, screenshots)
- [x] FAQ (refunds, support, "what is n8n?", "do I need to code?")
- [x] About / trust page (who's behind it, the guarantee)
- Legal basics (required before collecting data/payment):
      - [x] Privacy Policy (live at privacy.html)
      - [ ] Terms of Service
      - [ ] Refund Policy
- [ ] Contact method (a support email address on the domain, e.g. hello@sotechxy.com)
- [x] Favicon + social share preview (favicon, Apple icon, Open Graph + Twitter card)

**Exit criteria:** a stranger understands what they're buying, what it costs,
who to contact, and their rights — without asking.

---

## STAGE 2 — Capture interest (email, no payment yet)

Start building an audience before the store is fully live.

- [ ] Choose an email platform (free tier: MailerLite / Buttondown / ConvertKit)
- [ ] Wire the existing signup box to that platform (embed form / API)
- [ ] Confirm double opt-in + unsubscribe works (privacy compliance)
- [ ] Simple welcome email
- [ ] (Optional) "launching soon" / early-access hook to grow the list

**Exit criteria:** a real email entered on the site lands in a real, compliant list.

---

## STAGE 3 — Sell one thing (payments + delivery)

The smallest possible real transaction, done safely.

- [ ] Choose checkout provider — RECOMMEND Lemon Squeezy (merchant of record:
      it handles global sales tax/VAT for you) or Stripe
- [ ] Upload ONE template pack as a digital product (zip) to that provider
- [ ] Provider hosts the secure download + delivers an expiring link after payment
- [ ] Add a real "Buy" button on one template that opens the provider's secure checkout
- [ ] Test a full purchase end-to-end (use test mode, then one real $ purchase)
- [ ] Confirm: card data never touches our site; receipt + download arrive automatically

**Exit criteria:** you can point a friend at the site and they can actually buy
and download one template, safely, with tax handled.

---

## STAGE 4 — Protect the product (anti-copy, realistic)

You can't make files uncopyable — you make copying pointless and traceable.

- [ ] Clear license terms in every pack (personal/commercial use, no resale)
- [ ] Per-buyer watermark or license key stamped into each download
- [ ] Sell the RELATIONSHIP: updates, support, new templates (the real moat)
- [ ] Delivery via expiring links (already handled by the checkout provider)
- [ ] Takedown plan noted (how to report a reseller if it happens)

**Exit criteria:** each sale is traceable to a buyer, and value lives in the
ongoing service, not just the file.

---

## STAGE 5 — Scale the catalog & tiers

Now that one sale works, widen the offer.

- [ ] Fill out Essentials templates (several solid single templates)
- [ ] Build the first Growth "pack" (themed bundle + cross-platform variants)
- [ ] Define the Scale (done-for-you) intake — a form + call booking
- [ ] Catalog filtering/search on the site as the list grows
- [ ] Keep every template passing the studio's validator + cost_profile

**Exit criteria:** all three tiers (Essentials / Growth / Scale) are actually buyable.

---

## STAGE 6 — Accounts & members (only when needed)

Add logins ONLY when a feature needs them (re-downloads, member discounts).

- [ ] Choose auth/storage service (Supabase / Auth0) — never roll our own
- [ ] Customer login to re-download past purchases
- [ ] Member discounts / coupon codes
- [ ] (Optional) license dashboard

**Exit criteria:** returning customers can log in and re-access what they bought.

---

## STAGE 7 — Grow (content & marketing)

- [ ] Blog (SEO: "how to automate X", template guides)
- [ ] Launch on relevant channels (communities, directories, social)
- [ ] Collect testimonials / case studies
- [ ] Analytics (privacy-friendly, e.g. Plausible) to see what converts
- [ ] Email nurture sequence for the list from Stage 2

**Exit criteria:** steady traffic arriving and converting without you pushing each sale.

---

## STAGE 8 — Operate reliably (ongoing)

- [ ] Backups: repo is the site's backup; keep the Desktop copy too
- [ ] Update templates when platforms (n8n/Make/etc.) change
- [ ] Monitor: uptime + a way for customers to report broken templates
- [ ] Renewals watch: domain (2028), any paid services
- [ ] Security review: 2FA everywhere, least-privilege tokens, no secrets in the repo

**Exit criteria:** the business runs without surprises; problems are caught early.

---

## Product principle: prove it on Sotechxy first (dogfooding)

Every automation we sell must first be built, run, and proven successful on
Sotechxy's own operations before it enters the catalog. No template ships without
real proof of utility from Sotechxy itself. We sell only what we actually use.

**First template — the Content Machine.** Given only a topic to talk about, it
produces SEO-strong, catchy content across every format:

- Instagram / TikTok: static posts, carousels, reels, short videos
- YouTube: videos
- Blog posts
- Newsletter issues

We build and run this on Sotechxy's own channels first (Instagram, TikTok,
YouTube, the blog, the Kit newsletter). Once it demonstrably drives results for
us, it becomes the flagship template for sale. Every automation after it follows
the same rule: proven on Sotechxy, then sold.

---

## Cross-cutting rules (apply at every stage)

- Store as little user data as possible; let specialists (email tool, Stripe/
  Lemon Squeezy, Supabase) hold anything sensitive. Never store card numbers.
- Stay static + free-hosted until a feature truly requires a backend.
- One concern at a time. Ship it, verify it, then the next.
- Every change committed to Git so it's reversible.
- Mobile checked after every change.
- Security-first, and a plain-language "why" for each decision.

---

## Immediate next 3 actions (when you resume)

Finishing Stage 1 — everything needed before money moves:

1. **Template detail pages** — one page per template (what it does, real run-cost, screenshots).
2. **Terms of Service + Refund Policy** — the two legal pages still open (Privacy is done).
3. **Support email on the domain** — e.g. hello@sotechxy.com.

Then Stage 2: wire the **email signup** to a real list (MailerLite / Buttondown).
