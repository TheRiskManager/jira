# Prompt — Recreate the "EMS Explore Map" (single-file interactive HTML)

Paste everything below the line into another LLM. It is a complete build brief: the subject matter (ground truth), the hard rules, the design system, the interaction model, and a view-by-view content spec. Build it as **one self-contained `.html` file** with no external dependencies.

---

## 0. Role & goal

You are building **`EMS_Master_Map.html`** — a single, self-contained, interactive HTML "explore map." It is a **teaching tool**, not a product UI. A reader lands on a top-down diagram of a system called **EMS**, clicks any box to zoom into a dedicated explainer view, and can also read the whole thing as a linear "Guided Walkthrough." Everything lives in one HTML file: inline CSS, inline SVG, a tiny vanilla-JS view switcher. No frameworks, no CDNs, no external fonts or images.

**Audience:** task-oriented developers and analysts who take language literally and will hold you to it. So: every claim must be precise and true to the model below; every conceptual view must use **plain, concrete language**; visuals must be clean and genuinely beautiful, not decorative filler.

**What success looks like:** a reader who has never heard of EMS can follow the numbered flow ①→⑤ on the map, click into any piece to get an accurate deeper explanation, and come away understanding how raw records become a checklist of evidence that a human signs off. The map is calm, spacious, and self-explaining.

---

## 1. The subject — ground truth you must encode (do not invent beyond this)

**EMS = Evidence Management System.** A governance-risk-compliance (GRC) application. Its one job: **turn records from three source systems into a checklist of evidence to collect — one proof per control, per application — then walk a Risk Manager through confirming and signing off every cycle.** EMS stores the *data elements* it needs, not copies of the source systems. It sits **between** a controls system (which holds the control library) and an application-portfolio system (which holds the list of apps).

### The spine: a five-step flow, ①→⑤
1. **PULL** — records arrive from the sources and land in the stores.
2. **RESOLVE** — every record is assigned its **Business Unit (BU)**.
3. **RULES** — an admin authors applicability rules (which apps a control covers).
4. **CROSS** — an engine crosses controls × apps, applies the rules, and lands each pairing in a **2×2** pattern.
5. **EVIDENCE** — each applicable control-and-app pairing becomes one **evidence slot** to fill.

These five, in order, are the only things that carry a number badge. Everything else on the map (reference tables, config) is an **input or a setting**, not a step — it must NOT be numbered.

### The four sources (what feeds ① PULL)
- **Applications** — the application portfolio, from the app-portfolio system (call it *LeanIX* in examples).
- **Archer records** — the control library, from the controls system (call it *Archer*), arriving as **three record types**:
  - **Reference Controls** — what a framework *demands* (authentic examples: NIST 800-53r5 AC-2, RA-5, SI-2; NIST 800-171r3 03.01.01).
  - **Business Processes** — the real areas of the business (e.g., Accounting, Trading, HR, Billing), plus governance processes (e.g., Vulnerability Management Governance).
  - **Control Procedures (CPs)** — *how we actually meet* a requirement. A CP is the working unit EMS operates on.
- **Admin-maintained** master data — curated by an admin **by hand**: the **Business Units catalog** (the master list every resolution points at) and the **BU Match Token** table (name/alias → BU, used by Tier 1 resolution).
- **Engineer-configured** reference data — curated by **engineers**: the **connectors** (e.g., GitHub, Qualys, Okta, SIEM) and the **named checks** (one precise pull per evidence source) that evidence can be collected from.

Admin-maintained and Engineer-configured are **reference inputs**, not flow steps: they get an "open →" affordance but **no number**.

### ② RESOLVE — how a Business Unit is assigned
- **Applications** resolve in **two tiers**: **Tier 1** matches a **BU Match Token** against a **path segment**; if that misses, **Tier 2** matches an **exact org-unit path** (sync-discovered, admin-mapped). Anything matching nothing → **Unresolved**; matching two → **Ambiguous**; both are flagged for a human.
- **Control Procedures** inherit their BU, **ownership**, and **scope** from their **parent Business Process**.

