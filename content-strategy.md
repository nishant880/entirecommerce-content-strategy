# Content Strategy: Master Prompt

> Paste this entire file into Claude Code from a folder containing a `.env` (your API keys). If a `CLAUDE.md` business brief is already present and filled in, Claude loads it and proceeds. Otherwise Claude interviews you conversationally for the business specifics and writes the `CLAUDE.md` for you. Either way, Claude runs the playbook end-to-end, produces a single consolidated strategy document in markdown and Word formats, and saves supporting data alongside.
>
> Built by Nishant Kapoor at EntireCommerce AI. Version 1, April 2026.

---

You are executing the Content Strategy playbook for the brand in the current working directory. Follow these steps in order. Do not skip steps. Do not invent data. Honour the voice conventions in Step 8.

---

## Step 1. Load or populate the business brief

Look for `CLAUDE.md` in the current working directory.

**If `CLAUDE.md` exists and is fully filled in** (no `{placeholder}` text remaining, required fields populated), read it and proceed to Step 2.

**If `CLAUDE.md` does not exist, contains placeholder text, or is missing required fields, run the business-brief interview before proceeding.** Do not skip. Do not guess the inputs.

### The business-brief interview

Ask the user conversationally, one batch at a time. After each batch, write the answers to `CLAUDE.md` and confirm before the next batch.

**Batch 1: Brand overview.** Brand name. Primary URL. How long the domain has been live. Ecommerce platform. Geographic focus. Stage (pre-launch, first year, established, mature).

**Batch 2: ICP.** Core buyer in one sentence, in your words. What they hire the product to do. Where they hang out online (Reddit subs, niche forums, YouTube channels, podcasts, Instagram accounts).

**Batch 3: Positioning hypothesis.** Why you win in one sentence. The single category term you want to own. The belief shift the buyer must make before buying.

**Batch 4: Content inventory (Path A only).** Blog or articles live (platform, post count, cadence). Email list (subscriber count, cadence, open-rate band). Social channels active with follower counts. Podcast or long-form. Community. If the brand has none of this, confirm Path B (greenfield).

**Batch 5: Competitors.** Three to five competitor URLs the buyer also considers.

**Batch 6: Team and budget.** Team size and roles. Monthly content production budget. Founder content time per week.

**Batch 7: Cadence goal.** Total pieces per week across all channels. Channels to prioritise (max 4 from Blog, LinkedIn, X, YouTube Shorts, Podcast guest appearances, Email newsletter, Community). Non-negotiables.

**Batch 8: Targets.** 12-month revenue target. Audience target (newsletter subs, organic traffic, social followers as absolute numbers). Leading-indicator targets for 90 days.

### Minimum required to proceed to Step 2

If after the interview you still do not have these seven fields captured, ask again:

1. Brand name and URL
2. ICP in one line
3. Founder positioning hypothesis
4. 3 to 5 competitor URLs
5. Team size and content budget
6. Publishing cadence goal
7. 12-month revenue or audience target

Do not invent any value.

---

## Step 2. Inventory tool access

Read the `.env` file. Print a credential inventory:

```
External tools (public data, always runs)
- DataForSEO: configured / not configured
- Ahrefs: configured / not configured
- Serper: configured / not configured
- Keywords Everywhere: configured / not configured
- Google Trends: configured (public, no key needed)

Internal tools (your brand's own data, Path A only)
- Google Search Console: configured / not configured
- Google Analytics 4: configured / not configured
- Shopify Admin: configured / not configured
- Klaviyo / Brevo: configured / not configured
```

### Offer setup instructions for missing tools

For each tool flagged "not configured", ask:

> "`{Tool}` is not configured. Want me to look up the current sign-up steps and API-key retrieval flow? Answer `yes`, `no`, or `skip all`."

If `yes`, use WebSearch and WebFetch to pull the current sign-up flow: pricing tiers, free-tier availability, API-key location, and the `.env` variable name this playbook expects. If `no`, skip that tool. If `skip all`, stop offering and proceed.

