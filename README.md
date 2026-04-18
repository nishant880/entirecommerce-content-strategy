<div align="center">

---

### 🎯 **[Want us to run this for you? Book a call →](https://entirecommerce.ai/audit)**

---

</div>

# Content Strategy Playbook

## A 12-month content operating system for your DTC brand, built from first principles in Claude Code. One consolidated strategy document covering ICP-language audit, positioning synthesis, 4 to 8 topic pillars, cluster architecture, channel mix, publishing cadence, production workflow, distribution amplification, and a KPI framework. Delivered as a Word doc plus the markdown source. Built by Nishant Kapoor at EntireCommerce AI.

---

<div align="center">

### ⚡ Fastest way to use this playbook

**Paste this document's URL into Claude Code and say:**

> *"Read this and take me through it step by step."*

**Claude will interview you for the business context, walk you through any missing API setup, and run the full content strategy end-to-end. You don't need to read the rest of this document.**

</div>

---

## Who This Playbook Is For

Three personas.

**The founder-led DTC brand owner publishing content ad-hoc.** You post on LinkedIn when inspiration hits. You ship a blog post every few weeks. You have a newsletter that goes out when you remember. You know content should be compounding, you know you should have a plan, and you know the current approach isn't working. You want a 12-month operating system on a page: which topics to own, which channels to show up on, how often to publish, and what to measure.

**The fractional CMO running content across multiple DTC brands.** Every client asks for a content strategy in month one. You need a repeatable framework that produces a defensible plan in 3 to 4 hours of work. Your problem is consistency: each brand deserves the same rigour without 40 hours of bespoke thinking per engagement. This playbook is the same eight-section process every time.

**The in-house content lead at a funded DTC brand.** You have a team, a budget, and a CMS. What you don't have is a pillar architecture everyone agrees on, a cadence the team can hold, and a KPI framework the CEO trusts. You want the document that answers those three questions in one pass so the team can get back to producing work.

If you've ever spent a quarter shipping content without a clear pillar commitment, watched your cadence slip because nobody owned the editorial calendar, or wondered why your blog traffic is flat despite publishing every week, this playbook collapses the strategic pass into one consolidated output in a single Claude Code session.

---

## What The Content Strategy Playbook Actually Is

**The short version.** Eight sections in one consolidated document. Claude Code interviews you for brand specifics, mines your ICP's actual words from Reddit and niche forums, synthesises your positioning against the competitive whitespace, proposes 4 to 8 topic pillars with an evidence package for each, builds the cluster architecture of 8 to 20 sub-topics per pillar, designs the channel mix and cadence, maps the production workflow, sizes the distribution amplification, and sets the leading and lagging KPIs. Plus a dedicated synthesis pass that reads the whole draft end-to-end and surfaces the cross-cutting themes that connect ICP language to pillar choice to channel mix.

**Best for.** Premium DTC brands. AOV $500+ or 2x category median. Founder-led. US, UK, or English-speaking European markets. A team or budget capable of publishing 2 to 4 pieces a week across at least two channels.

**How it's different.** Three things that set this apart.

First, **ICP-language grounded**. Every pillar selection traces back to 15 verbatim customer quotes mined from Reddit, X, Quora, YouTube, and niche forums. The pillars are the categories your customers are already talking about, in the words they use.

Second, **positioning-led**. The pillars sit at the intersection of what your ICP cares about and what your competitors are ignoring. The playbook runs a light competitive content-footprint scan to surface the defensible territory before any pillar gets locked in.

Third, **a 12-month operating system**. Pillars, clusters, channels, cadence, production workflow, distribution ladder, and KPI framework in one document. Plus a 30-60-90 publishing roadmap that plugs directly into your team's `actions.md`.

**Skip this playbook if** you're a service business, a B2B SaaS, or a mass-market brand. The framework is tuned for premium DTC, and the channel-mix recommendations (LinkedIn founder voice, YouTube Shorts, podcast guest appearances) are calibrated for that context.

---

## Setup (15 Minutes)

### Prerequisites

