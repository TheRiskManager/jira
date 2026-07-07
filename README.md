# EMS — Seeded Backlog (Epics 1–7)

Derived from **EMS_Master_Map.html**. This is the buildable decomposition of the map — the map is the *context* (the whole system, the why); this is the *work*. Stories are written to be picked up cold: **why it exists · acceptance as an invariant · done proves both branches · where scope ends · where it grounds in the map.** No story says *how* — that's the dev's call.

---

## How to use this

- **Map whole, work narrow.** Share the map for orientation; hand out stories one at a time off this backlog. The map stays put as reference.
- **Estimates are a planning anchor, not the team's commitment.** Points below are mine, for *your* sequencing/roadmap. Let the team estimate for *their* commitment in planning — they own the number they build against. 1 pt ≈ 7.5h is a placeholder until measured velocity replaces it; the *relative* sizes are the durable signal, the hours are soft.
- **Fibonacci scale (2/3/5/8).** An 8 is a "consider splitting" flag, not just a big number.
- **Status per epic** (three buckets — the same lens as your CIO roadmap slide, pointed at the build):
  - **FOUNDATION** — built or substantially built in the current package; assign as *verify against tenant*, not net-new.
  - **BUILD** — designed in the map, not yet built; this is assignable build work.
  - **DESIGN-FIRST** — not yet designed; the first story is a spike, and build stories are blocked until it closes. Do **not** hand these out as build tasks.
- **Every story's done standard** is your closure bar: 4-box hygiene (Schema · ADR · Registry · File Inventory) closed **and** tenant test green — not spec-complete.
- IDs are illustrative (`L1-P-01`, etc.). Slot them into your real numbering. Cycle-stage tags: PULL ① · RESOLVE ② · RULES ③ · CROSS ④ · EVIDENCE ⑤ · SIGN-OFF ⑥.

---

# EPIC 1 — Ingestion & Data Contract (PULL ①)  · *FOUNDATION*

**Why:** every downstream stage reads from the reconciled stores. Nothing runs until raw source data lands, clears, and becomes a governed record. The mouth of the pipeline.
**Boundary:** in — a raw source file (1 LeanIX apps file; 3 Archer files: RC/BP/CP); out — a reconciled store record carrying the agreed data elements plus what EMS stamps on. Out of scope: BU resolution (Epic 2), the live-API carrier.
**The contract is the point:** the 32 app data elements and the 3 Archer crates (RC 3 / BP 4 / CP 11) are the fixed cargo. The carrier is swappable; the elements and their meaning are not.
**Scope decision to pin up front:** today's carrier is file-based. Scope this epic to **file ingestion only**, lock the loading-dock contract so the carrier is swappable, and leave live API as a later carrier-swap story. That keeps Epic 1 shippable now and blocks nothing downstream.

**L1-P-01 — Land the LeanIX app feed into staging** · **3 pts**
- *Why:* the app file must arrive in a cleared workspace before reconciliation — staging is the raw catch, wiped each run so no stale rows survive.
- *Acceptance (invariant):* for any LeanIX apps file, every row lands as a staging record with all delivered columns intact; staging is fully cleared at the start of each run so it holds only the current file's rows.
- *Done proves:* a fresh file populates staging · a second run wipes the first run's rows before loading.
- *Scope out:* reconciliation into the store, BU resolution, the Archer files.
- *From map:* LeanIX FEED (1 file · raw) → STAGING (cleared each run).

**L1-P-02 — Reconcile staged apps into the Applications store** · **5 pts**
- *Why:* staging is disposable; the Applications store is the governed record that survives across cycles. Reconciliation is where a raw row becomes the store's app.
- *Acceptance (invariant):* for any staged app row, the Applications store holds a reconciled record carrying the delivered cargo (the 32 fed fields), matched on `pei_displayname`. An existing app updates in place; a new app is created.
- *Done proves:* a new app creates a store record · a returning app updates its existing record rather than duplicating.
- *Scope out:* the EMS-derived fields (next story), staging load (prior story).
- *Pin:* match key is **`pei_displayname`**, not the LeanIX ID — the ID fails at runtime.
- *From map:* STAGING → APPLICATIONS STORE (reconciled record · 32 fields fed).

**L1-P-03 — Stamp the EMS-derived fields on the app record** · **3 pts**
- *Why:* the store isn't just delivered cargo — EMS adds the fields it governs itself. These make the record auditable, not merely present.
- *Acceptance (invariant):* on reconcile, every Applications-store record carries EMS-owned fields distinct from fed cargo — a change fingerprint to detect the next change, and an audit trail of who touched it and when.
- *Done proves:* a changed record updates its fingerprint · an unchanged record's fingerprint is stable · every write records who/when.
- *Scope out:* Owning BU (Epic 2) and lifecycle retirement (next story) — separate EMS-added fields, separate logic.
- *From map:* "EMS ADDS · glowing" — change fingerprint, audit trail.