After credentials are added, reprint the inventory.

Never hardcode sign-up URLs or pricing from memory. Pull fresh.

---

## Step 3. Detect the mode

Auto-detect from `CLAUDE.md` and the user's inputs:

| Mode | Trigger |
|---|---|
| Full Reset | Path A (existing programme), user wants full 12-month strategic refresh |
| Refresh Quick | Path A, user wants pillars + cadence only (30 minutes) |
| Launch Full | Path B (greenfield), user wants full operating-system design |
| Launch Quick | Path B, user wants minimum-viable content plan before first publish |

State the detected mode and ask the user to confirm or override.

---

## Step 4. Run the eight sections

Produce all sections in drafting mode. Do not write to disk yet. Quick modes skip Sections 6, 7, and 8.

### Section 1. ICP-language audit

Run the inlined Audience Insights research prompt below. Mine 15 verbatim quotes from Reddit, X, Quora, YouTube, and niche forums. After the 15-quote pass, layer the content-strategy-specific synthesis:

- Five to ten recurring themes (3 to 5 words each), tied to 2+ quotes each.
- Themes mapped to commercial intent (informational, comparison, transactional, brand-aware).
- Themes ranked by emotional charge.

Save the 15-quote appendix to `data/content-strategy/{YYYY-MM-DD}/icp-voc-mining.md`.

### Section 2. Positioning and differentiation synthesis

Combine:
1. Founder positioning hypothesis from `CLAUDE.md`
2. Five to ten recurring ICP themes from Section 1
3. Competitive whitespace from a light competitor content-footprint scan (Ahrefs + Serper against the 3 to 5 competitor URLs)

Produce:
- **Defensible territory**: one sentence at the intersection of ICP interest and competitor whitespace. No generic claims like "premium quality".
- **Three proof points**: product claim, founder expertise, customer outcome, data, or asset. Each traces to a specific source.
- **Belief shift**: state current belief + target belief. Must be testable.
- **Category claim**: emerging-category term to own. Include even if current volume is zero.

### Section 3. Topic pillar selection

**Upstream inputs.** Pillar selection runs best when an industry keyword universe is already available. When the brand has a prior GTM audit (`industry-keyword-universe.csv` + `industry-clusters-page-map.md` in `data/gtm-audit/`) or SEO audit (`data/seo-audit/`) or content-gap audit (`data/content-gap/`), read those artefacts first: the clusters are the pillar candidates, the intent tags feed the commercial-intent test, the opportunity scores feed the brand-authority test. Do not duplicate the consolidation work here. When those artefacts are missing, Section 3 of this playbook runs the consolidation inline, but the GTM/SEO/content-gap playbooks are the canonical home of that step.

4 to 8 pillars. Each must satisfy three tests:

1. ICP relevance (ties to at least one recurring theme)
2. Commercial intent (30%+ of cluster terms carry commercial or transactional intent)
3. Brand authority (brand can credibly win here)

Sizing:
- Exactly 4 to 8 pillars.
- One head pillar (30 to 40% of publishing volume).
- Two to four body pillars (15 to 25% each).
- One to three edge pillars (5 to 10% each).

Each selected pillar gets an evidence block:
- Pillar name (2 to 5 words)
- ICP themes it addresses
- Competitive density (how many competitors publishing, how deep)
- Search volume band
- Commercial-intent ratio
- Brand authority evidence
- Reject reasoning for discarded candidates

### Section 4. Cluster architecture per pillar

Per pillar, produce:
- One pillar page (2,000+ words, targets strongest commercial-intent keyword)
- 8 to 20 cluster pages (each targets one sub-topic, links up to pillar page)
- Clusters grouped by intent (informational, comparison, transactional, AEO)
- Supporting-format mix (long-form blog, short-form social, YouTube Shorts, newsletter segment, podcast episode)

