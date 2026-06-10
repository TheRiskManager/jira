# EMS — SPRINT 1 — JIRA-READY STORIES (14)

**Source:** EMS_Project v60 (Cowork-verified, grounded). **Sprint goal:** critical-path-led ramp.
**Per-dev load:** Dev 1 = 8 pts · Dev 2 = 8 pts · Dev 3 = 8 pts (target 10; loaded ~8 for new-dev ramp).
**Points = team-scale** (agile-Fibonacci). **3 stories carry ⚠ OPEN coordinator decisions — flagged at top of each.**

How to use: each block = one Jira issue. Copy **Summary** into the issue title, set **Assignee / Points / Priority**,
paste **Description** into the description field. The ⚠ OPEN blocks are decisions YOU resolve before that story is fully buildable.

═══════════════════════════════════════════════════════════════════════════════
## DEV 1 — RULE-ENGINE SPINE (8 pts) — owns the critical path
═══════════════════════════════════════════════════════════════════════════════

────────────────────────────────────────────────────────────────────
SUMMARY:   L1-B04 — JSON validation on Rule save
ASSIGNEE:  Dev 1   |   POINTS: 2   |   PRIORITY: P0 (Critical Path)   |   TYPE: Plugin/validation
────────────────────────────────────────────────────────────────────
DESCRIPTION:

⚠⚠ OPEN — COORDINATOR DECISION REQUIRED BEFORE FULL BUILD ⚠⚠
This story is at the FRONT of the critical path, but 2 of its 4 validation checks depend on the Rule
Expression JSON schema (ADR-066 / L1-B05) which is NOT yet locked. Buildable now: (1) parseable JSON,
(2) balanced AND/OR/NOT groups. BLOCKED until schema locks: (3) recognized operators, (4) valid
attribute names. COORDINATOR PICKS: either (a) lock ADR-066 first so all 4 checks build this sprint,
OR (b) ship the structural subset now and split operators/attributes to a follow-up.
DO NOT INVENT an operator list or attribute catalog — a guessed schema propagates a wrong contract to B08.

As a System Admin, I want the system to validate my rule's JSON syntax on save, so malformed rules
don't reach Stage 5 evaluation.

Dependencies (met): L1-B01 (Rule table) — Done. pei_rule has pei_conditionsjson (Multi-line text, 100k).

Approach: synchronous PLUGIN on pei_rule Create + Update (Update filtered to pei_conditionsjson), pre-operation
stage. A plugin gives control over JSON parsing and fail-vs-warn; a business rule can't parse JSON. Confirm
plugin/assembly deployment is allowed in the tenant.

BUILD BLOCKS:
1. Confirm target: validate pei_conditionsjson (NOT pei_plainenglish — that's L1-B06's rendered output).
2. Register synchronous steps on Create + Update (filtered), pre-operation. Async CANNOT block a save — must be sync.
3. Structural checks (BUILD NOW): parseable JSON (deserialize; on fail throw InvalidPluginExecutionException with
   position/message); balanced groups (walk tree; matched open/close + valid AND/OR/NOT). The thrown message is what
   the admin sees — make it human ("Unbalanced group under the second OR clause"), not a stack trace.
4. Operator + attribute checks (BLOCKED — see OPEN): recognized operators (unknown → hard-fail);
   valid attribute names (unknown attribute → WARN, not fail — allow save + surface warning).

ACCEPTANCE CRITERIA:
- Validates Conditions JSON on Rule create/update.
- Checks: parseable JSON, recognized operators, valid attribute names, balanced groups.
- Invalid → save fails with descriptive error. Valid-but-unknown-attribute → save warns.

DOD CHECKLIST:
[ ] Validation on pei_rule Create AND Update.
[ ] Valid rule saves cleanly.
[ ] Malformed JSON → fails with descriptive message.
[ ] Unknown operator → fails (GATED on ADR-066).
[ ] Unbalanced group → fails.
[ ] Unknown attribute → succeeds with warning (GATED on ADR-066).
[ ] Sidecar L1-B04_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-B03 — Hidden admin form for Rule authoring
ASSIGNEE:  Dev 1   |   POINTS: 2   |   PRIORITY: P0 (Critical Path)   |   TYPE: MDA form
────────────────────────────────────────────────────────────────────
DESCRIPTION:

RESUME NOTE: this form build was previously started and PARKED — pick up the existing in-progress form,
do NOT create a second one. Check the maker portal for an existing "Rule Admin Form" on pei_rule first.

As a System Admin, I want a dedicated form for authoring rules with a JSON editor, so I can write rule
expressions in a controlled, admin-only environment.

Dependencies (met): L1-B01 (Rule table) — Done.

