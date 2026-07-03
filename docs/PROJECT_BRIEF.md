# Sotechxy Website — Project Brief & Build Guide

> Single source of truth for building, modifying, and maintaining the Sotechxy
> website. Read this first in any new session before touching the site.
> Last updated: 2026-07-02

---

## 1. What this project is

Sotechxy is a storefront that sells no-code automation templates (n8n, Make,
Airtable, GCP, and more) to non-technical customers. People browse a catalog
organized by plan level, pay, and download a ready-to-run pack with a setup
wizard. Future additions: user sign-up, a blog, and member discounts.

The website is SEPARATE from the templates production system (that lives in a
different repo: `automation-templates-studio`). This repo/folder is ONLY the
public-facing website.

---

## 2. Who I am (the owner) and how to work with me

- I am NOT a developer. Explain everything in plain language, GUI-first.
- Give ONE instruction at a time, then wait for me to reply "done".
- Always security-first, and briefly explain why.
- Always provide code/commands in full, ready to copy-paste, even for small fixes.
- Be direct and share strong opinions when useful.
- "Smart first": before building, recommend the simplest reliable approach and
  flag anything that would cost money or add risk unnecessarily.

---

## 3. Brand identity (do not drift from this)

- **Name:** Sotechxy
- **Domain:** sotechxy.com (owned via Namecheap, 2-year registration, privacy on)
- **Tagline:** "Automations that actually run."
- **Personality:** modern, futuristic, geek-premium, editorial (inspired by monks.com —
  bold type, generous whitespace, restraint, one loud accent).

### Color palette
| Role | Hex | Use |
|------|-----|-----|
| Background (charcoal) | `#1a1a1a` | page base |
| Panel | `#212121` | cards, tiers |
| Panel dark | `#161616` / `#1b2530` | join box |
| Text (off-white) | `#f2f0e9` | headings, body |
| Muted | `#8a8a8a` | secondary text |
| **Primary accent (acid green)** | `#00ff9c` | buttons, prices, "runs free", featured tier |
| **Secondary accent (blue-gray)** | `#6A89A7` | nav links, section numbers, tags, join outline |
| Border | `#2e2e2e` | hairlines |

Rule: green LEADS (important/interactive things), blue-gray SUPPORTS (quiet
labels/links). Never let both shout. This "one loud, one quiet" balance is what
keeps it premium.

### Typography
- Sans-serif system font stack for everything.
- Monospace (`SF Mono` stack) for geek touches: section numbers (`01 —`),
  kicker (`// automation, packaged`), tags, "runs free".
- Sentence case everywhere. Bold = 600 max. Big editorial headlines.

---

## 4. Pricing tiers (the product structure)

| Tier | Price | What it is |
|------|-------|-----------|
| **Essentials** | $19 / template | one ready-to-run template + wizard + guide |
| **Growth** (most popular) | $79 / pack | 5+ related templates + cross-platform variants + priority setup |
| **Scale** | Custom | done-for-you + ongoing updates + direct support |

Key selling point vs free template libraries: we guarantee it WORKS, tell you
exactly what it costs to run ("runs free" badges), and support you. Never
compete on volume/price alone — compete on curation + setup + support.

---

## 5. Current state of the site

- Single file: `index.html` (self-contained: HTML + CSS inline, no dependencies).
- Location (working copy in the GitHub repo): `/Users/mlaura/Documents/GitHub/sotechxy/index.html`
- Original copy also on Desktop: `/Users/mlaura/Desktop/sotechxy-website/index.html`
- The GitHub repo folder (`/Users/mlaura/Documents/GitHub/sotechxy`) is the one
  that gets published. Edit there, then commit + push via GitHub Desktop.
- Sections, in order: nav → hero → stats bar → 01 plans → 02 catalog →
  03 join (email signup) → footer.
- Fully responsive (mobile breakpoint at 760px).
- Static only right now: buttons and the email form are visual — not yet wired
  to do anything. That's intentional for this stage.

---

## 6. Build principles (the "robust & reliable" rules)

1. **Keep it static as long as possible.** A static site (just HTML/CSS/JS
   files) has no server to hack, costs $0 to host, and can't "go down" from a
   backend bug. Only add a backend when a feature truly requires it.
2. **One concern at a time.** Don't bolt on payments, accounts, and a blog all
   at once. Ship one, verify it, then the next.
3. **Mobile is not optional.** Always check the phone layout after any change.
4. **Every change is version-controlled** (Git), so we can always undo.
5. **Security-first for anything involving money or user data.** Never handle
   card numbers ourselves — always use a trusted provider (e.g. Stripe,
   Lemon Squeezy) that takes payment on their secure page.