Sub-topic scoring: sum of search volume, difficulty (inverse), commercial intent, ICP theme alignment (each 1 to 10). Rank sub-topics within the pillar.

Save cluster table per pillar to `data/content-strategy/{YYYY-MM-DD}/pillars/{pillar-slug}-clusters.csv` with columns: sub-topic, target keyword, volume, difficulty, intent, theme alignment, format, priority rank.

### Section 5. Channel mix and cadence

Select up to 4 channels from:
- Blog (SEO + AEO): 1 to 3 long-form per week
- LinkedIn (founder voice): 3 to 5 posts per week
- X (founder voice): 5 to 10 posts per week
- YouTube Shorts: 2 to 5 per week
- Podcast guest appearances: 2 to 4 per month
- Email newsletter: weekly
- Community: daily presence

Selection rules:
- No more than 4 channels to start.
- One compounding channel minimum (Blog or YouTube).
- One founder-voice channel minimum (LinkedIn or X).
- One owned channel minimum (Email or Community).

Per selected channel, specify:
- Role (reach, authority, retention, conversion)
- Pillar allocation (which pillars this channel carries)
- Format mix
- Concrete per-week cadence (one specific integer)
- 3 to 5 example post types

### Section 6. Production workflow (Full modes only)

Define:
- Roles: founder (2 to 4 hrs/wk), writer/producer, editor, video producer, AI assistant (Claude Code)
- Workflow stages: brief, draft, edit, approve, ship, measure
- Tooling: Airtable or Notion editorial calendar, CMS, Buffer or Hypefury for distribution, GA4 + GSC + Clarity for measurement
- Throughput: typical premium DTC ships 2 long-form + 8 to 12 short-form + 1 newsletter + 2 to 4 short-form videos per week
- Cost estimate: £3K to £8K per month depending on writer model

### Section 7. Distribution amplification (Full modes only)

Produce:
- Repurposing ladder: 1 long-form to 1 newsletter + 3-5 LinkedIn + 5-10 X + 2-3 short-form videos + 1 infographic
- Syndication partners: 2 to 4 podcast guest appearances per month, 1 newsletter swap per month, 1 guest article per quarter, 5 to 20 creator partnerships
- DM-lead-capture comment playbook: one trigger word per asset, DM within 24 hours, log conversions in daily dashboard

### Section 8. KPI framework (Full modes only)

Leading indicators (weekly):
- Publishing velocity
- Audience growth (absolute numbers)
- Time on page (2+ min target)
- CTR from GSC (3%+ target on page-1 rankings)
- Comment and reply rate
- DM-trigger conversions

Lagging indicators (monthly):
- Organic traffic (90-day rolling)
- AEO citations across ChatGPT, Claude, Perplexity, Google AI Overview
- Qualified leads or signups
- LTV of content-sourced customers vs paid-sourced
- Pillar-level revenue attribution

Review cadence: weekly (10 min), monthly (30 min), quarterly (2 hours), annually (half day).

---

## Audience Insights prompt (inlined for Section 1)

```
## ROLE
You are a senior DTC audience researcher. Mine public conversations for
authentic customer language. Compress findings into a one-page brief a
founder reviews in under 5 minutes.

## INPUTS (required; refuse if any missing)
1. Target audience (1 line)
2. Their #1 struggle (1 line)
3. What the brand sells and how it helps (1 line)

If any input is missing, return: "Unable to proceed without audience, struggle, and product."

## RESEARCH METHOD
- Sources: Reddit, Indie Hackers, Hacker News, X/Twitter long-form, Quora,
  YouTube comments, niche forums, blog comments. Prioritise long-form
  first-person accounts.
- Recency: last 12-24 months. Flag anything older.
- Collect 15 verbatim quotes revealing direct experience, emotional charge,
  specific solutions tried, exact phrases used, moments of realisation.
- Per quote: platform, approx date, primary emotion, any recurring phrase.

## DELIVERABLE
≤500-word one-pager:
1. Avatar (≤50 words)
2. Core tension (2 sentences, traces to quotes)
3. What they tried and why it broke (3-row table)
4. Market gap (1 sentence)
5. Recurring language (5-7 phrases from multiple quotes)
6. Headlines (3, ≤15 words each, using language from section 5)
7. Top 3 objections + responses (≤25 words each, from research)
8. Positioning angle (1 sentence)
9. Belief shift (1 sentence)

## APPENDIX: VERBATIM QUOTES (15)
Format: `#N | "[verbatim]" | [platform], [date] | [emotion] | [recurring phrase]`
Save to data/content-strategy/{YYYY-MM-DD}/icp-voc-mining.md

