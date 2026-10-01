# Clay prospect landing pages

Personalized, Clay-branded landing pages for prospects who requested a Clay.com demo. The user (Ashwin Sadananthan) is the Account Executive; each page primes the prospect for the demo and pushes them to book a time on Ashwin's calendar.

## Inputs (read these first)
- `landing-page-prospects.csv` — 5 prospects: Sarah Mitchell (VP RevOps, Retool), Marcus Chen (Head of Growth, Linear), Emily Rodriguez (Dir. Sales Development, Loom), James Okonkwo (GTM Engineer, Webflow), Rachel Goldstein (VP Sales, Airtable). The LinkedIn URLs look like placeholders; don't rely on them.
- `clay_icp.txt` — ICP, buyer personas, the 7 trigger pain points.
- `clay_value_prop.txt` — product pillars and use cases. **Its scale numbers are stale** (5,000 customers / $3.1B / 150+ providers).
- `clay-brand-book.md` (+ `.html`) — colors, type, layout, components, motion, current proof points, governance. Source of truth for design.
- `clay-tone-of-voice.md` — voice rules, vocabulary, proof formula, headline and CTA patterns. Source of truth for copy.
- `clay assets.zip` (unzipped to `clay assets/`) — real Clay logos, Roobert trial font, animation clips, footer ball-pit still, founder photos.

## Decisions the user made
- Research each company on the web (plus Clay MCP) and personalize as much as possible. Cite public sources on the page. Never invent facts about the prospect.
- No call notes or CRM context exists for any prospect.
- CTA: book the demo on Ashwin's calendar link.
- Clay branding, prospect's company name and logo on the page, and Ashwin shown as the AE.
- Tailor to awkward facts (e.g. Loom is now part of Atlassian; some companies are above the 50–500 employee ICP).
- Customer names and proof points may be used, but only current ones (see below).
- Build one page at a time and get feedback before doing the rest.

## Current state (2026-09-28)
- `landing-pages/retool-sarah-mitchell.html` — v1, generic styling, superseded.
- `landing-pages/retool-sarah-mitchell-v2.html` — v2, built on the brand book and tone guide.
- `landing-pages/retool-sarah-mitchell-v3.html` — **v3 (2026-09-29), redesign of v2 using the `frontend-design` skill.** Same copy and facts. Awaiting user feedback on v2 vs. v3. v3 changes: the hero is the animated sample table (columns fill left to right on load, "Run again" replays; the only non-user motion); proof as a sentence with static logos instead of the marquee; Retool signals as a dated timeline; build vs. buy as a layer diagram; agenda as a bar sized by minutes; no eyebrow chips, no `→` on buttons, no `·` separators; accent second line kept only in the play cards. Copy later rewritten with `unslop`.
- `landing-pages/retool-sarah-mitchell-v4.html` — **v4 (2026-09-29), content and design rebuilt from scratch; newest, awaiting feedback.** About half the length of v3. Structure: green hero ("Your Clay demo, planned around Retool") with `reps.webm`; a signed letter from Ashwin beside a sticky "Your demo" booking card; Retool timeline (dark band) ending in a stated guess; the demo table (animates when scrolled into view) with four product-area cards underneath, one per colored column (Data/Anthropic, Orchestration/Mistral AI, Agents/Merge, Execution/Intercom); 30-minute agenda; ball-pit booking card. Cut from v3: the four stacked play cards, build vs. buy, the proof strip (one proof line now sits in the booking card).
- `landing-pages/assets/` — renamed copies used by the pages: `clay-logo-black.png`, `clay-logo-white.png`, `roobert-vf.ttf`, `footer-still.avif`, and `data` / `agents` / `orch` / `execution` / `reps.webm`. Keep this folder alongside the HTML files.
- `landing-pages/linear-marcus-chen.html` — Linear page (2026-09-29), built from v3. Public at https://vercel-linear-blush.vercel.app (Vercel project `vercel-linear`, deploy folder `landing-pages/vercel-linear/`). Angle: 40,000+ paying companies and 177% NRR, so find which self-serve workspaces belong to large companies; objection block is "Will this feel like a growth hack?" (Linear says it grew without A/B tests, SEO or growth hacks). Linear colors from linear.app live CSS: `#08090a` / `#f7f8f8` / `#7170ff`, muted `#8a8f98`, line `#37393a`. Facts from Linear's own posts (Series C June 2025; "Sharing growth" Aug 26 2026) and careers page. Table hides the CRM column below 1180px and engineers below 1000px because its cells are longer than Retool's.
- Not started: Loom, Webflow, Airtable.
- `landing-page-prospects.csv` has a `landing_page` column; fill it in as each page goes live.
- GitHub (2026-09-30): the whole folder is in the public repo https://github.com/AshwinSadan2/clay-landing-pages (`main`, `gh` logged in as `AshwinSadan2`). `.gitignore` leaves out `clay assets.zip` (over GitHub's 100 MB limit; the unzipped folder is committed), `.DS_Store` and `.vercel/`. Commits use the GitHub no-reply email set in the repo's git config. Commit and push after changes when the user asks.