### The 2×2 (what ④ CROSS produces) — the core mental model
Two independent dials:
- **Ownership:** **Horizontal** (owned centrally by governance) **vs BU-owned** (run by a real business area — operations).
- **Scope:** **Common** (proven **once**, at one point) **vs Per-app** (proven **separately on every application**).

Crossing them gives four patterns. The rule's scope **is** the column axis — the rules are not a filter layered on top of the 2×2; they *are* how the axes are set and which apps are in play.

**The fan-out (state this explicitly):** a **BU Per-app** control owned by a unit that runs **200 applications** produces **200 applicability records — one per app**. You set the control's unit, scope, and evidence configuration **once**; all 200 inherit them. You never configure a pairing by hand.

**Also true:** the *same* underlying control can appear as **multiple CP records** (different IDs) under different **BU-owned** processes; a **Horizontal** control appears **once**. Governance processes are Horizontal; operational processes (Accounting, Trading, HR…) are BU-owned and run on their apps.

### ⑤ EVIDENCE — how slots get filled (evidence collection)
- The **bindable unit is the CHECK** — a precise, named pull inside a connector (e.g., `github · pr-review-approvals`), **not** the connector as a whole (one system can hold evidence for many controls and apps).
- **Collection config is per-Control-Procedure**, set **once** (there are only a few hundred controls, so this is authored, not automated), and **inherited by every slot** in the fan-out. The config **rides on the control**.
- **Auto:** where the proof is a precise named check, **engineers bind it** and the system collects it (aggregator-pull or app-pull).
- **Manual:** where it isn't, an **AI agent drafts the requirement** from the control's description, a **human approves** it, and the **Risk Manager or app owner uploads** the file (RM-upload or owner-upload).
- Do **not** offer a rigid "evidence type" dropdown — auto is engineer-precise, manual is AI-recommended.
- **Collection ≠ sufficiency:** a filled slot is evidence *captured*, not evidence *judged*.

### The operational cycle (the sign-off) — six gates, in order
Nothing ships silently. Each run is a gated cycle a **Risk Manager** steps through; each gate blocks the next until confirmed:
**Detect Changes → Verify Application BU → Verify Control-Procedure BU → Confirm Rules → Review Output → Sign-off.**
**Sign-off** is where it becomes real: the cycle completes, removed controls/apps are retired, **Evidence records are produced, their SharePoint folders are created, and notifications are sent.**

### Why it lasts (the closing idea)
The spine is **deterministic** — the same 2×2 runs for every control. **AI only helps at the edges** (drafting manual requirements, recommending checks). Today the *cargo* is information-security controls; tomorrow it can be AI controls, with **no change to the engine**. Only the cargo changes.

---

## 2. Hard rules (non-negotiable)

1. **One file.** Self-contained HTML. All CSS inline in one `<style>`; all diagrams inline SVG; one small `<script>`. No external requests of any kind. System font stack only (`'Segoe UI', system-ui, Arial`).
2. **Conceptual views use plain language.** In any teaching/zoom view: **no database field or schema names**, **no internal decision-record ("ADR") references**, no acronym soup. Say "the Business-Unit catalog," not a table name. (A deliberate *backend/store mockup* view may show realistic field names — but the conceptual explainers may not.)
3. **Accuracy over embellishment.** Every statement must be supported by §1. Never pad with invented specifics. If you need an example, use the authentic ones named above.
4. **Numbering discipline.** Only ①–⑤ (the flow spine) are numbered. Reference inputs and settings are never numbered; they may carry an "open →" affordance.
5. **Beautiful and calm.** Generous whitespace, consistent rounded cards, a restrained palette, clear hierarchy. No clutter, no crossing-arrow spaghetti. If a diagram feels crowded, spread it out.
6. **Consistency.** Uniform "open →" pills, uniform back buttons, uniform badge treatment, uniform card styling across every view.

---

## 3. Design system