**L1-P-04 — Retire apps that drop out of the feed (soft-delete)** · **3 pts**
- *Why:* an app leaving the feed must not vanish — last year's evidence and cycles must survive for audit. Removal is a status change, never a delete.
- *Acceptance (invariant):* for any store app absent from the current feed, the record is marked retired (soft-delete) and is never removed; if it reappears in a later feed, it is reactivated. The store only ever grows.
- *Done proves:* a dropped app flips to retired and its record/evidence persist · a returning app reactivates the same record.
- *Scope out:* what retirement does to that app's downstream evidence (a later-cycle concern), the fed fields.
- *From map:* Lifecycle Status — "why retired, not deleted"; soft-delete, reactivates, history never lost.

**L1-P-05 — Land the 3 Archer files into staging** · **5 pts**
- *Why:* the control side arrives as one shipment, three crates — RC, BP, CP — each landing raw before reconciliation, same as the app feed.
- *Acceptance (invariant):* for the RC, BP, and CP files, every row lands in its staging area with delivered columns intact (RC 3 fields, BP 4, CP 11); staging clears each run.
- *Done proves:* each of the three files populates its staging area · a re-run clears prior rows.
- *Scope out:* reconciliation, the links between the three (next story), resolution.
- *From map:* ARCHER FILES (3 files · raw) → 3 ARCHER STORES.

**L1-P-06 — Reconcile the 3 Archer stores and resolve their links** · **8 pts** ⚠ *split candidate*
- *Why:* the three control records aren't independent — the CP is the hub pointing at its parent BP and the RCs it satisfies. Reconciliation must turn those text-ID references into real relational links, or the engine can't traverse them.
- *Acceptance (invariant):* for staged Archer rows, each store holds a reconciled record with fed cargo; a CP's Parent Business Process resolves to the real BP record, and its Reference Controls (newline-separated ID list) resolve to real RC records. Existing records update, new ones create.
- *Done proves:* a CP links to its parent BP · a CP with multiple RC IDs links to each · an unresolvable reference is surfaced, not silently dropped.
- *Scope out:* BU classification of the BP (Epic 2), staging load (prior story).
- *Split note:* at 8, carrying three reconciliations *and* link resolution. Consider "reconcile the 3 Archer stores" (~5) + "resolve CP links" (~5) — de-risks the biggest story in the foundation.
- *From map:* "How the 3 Archer files connect" — CP is the hub, FK→PK; Parent Business Process and Reference Controls are the linking keys.

**Epic 1 subtotal: 27 pts** · app track (P-01→04) and Archer track (P-05→06) are independent — two devs can run parallel and meet at the reconciled stores.

---

# EPIC 2 — Business Unit Resolution (RESOLVE ②)  · *FOUNDATION*

**Why:** every app and control must carry an Owning BU before the engine can filter or scope anything — BU is the key both worlds meet on. No BU, the engine can't place the record.
**Boundary:** in — a reconciled app record (org-path) or a BP/CP record (parent link); out — Owning BU stamped, or a flag (Unresolved / Unmapped) routing it to an admin. Out of scope: what the engine does with the BU (Epic 4 / CROSS), how records arrive (Epic 1 / PULL).
**Two sub-areas:** app-side (path-based, automated, three outcomes) and control-side (admin-classified process, inherited by procedures).

**L1-R-01 — Resolve app BU by token match (Tier 1)** · **5 pts**
- *Why:* an app's BU derives from its org-path; the fast first pass matches known BU tokens against path segments.
- *Acceptance (invariant):* for any app, splitting its org-path on "/", when exactly one segment equals an active BU Match Token, Owning BU = that token's BU. Two or more matching segments → flagged Unmapped, no BU set. Zero → falls through to Tier 2, no BU set, no flag yet.
- *Done proves:* a 1-match app resolves · a 0-match app sets nothing and passes on · a 2+-match app is flagged Unmapped.
- *Scope out:* override, Tier 2, what happens to a flagged app after the admin sees it.
- *From map:* BU Match Token / Tier 1; traced SAP (1→Finance), Legacy Billing (0→fall through), Data Platform (2→Unmapped).

**L1-R-02 — Tier 2 exact org-path backstop** · **3 pts**
- *Why:* apps whose path has no token match still need a BU; the exact full path is the deterministic backstop.
- *Acceptance (invariant):* for any app Tier 1 left unresolved, when its exact full org-path exists in the BU Org-Unit Mapping, Owning BU = the mapped BU. When it does not, the app is flagged Unresolved and a flagged row is created for the admin.
- *Done proves:* a path present in the map resolves · a path absent flags Unresolved and creates the admin row.
- *Scope out:* Tier 1, override, the admin's manual fill of the Unresolved row.
- *From map:* Resolve Application BU / Tier 2; traced Confluence (hit → Platform Eng), Legacy Billing (miss → Unresolved).