## v2 page structure (reuse for the other prospects unless v3 is chosen)
1. Sticky nav: Clay logo × prospect mark, "Prepared for …", CTA.
2. Dark-green (`#035D44`) hero: two-line headline (second line in lime), lede, CTAs, `reps.webm`.
3. Proof marquee: logos interleaved with stats.
4. Prospect-colored band: 4 sourced public signals + a "what that means for [role]" line.
5. Four sticky stacked play cards, one Clay accent family each: Orchestration/lime/`orch`, Data/blueberry/`data`, Agents/tangerine/`agents`, Execution/dragonfruit/`execution`. Each gets a named-customer proof line.
6. Sample Clay table (fictional rows, labeled as such).
7. A company-specific objection block (for Retool: "you build software for a living", build vs. buy).
8. 30-minute demo agenda, "No slides."
9. Final CTA card over the ball-pit image with the AE card; footer marked as a private preview.

## Rules to keep following
- Proof points (July 2026): 500,000+ GTM teams · $5B valuation · 200+ data providers · 140M monthly Claygent runs · 4.9★ G2. Customer proof uses the format **Company** + metric + mechanism: Anthropic 3x enrichment, Merge +15% enterprise meetings, Intercom +140% outbound pipeline, Mistral AI TAM mapping cut from 2 months to 10 days. Drop any claim without a source (e.g. "80% less research").
- Voice: second person, verb-first, contractions, no exclamation marks, no emoji, never name competitors, at most one rhetorical question per page.
- Copy must not sound AI-written. Apply the `unslop` skill (`~/.claude/skills/unslop/`) to every page: no stacked fragments, no "X, not Y" or mirrored contrasts, no forced threes, no em dashes, colons only before lists, no lines about the page itself. Write as Ashwin talking to the prospect in plain sentences. This overrides the tone guide's fragment and setup-payoff colon patterns. v3 of the Retool page (2026-09-29) is the reference.
- Design: Roobert (Schibsted Grotesk fallback), headings at line-height 1.0 and weight 500–575, 12px button radius, flat color with no shadows, max width 1280px.
- Partner colors go in the page, never in either logo. Pull partner hex values from their live site, not from memory. Retool: `#151515` / `#e9ebdf` / `#e8765e`.
- Hosting (user decision, 2026-09-29): v3 is the chosen template. Pages deploy to Vercel as **protected preview deployments** (Vercel login required, so only Ashwin can view; prospects can't yet). Deploy folder: `landing-pages/vercel-retool/` (v3 as `index.html`, only the assets it uses, `vercel.json` with a noindex header). Keep the Roobert trial font only while previews stay protected; before anything public, swap to Schibsted Grotesk or get a license, add the real calendar link, and get logo permission. Never `--prod` or turn off protection without asking. Vercel account `ash-4456`, project `vercel-retool`. Current protected preview (2026-09-29): https://vercel-retool-oeoiytpoz-ash-4456.vercel.app. **Update 2026-09-29: user asked to make it public.** v3 is now on production at https://vercel-retool.vercel.app (public, noindex), knowingly shipped with the Roobert trial font and the `{{CALENDAR_LINK}}` placeholder (booking buttons broken). Public redeploys use `npx vercel deploy --prod --yes`; the preview-only rule above applies to new pages until the user says otherwise. Trap: a project's *first* `vercel deploy` goes to production, and the production domain (`vercel-retool.vercel.app`) is public on Hobby; that happened once and the deployment was removed. For a new project, check with plain `curl` that every URL returns 302/404, not 200. Redeploy after edits: copy the page to `vercel-retool/index.html`, then `npx vercel deploy --yes` from that folder, and verify with `npx vercel curl <url>`.
- Check layout with headless Chrome screenshots. Headless Chrome has a minimum window width of ~500px, so check phone widths with an iframe probe, not a screenshot.

## Open items from the user
- Calendar link: pages use the `{{CALENDAR_LINK}}` placeholder (7 occurrences in v2).
- Ashwin's work email and headshot (the page currently shows "AS" initials).
- Actual demo length (the page says 30 minutes).
- Roobert is a trial license and needs a real one before pages go to real prospects. The Clay logo needs permission from press@clay.com for public use.