**Palette (roles → hex):**
- Flow badges: ① indigo `#4f46e5` · ② blue `#2563eb` · ③ teal `#0d9488` · ④ violet `#7c3aed` · ⑤ green `#16a34a`.
- Admin / teal family: `#0d9488`, `#0f766e`, surfaces `#f0fdfa`, border `#99f6e4`.
- Engineers / orange family: `#d97706`, `#b45309`, surface `#fff7ed`, border `#fed7aa`.
- Archer / blue family: `#2563eb`, surface `#eff6ff`.
- Evidence / green family: `#16a34a`, `#059669`, surface `#ecfdf5`.
- Neutrals: page bg `#eef1f8`; ink `#1e293b` / `#0f172a`; muted `#64748b` / `#94a3b8`; hairline `#e2e8f0`.
- Dark top bar: `#0f172a`.

**Type:** `'Segoe UI', system-ui, Arial`. Titles 20–23px/800; body 13–15px/1.6; labels/kickers 11–12px/800 uppercase with letter-spacing.

**Core components:**
- **Top bar** (sticky, dark `#0f172a`): brand "EMS" + two **Level-1 tab buttons** ("Explore the Map", "Guided Walkthrough") + a breadcrumb span + a right-aligned hint span. Active tab = white pill on dark.
- **Stage** (the map card): white, `border-radius:18px`, soft shadow `0 10px 34px rgba(15,23,42,.12)`, `max-width:~1380px`, centered, `overflow:hidden`. `svg{width:100%;height:auto;display:block}`.
- **Hotspots:** transparent `<button class="hot">` absolutely positioned over the SVG in **percentages**; on hover show a subtle indigo tint + 2px inset ring (`rgba(67,56,202,.55)`).
- **Zoom pages:** a back "← Home" button (`.zbar`, indigo `#4338ca`), a title, then either a `.zstage` (white card holding an SVG) or a `.phwrap`/`.storywrap` (max-width ~860px prose card) for text-led explainers.
- **Boxes in SVG:** rounded rects (`rx 12–14`), 2–2.4px colored stroke, a small soft drop-shadow rect behind, an uppercase "pill" header tag, 1–2 inner "row" chips, and a small **"open →"** pill bottom-right when the box is clickable.
- **Badges:** filled circles with the step number, colored per the palette above.
- **Arrows:** thin (1.4–2px) curved paths with small triangular arrowheads (SVG markers); dotted for "reference/looks-up" links, solid for flow. Label arrows with tiny 7–8px captions.
- **End-to-end writeup card** (`.e2e`): a rounded white→pale-blue gradient card with a small indigo kicker, a bold title, a lede, a list of numbered steps (colored circular badge + heading + paragraph, thin top-borders between), and an amber footer note. Scope its CSS with the `.e2e` prefix so it can't collide with page styles.

---

## 4. Interaction model (implement exactly)

- A single `show(id)` function: hides all `.view`, shows `#id`, sets the breadcrumb from a `names` map, toggles the active Level-1 tab (the "Guided Walkthrough" tab is active only when `id === 'example'`), updates the hint text, and scrolls to top.
- `.view{display:none}` / `.view.active{display:block}`.
- **Esc** returns to `home`.
- Hotspots call `show('<viewId>')`.
- **Hotspot math:** each hotspot's `left/top/width/height` in **%** = the target SVG rect's `x / y / w / h` divided by the SVG's `viewBox` width/height × 100. (If you move or resize the SVG's viewBox, recompute every hotspot.)

---

## 5. The map (`home`) — detailed spec

One tall SVG (aspect roughly 1240×1570, portrait, spacious). Top-down, five bands with clear vertical gaps between them:

- **Actors row (top, above the system box):** a small feed-preview for each source ("today · LeanIX — 1 file", "today · Archer — 3 files" listing Reference Controls / Business Processes / Control Procedures), plus two **actor** chips: **Admin** (teal, "a person") and **Engineers** (orange, "configure connectors + checks").
- **The EMS system container:** one large rounded rect labeled "EMS — the system" enclosing the whole flow.
- **Input row (inside EMS, four peer boxes at the same level):**
  1. **① Applications** (indigo badge) — "records · LeanIX".
  2. **Admin-maintained** (teal, no number, "open →") — rows: *Business Units* (master BU catalog), *BU Match Token* (token → BU, Tier 1). Fed by the Admin actor via a "maintains" arrow.
  3. **Engineer-configured** (orange, no number, "open →") — rows: *Connectors* (GitHub · Qualys · Okta), *Checks* (named pulls · per source). Fed by the Engineers actor via a "configures" arrow.
  4. **① Archer records** (blue badge, "open →") — bullets: Reference Controls, Business Processes, Control Procedures.
- **Resolve row (②):** left = **Resolve Application BU** (two tiers inside: *try BU Match Token — token = path segment*; on "no match falls back", *try BU Org-Unit Mapping — exact full-path match*). Right = **Resolve BP & CP BU** ("the two dials the rule engine will cross") with two inner stages: *Ownership: Horizontal / BU-owned* and *Scope: Common / Per-app*.
- **③ Rules Catalog (center):** **Applicability rules** — "which apps a control covers · Common / Per-app", with a line about exclusions / compliance drivers / BU patterns.
- **CP Evidence Config (right, green, no number, "open →"):** "per CP · set once · method + check · rides on the control → inherited by every slot." A dotted "looks up the checks" line runs up to the Engineer-configured box; a green "inherited by every slot · 1 per app" arrow runs down to ⑤.
- **④ Rule engine (center):** "runs the rules × ownership → the 2×2 (the evidence pattern)."
- **⑤ Evidence (center-bottom):** "fill the slots — one slot per app · inherits the CP's config."
- **Arrows across the flow:** "the app record" and "the process record" feed ② from ①; "used in resolution" from Admin-maintained → Resolve App BU; "admin also authors" from Admin-maintained → Rules Catalog; "the resolved records" from both resolve boxes → ④; "the rules" from ③ → ④.
- **Below the container:** an amber callout **"Reference Control vs Control Procedure — commonly confused"** (Reference Control = the requirement a framework demands; Control Procedure = how we meet it and the evidence that proves it), and a **"HOW IT FLOWS — read the map ①→⑤"** legend strip summarizing the five steps.

**Then, at the bottom of the home view (outside the SVG):** the **end-to-end writeup card** from §7.

---

## 6. Zoom views — build each of these

Each is reachable from a hotspot or a link, and each has a "← Home" back button. Keep every conceptual view in plain language (rule 2).

**Primary teaching views**
- **`rules`** — *The rules: the applicability rule set the admin writes.* What a rule declares (which apps a control covers), the inputs (BU, compliance driver, pattern, exclusions), and that rules are authored once and reviewed each cycle. Include one clean worked example table with illustrative colors.
- **`rule`** — *The rule engine: the 2×2 control-scope model.* The single clean 2×2 (Ownership × Scope), plain-language reading of each quadrant, a band stating "the engine runs once per Control Procedure," chips annotating the axes (BP → row, rule → column, condition → apps), a color-coded worked-example table, and an explicit **fan-out callout** (BU Per-app × a unit owning 200 apps → 200 applicability records; all inherit the one config).
- **`clarity`** — *The whole thing in one picture.* Both sides (app side vs control side) meeting at the rule engine, producing evidence. A one-glance summary diagram.
- **`cpevidence`** — *CP Evidence Collection — the full design.* The complete evidence-collection model: the CHECK as bindable unit; per-CP config set once and inherited; auto vs manual routing (bound check → auto; else AI-drafts requirement → human approves → upload); the four methods (aggregator-pull, app-pull, RM-upload, owner-upload); the control↔check and app→identity joins; the Check Registry; and "collection ≠ sufficiency."
- **`appbu`** — *Resolve Application BU (overview + Tier 1 + Tier 2 in one view).* Tier 1 = BU Match Token on a path segment; Tier 2 = exact org-unit path; both look up the Business Units catalog; Unresolved / Ambiguous outcomes.
- **`bpbu`** — *Resolve BP BU → Resolve CP BU (control side, one view).* A CP inherits BU + ownership + scope from its parent Business Process; the two dials (Horizontal/BU-owned, Common/Per-app).