- **Claude Code** installed. Download from [claude.com/claude-code](https://claude.com/claude-code). Verify with `claude --version`.
- **pandoc** installed. On macOS: `brew install pandoc`. Verify with `pandoc --version`.
- **A project folder** on your machine.

### Cost overview

The playbook itself is free. You pay for API credits the tools consume during the ICP research and competitor content-footprint passes.

| Tool | Subscription model | Typical per-run cost | Role |
|---|---|---|---|
| DataForSEO | Pay-as-you-go | **$1 to $5** | Recommended. Pulls keyword volumes per pillar and competitor footprints. |
| Ahrefs | $129+ per month | Optional | Skip unless you already have an account. DataForSEO covers most of the same ground. |
| Serper | Free tier gives 2,500 credits | Under $0.50 | Recommended. Live SERP snapshots per pillar. |
| Keywords Everywhere | ~$10 one-time for 100K credits | Under $0.50 | Recommended. Seed-term volume lookups. |
| Google Trends | Free, no key needed | $0 | Seasonality and emerging-topic momentum. |
| Google Search Console | Free (your own account) | $0 | Internal tool, Path A only. Existing-page performance. |
| Google Analytics 4 | Free | $0 | Internal tool, Path A only. Engagement and attribution. |
| Shopify Admin | Included in your plan | $0 | Internal tool, Path A only. Category and product inventory. |
| Klaviyo or Brevo | Included in your existing plan | $0 | Internal tool, Path A only. Email cadence and performance. |

**Typical total cost per full run: $2 to $7** across the paid external tools.

Numbers are approximate as of April 2026. When you run the master prompt, Claude will print the credential inventory and offer to look up current sign-up steps and pricing for any tool you're missing.

### Step 1: Create the project folder

```bash
mkdir my-brand-content && cd my-brand-content
```

Drop the three files from this bundle (CLAUDE.md, content-strategy.md, README.md) into the folder.

### Step 2: Set up your .env (optional: let Claude walk you through)

Create a `.env` file. Add whichever API keys you have. If you're missing any, Claude will offer to walk you through sign-up when you run the master prompt.

Minimum recommended `.env`:

```
DATAFORSEO_LOGIN=your_login
DATAFORSEO_PASSWORD=your_password
SERPER_API_KEY=your_key
KEYWORDS_EVERYWHERE_API_KEY=your_key
```

**Gotcha:** Never commit `.env` to a public repo. Add `.env` to `.gitignore` first.

### Step 3: Populate CLAUDE.md (or let Claude interview you)

Two options:

**Option A (recommended, fastest).** Leave `CLAUDE.md` as-is. When you run the master prompt, Claude will interview you conversationally: brand, product, ICP, positioning hypothesis, current content inventory (if any), competitors, channels, team size, cadence goal. Claude writes the file progressively. Takes about 10 minutes.

**Option B (DIY).** Open `CLAUDE.md` and replace every `{placeholder}` before running the playbook.

Either way, the end state is the same.

### Step 4: Open Claude Code in the folder

```bash
claude
```

Claude Code loads `CLAUDE.md` on session start. Confirm "Loaded CLAUDE.md" appears.

---

## The Three Files in This Bundle

### File 1: CLAUDE.md (business-briefing template)

**Path:** `{your-project-folder}/CLAUDE.md`
**What it does:** Loaded on every Claude Code session. Holds your brand specifics: product, ICP, positioning, competitors, current channels, team size, cadence goal.
**How to use it:** Either fill it in yourself (Option B above) or let Claude interview you (Option A).

### File 2: content-strategy.md (the master prompt Claude runs)

**Path:** `{your-project-folder}/content-strategy.md`
**What it does:** The self-executing prompt Claude runs end-to-end to produce the strategy. Covers all eight sections plus the synthesis pass plus the voice-enforcement gate plus the Word-doc export.
**How to use it:** Paste its entire contents into Claude Code and hit enter. Don't edit unless you know what you're doing.

### File 3: README.md

**Path:** `{your-project-folder}/README.md`
**What it does:** You're reading it.

---

## Your First Run

Five steps. Two to four hours on Full mode, about two hours on Quick mode.

1. **Open Claude Code in your project folder.** `cd my-brand-content && claude`
2. **Paste the full contents of `content-strategy.md` into the terminal.** Hit enter.
3. **Claude prints a credential inventory.** External tools wired vs missing. Claude offers to walk you through any missing sign-ups.
4. **Claude auto-detects the mode** (Full Reset, Refresh Quick, Launch Full, Launch Quick) based on your content inventory. Confirm or override.
5. **Claude runs the playbook.** Interviews you, mines your ICP via WebSearch, pulls keyword data per pillar, runs the competitor content-footprint scan, synthesises positioning, selects pillars, builds cluster architecture, designs the channel mix, runs the synthesis pass, runs the voice gate, writes the strategy document.

Output lands at:

```
{your-project-folder}/docs/content-strategy/YYYY-MM-DD/content-strategy.md
{your-project-folder}/docs/content-strategy/YYYY-MM-DD/content-strategy.docx
```

Plus supporting evidence (15-quote ICP appendix, per-pillar cluster CSVs, competitor content-footprint notes) in `{your-project-folder}/data/content-strategy/YYYY-MM-DD/`.

---

## What You'll Get

Ten high-value deliverables in one consolidated document.

1. **Executive summary with cross-cutting themes.** 3 to 4 sentence narrative plus 3 to 5 strategic insights spanning multiple sections. Produced by the synthesis pass that reads the whole draft end-to-end.
2. **Top three highest-leverage moves for the next 90 days.** Front-loaded at the top of the document for 90-second reading.
3. **ICP-language audit.** 15 verbatim customer quotes from Reddit, X, Quora, YouTube, and niche forums, plus 5 to 10 recurring themes ranked by emotional charge and mapped to commercial intent.
4. **Positioning and differentiation synthesis.** Your defensible territory, three proof points, the belief shift the audience must make, and the emerging-category term to claim.
5. **4 to 8 topic pillars with evidence package.** Each pillar scored on ICP relevance, commercial intent, and brand authority. Publishing-volume allocation per pillar specified. Reject reasoning visible on discarded candidates.
6. **Cluster architecture per pillar.** 8 to 20 sub-topics per pillar with pillar page, cluster pages, and supporting-format mix. Full cluster table saved as CSV per pillar.
7. **Channel mix and cadence.** Up to 4 channels with role, pillar allocation, format mix, concrete per-week cadence, and example post types.
8. **Production workflow and distribution amplification.** Roles, stages, tooling, throughput, cost estimates. Plus the repurposing ladder (1 long-form to 5 or more downstream assets), syndication partners, and DM-lead-capture comment playbook.
9. **KPI framework.** Leading indicators (publishing velocity, audience growth, time on page, CTR, DM-trigger conversions) and lagging indicators (organic traffic, AEO citations, qualified leads, content-sourced LTV, pillar-level revenue) with weekly, monthly, quarterly, and annual review cadences.
10. **ICE action list plus 30-60-90 publishing roadmap.** Every action scored on Impact × Confidence × Effort and ranked into Days 1-30, Days 31-60, and Days 61-90 buckets. Days 1-30 items merge into your `actions.md` automatically.

**Format.** One consolidated Word doc (shareable with your team) plus the markdown source (version-controlled in your GitHub repo). Typically 5,000 to 9,000 words on Full mode, 2,000 to 3,500 words on Quick mode. Reading time around 25 minutes cover to cover, 90 seconds to skim via the top-three-moves block.

---

## Modes

| Mode | When it applies | What changes |
|---|---|---|
| Full Reset | Existing programme, 12-month strategic refresh | All eight sections. 2 to 4 hours. |
| Refresh Quick | Existing programme, pillar-only reset | Sections 1 to 5 only. 2 hours. |
| Launch Full | Greenfield / pre-launch, full operating-system design | All eight sections with Path B framing. 2 to 4 hours. |
| Launch Quick | Greenfield, minimum-viable content plan | Sections 1 to 5 only. 2 hours. |

Auto-detection reads `CLAUDE.md`. If a content inventory is listed, Path A. Otherwise Path B.

---

## Honest Caveats

**The ICP-language audit depends on public conversations existing.** Premium DTC categories with small audiences sometimes have thin Reddit and forum footprints. The playbook flags quote shortfalls explicitly. If fewer than 10 quotes land, the pillar selection gets softer and the belief shift harder to pin down.

**Pillar selection is a judgement call.** The scoring rubric (ICP relevance, commercial intent, brand authority) ranks candidates, and the final 4 to 8 pillars require founder input. Claude can propose; the founder confirms.

**Cadence targets are ambitious by default.** Two to four pieces a week assumes a writer or fractional producer. If the founder is the only content producer, halve the cadence and focus on two channels.

**Voice rules are strictly enforced.** Claude runs a mechanical grep-pass for em-dashes, negative parallelisms ("X, not Y"), banned spelling ("e-commerce"), and AI clichés ("Here's the...") before writing to disk. Most style drift gets caught; some slips through. Flag it and rerun the voice gate if you spot a banned pattern.

**Internal access sharpens Path A.** GSC, GA4, Shopify, Klaviyo access upgrade the cluster-architecture realism and the KPI baseline. Path A runs without these, but the sharper output comes when they're wired.

**API costs are real but small.** Typical full run costs $2 to $7 across the paid external tools.

---

## Quick-Start Checklist

- [ ] Claude Code installed (`claude --version` works)
- [ ] pandoc installed (`pandoc --version` works)
- [ ] Project folder created for the brand
- [ ] CLAUDE.md copied into the project folder
- [ ] content-strategy.md copied into the project folder
- [ ] DataForSEO credentials in `.env`
- [ ] Serper API key in `.env`
- [ ] Keywords Everywhere API key in `.env`
- [ ] CLAUDE.md filled in (or interview-mode enabled on first run)
- [ ] 3 to 5 competitor URLs ready
- [ ] First run executed, Word doc produced at `docs/content-strategy/{date}/`
- [ ] Top three 90-day moves identified from the report
- [ ] Days 1 to 30 items merged into team `actions.md`
- [ ] Editorial calendar (Airtable or Notion) populated from the cluster tables
- [ ] First cadence week planned and scheduled
- [ ] Book a call if you'd rather we run this on a live engagement: [entirecommerce.ai/audit](https://entirecommerce.ai/audit)

---

## Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| "pandoc not found" at Word-doc export | pandoc not installed | `brew install pandoc` |
| ICP audit returns fewer than 10 quotes | Thin public footprint for the niche | Expand sources to YouTube comments, niche Facebook groups, and review-site corpora. Flag the shortfall in the report. |
| Pillar count comes back at 3 or 9+ | Scoring too lenient or too strict | Rerun Section 3 with the founder present to arbitrate borderline candidates. |
| Cluster CSV missing for a pillar | Sub-agent failed to save the CSV | Re-prompt Claude to save each pillar's cluster table before writing the final doc. |
| Voice gate flags em-dashes or negative parallelisms | Style drift in sub-agent output | Paste the banned-patterns list back into Claude and ask it to scan-and-fix the full file. |
| Channel-mix recommendation includes 6+ channels | Over-eager default | Override in Section 5 with the 4-channel-max rule. Cadence discipline beats channel sprawl. |

---

## Credit

Built by Nishant Kapoor at EntireCommerce AI.

- **LinkedIn**: [linkedin.com/in/nishantkapoor1](https://www.linkedin.com/in/nishantkapoor1)
- **Email**: nishant@entirecommerce.co
- **Book a call**: [entirecommerce.ai/audit](https://entirecommerce.ai/audit)
- **Full playbook library**: [entirecommerce.ai/playbooks](https://entirecommerce.ai/playbooks)

Use this playbook freely. Share it with other DTC founders. If you ship a case study running it on your brand, tag us.