## RULES
- Every claim traces to a quote. No speculation, no invented stats.
- Use the audience's register.
- Spelling: "ecommerce" one word.
- No em dashes. No AI clichés. No "X, not Y" contrasts.
```

---

## Step 5. Synthesis pass (mandatory before writing to disk)

Do not write the document yet. Assemble the complete draft as a single document in your working context and read it end-to-end in one pass. Ask:

- What pattern crosses three or more sections that no single section captures?
- Does an ICP theme from Section 1 imply a pillar in Section 3 the founder's positioning understates?
- Does the channel mix in Section 5 underuse a format Section 1 says the audience prefers?
- Does the production workflow in Section 6 bottleneck a cadence Section 5 requires?
- Does the KPI framework in Section 8 fail to measure the belief shift from Section 2?

Produce 3 to 5 cross-cutting insight bullets. Each bullet:
- States the insight in one sentence.
- Names the sections it spans in brackets at the end.
- Is a synthesis of cross-section implications.

Then revise:
- **Executive summary** to lead with the narrative (3 to 4 sentences).
- **Section 9** to promote actions hitting multiple leverage points.
- Write the bullets into the **Cross-cutting themes** block immediately after the Executive summary.
- Generate the **top 3 highest-leverage moves for the next 90 days** block.
- Draft the **Conclusion** block (2 to 3 paragraphs, booking CTA at https://entirecommerce.ai/audit).

---

## Step 6. Voice enforcement gate (mandatory before writing to disk)

Run a mechanical voice-scan on the full draft. Grep for each banned pattern and rewrite every match:

| Banned | Grep for | Fix |
|---|---|---|
| Em-dash | `—` (U+2014) or `--` used as em-dash | Replace with period, comma, or colon |
| Negative parallelism | `, not `, ` rather than `, ` instead of `, `opposite of `, `not only ` | Rewrite to state the positive claim alone |
| Banned spelling | `e-commerce`, `E-commerce`, `E-Commerce` | Replace with `ecommerce` |
| AI clichés | `Here's the`, `Here's what`, `Here's why`, `Most people`, `The uncomfortable truth`, `The brutal truth`, `The breakthrough` | Rewrite without the cliché frame |
| Sub-four-word sentence | Sentences of 1 to 3 words standing alone | Merge into neighbour or expand |

`not` is permitted only when the negation is load-bearing. Default to rewriting.

Shipping with more than zero matches is a spec violation. Sub-agents must run the same scan before handoff.

---

## Step 7. Write outputs

Document structure (fixed order):

```
# Content Strategy: {Brand Name} ({YYYY-MM-DD})

Mode: {Full Reset / Refresh Quick / Launch Full / Launch Quick}
Path: {A existing / B greenfield}

## Executive summary
(3-4 sentences leading with the narrative)

## Cross-cutting themes
(3-5 synthesis bullets from Step 5)

## The three highest-leverage moves for the next 90 days
(top 3 from Section 9 with "why this first")

## 1. ICP-language audit
## 2. Positioning and differentiation synthesis
## 3. Topic pillar selection
## 4. Cluster architecture per pillar
## 5. Channel mix and cadence
## 6. Production workflow
## 7. Distribution amplification
## 8. KPI framework
## 9. ICE action list and 30-60-90 publishing roadmap

## Conclusion
(2-3 paragraphs, booking CTA)
```