**Source & store views**
- **`leanix`** — *A · Applications:* the cargo, the story, and its data elements.
- **`archer`** — *B–D · The Archer files:* Reference Controls, Business Processes, Control Procedures — cargo, story, data.
- **`mdapp`** — *Master data · the Applications store.* (Backend mockup: realistic field names allowed here.)
- **`mdarcher`** — *Master data · the Archer stores.* (Backend mockup.)
- **`mdadmin`** — *Master data · the admin-maintained store.* (Backend mockup.)

**"App view, explained" set** (short, icon-led explainers of each entity as seen in the app)
- **`rc`** Reference Controls · **`bp`** Business Processes · **`cp`** Control Procedures · **`app`** Applications · **`bu`** Business Units.

**Supplementary explainers** (prose cards; keep if useful)
- **`ingest`** — how the source files come in (the ingestion story).
- **`bureflists`** — the admin-maintained BU reference lookups (read-only during the sync).
- **`adminman`** — admin-authored manual config (Business Units catalog + match tokens).
- **`adminsync`** — sync-discovered → admin-resolved mappings (org-unit and BP-to-BU).
- **`manual`** — setting an Owning BU by hand (override outside the sync).
- **`proof`** — proof slots → evidence (where chosen pairs become concrete slots).

---

## 7. The Guided Walkthrough (`example`) + the end-to-end writeup

- **`example`** is the second Level-1 tab: a **linear narrative journey** (not a bulleted list) that walks one record end to end through ①→⑤ with sample data — every feed, every case (admin-authored, sync-discovered, business-process feeds, resolution, rules, the 2×2, evidence). Give it a spine with milestones and a short **story vignette at each stop**. Include a small table of evidence slots so the reader sees them like the 2×2 table.
- **The end-to-end writeup card** (§3 `.e2e`) appears at the **bottom of BOTH** the `home` view and the `example` view, identical in both. Its content, in order:
  - Kicker "READ IT STRAIGHT THROUGH"; title **"The whole workflow, end to end"**; lede (EMS's one job, per §1).
  - Six steps with colored badges: **① Pull** (the four sources) · **② Resolve** (two-tier app BU; CP inherits ownership+scope from its BP) · **③ Rules** (admin declares coverage) · **④ Cross** (the 2×2 + the 200-app fan-out) · **⑤ Evidence** (slots; auto vs manual; collection ≠ sufficiency) · **↻ The cycle** (the six gates in order; sign-off produces evidence records + SharePoint folders + notifications).
  - Amber footer **"Why it lasts"** (deterministic spine, AI only at the edges, cargo can become AI controls with no engine change).

---

## 8. Build approach & quality bar

- **Build the SVGs programmatically** (e.g., a small script that emits SVG strings) rather than hand-typing coordinates; it makes spacing and alignment consistent and editable.
- When inlining multiple SVGs into one file, **namespace every `id`** (markers, gradients, filters) per-diagram (e.g., prefix `m0_`, `ce_`, `ru_`) so definitions don't collide.
- **Render-and-verify loop:** after each diagram, render it to an image and actually look at it; fix overlaps, crossing arrows, clipped text, and misaligned hotspots before moving on. Re-verify hotspot alignment by overlaying the hotspot rectangles on the render.
- **Spacing check:** if any band feels crowded, increase the viewBox and open the gaps (and recompute hotspots). Prefer calm over dense.
- **Final pass:** confirm one file with no external requests; ①–⑤ numbering is correct and nothing else is numbered; no field/schema/decision-record names leak into conceptual views; every clickable box has a uniform "open →" and a working hotspot; the end-to-end writeup is present and identical on both tabs; Esc returns home.

**Deliverable:** the single `EMS_Master_Map.html`, ready to open in any browser.