6. **Accessibility & clarity:** real text (not images of text), labels on form
   fields, readable contrast, plain-language copy.
7. **Fast:** no heavy frameworks unless a feature demands it. The current site
   loads instantly because it's one small file.

---

## 7. Roadmap (rough order — smart-first)

- [x] Brand, name, domain secured
- [x] Storefront design + static homepage (`index.html`)
- [x] Website in its own GitHub repo (`sotechxy`, public)
- [x] Published live for free on GitHub Pages
      LIVE URL: https://mlauradeveloper.github.io/sotechxy/
- [~] Connect the sotechxy.com domain to the live site — DNS RECORDS ADDED,
      DNS CHECK SUCCESSFUL on GitHub. Site live at http://www.sotechxy.com/
      Records set at Namecheap Advanced DNS:
        A  @  185.199.108.153
        A  @  185.199.109.153
        A  @  185.199.110.153
        A  @  185.199.111.153
        CNAME  www  mlauradeveloper.github.io
      GitHub custom domain set to: www.sotechxy.com
      REMAINING: enable "Enforce HTTPS" — GitHub is issuing the free TLS
      certificate automatically (can take up to ~24h). The checkbox unlocks
      once the certificate is ready. No action possible until then.
- [ ] Wire the email signup to a real list (e.g. a free tier of an email tool)
- [ ] Individual template detail pages
- [ ] Payments + digital download delivery (via Stripe / Lemon Squeezy)
- [ ] User accounts / sign-in
- [ ] Blog
- [ ] Member discounts

---

## 8. Hosting decision (recorded so we don't re-debate)

- Website = static content → host FREE on GitHub Pages (repo is public, so
  Pages is available). Netlify or Cloudflare Pages are equally good free
  alternatives. NOT Heroku (Heroku is for running live backend code and costs
  money; this site doesn't need it yet).
- Website lives in its OWN GitHub repo (`sotechxy`), separate from the
  templates studio.

---

## 8b. Data storage decision (how we store user data) — IMPORTANT

Core principle: **store as little as possible ourselves, and let trusted
specialist services hold anything sensitive.** We do NOT build or run our own
database for user data. Running our own store of emails / names / payment info
would make us responsible for securing it, backing it up, patching it, and
complying with privacy law (GDPR etc.) — too much risk and work for a solo
founder, and one mistake can leak customer data.

Instead, each type of data lives in a service built and legally hardened for it:

| Data type | Where it lives (NOT us) | Notes |
|-----------|-------------------------|-------|
| Email signups / newsletter | An email platform's free tier (e.g. MailerLite, Buttondown, ConvertKit) | They store the list, handle unsubscribes + privacy compliance, give us an embeddable form. |
| Payments + customer/order info | Stripe or Lemon Squeezy | PCI-compliant. We NEVER see, type, or store a card number. Lemon Squeezy also handles sales tax/VAT as merchant of record. |
| User accounts / logins (later) | Supabase, Auth0, or similar | They hash/store passwords securely. We never roll our own auth. |
| The downloadable template packs | Private storage the checkout tool delivers from (e.g. Lemon Squeezy file delivery) | Buyer gets a secure, expiring download link after payment. |

Rules that follow from this:
- The website stays a static frontend. Data lives in the services above.
- Never handle raw card numbers, ever. Payment always happens on the
  provider's secure page/widget.
- Collect only what we actually need (email to send updates; name + email +
  order for a purchase). Less stored = less risk.
- Whenever we add a data-collecting feature, add a short privacy note telling
  users what we collect and why, and link a simple privacy policy.

---

## 9. How to resume in a new session

Tell the assistant:
"Read docs/PROJECT_BRIEF.md in the sotechxy repo, then help me with [task].
Work one step at a time, GUI-first, security-first, and give copy-paste-ready
code."

Documentation lives in the `docs/` folder:
- `docs/PROJECT_BRIEF.md` (this file — the source of truth)
- `docs/LAUNCH_ROADMAP.md` (idea → market-ready stages)

The assistant has filesystem access to:
- `/Users/mlaura/Documents/GitHub/sotechxy` (the live repo — edit here)
- `/Users/mlaura/Desktop/sotechxy-website` (original backup copy)

---

## 10. Glossary (plain language)

- **Static site** — a website made of plain files that just display; no
  server-side program running. Cheapest, safest, fastest.
- **Hosting** — where the website's files live so the public can see them.
- **Repo (repository)** — a project folder tracked by Git/GitHub so every change
  is saved and undoable.
- **Deploy / publish** — putting the site online so a real web address shows it.
- **DNS** — the system that points your domain (sotechxy.com) at your hosting.
- **Frontend** — what visitors see. **Backend** — hidden server logic (accounts,
  payments). We stay frontend-only as long as we can.