FORM — "Rule Admin Form" (main form on pei_rule), sections:
- Identity:        pei_rulename, pei_description, pei_rulestatus
- Logic:           pei_conditionsjson (JSON editor area), pei_plainenglish, pei_output
- Scope/Priority:  pei_collectionscope, pei_priority, pei_terminating
- Lifecycle:       pei_effectivefrom, pei_effectiveto, pei_currentversion
Helper text on pei_conditionsjson: short JSON-schema description + link to L1-B05 schema doc (forward-link
placeholder; B05 not yet built).

BUILD BLOCKS:
1. Create a SEPARATE main form "Rule Admin Form" (do not edit the default Information form — role scoping must differ).
2. Add helper text on pei_conditionsjson (short; link to L1-B05, don't duplicate the schema).
3. Add a sitemap subarea pointing at pei_rule via the Rule Admin Form (admin group).
4. Scope visibility: form security roles → System Admin ONLY; REMOVE Risk Manager. A form with no role
   restriction shows to everyone — restrict explicitly. Check the subarea's role filter too.

ACCEPTANCE CRITERIA:
- "Rule Admin Form" created with all fields incl. JSON Conditions area + helper text.
- Hidden from Risk Manager; visible to System Admin only via sitemap subarea.

DOD CHECKLIST:
[ ] Form exists with all fields + JSON area + helper text.
[ ] Sitemap subarea scoped to System Admin.
[ ] As System Admin: form reachable, all fields shown.
[ ] As Risk Manager: form does NOT appear.
[ ] Helper text links to L1-B05 doc (forward-link noted).
[ ] Sidecar L1-B03_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-B10 — Rule version snapshot on edit
ASSIGNEE:  Dev 1   |   POINTS: 2   |   PRIORITY: P0 (Critical Path)   |   TYPE: Plugin
────────────────────────────────────────────────────────────────────
DESCRIPTION:

As a System Admin, I want every rule edit to create a Rule Version snapshot automatically, so historical
rule states are preserved.

Dependencies (met): L1-B02 (Rule Version table pei_ruleversion) — Done. L1-B01 (Rule table) — Done.

Versioning semantics (confirm exact column set vs pei_ruleversion schema):
- Snapshot fields: pei_conditionsjson, pei_output, pei_collectionscope, pei_priority, pei_terminating, rule name (min).
- Effective dating: prior version Effective To = now; new version Effective From = now.
- Version increment: pei_currentversion on pei_rule += 1.
- Change reason: from a change-reason field if provided (confirm where).

BUILD BLOCKS:
1. Confirm snapshot target columns on pei_ruleversion. The snapshot is an EMBEDDED COPY (actual values), not just a lookup.
2. Register plugin on pei_rule Update, pre-operation, WITH A PRE-IMAGE capturing snapshot fields. Without a pre-image
   you can't see the OLD values during Update (Target only carries changes).
3. Write the version row from the pre-image; stamp Effective To on the PRIOR row, Effective From on the new state; link to pei_rule.
4. Increment pei_currentversion (+1); capture user + timestamp + change reason. Guard re-entrancy (depth check) — exactly
   ONE version row per edit.

ACCEPTANCE CRITERIA:
- Plugin on Rule update captures pre-update state to a new Rule Version row.
- Effective To on prior, Effective From on new; Current Version increments; user/timestamp/reason captured.

DOD CHECKLIST:
[ ] Plugin on pei_rule Update with pre-image.
[ ] Editing a Rule creates EXACTLY ONE pei_ruleversion row.
[ ] Effective dates stamped correctly (prior To / new From).
[ ] pei_currentversion increments by 1.
[ ] User, timestamp, change reason captured.
[ ] No duplicate rows on a single edit.
[ ] Sidecar L1-B10_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-B15 — Create Cycle Rule Execution Log table
ASSIGNEE:  Dev 1   |   POINTS: 1   |   PRIORITY: P0 (Critical Path)   |   TYPE: Schema
────────────────────────────────────────────────────────────────────
DESCRIPTION:

NAMING CORRECTION (part of this story): the schema-doc placeholder "pei_cyclereexecutionlog" is a TYPO.
The correct deployed name is "pei_cycleruleexecutionlog". Fix the placeholder and log the correction.

As a System Admin, I want a Cycle Rule Execution Log table recording every rule firing during a cycle,
so the platform has an immutable, queryable audit trail of which rule version evaluated which CP × App
pair to which outcome. TABLE-CREATE ONLY — rows are written later by the L1-C05 flow (not this story).

Dependencies (met): L1-B01, L1-B02 — Done. ADR-054 (cycle pinning) — locked.

TABLE — pei_cycleruleexecutionlog (Display "Cycle Rule Execution Log"), User/Team owned, AUDIT ENABLED,
READ-ONLY (no human create/write — rows only from the L1-C05 flow under System context).
Verify schema name reads pei_cycleruleexecutionlog BEFORE first Save (locks at save).

COLUMNS (ADR-054 cycle-pinning):
1. Rule Version          pei_ruleversionid          Lookup → pei_ruleversion
2. Rule Version JSON Snapshot  pei_ruleversionjsonsnapshot  Multi-line text  ← EMBEDDED immutable copy (the pinning column)
3. Cycle                 pei_cycleid                Lookup → Import Cycle
4. Control Procedure     pei_controlprocedureid     Lookup → Control Procedure
5. Application           pei_applicationid          Lookup → Application
6. Evaluation Result     pei_evaluationresult       Choice (Applicable / Not Applicable / Error)
7. Error Message         pei_errormessage           Multi-line text
8. Evaluated At          pei_evaluatedat            Date and Time
9. Evaluator Version     pei_evaluatorversion       Single Line of Text
Confirm Evaluation Result values vs the existing verdict convention (Applicable=890920000 / Not Applicable=890920001, Error next).

BUILD BLOCKS:
1. Create table + primary column; verify schema name (NOT the typo) before Save.
2. Add the 5 lookups + 4 data columns. The JSON snapshot is plain multi-line text holding an embedded copy — NOT a lookup.
3. Create Evaluation Result choice (values aligned to the verdict convention).
4. Lock read-only by NOT granting create/write to human roles (confirm roles, not just form-level). Enable audit.
5. Smoke-insert one row via system context; then fix the schema doc (full inventory + log the typo correction).

ACCEPTANCE CRITERIA:
- Table created (typo fixed); 9 columns per ADR-054; read-only at platform level; audit enabled; schema doc updated.

DOD CHECKLIST:
[ ] Table deployed with full column set + embedded JSON snapshot column.
[ ] Read-only confirmed (no human create/edit); one sample row via system context.
[ ] Audit enabled and verified.
[ ] Schema doc updated; typo correction logged.
[ ] No populated rows expected yet (L1-C05 is the only writer).
[ ] Sidecar L1-B15_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   DOC-05 — ADR-029: Collection Scope as rule property
ASSIGNEE:  Dev 1   |   POINTS: 1   |   PRIORITY: P2   |   TYPE: Documentation
────────────────────────────────────────────────────────────────────
DESCRIPTION:

As an Architect, I want ADR-029 formally written, so the rationale for storing Collection Scope on rules
(not Control Procedures) is preserved and the deprecation of Common/Hybrid/App-Level labels is documented.
NO TENANT WORK — documentation deliverable.

Dependencies: none (documents a settled April-25 decision).

DOCUMENT — ADR-029_Collection_Scope_as_Rule_Property.md, canonical ADR sections:
- Context:      pre-pivot CPs carried a scope label (Common/Application-Level/Hybrid); pivot makes applicability rule-driven.
- Decision:     Collection Scope inherent to each rule (pei_rule.pei_collectionscope / KDD-002 D-04); labels removed from CP.
- Consequences: Stage-5 output language changes — sample: "AC-2 produced 47 evidence collection points across 47 apps in
                Finance BU." Deprecate pei_finalscopetype on CP (or repurpose as denormalized last-cycle field).
- Alternatives: keeping scope on CP; hybrid model — why rule-level won.
- Implementation Notes: where scope lives, how Stage 5 reads it, migration of the deprecated label.

BUILD BLOCKS:
1. Author the ADR (match the existing ADR template's section order/heading style for clean index import).
2. Document the deprecation explicitly + the pei_finalscopetype decision.
3. Reciprocate cross-references (rule schema doc, Stage-5 samples, superseded docs) + link from the ADR index.
   Cross-refs must be reciprocal — a one-way link leaves the other doc unaware it's superseded.

ACCEPTANCE CRITERIA:
- ADR-029 authored with all 5 sections; deprecation documented; Stage-5 sample captured; affected fields listed;
  cross-referenced reciprocally + linked from the ADR index.

DOD CHECKLIST:
[ ] ADR covers all 5 canonical sections.
[ ] Deprecated labels documented as removed-from-CP with rule-inherent replacement.
[ ] Stage-5 output-language sample captured.
[ ] pei_finalscopetype decision recorded.
[ ] Cross-refs reciprocated + linked from the ADR index.


═══════════════════════════════════════════════════════════════════════════════
## DEV 2 — INFRASTRUCTURE + L3 (8 pts)
═══════════════════════════════════════════════════════════════════════════════

────────────────────────────────────────────────────────────────────
SUMMARY:   L1-Z02 — Service principal setup + flow migration
ASSIGNEE:  Dev 2   |   POINTS: 3   |   PRIORITY: P0 (Critical Path)   |   TYPE: Infra/Flow
────────────────────────────────────────────────────────────────────
DESCRIPTION:

⚠ EXTERNAL APPROVAL GATE (real-world, not code): Azure AD App Registration may require IT/security approval
OUTSIDE the build team's authority. OPEN THE IT/SECURITY TICKET FIRST (Block 1) so provisioning isn't blocked at runtime.

As a System Admin, I want all flows running under a dedicated service principal (not a personal account),
so the system can deploy to production per policy and FSP integrity rules actually enforce against admins.
KEYSTONE: several downstream stories (L1-G33–G38, L1-D10 re-resolve, L1-G03 create path) depend on this SP existing.

Dependencies (met): L1-Z01 Decision 2 (SP required) — locked. Plus the external approval gate above.

THE 7 PRODUCTION FLOWS (re-point each, re-test each): Flow 1 (Monthly Sync, 187 actions), Flow 2 (Gate Validation, 21),
Flow 3A/3B/3C, Flow 3D (Evidence Generation, 18), Flow 4A (Confirmation, 43).

BUILD BLOCKS:
1. Open the approval channel FIRST (IT/security ticket / confirm authority) — the single most likely runtime blocker.
2. Provision the SP (Azure AD → App Registrations → New). RECORD the Application (client) ID immediately.
3. Assign a Power Platform license to the SP (per-flow or per-user — confirm tenant model; affects cost).
4. Add the SP as a Dataverse application user with create/write on EMS tables. Grant EXACTLY the privileges the flows
   exercise — over-granting weakens integrity, under-granting breaks flows. Cross-check what each flow writes.
5. Migrate connections ONE FLOW AT A TIME (Flow 1 → 2 → 3A/3B/3C → 3D → 4A): Dataverse, SharePoint, Office 365, AI Builder.
   A broken connection on 187-action Flow 1 is far easier to localize if you didn't change six others at once.
6. Re-test each flow end-to-end. Highest risk: Flow 4A evidence path, Flow 1 Archer ingestion — verify correct rows under the SP.

ACCEPTANCE CRITERIA:
- SP provisioned; license assigned; SP in Dataverse role(s) with create/write on EMS tables; all 7 flows migrated to run as SP.

DOD CHECKLIST:
[ ] SP provisioned; client ID recorded.
[ ] License assigned per agreed model.
[ ] SP in Dataverse role(s) with create/write on EMS tables.
[ ] All 7 flows re-pointed to SP; connections updated.
[ ] Each flow re-tested end-to-end, no regressions (in sidecar).
[ ] Sidecar L1-Z02_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L3-A01 — Engagement table
ASSIGNEE:  Dev 2   |   POINTS: 2   |   PRIORITY: P3   |   TYPE: Schema
────────────────────────────────────────────────────────────────────
DESCRIPTION:

⚠⚠ OPEN — COORDINATOR DECISION REQUIRED BEFORE BUILD ⚠⚠
Live AC lists fields ending in "etc." Schema names freeze at first save and L3 stories downstream (L3-A02/A03/A06)
bind to these columns. CONFIRM BEFORE BUILDING:
1. The FULL column list (resolve "etc." to an explicit set — do not guess).
2. The "Scope" composite (BU/BP/framework/time window): separate columns or other model? CARDINALITY of each
   (single BU vs many BUs — many-valued scope needs a junction table, not a lookup).
3. Lookup targets (Engagement Type = Choice configured by L3-A02; Lead Auditor = System User — confirm).
DO NOT invent columns to "finish" the table — a guessed scope model forces rework in L3-A03's scope-freeze.

As a Risk Manager, I want an Engagement table to model audits/assessments, so evidence reviews can be scoped formally.

Dependencies: none (Layer 3 entry table).

TABLE — pei_engagement (Display "Engagement"), primary pei_engagementname (NOT pei_name — set before save),
User/Team owned, AUDIT ENABLED.
GROUNDED FIELDS (pending OPEN inventory): pei_engagementname (primary), pei_engagementtype (Choice, values from L3-A02),
pei_status (Choice — transitions align with ADR-024 scope-freeze), pei_startdate, pei_enddate, pei_leadauditorid
(Lookup → System User), Scope (see OPEN). ADR-024: Status values/transitions designed to support a clean active/locked state.

BUILD BLOCKS (run only after OPEN confirmed):
1. Create table + primary column pei_engagementname (verify, not pei_name) before Save.
2. Add confirmed columns. Engagement Type as Choice (values by L3-A02). Lead Auditor as System User lookup.
3. Generate default form/view/quick-create; smoke-test one Engagement.
4. Enable audit; move Engagement into the live-tables section of the schema doc.

ACCEPTANCE CRITERIA:
- pei_engagement with Name, Engagement Type, Scope (BU/BP/framework/time window), Status, Start/End Date, Lead Auditor,
  etc. (the "etc." is the OPEN item); form/view/list created.

DOD CHECKLIST:
[ ] OPEN resolved: full inventory + Scope shape + cardinality confirmed.
[ ] pei_engagement deployed with confirmed fields, Status choice, Lead Auditor lookup; one sample record.
[ ] Default form/view/quick-create smoke-tested.
[ ] Audit enabled; edits in audit history.
[ ] Schema doc updated.
[ ] Sidecar L3-A01_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   INF-B01 — Failure notifications
ASSIGNEE:  Dev 2   |   POINTS: 2   |   PRIORITY: P2   |   TYPE: Notification
────────────────────────────────────────────────────────────────────
DESCRIPTION:

As a System Admin, I want alerts when flows fail, so I can intervene quickly.

Dependencies: none (wraps existing flows).

PRE-BUILD DECISIONS (confirm): major-flows set (Flow 1, 2, 3A/3B/3C/3D, 4A min); alert recipient(s) (admin DL);
payload (flow name, error, run URL, timestamp, correlation ID); failure-log surface (Dataverse table OR SharePoint list
— SharePoint at the EMS site is lighter).

BUILD BLOCKS:
1. Stand up the failure-log surface (queryable — email alone isn't auditable).
2. Wrap each major flow with try-catch using the SCOPE pattern: a "Try" scope + a "Catch" scope with run-after =
   "has failed"/"is skipped". This is Power Automate — build the catch via scope run-after config, not code-style try/catch.
3. From each Catch, write a failure-log record with the full payload (use result()/expressions for the failed action's
   error + run URL).
4. Send the email alert from the catch path (error EXCERPT in body; full detail in the log record — keep it scannable).
5. Induce a controlled failure in each flow to verify the record writes + email arrives. Set log retention to match the
   audit-log target (cross-ref INF-B05).

ACCEPTANCE CRITERIA:
- All major flows wrapped; failures logged + email alert (flow name, error, run URL, timestamp).

DOD CHECKLIST:
[ ] Every flow wrapped at action boundaries; uncaught exceptions route to catch (not silent).
[ ] Failure-log record on every catch; verified by induced failure per flow.
[ ] Email fires with flow name, error excerpt, run URL, timestamp; verified in inbox.
[ ] Log retention matches audit target (INF-B05).
[ ] Sidecar INF-B01_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   INF-C01 — Archer feed retry logic
ASSIGNEE:  Dev 2   |   POINTS: 1   |   PRIORITY: P2   |   TYPE: Flow resilience
────────────────────────────────────────────────────────────────────
DESCRIPTION:

COORDINATION: the after-3-failures alert should land on the INF-B01 catch path (same Dev 2 work) — share ONE
notification surface, don't build a second.

As the System, I want Flow 1 to retry on transient Archer errors, so ingestion is resilient.

Dependencies: none (hardens Flow 1, EMS Monthly Sync, 187 actions).

PRE-BUILD DECISIONS (confirm): transient-error classes to retry (read timeout, file-not-found-yet, intermittent
network — NOT a genuinely malformed file forever); backoff (3 retries, exponential); notification endpoint (INF-B01);
delay-metadata target (run log).

BUILD BLOCKS:
1. Identify the Archer file-READ action in Flow 1 (target the read step, not downstream parsing).
2. Configure retry with exponential backoff: action Settings → Retry Policy (exponential), and/or a Do-Until loop for
   per-attempt delay logging. 3 retries, scoped to the catalogued transient classes.
3. After retries exhausted, route to the INF-B01 catch path (file path, error context, run URL). REUSE INF-B01's surface.
4. On successful retry, log attempt# + elapsed-ms per attempt. Confirm idempotency — a recovered retry must NOT
   double-insert Staged rows.
5. Verify: remove the Archer file mid-run (transient) → recovery; make it persistent → after-3 alert fires.

ACCEPTANCE CRITERIA:
- Retry 3× exponential on file-read failures; after 3 → notify admin; successful retry logs delay metadata.

DOD CHECKLIST:
[ ] Flow 1 retries Archer call 3× exponential on catalogued classes; verified by transient failure recovering.
[ ] After 3rd failure admin notification fires (INF-B01 path); verified by persistent failure.
[ ] Successful retry writes delay metadata to the run log.
[ ] No duplicate Staged rows on success (idempotent).
[ ] Sidecar INF-C01_Tenant_Test.md = PASS before Done.


═══════════════════════════════════════════════════════════════════════════════
## DEV 3 — IMPORT/CYCLE + EVIDENCE FOUNDATIONS (8 pts)
═══════════════════════════════════════════════════════════════════════════════

────────────────────────────────────────────────────────────────────
SUMMARY:   L1-D01 — Update Import Cycle BPF to 6 stages
ASSIGNEE:  Dev 3   |   POINTS: 2   |   PRIORITY: P1   |   TYPE: Business Process Flow
────────────────────────────────────────────────────────────────────
DESCRIPTION:

SEQUENCING NOTE: gate fields are added in L1-D02; this story wires the BPF stages to those fields. Confirm the gate
fields exist (or coordinate with D02) before binding. The stage→gate mapping is load-bearing (L1-D03–D08 replicate off it).

As a Risk Manager, I want a 6-stage Business Process Flow on Import Cycle, so cycle progression matches the new architecture.
MODIFIES the existing 5-stage BPF (L0-A05, Done) — expand to 6, do NOT build from scratch.

Dependencies (met): modifies L0-A05 (Import Cycle, 5-stage BPF) — Done.

THE 6 STAGES (in order): 1. Detect Changes → 2. Verify App BU → 3. Verify CP BU → 4. Confirm Rules → 5. Review Output → 6. Sign-off
Each stage has ONE required gate field (Yes/No). Stage advances only when its gate = Yes.

BUILD BLOCKS:
1. Open the EXISTING "EMS Import Cycle" BPF (do NOT create a second — two active BPFs on one table fight to render).
2. Expand 5 → 6 stages to match the order exactly. Confirm with coordinator how existing in-flight Import Cycle records
   map onto the revised stages.
3. Bind each stage to its gate field 1:1 (verify each gate's schema name). Gate fields come from L1-D02 — if D02 isn't
   done they won't be selectable; coordinate.
4. Enforce forward progression (required-step binding drives it; the gate-reversion LOCK itself is L1-G39, out of scope here).
   Render the BPF on the Import Cycle form for Risk Manager. Verify a half-filled cycle can't jump ahead.

ACCEPTANCE CRITERIA:
- 6 stages in order; each has its required gate flag; stage advances only when gate = Yes; BPF visible on Import Cycle form.

DOD CHECKLIST:
[ ] BPF has the 6 stages IN ORDER.
[ ] Each stage has one gate field bound.
[ ] Forward progression verified; no skip possible.
[ ] BPF visible/functional on the form for Risk Manager.
[ ] Smoke-tested on a fresh Import Cycle record through all 6 stages.
[ ] Sidecar L1-D01_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-D10 — BU Mapping admin pages
ASSIGNEE:  Dev 3   |   POINTS: 2   |   PRIORITY: P1   |   TYPE: MDA views
────────────────────────────────────────────────────────────────────
DESCRIPTION:

COORDINATION: the "Re-resolve BU" action invokes a flow as the SERVICE PRINCIPAL (provisioned by L1-Z02, Dev 2,
this sprint) — coordinate so the flow's SP connection is in place.

As a System Admin, I want dedicated pages for managing BU and BU mappings, so I can maintain the resolution data.

Dependencies (met): L1-A02 (BU Org Unit Mapping) — Done. L1-A03 (BP-to-BU Mapping) — Done.

FOUR SUB-PAGES: 1. Business Units (CRUD) · 2. Org Unit Mappings (L1-A02 CRUD) · 3. BP Mappings (L1-A03 CRUD) ·
4. Unresolved Items (filtered view of records that failed to resolve).

BUILD BLOCKS:
1. Add a "BU Configuration" sitemap area (admin surface).
2. Add four sub-pages, each pointing at its table with a list view + usable main form. Unresolved Items = filtered view
   of records lacking a resolved BU (confirm the filter selects the unresolved set).
3. Wire the "Re-resolve BU" action: it must INVOKE A FLOW RUNNING AS THE SERVICE PRINCIPAL — no direct UI write
   (master records are strict-immutable, L1-Z01 Decision 4). Coordinate with L1-Z02 for the SP connection.
4. Scope the "BU Configuration" subarea to System Admin only (ADR-032). Unrestricted subareas show to everyone.

ACCEPTANCE CRITERIA:
- "BU Configuration" subarea (System Admin); 4 sub-pages each with list+form CRUD; "Re-resolve BU" action linked.

DOD CHECKLIST:
[ ] "BU Configuration" visible ONLY to System Admin.
[ ] Four sub-pages with list view + form CRUD.
[ ] "Re-resolve BU" verified to invoke the resolution flow AS SERVICE PRINCIPAL (not a direct write).
[ ] As a non-admin: "BU Configuration" does not appear.
[ ] Sidecar L1-D10_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L2-D01 — Evidence reuse data model
ASSIGNEE:  Dev 3   |   POINTS: 2   |   PRIORITY: P3   |   TYPE: Schema
────────────────────────────────────────────────────────────────────
DESCRIPTION:

⚠⚠ OPEN — COORDINATOR DECISION REQUIRED BEFORE BUILD ⚠⚠
Intent is grounded (ADR-025 snapshot-matching; additive junction; reuse flag), but 3 schema decisions are undecided
(names freeze at save). CONFIRM BEFORE CREATING THE TABLE:
1. Junction table NAME (e.g. pei_evidenceapplicability / pei_evidencereuselink — confirm canonical).
2. Exact COLUMN INVENTORY: the two FK lookups (Evidence, Applicability), the originating-evidence reference
   (source of the snapshot match), and any match-trail metadata (matched-on, matched-at).
3. CARDINALITY: a junction implies M:N — confirm intended cardinality + uniqueness (one row per Evidence×Applicability),
   plus the reuse-flag definition (Yes/No or derived count) and that it is flow-written (L2-D03/ADR-034), never human-written.
DO NOT invent the table name or columns — a guessed shape forces rework in L2-D03 and breaks the snapshot-match audit trail.

As an Auditor, I want to know when one piece of evidence satisfies multiple controls, so the same artifact isn't requested twice.
Reuse is detected by SNAPSHOT MATCHING (ADR-025) — NOT file hash or filename.

Dependencies: none (anchored on ADR-025 — locked).

BUILD BLOCKS (run only after OPEN confirmed):
1. Create the junction table with the confirmed name (verify schema name before Save).
2. Add the FK pair (→ pei_evidence, → Applicability) + originating-evidence reference (makes reuse auditable) + match-trail metadata.
3. Add the reuse flag on pei_evidence per confirmed type. FLOW-WRITTEN only (L2-D03/ADR-034) — confirm no form exposes it editable.
4. Verify backward compat: a pre-existing Evidence still resolves to its Applicability via the original 1:1 lookup WITHOUT a
   junction row (additive — no migration, no field deletion).

ACCEPTANCE CRITERIA:
- Junction linking Evidence to multiple Applicabilities; backward-compatible 1:1 preserved; reuse flag on Evidence.

DOD CHECKLIST:
[ ] OPEN resolved: name, column inventory, cardinality (+ reuse-flag type/write path) confirmed.
[ ] Junction deployed with FK pair + originating-evidence reference.
[ ] Existing 1:1 preserved (no deletion/migration); pre-junction record still resolves without a junction row.
[ ] Reuse flag on pei_evidence, flow-written only (no human-edit path); verified.
[ ] Sidecar L2-D01_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-G02 — Evidence cannot be manually deleted
ASSIGNEE:  Dev 3   |   POINTS: 1   |   PRIORITY: P1   |   TYPE: Field security / FSP
────────────────────────────────────────────────────────────────────
DESCRIPTION:

As an Auditor, I want Evidence records protected from deletion, so ADR-025 immutability is enforced.

Dependencies: none (ADR-025 — evidence never deleted — locked).

BUILD BLOCKS:
1. Confirm target: remove Delete on pei_evidence for ALL roles (incl. BULK delete — bulk uses the same privilege; verify the bulk path).
2. Set Delete = None on every role (incl. System Admin — ADR-025 means NO human role keeps Delete; watch inherited/derived roles).
3. Verify a delete attempt fails — single AND bulk, at the form AND API/Advanced-Find paths (test the API path: a hidden
   form button doesn't mean the API blocks it).

ACCEPTANCE CRITERIA:
- FSP blocks Delete on pei_evidence for all roles; bulk delete blocked; tested by attempting delete (fails).

DOD CHECKLIST:
[ ] Delete removed for all roles; bulk also blocked.
[ ] Delete attempt (single AND bulk) fails at form AND API paths.
[ ] ADR-025 immutability enforced at the delete boundary.
[ ] Sidecar L1-G02_Tenant_Test.md = PASS before Done.


────────────────────────────────────────────────────────────────────
SUMMARY:   L1-G03 — Evidence cannot be manually created
ASSIGNEE:  Dev 3   |   POINTS: 1   |   PRIORITY: P1   |   TYPE: Flow / FSP
────────────────────────────────────────────────────────────────────
DESCRIPTION:

⚠ COORDINATION GATE — READ BEFORE BUILDING:
Full DoD needs a SERVICE-PRINCIPAL flow create to SUCCEED while human creates are blocked. That succeeding leg depends on:
- L1-Z02 (SP provisioned) — THIS SPRINT, Dev 2. Coordinate so the SP exists before verifying the create-succeeds leg.
- L1-G18 (SP FSP bypass) — NOT STARTED, NOT in Sprint 1. L1-G18 is what lets the SP retain Create despite this block.
RISK: a blanket Create-block without the SP bypass can block FLOW-PRODUCED evidence too (Flow 3D/4A), breaking ingestion.
TWO SAFE PATHS — confirm with coordinator: (1) build this FSP to EXPLICITLY EXEMPT the SP's application-user role in the
same step (fold the L1-G18 bypass for the create privilege), OR (2) sequence L1-G18 alongside this story.
DO NOT deploy a blanket Create-block that also catches the service principal.

As a System Admin, I want Evidence records only creatable via flows, so evidence has proper rule provenance.

Dependencies: none formal (ADR-025 + L1-Z01 Decision 5 — locked) + the coordination gate above.

BUILD BLOCKS:
1. Confirm target + the SP exemption: block Create on pei_evidence for all non-System roles; identify WHICH application-user/
   role is the SP that must retain Create (from L1-Z02). Target the exemption precisely — nothing broader.
2. Set Create = None for every human role; ensure the SP application user RETAINS Create (via the exemption / L1-G18 bypass).
3. Verify: human create blocked (each non-System role, form AND API) AND a service-principal flow create SUCCEEDS. If the
   SP-create leg can't yet be verified (L1-G18 not in place), record human-blocked as verified, SP-succeeds as PENDING —
   do NOT mark Done until both legs pass.

ACCEPTANCE CRITERIA:
- FSP blocks Create on pei_evidence for all roles except the SP; SP retains Create via L1-G18 bypass; verified both legs.

DOD CHECKLIST:
[ ] Create removed for all non-System (human) roles.
[ ] SP retains Create (exemption / L1-G18 bypass) — coordinate per gate.
[ ] Human create blocked at form AND API in each non-System role.
[ ] SP flow create SUCCEEDS (gated on L1-Z02 + L1-G18; if G18 not in place, leg pending, story NOT Done).
[ ] No human-originated Evidence.
[ ] Sidecar L1-G03_Tenant_Test.md = PASS (both legs) before Done.

═══════════════════════════════════════════════════════════════════════════════
## SPRINT-1 SUMMARY TABLE
═══════════════════════════════════════════════════════════════════════════════

| Story  | Dev   | Pts | Priority | Type        | Flag |
|--------|-------|-----|----------|-------------|------|
| L1-B04 | Dev 1 | 2   | P0 Crit  | Plugin      | ⚠ OPEN (ADR-066) |
| L1-B03 | Dev 1 | 2   | P0 Crit  | MDA form    | resume parked |
| L1-B10 | Dev 1 | 2   | P0 Crit  | Plugin      | — |
| L1-B15 | Dev 1 | 1   | P0 Crit  | Schema      | typo fix incl. |
| DOC-05 | Dev 1 | 1   | P2       | Doc         | — |
| L1-Z02 | Dev 2 | 3   | P0 Crit  | Infra/Flow  | ⚠ ext approval |
| L3-A01 | Dev 2 | 2   | P3       | Schema      | ⚠ OPEN (columns) |
| INF-B01| Dev 2 | 2   | P2       | Notification| — |
| INF-C01| Dev 2 | 1   | P2       | Resilience  | shares INF-B01 |
| L1-D01 | Dev 3 | 2   | P1       | BPF         | coord L1-D02 |
| L1-D10 | Dev 3 | 2   | P1       | MDA views   | coord L1-Z02 |
| L2-D01 | Dev 3 | 2   | P3       | Schema      | ⚠ OPEN (schema) |
| L1-G02 | Dev 3 | 1   | P1       | FSP         | — |
| L1-G03 | Dev 3 | 1   | P1       | FSP         | ⚠ coord L1-Z02+G18 |

TOTALS: Dev 1 = 8 · Dev 2 = 8 · Dev 3 = 8 · Sprint = 24 pts / 14 stories

THE 3 OPEN COORDINATOR DECISIONS (resolve these — they block full build of those 3 stories):
1. L1-B04 — lock ADR-066 (operator set + attribute catalog), OR approve shipping the structural subset now.
2. L3-A01 — confirm the full Engagement column inventory + the Scope composite shape & cardinality.
3. L2-D01 — confirm the junction table name + exact columns + cardinality + reuse-flag type/write-path.