**L1-R-03 — Admin override precedence** · **2 pts**
- *Why:* admins must be able to hand-set a BU the tiers would get wrong, and that decision must stick.
- *Acceptance (invariant):* for any app where the BU-override flag is set, Owning BU = the admin's value and neither tier runs. When unset, resolution proceeds to the tiers.
- *Done proves:* an override-set app keeps the admin BU with tiers skipped · an override-unset app runs the tiers.
- *Scope out:* the UI for setting the override; the tier logic itself.
- *From map:* "override first, then Tier 1, then Tier 2"; traced Okta (override → keep Engineering, tiers don't run).

**L1-R-04 — Classify a Business Process to a BU** · **3 pts**
- *Why:* control-side records get their BU from a human classifying the process, not from path-matching — the one admin decision every child control inherits.
- *Acceptance (invariant):* for any Business Process, admin sets BU-owned + target BU → Owning BU = that BU; set Horizontal → Owning BU = Horizontal; left unclassified → Owning BU empty, process Unresolved. BU-owned and Horizontal both count as resolved.
- *Done proves:* a BU-owned BP carries the BU · a Horizontal BP carries Horizontal · an unclassified BP is Unresolved.
- *Scope out:* CP inheritance (next story); what "blocks downstream" does operationally.
- *From map:* Resolve BP & CP BU / Stage 1; the Target BU → Owning BU sync (input vs result, same value two names).

**L1-R-05 — Control Procedure inherits BU from parent process** · **3 pts**
- *Why:* a CP is never classified on its own — it takes its parent's BU as-is, so classification happens once and every control follows.
- *Acceptance (invariant):* for any Control Procedure, Owning BU = its parent process's Owning BU. Parent resolved → CP carries that BU. Parent Unresolved → CP's Owning BU empty and the CP blocked.
- *Done proves:* a CP under a resolved parent inherits the BU · a CP under an Unresolved parent is left empty/blocked.
- *Scope out:* BP classification (prior story); the downstream block behavior.
- *From map:* Stage 2; traced process_001 (Engineering) → CP-0001/0002 inherit; process_014 (Unresolved) → CP-0012 empty.

**Epic 2 subtotal: 16 pts**

---

# EPIC 3 — Rules Catalog Authoring (RULES ③)  · *BUILD (partial — table exists)*

**Why:** the engine needs rules to run. This is the admin-facing surface where each rule is authored: one **WHEN → verdict** statement — a condition, a binary verdict (Applicable / Not Applicable), and a collection scope.
**Boundary:** in — an admin authoring intent; out — a stored, versioned rule the engine can later read. Out of scope: *evaluating* rules and *combining* them into a verdict (Epic 4) — this epic writes rules, it does not run them.
**Grounding note on maturity:** the `pei_rule` table and Active Rules view already render in the map. The **conditions-JSON grammar is deferred** — the map states that before it lands, conditions are opaque text. So a rule's condition can be authored as text *now*; making it machine-evaluable is Epic 4's spike, not this epic.

**L1-C-01 — The Rules Catalog table + Active Rules view** · **3 pts**
- *Why:* rules need a home and a working view before anything can author or read them.
- *Acceptance (invariant):* the `pei_rule` table exists with the authoring columns (Rule Name, Output, Collection Scope, Terminating, Plain-English Rendering, Status); the Active Rules view lists rules and is the working surface for an admin.
- *Done proves:* a rule created appears in the Active view · the view columns render the rule's authored fields.
- *Scope out:* condition semantics, evaluation, versioning history.
- *From map:* "① THE RULES CATALOG — the pei_rule table (Active Rules view)."

**L1-C-02 — Author a rule: condition (text), binary verdict, collection scope** · **3 pts**
- *Why:* the three things a rule *is* — a condition, the verdict it casts if matched, and how much evidence to collect — must be capturable on the record.
- *Acceptance (invariant):* a rule record captures a condition (opaque text until the grammar lands), a binary Output of exactly Applicable **or** Not Applicable, and a Collection Scope of Common or Per-app. No third verdict value is selectable.
- *Done proves:* a rule saves with condition + Applicable + Per-app · Output rejects any value outside {Applicable, Not Applicable}.
- *Scope out:* parsing/evaluating the condition (Epic 4), the plain-English render (next story).
- *Pin:* Collection Scope lives at the **rule** level (the Apr 25 pivot), not the CP.
- *From map:* "ANATOMY OF ONE RULE"; Output = Applicable (vs Not Applicable); Collection Scope = Per app — all / — same BU / Per BU-BP.

**L1-C-03 — Plain-English rendering of a rule** · **3 pts**
- *Why:* humans author and audit the rendering, not the machine form — every rule needs a readable one-line statement.
- *Acceptance (invariant):* for any saved rule, a plain-English rendering is present that states its condition and verdict readably (e.g. "When Hosting Type is Cloud → Applicable").
- *Done proves:* a saved rule shows a readable rendering · editing the rule's fields updates the rendering.
- *Scope out:* auto-derivation from structured JSON (couples to Epic 4's grammar — until then the rendering is templated/authored, not machine-generated).
- *From map:* "auto-written from the JSON on save — what humans read & audit."

**L1-C-04 — Rule status lifecycle (Draft / Inactive / Active)** · **3 pts**
- *Why:* not every authored rule should run — status gates which rules the engine will ever pick up, and freezes the catalog during a cycle.
- *Acceptance (invariant):* a rule carries a status; only Active rules are eligible to run; a Draft or Inactive rule never runs. During an active cycle the catalog is read-only.
- *Done proves:* an Active rule is engine-eligible · a Draft/Inactive rule is excluded · the catalog rejects edits mid-cycle.
- *Scope out:* the engine's actual reading of rules (Epic 4).
- *From map:* "Read-only during a cycle · a Draft/Inactive rule never runs."

**L1-C-05 — Terminating flag (authored, not enforced)** · **2 pts**
- *Why:* the exclusion-final short-circuit is a real concept authors need to set now, even though the engine that acts on it comes later.
- *Acceptance (invariant):* a rule carries a Terminating flag that persists on the record and is visible in the catalog. **Enforcement is explicitly out of scope** — nothing acts on the flag in this epic.
- *Done proves:* the flag saves and displays · no evaluation behavior changes as a result (enforcement lands in Epic 4).
- *Scope out:* short-circuit behavior — that's Epic 4's combination logic.
- *From map:* "a planned short-circuit flag — the engine that acts on it isn't built yet (see ③)."

**Epic 3 subtotal: 14 pts**

---

# EPIC 4 — Evaluation Engine & Fan-out (CROSS ④)  · *DESIGN-FIRST* ⚠

**Why:** this is where the two worlds meet — the engine crosses each Control Procedure's ownership (from its BP) against the rules' scope and conditions (against the apps) to decide *exactly where evidence is collected*, then emits the applicability records. It is the heart of the system.
**Boundary:** in — resolved CPs + active rules + resolved apps; out — applicability records (Applicable / Not Applicable), fanned out per pattern. Out of scope: what fills the resulting slots (Epics 5–6).

> **⚠ This epic is not build-ready.** The map states plainly that (a) the conditions-JSON grammar is deferred, and (b) how rules combine into a single verdict — the evaluation engine — is **not designed yet**. You cannot write tight acceptance for a design that doesn't exist, and handing a dev "build the engine" now is handing them the vision, not a task. **The first story is a spike.** The build stories below carry *provisional* scope and *provisional* points for roadmap planning only — their acceptance is authored **after** the spike closes and is captured in an ADR. Do not release them to the team until then.

**L1-X-00 — SPIKE: Design the evaluation engine** · **5 pts** · *assignable NOW*
- *Why:* everything downstream depends on the engine emitting the 2×2, and nothing about *how* it does so is decided. Lock this design now — it's the thing blocking L2.
- *Acceptance (invariant):* an approved design spec (an ADR) exists that defines: (1) the conditions-JSON grammar; (2) how a single rule's condition is tested against an app; (3) how multiple rules on one CP combine into one verdict, including terminating short-circuit precedence; (4) how scope × ownership resolves to one of the four cells; (5) the applicability record shape and its supersession behavior on re-run.
- *Done proves:* the spec is reviewed and accepted (ADR logged) · each downstream build story (X-01…X-05) can point to a section of it for its acceptance. Done is an approved document, not code.
- *Scope out:* implementing any of it (the build stories).
- *From map:* "③ HOW THEY COMBINE INTO A VERDICT — TBD, not built yet"; the 2×2; "the engine runs once per Control Procedure."

**L1-X-01 — Evaluate one rule's condition against an app** · *~5 pts, provisional* · *blocked on X-00*
- *Provisional scope:* given the grammar from the spike, test a single rule's condition against a single app and produce a match / no-match. Acceptance authored from the spike.
- *From map:* Conditions JSON — "the machine-readable condition — tested against each application."

**L1-X-02 — Combine multiple rules on a CP into one verdict** · *~8 pts, provisional* · *blocked on X-00*
- *Provisional scope:* apply all matching rules on a CP and resolve to a single Applicable / Not Applicable, honoring terminating precedence and hybrid composition. Acceptance authored from the spike.
- *From map:* "several rules → composition (hybrid)"; terminating "if a rule matches, evaluation stops and its verdict wins."

**L1-X-03 — Place a CP in the 2×2 cell (scope × ownership)** · *~5 pts, provisional* · *blocked on X-00*
- *Provisional scope:* cross the CP's ownership (Horizontal / BU-owned, from its BP) with the rule's collection scope (Common / Per-app) to select one of the four cells. Acceptance authored from the spike.
- *From map:* "Control Scope — the 2×2"; DIAL 1 Ownership × DIAL 2 Collection Scope.

**L1-X-04 — Fan-out: emit applicability records per cell** · *~8 pts, provisional* · *blocked on X-00*
- *Provisional scope:* from a CP's cell, emit the correct records — 1 (Horizontal Common) · 1 per applicable app (Horizontal Per-app) · 1 per owning BU (BU Common) · 1 per app in the owning BU (BU Per-app). Config set once; every emitted record inherits it. Acceptance authored from the spike.
- *From map:* "THE FAN-OUT — the engine emits records, not a label"; "BU Per-App × a BU that owns 200 apps → 200 applicability records."

**L1-X-05 — Applicability record lifecycle (Active / Inactive, re-run supersession)** · *~3 pts, provisional* · *blocked on X-00*
- *Provisional scope:* applicability records carry Applicable / Not Applicable and Active / Inactive status; a re-run supersedes the prior cycle's records cleanly. Acceptance authored from the spike.
- *Pin:* `pei_applicability` Applicable=890920000 / Not Applicable=890920001; `pei_applicabilitystatus` Active=890920000 / Inactive=890920001.

**Epic 4 subtotal: 5 pts firm (spike) + ~29 pts provisional (blocked on spike).** Treat the 29 as a roadmap placeholder, not a commitment.

---

# EPIC 5 — Evidence Slot Generation & Lifecycle (EVIDENCE ⑤)  · *BUILD*

**Why:** an applicability record says a control *needs* evidence somewhere; a slot is the actual place that evidence lives and moves through its states. This turns the engine's output into fillable, trackable proof.
**Boundary:** in — an applicability record (Applicable); out — a slot moving Gap → Pending → Provided, with its evidence frozen once approved. Out of scope: *how* the evidence is fetched or drafted (Epic 6), cycle finalization (Epic 7).

**L2-E-01 — Generate slots from applicability records** · **5 pts**
- *Why:* each applicable control × app pairing must become exactly one slot, inheriting the control's config so nothing is configured per-slot by hand.
- *Acceptance (invariant):* for every Applicable applicability record, exactly one evidence slot exists for that control × app; the slot inherits the CP's evidence config (method + check). A Not-Applicable record produces no slot.
- *Done proves:* an applicable CP × app yields one slot carrying inherited config · a not-applicable pairing yields none · no duplicate slots on re-run.
- *Scope out:* the config's *contents* and how it's authored (Epic 6), the fill (below).
- *From map:* "one slot per app · inherits the CP's config"; "you never configure a slot by hand."

**L2-E-02 — Slot state machine (Gap → Pending → Provided)** · **5 pts**
- *Why:* a slot's whole value is that its state tells you, at a glance, whether proof exists and how far along it is.
- *Acceptance (invariant):* a slot begins Gap (empty); a submission moves it to Pending (awaiting review); approval moves it to Provided. A rejection returns the slot to Gap. No transition skips a state.
- *Done proves:* an upload takes Gap→Pending · an approval takes Pending→Provided · a rejection takes Pending→Gap · an illegal jump is refused.
- *Scope out:* who approves and how (next story), immutability of the approved record (E-04).
- *Open question — reconcile before build:* the map shows **reject → Gap** (a slot reset), while **ADR-034** says evidence status has *no backward transitions*. Likely resolution: the *evidence record* is immutable and never transitions backward, while the *slot* resets on rejection to await a fresh submission — but confirm against ADR-034 and pin it, don't assume.
- *From map:* "THE SLOT LIFECYCLE — Gap / Pending / Provided · reject → back to Gap."

**L2-E-03 — Risk Manager approval gate** · **3 pts**
- *Why:* the RM is the gate, not the data-entry clerk — a human decides when captured proof becomes the record.
- *Acceptance (invariant):* a Pending slot can be approved only by the Risk Manager role; approval → Provided, rejection → Gap (per the reconciliation above). No other role can approve.
- *Done proves:* an RM approves Pending→Provided · a non-RM cannot approve · a rejection routes back correctly.
- *Scope out:* the state machine mechanics (prior story), snapshotting (next).
- *Pin:* Risk Manager is BU-scoped (ADR-032). Writes to FSP-protected fields route through service-principal flows — no human override path (ADR-033).
- *From map:* "The Risk Manager is the gate, not the data-entry clerk"; "RM approves → Provided."

**L2-E-04 — Evidence record immutability + snapshot** · **5 pts**
- *Why:* an auditor must trust that Provided proof can't change after the fact — immutability is what makes the record admissible.
- *Acceptance (invariant):* on Provided, the evidence is snapshotted (frozen) and cannot be altered thereafter; the file lives in SharePoint, and Dataverse holds the metadata plus the snapshot. No edit path exists to a Provided record's evidence.
- *Done proves:* a Provided record's snapshot is fixed · an attempt to alter it is refused · the SharePoint file and Dataverse metadata both exist.
- *Scope out:* the approval decision (prior story), provenance fields (next).
- *Pin:* Evidence immutable after creation (ADR-025); files in SharePoint (`.../sites/EMS`, library "EMS"), Dataverse holds metadata + snapshots.
- *From map:* "Provided · immutable — snapshotted & locked."

**L2-E-05 — Provenance stamping / uniform evidence record** · **3 pts**
- *Why:* every piece of evidence must carry the same audit fields regardless of how it arrived — downstream never cares whether it was auto-pulled or uploaded.
- *Acceptance (invariant):* every evidence record carries a uniform shape: who provided it / when / method · source · exact query · timestamp · SharePoint URL · immutable snapshot. An auto-pulled record and an uploaded record have the identical field set.
- *Done proves:* an uploaded record has the full field set · an auto-pulled record has the identical set · no method-specific field divergence.
- *Scope out:* the fetch/upload mechanics that populate these (Epic 6).
- *From map:* "UNIFORM EVIDENCE RECORD (every method)"; "downstream never cares how it arrived."

**L2-E-06 — Freshness / expiry** · **5 pts**
- *Why:* evidence goes stale — a control proven a year ago isn't proof today, so slots must be able to age out and demand refresh.
- *Acceptance (invariant):* an evidence record has a freshness policy; when its as-of date exceeds the policy window it moves to Expired, and the slot signals it needs refreshing for the current cycle.
- *Done proves:* a record past its window flips to Expired and its slot signals refresh · a record within window stays valid.
- *Scope out:* re-collection itself (that re-enters the fill flow, Epic 6), the sufficiency judgment.
- *Pin:* Evidence status Expired=890920005. Continuous sources pull the latest *snapshot* at cycle time so evidence stays a fixed as-of date, not a live query.
- *From map:* "Status ... Expired"; "CONTINUOUS sources → pull the latest SNAPSHOT at cycle time."

**Epic 5 subtotal: 26 pts**

---

# EPIC 6 — Evidence Collection & Checks  · *BUILD (largest, AI + integration surface)*

**Why:** this is *how* a slot gets filled — the routing between automated pull and manual upload, the registry of precise checks, the joins that make a pull hit the right app, and the AI that recommends matches and drafts asks. It's the build-out of ⑤.
**Boundary:** in — a slot needing evidence + its control's config; out — evidence landed in the slot as Pending (however it arrived). Out of scope: the slot's state machine and immutability (Epic 5) — this epic *delivers* evidence into that machine.
**Launch posture (from map):** default every control to **manual**, assigned to owners; turn on auto per control as it earns it. Build accordingly — manual is the default path, auto is the opt-in.

**L2-K-01 — Check Registry** · **5 pts**
- *Why:* the atomic unit is a *check*, not a connector — a system like GitHub answers a dozen controls, so you bind to a precise pull inside it. Engineers need a registry to define and maintain those.
- *Acceptance (invariant):* the registry holds connectors (auth + base API, built once) and, under each, named checks (a precise, named pull — e.g. `github · pr-review-approvals`). The registry contains only checks engineers have actually wired.
- *Done proves:* a connector holds many named checks · an unbuilt source has no check to bind (and will route to manual — K-04) · the registry rejects a check with no backing wiring.
- *Scope out:* binding checks to controls (next), the runtime pull (K-05).
- *From map:* "THE CORE UNIT — a CHECK, not a connector"; "Registry = built things only."

**L2-K-02 — Control ↔ Check binding (many-to-many)** · **5 pts**
- *Why:* which pulls satisfy a control is the first of the two joins that make auto-pull work — get it right and auto-pull scales.
- *Acceptance (invariant):* a control can bind to several checks and a check can serve several controls (many-to-many); the AI recommends the match from the control's text, a human approves, and the approved binding persists. The AI recommends — it never persists a binding on its own.
- *Done proves:* a control binds to multiple checks · a check serves multiple controls · an AI-recommended binding persists only after human approval.
- *Scope out:* the AI recommendation mechanics (K-06), app identity (next).
- *From map:* "CONTROL ↔ CHECK — many-to-many · AI recommends ... a human approves & it persists."

**L2-K-03 — App → Identity per connector (the crux join)** · **5 pts**
- *Why:* this cross-system identity join — which repo / asset / account an app *is* in each source system — is what makes an auto-pull hit the right app. The map calls it the highest-risk dependency; solve it first among the joins.
- *Acceptance (invariant):* each app carries its identity in each connector's system (repo, asset-id, account), entered once per app and carried in LeanIX — never per slot. A runtime pull resolves the app's identity for the relevant connector.
- *Done proves:* an app resolves to its GitHub repo and its Qualys asset · identity is entered once and reused across that app's slots · a missing identity is surfaced, not guessed.
- *Scope out:* the pull itself (K-05), the control↔check side (prior).
- *Pin:* "THE CRUX: this cross-system identity join is what makes auto-pull hit the right app."
- *From map:* "APP → IDENTITY per connector — entered once per app, never per slot."

**L2-K-04 — Routing resolution (bound check → auto · none → manual)** · **3 pts**
- *Why:* one clean rule decides how every control collects — no separate auto/manual flag to keep in sync.
- *Acceptance (invariant):* for each Control Procedure, the presence of a bound check *is* the routing decision: bound → AUTO-PULL via that check; none → MANUAL (AI drafts the ask, human approves). A control needing an unbuilt source falls to manual.
- *Done proves:* a bound control routes auto · an unbound control routes manual · a control whose source isn't in the registry routes manual and thereby joins the "build a connector" list.
- *Scope out:* the pull runtime (next), the AI draft (K-07).
- *From map:* "THE ROUTING RULE — presence of a binding is the answer"; "self-documenting backlog: a control needing an unbuilt source falls to manual."

**L2-K-05 — Auto-pull runtime** · **8 pts** ⚠ *split candidate*
- *Why:* the automated path must fetch, normalize, and stamp evidence so an auditor trusts it exactly like an upload.
- *Acceptance (invariant):* for each bound check, the runtime resolves the app's identity → pulls → normalizes → provenance-stamps (source · exact query · timestamp · provided-by = connector) → snapshots (frozen), landing the slot as Pending. Continuous/streaming sources pull the latest snapshot as of cycle time, not a live query.
- *Done proves:* a bound check lands a stamped, snapshotted Pending record · a continuous source yields a fixed as-of snapshot · a failed pull is surfaced, not silently empty.
- *Scope out:* the RM approval that follows (Epic 5), manual path (K-07).
- *Split note:* consider "resolve + pull + normalize" and "stamp + snapshot + land" as two stories.
- *Pin:* AI/connector output paths and normalization live here; the record it lands must match E-05's uniform shape exactly.
- *From map:* "RUNTIME — filling one slot"; the AUTO-PULL path.

**L2-K-06 — AI check-match recommendation** · **5 pts**
- *Why:* mapping ~300 controls to checks by hand is the bottleneck; the AI reads a control's description and recommends the check(s) — smart suggestion under human approval.
- *Acceptance (invariant):* given a control's description, the AI recommends the matching check(s) from the registry; the recommendation is surfaced for human approval and never binds on its own. It recommends — it never decides.
- *Done proves:* a control description yields a ranked check recommendation · the recommendation requires approval to persist (feeds K-02) · a control with no good match yields no false binding.
- *Scope out:* the persistence of the approved binding (K-02).
- *Pin:* AI via AI Builder "Run a prompt"; output at `body()?['responsev2']?['predictionOutput']?['text']`. AI recommends, human always approves (ADR posture).
- *From map:* "AI AGENT — recommends which check matches a control ... Recommends — never decides."

**L2-K-07 — AI-drafted manual ask** · **5 pts**
- *Why:* for controls with no bound check, the owner still needs to know exactly what to provide — the AI drafts the evidence requirement so the ask is precise, under human approval.
- *Acceptance (invariant):* for a manual-routed control, the AI drafts the evidence ask from the control's description; a human approves the draft; the owner uploads against the approved ask, landing the slot as Pending with the uniform record shape. The AI drafts — it never finalizes the ask.
- *Done proves:* a manual control gets an AI-drafted ask · the ask requires approval before it's live to the owner · an owner upload lands as Pending matching the uniform shape.
- *Scope out:* the state machine / approval of the *evidence* (Epic 5) — this delivers the upload into it.
- *From map:* "MANUAL path — a control owner uploads the file against the AI-drafted, human-approved ask."

**Epic 6 subtotal: 36 pts**

---

# EPIC 7 — Sign-off & Cycle Close (SIGN-OFF ⑥)  · *BUILD*

**Why:** the 6th gate — where the cycle's slots become *the record*. Sign-off is what converts a working cycle into the durable, audit-ready artifact set and closes the loop for removed controls and apps.
**Boundary:** in — a cycle's completed/reviewed slots; out — finalized evidence records, folders, notifications, retirements. Out of scope: filling the slots (Epics 5–6) — this is what happens *after* they're filled and reviewed.
**Grounding principle (from map):** "The audit trail exists whether a slot was filled automatically or by hand — automation is efficiency, not a compliance prerequisite." Sign-off treats auto and manual evidence identically.

**L2-S-01 — Cycle sign-off gate** · **3 pts**
- *Why:* a cycle shouldn't finalize until a human signs it off — the gate that authorizes everything downstream in this epic.
- *Acceptance (invariant):* a cycle can be signed off only from a reviewable state; sign-off is a deliberate authorized action that triggers finalization. An un-signed cycle produces no finalized artifacts.
- *Done proves:* a signed-off cycle triggers finalization · an un-signed cycle does not · only an authorized role can sign off.
- *Scope out:* the individual finalization actions (following stories).
- *From map:* "AT SIGN-OFF (the 6th gate) — the slots become the record."

**L2-S-02 — Produce evidence records at close** · **3 pts**
- *Why:* the cycle's reviewed slots must be committed into the finalized evidence record set that survives as the audit trail.
- *Acceptance (invariant):* on sign-off, each qualifying slot's evidence is produced as a finalized record in the cycle's record set. Nothing is produced for slots that didn't qualify.
- *Done proves:* qualifying slots yield finalized records · non-qualifying slots yield none · the produced set matches the signed-off cycle.
- *Scope out:* folder creation and notifications (below).
- *From map:* "Evidence records produced."

**L2-S-03 — Create SharePoint folders** · **3 pts**
- *Why:* the finalized evidence needs its durable home in SharePoint, organized so an auditor can navigate it.
- *Acceptance (invariant):* on sign-off, the cycle's SharePoint folders are created under the EMS site/library in the agreed structure; produced records land in their correct folder.
- *Done proves:* sign-off creates the folder structure · each produced record maps to its folder · a re-run doesn't duplicate folders.
- *Scope out:* record production (prior), notifications (next).
- *Pin:* SharePoint site `.../sites/EMS`, library "EMS".
- *From map:* "SharePoint folders created."

**L2-S-04 — Send notifications** · **2 pts**
- *Why:* the right people need to know the cycle closed and what it produced.
- *Acceptance (invariant):* on sign-off, notifications are sent to the configured recipients summarizing the closed cycle. No notifications fire for an un-signed cycle.
- *Done proves:* sign-off sends the notification · an un-signed cycle sends none · recipients match configuration.
- *Scope out:* the content authoring of notification templates (config, not this story).
- *Pin:* notification sender `risk-manager@ems.com`.
- *From map:* "Notifications sent."

**L2-S-05 — Retire removed controls & apps at close** · **3 pts**
- *Why:* controls and apps that dropped out during the cycle must be retired as part of close, keeping the record honest without deleting history.
- *Acceptance (invariant):* on sign-off, controls and apps flagged removed during the cycle are retired (soft-delete, consistent with Epic 1's lifecycle); their historical records and evidence persist.
- *Done proves:* a removed control/app is retired at close · its history and evidence survive · a still-active control/app is untouched.
- *Scope out:* the ingestion-time retirement of apps (Epic 1, L1-P-04) — this is the close-time counterpart for the cycle.
- *From map:* "Removed controls & apps retired."

**Epic 7 subtotal: 14 pts**

---

# Summary & sequencing

| Epic | Stage | Status | Firm pts | ~Hours |
|---|---|---|---:|---:|
| 1 · Ingestion & Data Contract | PULL ① | Foundation | 27 | 202.5 |
| 2 · BU Resolution | RESOLVE ② | Foundation | 16 | 120 |
| 3 · Rules Catalog Authoring | RULES ③ | Build (partial) | 14 | 105 |
| 4 · Evaluation Engine & Fan-out | CROSS ④ | **Design-first** | 5 spike | 37.5 |
| 5 · Evidence Slots & Lifecycle | EVIDENCE ⑤ | Build | 26 | 195 |
| 6 · Evidence Collection & Checks | — | Build (largest) | 36 | 270 |
| 7 · Sign-off & Cycle Close | SIGN-OFF ⑥ | Build | 14 | 105 |
| **Firm total** | | | **138** | **~1,035** |
| Epic 4 build (provisional, blocked on spike) | | | ~29 | ~217.5 |
| **Planning total** | | | **~167** | **~1,252.5** |

**The three sequencing rules that keep this from becoming a sea:**

1. **Start with the foundation.** Epics 1 → 2 are assignable this week with no further design; everything else binds to them. Within Epic 1, the app track (P-01→04) and Archer track (P-05→06) run in parallel.
2. **Epic 4 leads with a spike, not a build.** Assign **L1-X-00** now. Do not release X-01…X-05 until the spike's ADR closes — that's what unblocks all of L2's dependence on the 2×2.
3. **Evidence epics wait on the engine.** Epics 5–6 consume applicability records, so their *build* can't finish until Epic 4's engine emits them. You can, however, run Epic 5's slot-lifecycle and Epic 6's registry/joins design in parallel with the spike — they don't need the engine *running*, only its record shape decided.

**Open questions to pin (log each as a numbered backlog item, don't resolve silently):**
- **Reject → Gap vs ADR-034** (Epic 5, L2-E-02): the map's slot reset vs "no backward transitions." Confirm the slot-vs-record distinction before building.
- **Live-API carrier** (Epic 1): confirmed out of scope as a later carrier-swap? Pin it so the contract is built swappable.
- **Terminating enforcement boundary** (Epics 3/4): authored in Epic 3, enforced in Epic 4's combination logic — confirm nothing in between assumes it acts.

**Two hard constraints that bite at runtime** (surfaced inside the stories, repeated here so they don't get lost): app match key is **`pei_displayname`**, not the LeanIX ID (L1-P-02); Archer links resolve from **text-ID references** into real relationships (L1-P-06).