Write to:

```
{cwd}/docs/content-strategy/{YYYY-MM-DD}/content-strategy.md
```

Convert to Word doc:

```bash
pandoc {cwd}/docs/content-strategy/{YYYY-MM-DD}/content-strategy.md \
  -o {cwd}/docs/content-strategy/{YYYY-MM-DD}/content-strategy.docx \
  --toc --number-sections
```

If pandoc is not installed, tell the user: `brew install pandoc`. Do not skip the Word doc silently.

Save supporting data to:

```
{cwd}/data/content-strategy/{YYYY-MM-DD}/
```

Include: `icp-voc-mining.md` (15-quote appendix), `pillars/{pillar-slug}-clusters.csv` per pillar, competitor content-footprint notes.

**Exactly one consolidated document at the primary output path.** Do not produce per-section files.

---

## Step 8. Merge into actions.md

If the current working directory has an `actions.md` file, merge the Days 1 to 30 items from Section 9 into the Next Actions section. Respect the priority caps (P0 max 5, P1 max 10, P2 max 15). Rescore by ICE and demote the weakest if any tier is over cap.

---

## Step 9. Commit (optional)

If the folder is a git repo, commit the strategy doc, Word doc, data files, and updated actions.md. Commit message format:

```
Content strategy: {Brand Name} ({YYYY-MM-DD}): {pillar commitment in 6 words}
```

---

## Section 9. ICE action list and 30-60-90 publishing roadmap

Every action from Sections 3 through 7 converts into a candidate initiative. Score each on ICE (Impact 1-10, Confidence 1-10, Effort 1-10 inverse). Multiply, rank descending, group into three buckets:

- **Days 1 to 30.** Foundation. Pillar pages drafted, editorial calendar live, first cadence held for 4 weeks, 15 ICP quotes accessible to the writer.
- **Days 31 to 60.** Momentum. Cluster pages shipping, repurposing ladder running, first syndication partner landed.
- **Days 61 to 90.** Compounding. Pillar page organic traffic showing, first AEO citation captured, founder-voice channel at target cadence, owned-audience growth verified.

Use bucket names in the output. No P0/P1/P2 labels client-facing.

---

## Voice conventions (strict, applied throughout)

- No em-dashes. Use period, comma, or colon.
- No negative parallelisms. State the positive.
- Four-word sentence floor.
- "ecommerce" one word.
- No AI clichés.
- Every claim traces to evidence (ICP quote, keyword data, competitor crawl, founder input).
- Plain English over internal shorthand. Avoid P0, binding constraint, highest-ICE, MMM-lite in client-facing output.

---

## Acceptance criteria

- End-to-end from this one prompt. No manual copy-paste between steps.
- Correct mode detection with user confirmation.
- Single consolidated document at the output path. Cross-cutting themes, top-3 moves, Conclusion populated by synthesis pass.
- Word doc produced alongside the markdown via pandoc.
- 15-quote ICP appendix saved to `data/content-strategy/{date}/icp-voc-mining.md`.
- 4 to 8 pillars with evidence package, cluster CSV saved per pillar.
- Voice enforcement gate run before write. Zero banned-pattern matches.
- Days 1 to 30 items merged into `actions.md` respecting caps.

---

## What to do with the output

The top three highest-leverage moves at the top of the document are your focus for the next 90 days. The Days 1 to 30 items in Section 9 go straight onto your team's Kanban. Hold the cadence from Section 5 for four weeks before judging whether the plan is working. Leading indicators show up inside 14 days; lagging indicators need 60 to 90.

Re-run this playbook annually, or sooner after a material positioning shift.

Want this run for you with a weekly content-review cadence, a daily publishing dashboard, and the full downstream content production stack? Book a call at https://entirecommerce.ai/audit.
