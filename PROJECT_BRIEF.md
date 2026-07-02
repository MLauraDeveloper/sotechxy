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
- [ ] Publish live for free (GitHub Pages, since repo is public)
- [ ] Connect the sotechxy.com domain to the live site
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

## 9. How to resume in a new session

Tell the assistant:
"Read PROJECT_BRIEF.md in the sotechxy repo, then help me with [task].
Work one step at a time, GUI-first, security-first, and give copy-paste-ready
code."

The assistant has filesystem access to:
- `/Users/mlaura/Documents/GitHub/sotechxy` (the live repo — edit here)
- `/Users/mlaura/Desktop/sotechxy-website` (original copy)

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
