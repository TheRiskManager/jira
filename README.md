**EMS — All Stories (Jira-ready)**

279 stories · 1069.2h · 148.75 story points · 93 Done / 279 total.

Status roll-up — Done: 93 · In Progress: 2 · Partial: 1 · Not Started: 176 · Parked: 1 · Superseded: 6

Each story below is a Heading 2 section — copy a whole section into a Jira issue (the heading is the Summary, the text is the Description). Features are Heading 1 so a Word table of contents nests stories under their feature. Epic links are EMS feature keys, mapped to real epics at import time.

# L0-Z — Project Inception & Discovery (~70 hrs · Done)

13 of 13 done

## [L0-Z01] Project kickoff and scope agreement

**Status:** Done

**As a** Project Manager, **I want** to formally launch the project with stakeholders aligned on goals and scope, **so that** all parties had a shared understanding before work began.

**Acceptance criteria**

Kickoff meeting with stakeholders (Risk Manager, GRC team, IT)

Project goals and non-goals documented

High-level scope agreement signed off

RACI matrix drafted

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z02] Stakeholder interviews — Risk Manager

**Status:** Done

**As a** Project Manager, **I want** to deeply understand the Risk Manager's current pain points and vision, **so that** the EMS solution addresses real needs, not assumed ones.

**Acceptance criteria**

Interview guide prepared

2-3 interview sessions held with primary Risk Manager

Current state pain points documented (manual collection, audit gaps, scope ambiguity)

Future state vision captured (continuous evidence, gap visibility)

Notes synthesized into requirements input

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z03] Stakeholder interviews — Control Owners

**Status:** Done

**As a** Project Manager, **I want** to interview a representative sample of Control Owners across business areas, **so that** the system supports their actual workflows for evidence submission.

**Acceptance criteria**

Interview guide for Control Owners

Sessions held with 4-5 Control Owners across BUs

Current evidence submission processes documented

Feedback on simplification opportunities captured

Persona profiles drafted

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z04] Stakeholder interviews — Auditors and GRC team

**Status:** Done

**As a** Project Manager, **I want** to understand auditor expectations and GRC team requirements, **so that** the system produces audit-ready evidence packages.

**Acceptance criteria**

Auditor expectations documented (immutability, traceability, snapshot fidelity)

GRC team requirements captured (engagement workflow, finding tracking)

Compliance evidence standards reviewed

ADR-024 and ADR-025 seed concepts identified here

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z05] RSA Archer schema discovery

**Status:** Done

**As a** Builder, **I want** to fully understand the Archer data model that EMS will integrate with, **so that** the EMS schema correctly maps to source-of-truth controls.

**Acceptance criteria**

Archer entity inventory: Reference Controls, Control Procedures, Business Processes, mapping tables

Field-level documentation for each entity (data types, choice values, hierarchy)

API or export capabilities investigated

Mapping document drafted (Archer → EMS field correspondence)

Limitations and gotchas captured (e.g., flat structure, missing BU info)

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z06] LeanIX schema discovery

**Status:** Done

**As a** Builder, **I want** to understand the LeanIX application portfolio data model, **so that** EMS application records correctly reflect the system-of-record.

**Acceptance criteria**

LeanIX entity inventory: Applications, Business Capabilities, IT Components

Application attributes catalogued (15 evidence-affecting fields identified)

Display Name as match key decision (vs. internal IDs)

Export approach validated (Excel-based for POC)

Field mapping document drafted

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z07] Source-of-truth and integration approach decision

**Status:** Done

**As a** Architect, **I want** to decide how EMS pulls data from Archer and LeanIX, **so that** the integration approach is sustainable and DLP-compliant.

**Acceptance criteria**

Options evaluated: Power Automate Dataflows, custom HTTP, Excel-based pull

Dataflows blocked by DLP discovered

HTTP actions blocked by DLP discovered

Excel-based monthly sync approach selected

ADR drafted (basis for what became L0-D05)

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z08] POC scope and success criteria document

**Status:** Done

**As a** Project Manager, **I want** to define what "POC done" means concretely, **so that** we knew when to declare the POC successful and move to production planning.

**Acceptance criteria**

POC scope: 6 stages, 3-CP test cycle, full evidence collection workflow

Success criteria: end-to-end cycle execution, evidence immutability proven, gap visibility demonstrated

Out-of-scope items documented (production cutover, multi-tenant, real source integration)

POC presentation deliverable defined

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z09] Power Platform environment setup

**Status:** Done

**As a** Builder, **I want** a clean Power Platform development environment with appropriate licensing, **so that** building could begin without infrastructure friction.

**Acceptance criteria**

Dev environment provisioned (Dataverse-enabled)

Per-user Premium licenses confirmed

Solution publisher configured

Source control approach chosen (managed solution exports)

DLP policies for the environment reviewed

**Definition of Done**

Form deployed and visible in MDA

All tabs render correctly across screen sizes

Required fields enforce on save

Visible/editable per role tested

Reference doc updated with form layout

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z10] Publisher prefix and naming convention decision

**Status:** Done

**As a** Architect, **I want** to lock the publisher prefix and naming conventions before any tables were created, **so that** all assets carry consistent branding and naming.

**Acceptance criteria**

Publisher prefix `pei` selected and rationale documented

Table naming convention: `pei_<entityname>` (lowercase, no underscores in entity name)

Field naming convention: `pei_<fieldname>` (lowercase, descriptive)

Choice option set naming: `pei_<entityname><fieldname>`

Schema naming standard published

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z11] Initial conceptual data model

**Status:** Done

**As a** Architect, **I want** a draft entity-relationship model before tables were built, **so that** schema decisions were intentional rather than accumulated by accident.

**Acceptance criteria**

Whiteboard sessions to draft entity relationships

Entity list: Reference Control, CP, Application, BP, Import Cycle, Staged Records, Applicability, Evidence

Cardinality decisions: 1:N vs N:N relationships

Junction tables identified

Initial ERD diagram drafted

Reviewed against Archer/LeanIX schemas

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z12] DLP policy review and workaround discovery

**Status:** Done

**As a** Architect, **I want** to understand all DLP constraints in the target environment, **so that** the build plan accounts for connector restrictions early.

**Acceptance criteria**

DLP policies reviewed; HTTP, Dataflows, Custom Connectors all blocked

AI Builder confirmed available (replaces Copilot Studio plan)

Power Automate row-by-row pattern selected over Dataflows

ADR drafted for record (became L0-D05)

Build approach revised based on findings

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-Z · Labels: L0, L0-Z

## [L0-Z13] Initial architectural sketch and vision deck

**Status:** Done

**As a** Architect, **I want** a high-level architecture vision to communicate with leadership, **so that** stakeholders saw the bigger picture before granular work began.

**Acceptance criteria**

Architecture vision deck (15 slides)

High-level diagram: Archer → EMS → LeanIX → Reports

Layer concept introduced (later refined into 3-layer model)

Reviewed with stakeholders for buy-in

Updated based on feedback

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-Z · Labels: L0, L0-Z

# L0-A — Data Model Foundation (~32 hrs · Done)

10 of 10 done

## [L0-A01] Reference Control table

**Status:** Done

**As a** System, **I want** a Dataverse table for NIST/ISO framework controls, **so that** Control Procedures can reference governing controls.

**Acceptance criteria**

Table `pei_referencecontrol` with primary key, title, description, framework, control family

Source data hash for change detection

EMS Lifecycle Status (Active / Removed)

Form, default views, list views

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A02] Parent Business Process table

**Status:** Done

**As a** System, **I want** a Dataverse table for Archer business processes, **so that** Control Procedures can have a parent process relationship.

**Acceptance criteria**

Table `pei_parentbusinessprocess` with BP Identifier, Process Name, Owner

Source data hash, EMS Lifecycle Status

Form, views, list

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A03] Control Procedure table

**Status:** Done

**As a** System, **I want** a Dataverse table for control implementations from Archer, **so that** the system has the canonical CP records.

**Acceptance criteria**

Table `pei_controlprocedure` with CP ID, title, description, owner, coordinator, common unit, parent BP lookup, status, reference controls text, SOX flag

Source data hash, EMS Lifecycle Status, Reviewed flag

Form rebuild with command bar → Details → Attachments → Timeline pattern

Logical name discovery (`pei_description` not `pei_controlproceduredescription`) captured in Edge Case Guide

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A04] Application table

**Status:** Done

**As a** System, **I want** a Dataverse table for LeanIX applications with all evidence-affecting attributes, **so that** the system has the canonical app inventory.

**Acceptance criteria**

Table `pei_application` with primary fields, all 15 evidence-affecting fields (Hosting Type, Application Criticality, SOX, Information Classification, Usage Type, MFA Provider, Partner Facing, Privileged Access, SSO Availability, SSO Pattern, Target Hosting Class, Web Application, URL Accessible Externally, Customer Facing, Penetration Testing Required)

Org Unit Display Name field

Source data hash, EMS Lifecycle Status

Display Name uniqueness alternate key (added after discovering `pei_leanixapplicationid` match key fails at runtime)

Form with tab-based layout

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A05] Import Cycle table with 5-stage BPF

**Status:** Done

**As a** Risk Manager, **I want** a cycle orchestration table with stage gates, **so that** the workflow has a host record.

**Acceptance criteria**

Table `pei_importcycle` with Cycle Name, Status, AI Assessment, count fields, gate fields (Impact Reviewed, Classification Reviewed, Applicability Reviewed, Evidence Reviewed, Cycle Confirmed), Validation Message, Last Flow Activity

5-stage BPF (Detect / Classify / Apply / Evidence / Confirm)

Form with tab redesign (Overview, Stage 1, Stage 2, Stage 3, Stage 4, Stage 5)

Tab rename and BPF data step alignment iterations

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A06] Staged Record table

**Status:** Done

**As a** System, **I want** a per-cycle log of changes detected, **so that** Risk Manager can review what changed before processing.

**Acceptance criteria**

Table `pei_stagedrecord` with Cycle lookup, Entity Type (CP / App / RC / BP), What Changed (New / Updated / Removed / Reactivated), Entity Reference, snapshot fields

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A07] Applicability table

**Status:** Done

**As a** System, **I want** a junction table for CP × App applicability decisions, **so that** evidence requirements have a parent record.

**Acceptance criteria**

Table `pei_applicability` with CP lookup, App lookup, Applicability State, Cycle lookup, Manual Override fields

Choice values for state defined and tested

Form, views

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A08] Evidence table with snapshot fields

**Status:** Done

**As a** Auditor, **I want** Evidence records to be immutable per ADR-025, **so that** historical compliance proof is preserved.

**Acceptance criteria**

Table `pei_evidence` with Status (Gap / Pending / Collected / Not Required), SharePoint URL, file metadata

Snapshot fields per ADR-025: CP title snapshot, CP description snapshot, App display name snapshot, App attribute snapshots

Form with tabs (command bar → Details → Attachments → Timeline)

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A09] Control Mapping junction table

**Status:** Done

**As a** System, **I want** a junction table linking CPs to Reference Controls, **so that** the relationship is queryable.

**Acceptance criteria**

Table `pei_controlmapping` with CP lookup, RC lookup

Form, view

Manual population for POC scope

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-A · Labels: L0, L0-A

## [L0-A10] Choice option sets defined

**Status:** Done

**As a** System, **I want** consistent choice values across tables, **so that** Power Automate flows can match values precisely.

**Acceptance criteria**

Scope Types: Common Control=890920000, Application-Level=890920001, Hybrid=890920002

Staged Records Entity Type: CP=890920000, Application=890920001, RC=890920002, BP=890920003

Applicability: Applicable=890920000, Not Applicable=890920001

Applicability Status: Active=890920000, Inactive=890920001

All choice values documented for flow expressions

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-A · Labels: L0, L0-A

# L0-B — Power Automate Flows (~90 hrs · Done)

10 of 10 done

## [L0-B01] Flow 1: EMS Monthly Sync

**Status:** Done

**As a** System, **I want** to ingest source files and detect changes per cycle, **so that** the cycle has accurate change information.

**Acceptance criteria**

Reads source files from SharePoint (Archer + LeanIX feeds)

Hash-based change detection per record

Identifies New / Updated / Removed / Reactivated

Populates Staged Records

Generates AI assessment summary via AI Builder "Run a prompt"

Reactivation handling (records that come back from Removed)

Removal staging

Idempotency, race protection, concurrency control

File archival pattern (read content + create new file; Move/Copy fail per Edge Case Guide)

HTML strip from AI response

Inline AI prompt construction (no separate Compose action)

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 5.25 · Estimate: 40.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B02] Flow 2: EMS Gate Validation

**Status:** Done

**As a** Risk Manager, **I want** gates to enforce stage ordering, **so that** the cycle progresses only when prerequisites are met.

**Acceptance criteria**

Triggered on Cycle modify

Option B loop prevention (only triggers on relevant field changes)

Stage 5 backward detection (if any field flips back to No, blocks)

Validation Message field populated with helpful error

Queries actual tables not rollups (per Edge Case Guide)

Blocks save if invalid

Three test iterations to refine logic

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 1.75 · Estimate: 14.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B03] Flow 3A: Create Scope Classifications

**Status:** Done

**As a** System, **I want** to create per-cycle Scope Classification records for impacted CPs, **so that** Stage 2 review has data.

**Acceptance criteria**

Triggered when Stage 1 gate ticked

Iterates impacted CPs from Staged Records

Creates Scope Classification records linked to Cycle and CP

Idempotency check (don't duplicate)

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B04] Flow 3B: AI Classify Scope

**Status:** Done

**As a** System, **I want** AI to suggest Scope Type per CP, **so that** Risk Manager doesn't classify from scratch.

**Acceptance criteria**

AI Builder "Run a prompt" action

Inline AI prompt construction (per Edge Case Guide — no separate Compose)

HTML strip from AI response

Writes AI Suggested Scope Type to Scope Classification

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 7.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B05] Flow 3C: Create Applicability

**Status:** Done

**As a** System, **I want** to create CP × App applicability records based on classification, **so that** evidence requirements have parents.

**Acceptance criteria**

Triggered when Stage 3 gate ticked

Iterates CPs by Final Scope Type

For Application-Level: creates one Applicability per app

For Common Control: creates one Applicability with NULL app

For Hybrid: creates per-app + summary

Idempotency, race protection

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B06] Flow 3D: EMS Evidence Generation

**Status:** Done

**As a** System, **I want** Evidence records created at Stage 3 gate (not Stage 5), **so that** evidence collection can begin earlier.

**Acceptance criteria**

Race protection: re-fetch Cycle + Prior Gates Incomplete OR condition

Idempotency: Find Existing + length=0 check before Create

In-memory match pattern using Filter array action (per Edge Case #29 — `filter()` not in PA expression schema)

Orphan detection

Snapshot field population per ADR-025

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 1.5 · Estimate: 12.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B07] Flow 4A: EMS Confirmation (Stage 5 closure)

**Status:** Done

**As a** Risk Manager, **I want** cycle closure to set state correctly, **so that** post-cycle workflows fire and master records reflect the cycle.

**Acceptance criteria**

Triggered on Cycle Confirmed = Yes

Cycle Status → Completed

Reviewed flag set on impacted master records (CPs, Apps)

Removed records deactivated (EMS Lifecycle Status flipped)

Notifications sent to risk-manager@ems.com

Race protection

Live test: produced exactly expected count (1+21+20=42 evidence for 3-CP cycle)

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 2.5 · Estimate: 18.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B08] Form Script: BPF↔tab navigation

**Status:** Done

**As a** Risk Manager, **I want** the form tab to follow BPF stage selection, **so that** I see the relevant content for the current stage.

**Acceptance criteria**

Form script `pei_EMSImportCycleFormScript.js` (first documented JavaScript exception)

Two handlers: `addOnStageChange` + `addOnStageSelected`

Decision: NO auto-switch on form load

Captured in `EMS_Form_Scripts_Reference.md`

**Definition of Done**

Form deployed and visible in MDA

All tabs render correctly across screen sizes

Required fields enforce on save

Visible/editable per role tested

Reference doc updated with form layout

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B09] Edge Case Handling Guide

**Status:** Done

**As a** Builder, **I want** documented gotchas to prevent re-encountering known issues, **so that** future flow work doesn't waste time.

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-B · Labels: L0, L0-B

## [L0-B10] Flow operational hardening (cross-cutting)

**Status:** Done

**As a** Builder, **I want** consistent operational patterns across all flows, **so that** failures are recoverable and behavior is predictable.

**Acceptance criteria**

Race protection patterns (re-fetch + check) reusable across flows

Idempotency patterns (Find Existing + length=0) reusable

Concurrency limits (1 concurrent run on critical flows)

Last Flow Activity field updates for operational visibility

Standardized error handling and logging approach

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-B · Labels: L0, L0-B

# L0-C — Model-Driven App UI Foundation (~38 hrs · Done)

2 of 3 done

## [L0-C01] Template 3 Navy Sidebar shell

**Status:** Done

**As a** Risk Manager, **I want** a consistent visual shell across all screens, **so that** the app feels professional and cohesive.

**Acceptance criteria**

Navy chrome (#1e2030), header (#282b3e), gold logo (#f49600)

Green active nav (#00a758) + gold border

Body bg (#f0f1f3), content bg (#fff)

CSS locked and documented in user memory

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-C · Labels: L0, L0-C

## [L0-C02] 17-screen Package C suite (S1-S8 + S9-S17)

**Status:** Partial

**As a** Risk Manager, **I want** dedicated screens for each capability area, **so that** I can navigate to relevant work directly.

**Acceptance criteria**

S1-S8 rebuilt with native MDA patterns at version 50

S9-S17 at v43 (pending rebuild that's now superseded by Package C 18→8 plan)

Flat navigation, Segoe UI

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Partial · Type: Story · Points: 3.25 · Estimate: 25.0h · Epic: L0-C · Labels: L0, L0-C

## [L0-C03] Form pattern: command bar → Details → Attachments → Timeline

**Status:** Done

**As a** Risk Manager, **I want** a consistent form layout across entities, **so that** I know where to find things on every record.

**Acceptance criteria**

Evidence form

Pattern documented for use across other entity forms

**Definition of Done**

Form deployed and visible in MDA

All tabs render correctly across screen sizes

Required fields enforce on save

Visible/editable per role tested

Reference doc updated with form layout

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L0-C · Labels: L0, L0-C

# L0-D — Architectural Decisions Captured (~17 hrs · Done)

9 of 9 done

## [L0-D01] ADR-023: EMS data quality scope

**Status:** Done

**Story:** ADR-023: EMS data quality scope

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D02] ADR-024: Engagement scope immutability

**Status:** Done

**Story:** ADR-024: Engagement scope immutability

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D03] ADR-025: Evidence immutability

**Status:** Done

**Story:** ADR-025: Evidence immutability

**Definition of Done**

View deployed and accessible from sitemap

All filters/sorts work as specified

Empty state renders cleanly

Performance acceptable at production data volume

Tested across target roles

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D04] Three-layer architecture

**Status:** Done

**Story:** Three-layer architecture

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D05] DLP constraints documented

**Status:** Done

**Story:** DLP constraints documented

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D06] Evidence completeness model

**Status:** Done

**Story:** Evidence completeness model

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D07] Source system identification

**Status:** Done

**Story:** Source system identification

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D08] Publisher prefix and naming convention

**Status:** Done

**Story:** Publisher prefix and naming convention

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L0-D · Labels: L0, L0-D

## [L0-D09] Power Platform infrastructure decisions

**Status:** Done

**Story:** Power Platform infrastructure decisions

**Definition of Done**

Form deployed and visible in MDA

All tabs render correctly across screen sizes

Required fields enforce on save

Visible/editable per role tested

Reference doc updated with form layout

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-D · Labels: L0, L0-D

# L0-E — Documentation & Session Handoff Infrastructure (~30 hrs · Done)

6 of 6 done

## [L0-E01] Session handoff system (5 prompt files)

**Status:** Done

**As a** Builder, **I want** session continuity infrastructure, **so that** work resumes effectively across multiple sessions without context loss.

**Acceptance criteria**

`Prompt_1_How_We_Work.md` — working style and interaction patterns

`Prompt_2_Testing.md` — testing approach

`Prompt_3_Flow_Inventory.md` — flow-by-flow inventory and status

`Prompt_4_Progress_Tracker.md` — progress log

`Prompt_5_Handoff_Checklist.md` — session-end checklist

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-E · Labels: L0, L0-E

## [L0-E02] Definitive Flow Reference document

**Status:** Done

**As a** Builder, **I want** authoritative flow documentation, **so that** I can reference precise action specifications without re-deriving them.

**Acceptance criteria**

`Definitive_Flow_Reference.md` documenting all flows action-by-action

Triggers, conditions, expressions, error handling

Updated incrementally per flow change

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L0-E · Labels: L0, L0-E

## [L0-E03] Rules and Validations Tracker

**Status:** Done

**As a** Builder, **I want** to track non-flow validations and business rules, **so that** they don't get lost in the build noise.

**Acceptance criteria**

`Rules_And_Validations_Tracker.md` with 40 items in 7 categories

Status FSP, gate ordering, evidence protection rules

Cross-cutting audit, identity, role rules

**Definition of Done**

Rule deployed in Active status

JSON validated by parser

Plain-English rendering generated and reviewed

Tested against expected matching pairs

Tested against expected non-matching pairs

Documented in rule library

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-E · Labels: L0, L0-E

## [L0-E04] Complete System Context document

**Status:** Done

**As a** Builder, **I want** comprehensive onboarding documentation for new sessions, **so that** context is restored quickly.

**Acceptance criteria**

`EMS_Complete_System_Context.md` covering all aspects beyond Flow 1/S1

Choice values, fields, relationships

Now flagged with deprecation banner pointing to new architecture decisions

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L0-E · Labels: L0, L0-E

## [L0-E05] MDA Forms Views Reference

**Status:** Done

**As a** Builder, **I want** comprehensive UI reference, **so that** form/view changes are traceable.

**Acceptance criteria**

`MDA_Forms_Views_Reference.md` with form layouts, view definitions, business rules

**Definition of Done**

Form deployed and visible in MDA

All tabs render correctly across screen sizes

Required fields enforce on save

Visible/editable per role tested

Reference doc updated with form layout

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-E · Labels: L0, L0-E

## [L0-E06] POC presentation deliverables

**Status:** Done

**As a** Stakeholder, **I want** demo-ready presentation materials, **so that** stakeholders see the POC's progress.

**Acceptance criteria**

`EMS_POC_Demo_Guide.html` — narrative walkthrough

`EMS_POC_Technical_Review.html` — technical deep dive

`EMS_POC_Technical_Review_Narrative.html` — narrative version

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-E · Labels: L0, L0-E

# L0-F — Testing & Validation Infrastructure (~16 hrs · Done)

5 of 5 done

## [L0-F01] Flow 1 QA test suite

**Status:** Done

**As a** Builder, **I want** a regression test suite for Flow 1, **so that** future changes don't break monthly sync.

**Acceptance criteria**

`Flow1_QA_Test_Cases.md` documenting 20 test scenarios

Each scenario: setup, expected behavior, validation steps

All cases verified passing

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-F · Labels: L0, L0-F

## [L0-F02] Flow 2 gate validation tests

**Status:** Done

**As a** Builder, **I want** test cases for gate ordering, **so that** Flow 2 enforces correctly.

**Acceptance criteria**

3 test cases: forward progression, backward block, validation message

All passing

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-F · Labels: L0, L0-F

## [L0-F03] Flow 3D evidence generation live test

**Status:** Done

**As a** Builder, **I want** to validate Flow 3D in production-like conditions, **so that** evidence is generated correctly at scale.

**Acceptance criteria**

Live test: 88 Evidence records created in cycle

Edge case validation: 1 evidence correctly flipped to Not Required after rule change

Documented in flow inventory

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-F · Labels: L0, L0-F

## [L0-F04] Flow 4A confirmation live test (3-CP cycle)

**Status:** Done

**As a** Builder, **I want** to validate end-to-end cycle closure, **so that** sign-off behavior is correct.

**Acceptance criteria**

Live test with 3 CPs producing 42 Evidence records (1+21+20)

Matched expected count exactly

Validated state transitions, deactivations, notifications

**Definition of Done**

Flow deployed and active

All actions work end-to-end with test data

Race condition test passes (concurrent triggers)

Idempotency test passes (re-run produces same outcome)

Error handling tested (forced failure → expected behavior)

Production-scale test passes

Flow documented in flow inventory

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-F · Labels: L0, L0-F

## [L0-F05] End-to-end cycle smoke testing

**Status:** Done

**As a** Builder, **I want** end-to-end cycle smoke tests across multiple iterations, **so that** integrated behavior is verified.

**Acceptance criteria**

Multiple cycle dry-runs across sessions

Validated stages progressing correctly

Edge cases discovered and added to Edge Case Guide

**Definition of Done**

All test cases executed

All cases pass (or failures investigated and resolved)

Test results documented

Regression suite updated

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L0-F · Labels: L0, L0-F

# L0-G — Architecture Lock-In & Strategic Pivot (~22 hrs · Done)

5 of 5 done

## [L0-G01] Layer 1 deep analysis

**Status:** Done

**As a** Builder, **I want** to understand scale concerns before locking the architecture, **so that** the new design addresses production realities.

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-G · Labels: L0, L0-G

## [L0-G02] Layer 1 architecture decisions document (locked)

**Status:** Done

**As a** Builder, **I want** authoritative architecture decisions documented, **so that** all subsequent design references one source of truth.

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L0-G · Labels: L0, L0-G

## [L0-G03] Document audit and deprecation banners

**Status:** Done

**As a** Builder, **I want** to align all 55 project files with the new architecture, **so that** stale docs don't confuse future work.

**Definition of Done**

Document drafted and reviewed

Screenshots up to date

Linked from relevant entry points

Stored in canonical location

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L0-G · Labels: L0, L0-G

## [L0-G04] Production data model v4

**Status:** Done

**As a** Builder, **I want** an updated schema reflecting the new architecture, **so that** implementation has clear targets.

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L0-G · Labels: L0, L0-G

## [L0-G05] Layer 1 architecture presentation deck

**Status:** Done

**As a** Stakeholder, **I want** a presentable architecture overview, **so that** the new direction is communicable.

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L0-G · Labels: L0, L0-G

# L1-Z — Architectural Pre-work (~8 hrs)

1 of 2 done

## [L1-Z01] Resolve open architectural decisions blocking forward work

**Status:** Done

**As a** Architect, **I want** to resolve five open architectural questions documented in the Apr 24 Tracker Overview, **so that** Layer 1 forward work (BU model, rules engine, Rules & Validations FSP) can proceed without ambiguity.

**Acceptance criteria**

Decision 1 — Gate reversion policy LOCKED Apr 28, 2026: NOT ALLOWED. Once a gate is ticked Yes it cannot be unticked, uniformly across all 6 stages. Implementation lives in L1-G39 (Gate reversion lock + warning dialog). Pattern: one-way state transitions for cycle progression. Full rationale and escape-hatch detail in the Outcomes section below.

Decision 2 — Service principal identity LOCKED Apr 28, 2026: REQUIRED. All production flows must run as a service principal, not Ahmad's personal account. Implementation lives in L1-Z02 (provisioning + 7-flow migration) and L1-G18 (FSP bypass config). Full rationale in the Outcomes section below.

Decision 3 — Security roles inventory LOCKED Apr 29, 2026: 7 ROLES (System Admin / Risk Manager / Control Owner / Control Tester / Auditor / Stakeholder / System). Mixed scoping model (org-wide / BU-scoped / per-record / engagement-scoped / read-only / service principal). Implementation lives in INF-A01 + INF-A02 + ADR-032. Full per-role definitions and rationale in the Outcomes section below.

Decision 4 — Master record manual override capability LOCKED Apr 29, 2026: NO OVERRIDE. Strict immutability for human users on FSP-protected fields of `pei_controlprocedure`, `pei_application`, `pei_referencecontrol`, `pei_parentbusinessprocess`; all writes route through service-principal-run flows. Implementation lives in L1-G38 + ADR-033 + L1-OPS01 (operational runbook). Full rationale and trade-offs in the Outcomes section below.

Decision 5 — Evidence Status flip mechanism LOCKED Apr 29, 2026: FLOW-BASED, NO BACKWARD TRANSITIONS. All `pei_evidencestatus` writes performed by service-principal flows; no human direct writes; no backward transitions allowed (parallel to Decision 1 pattern). 6 choice values confirmed against tenant. Implementation lives in L1-G36 + ADR-034 + L2-A02b / L2-A03b / L2-A03c / L2-A04b. Full state-machine detail in the Outcomes section below.

Each decision recorded as an ADR or appended to the existing ADR list (ADR-032, ADR-033, ADR-034 are the three captured this cycle)

Implementation implications captured per decision (downstream stories listed above and consolidated in the Outcomes section's effort-unblocked summary)

Memory updated with the 5 locked decisions

Downstream stories updated to reflect locked decisions (acceptance criteria + dependencies)

**Definition of Done**

All 5 decisions documented and locked (Gate reversion one-way / Service principal required / 7 production roles / Strict master-record immutability with no override / Evidence Status flow-based with no backward transitions) on Apr 28-29, 2026

ADR-032, ADR-033, ADR-034 captured in the Decision Log as formal architecture decision records for Decisions 3, 4, and 5 respectively

Downstream cascade defined (~37 hrs of newly-defined or rewritten stories): L1-Z02, L1-G18, L1-G36, L1-G38, L1-G39, INF-A01, INF-A02, L3-A07, L1-OPS01, L2-A02b/A03b/A03c/A04b — each with acceptance criteria + dependencies updated to reflect the locked decisions

Memory updated with the 5 decisions (recorded as part of the working-style memory at the time)

Two preexisting findings caught and addressed during the decision work: schema gap (engagement-member junction table required for Auditor scoping → L3-A07 created) and documentation drift (`pei_status` / fictional "Collected" state corrected to `pei_evidencestatus` + the 6 tenant-confirmed choice values)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-Z · Labels: L1, L1-Z

## [L1-Z02] Service principal setup + flow migration

**Status:** Not Started

**As a** System Admin, **I want** all flows running under a dedicated service principal (not Ahmad's personal account), **so that** the system can be deployed to production per company policy and FSP-based integrity rules actually enforce against admin users.

**Acceptance criteria**

Service principal provisioned (App Registration in Azure AD) — coordinate with IT/security if approval required

Power Platform license assigned to service principal (per-flow or per-user license depending on tenant model)

Service principal added to relevant Dataverse security role(s) with create/write privileges on EMS tables

All 7 production flows migrated to run as service principal:

**Definition of Done**

Service principal provisioned (App Registration in Azure AD) and the Application (client) ID recorded for runbook reference

Power Platform license assigned to the service principal per the agreed model

Service principal added to the relevant Dataverse security role(s) with create/write privileges on EMS tables

All 7 production flows migrated to run as service principal (Flow 1 / Flow 2 / Flow 3A / 3B / 3C / 3D / Flow 4A) — connections updated for Dataverse, SharePoint, Office 365, AI Builder where applicable

Each flow re-tested end-to-end after migration with no regressions captured

Audit log clearly distinguishes service-principal actions from human user actions (verified by inspecting an audit entry on a record updated by a migrated flow)

Trigger field watches re-validated: no self-loop introduced where the service principal itself writes a field that re-fires the trigger

`Definitive_Flow_Reference.md` updated to record service principal as the run identity for each flow

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L1-Z · Labels: L1, L1-Z · Depends on: L1-Z01

# L1-A — Foundation: Business Unit Model (~30 hrs)

14 of 19 done

## [L1-A01] Create Business Unit table

**Status:** Done

**As a** System Admin, **I want** a Business Unit table with hierarchy support, **so that** apps and CPs can be organized by BU and rules can filter by BU.

**Acceptance criteria**

Dataverse table `pei_businessunit` created with publisher prefix `pei`

Fields: Name, BU Code, Parent BU (self-lookup), Owner (user lookup), Status (Active/Inactive)

Form, default view, list view created

Initial seed data populated (5-10 typical BUs based on org structure)

Audit log enabled on table

**Definition of Done**

`pei_businessunit` deployed with `pei_Name` (primary), `pei_bucode`, and `pei_bustatus` (Active=890920000 / Inactive=890920001); Owner via standard `ownerid`; `pei_status` avoided per the ADR-034 generic-field anti-pattern

`BU Code Unique` alternate key verified by rejecting a duplicate BU Code; default form + Active/Lookup/All views smoke-tested by saving one record

5 seed BUs created as flat siblings (FIN, ENG, HR, ENG-PLAT, ENG-APP) - the `pei_parentbu` self-lookup from the original spec was removed mid-build per ADR-035 (this org's BUs are flat)

Schema doc moved Business Unit FORWARD_PLANNED -> TENANT_TABLES (post-amendment, no Parent BU); Schema Currency drift reduced by 1

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-A · Labels: L1, L1-A

## [L1-A02] Create BU Org Unit Mapping table

**Status:** Done

**As a** System Admin, **I want** to maintain mappings from LeanIX Org Unit strings to Business Units, **so that** Flow 1 can deterministically resolve which BU each application belongs to.

**Acceptance criteria**

Dataverse table `pei_buorgunitmapping` created

Fields: Org Unit Variant (text, primary), Target BU (lookup → BU), Status, Notes, First Seen, Affected Records count

Admin form supports CRUD operations

View "Unresolved Org Units" filters where Target BU is NULL

Bulk-assign action available on view (multi-select rows → assign BU)

Audit log enabled

**Definition of Done**

`pei_buorgunitmapping` deployed with `pei_Name` (primary, "Org Unit Variant" display - logical landed as `pei_Name` because the table was saved before the primary rename; a process slip, not a platform default), `pei_targetbu`, `pei_mappingstatus` (Unresolved=890920000 default / Mapped=890920001 / Ignored=890920002), `pei_notes`, `pei_firstseen`, Affected Records count

"Unresolved Org Units" view filters Target BU = NULL; bulk-assign action on the view (multi-select -> assign BU); admin form supports CRUD

Auditing enabled and smoke-tested; ADR-035 flat-BU detour absorbed during this build

Schema doc updated (TENANT_TABLES)

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01

## [L1-A02b] Create BU Match Tokens table

**Status:** Done

**As a** System Admin, **I want** each BU to have a small set of match tokens (e.g., `US-Engineering`, `USEngineering`, `US-Eng`), **so that** Flow 1 can resolve LeanIX hierarchical Org Unit paths to the right BU automatically without per-path mapping rows.

**Acceptance criteria**

New table `pei_bumatchtoken` created (Display: BU Match Token), Standard table, Auditing enabled

Column BU (`pei_bu`): lookup -> Business Unit, Required

Column Token (`pei_Token`): text, Required, primary column

Column Priority (`pei_priority`): integer, default 0 (higher wins on tie)

Column Active (`pei_active`): Yes/No, default Yes

Audit ON on all custom fields

Added to the EMS app site map under the "BU Foundation" group

3 seed records covering US-Engineering BU's typical aliases (for L1-A07 testing)

**Definition of Done**

`pei_bumatchtoken` deployed with `pei_Token` (primary), `pei_bu` (lookup -> BU), `pei_priority` (default 0, reserved/unused by the current rule), `pei_active` (default Yes); Auditing ON

9 seed tokens populated against the real LeanIX path patterns (richer than the 3 in the original spec), each mapped to its Business Unit (BU rows added the same session); form + "Active BU Match Tokens" view verified; subarea added under "BU Foundation" and the app published

ADR-038 captured during seed design (path-segment equality replaces ADR-037 substring matching); schema doc updated (TENANT_TABLES, all 4 columns)

Verified working under Flow 1 load (May 2 test): the Tier 2 mapping branch exercised end-to-end; two doc-only bugs surfaced and fixed (Excel header colon-stripping; `pei_name` lowercase OData)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01

## [L1-A03] Create BP-to-BU Mapping table

**Status:** Done

**As a** System Admin, **I want** to maintain mappings from Parent Business Process IDs to Business Units, **so that** Flow 1 can resolve which BU each control procedure belongs to via its parent BP.

**Acceptance criteria**

Dataverse table `pei_bptobumapping` created

Fields: BP Identifier (text, primary), Target BU, Status, Notes

Admin form, view, bulk-assign action

Audit log enabled

**Definition of Done**

`pei_bptobumapping` deployed with `pei_ParentBusinessProcessIdentifier` (primary - logical correctly derived from the display name because it was set before first save), `pei_targetbu`, `pei_mappingstatus` (Unresolved=890920000 default / Mapped=890920001 / Ignored=890920002, local choice), `pei_notes`, `pei_firstseen`, Affected Records

Admin form + view + bulk-assign action delivered; Auditing enabled and smoke-tested

Schema doc updated (TENANT_TABLES)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01

## [L1-A04] Add Owning BU lookup to Application

**Status:** Done

**As a** Risk Manager, **I want** every application to have a resolved Owning BU, **so that** rule engine can evaluate BU-based applicability decisions.

**Acceptance criteria**

Field `pei_owningbu` (lookup → Business Unit) added to `pei_application`

Visible on Application form

Filterable in views

Empty allowed (NULL = unresolved)

**Definition of Done**

`pei_owningbu` added to `pei_application` (Simple behavior, Audit ON); added to the Information form + Active Applications view

Smoke tests passed: dropdown lists BUs, selection saves, hyperlink navigates to the BU record, audit captured the change (old=empty -> new=Finance)

Schema doc updated; lowercase-vs-CamelCase naming note recorded (custom lookups lowercase, Archer-imported CamelCase)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01

## [L1-A04b] Add Owning BU manual-override flag to Application

**Status:** Done

**As a** Risk Manager, **I want** to manually override the auto-resolved Owning BU on specific applications, **so that** I can set the correct BU when LeanIX Org Unit data doesn't reflect actual BU accountability.

**Acceptance criteria**

Field `pei_owningbumanual` (Yes/No, default No) added to `pei_application`

Visible on Application form and main view

Audit ON (captures who flipped the flag and when)

Required: No (default is No / not overridden)

Documented in ADR-036 — exception to ADR-033 master record immutability for `pei_owningbu`

**Definition of Done**

`pei_owningbumanual` added (default No, Audit ON) next to Owning BU on the form + view

ADR-036 captured (the curated-judgment exception); Flow 1 (L1-A07) gates resolution on this flag - skips the write when Yes

Schema doc updated (Application column count -> 237)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A04

## [L1-A05] Add Owning BU lookup to Control Procedure

**Status:** Done

**As a** Risk Manager, **I want** every control procedure to have a resolved Owning BU, **so that** rule engine can evaluate BU-based applicability decisions.

**Acceptance criteria**

Field `pei_owningbu` (lookup → Business Unit) added to `pei_controlprocedure`

Visible on CP form

Filterable in views

Derived from Parent BP's Owning BU at sync time (Flow 1 logic in L1-A09)

**Definition of Done**

`pei_owningbu` added to `pei_controlprocedure` (Simple, Audit ON); added to the Information form + Active Control Procedures view

Smoke tests passed (dropdown, save, click-through, audit); schema doc updated; naming note recorded

Fourth column-add of the same shape - bundled instructions reused (pattern identical to A04/A06)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01

## [L1-A06] Add Owning BU lookup to Parent Business Process

**Status:** Done

**As a** System Admin, **I want** every parent business process to have a resolved Owning BU, **so that** CPs can inherit BU from their parent BP.

**Acceptance criteria**

Field `pei_owningbu` (lookup -> Business Unit) added to `pei_businessprocess` (NOT `pei_parentbusinessprocess` - schema doc v4 had the wrong logical name; corrected per BL-002 reconciliation)

Populated by Flow 1 from the BP-to-BU Mapping table (deferred to L1-A08)

Lookup integrity verified: the dropdown lists BUs, selecting a BU saves, the hyperlink navigates to the BU record, and the audit history captures the change

**Definition of Done**

`pei_owningbu` added to `pei_businessprocess` (Simple, Audit ON); schema name entered lowercase before save per the A02 lesson; added to the Information form + Active Parent Business Processes view

Smoke tests passed: dropdown lists BUs, Finance saves, hyperlink navigates to the Finance BU record, audit captured Update (old=empty -> new=Finance)

Schema doc updated; lowercase-vs-CamelCase naming note recorded; population by Flow 1 deferred to L1-A08

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A01, L1-A03

## [L1-A07] Flow 1 BU resolution for Applications

**Status:** Done

**As a** System, **I want** Flow 1 to resolve and populate Owning BU on each Application during sync, **so that** all apps have BU assignments before rule evaluation runs.

**Acceptance criteria**

Flow 1 reads each app's `Org Unit Display Name` from LeanIX

Lookup in `pei_buorgunitmapping` for exact match

If found → write `pei_owningbu` on the Application

If not found → auto-create row in mapping table with NULL Target BU

Increment "Affected Records" count on the mapping row

Log resolution result in flow run history

**Definition of Done**

Tier 1 token resolution + Tier 2 mapping fallback both live in Flow 1, gated by Manual Override (Phase B) and short-circuited so Tier 1 winners aren't clobbered by Tier 2

Phase C nesting deadlock resolved via Option D: a Switch on a string classifier (`RESOLVED`/`UNRESOLVED`/`NO_MAPPING`) replaces the nested conditions, adding only one nesting level (stays under PA's cap)

The not-found path auto-creates an Unresolved mapping row and increments Affected Records; resolution logged in run history; verified end-to-end

`EMS Monthly Sync - BACKUP pre-L1-A07` recorded in Flow_Backup_Registry (ineligible for cleanup until production close)

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A02, L1-A04

## [L1-A08] Flow 1 BU resolution for Parent BPs

**Status:** Done

**As a** System, **I want** Flow 1 to resolve and populate Owning BU on each Parent BP during sync, **so that** CPs can derive BU from their parent BP.

**Acceptance criteria**

Flow 1 reads each BP's identifier

Manual Override gate: if Parent BP's `pei_owningbumanual = Yes`, skip resolution and increment ManualSkipped counter (symmetric with L1-A07's Application override per ADR-036)

Otherwise: lookup in `pei_bptobumapping` by BP identifier

If found with non-null Target BU → write `pei_owningbu` on Parent BP, increment Resolved counter

If not found → auto-create row in mapping table with NULL Target BU, increment AutoCreated counter (admin resolves later)

If found with NULL Target BU → leave Parent BP's `pei_owningbu` NULL, increment Unmapped counter

Log resolution result with all four counters

**Definition of Done**

~25 actions built across Flow 1 Sections 1 & 5; all four resolution paths proven end-to-end (Resolved -> write BU; Unmapped -> leave NULL; NotFound -> auto-create Unresolved row; ManualSkipped -> preserve existing)

Final test summary: "Resolved: 1, Unmapped: 21, Auto-Created Mapping: 1, Manual Override Skipped: 1. Total processed: 24."

5 mid-build defects diagnosed and fixed during the ~4-hr build (vs the 2.5-hr estimate); the run summary logs all four counters

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A03, L1-A06

## [L1-A09a] Add Ownership Type column to BP-to-BU Mapping table

**Status:** Done

**As a** System Admin, **I want** an Ownership Type field on the BP-to-BU Mapping table, **so that** Parent BPs can be classified as BU-owned vs Horizontal per ADR-040, enabling L1-A09's CP inheritance logic.

**Acceptance criteria**

New choice column `pei_ownershiptype` on `pei_bptobumapping` table

Choices: `BU-owned` (890920000), `Horizontal` (890920001), `Unresolved` (890920002 — default for newly-imported BPs)

Required: No (defaults to Unresolved when not set)

Audit: ON

Description references ADR-040 as the canonical source

Existing rows (current BP mappings) get migrated to `BU-owned` if Target BU is set, `Unresolved` if Target BU is empty — one-time admin update via Advanced Find or a one-off flow

Schema doc (`02_Production_Schema_v4.html`) updated to document the new column

**Definition of Done**

Global Choice "Ownership Type" created with locked numeric values; `pei_ownershiptype` added to `pei_bptobumapping` (default Unresolved, Audit ON, description references ADR-040 + ADR-051)

26 existing rows migrated (tenant truth was 26, not the 24 assumed from memory - reinforces "tenant is source of truth"); pre-change baseline snapshot captured per Phase 0.5

ADR-051 drafted the same day (Status=Inactive rows must have empty Ownership Type); schema doc updated

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: ADR-040, L1-A02

## [L1-A09] Flow 1 BU derivation for Control Procedures

**Status:** Done

**As a** System, **I want** Flow 1 to derive Owning BU on each Control Procedure from its Parent BP per ADR-040's classification model, **so that** CPs are partitioned by BU consistently with their parent processes' classification.

**Acceptance criteria**

Read Parent BP linkage: for each imported CP, read the CP's Parent Business Process Identifier

Read the BP-to-BU Mapping row by Parent BP Identifier

Active-row filter per ADR-051: skip mapping rows where Status IN (Ignored, Inactive); only Status IN (Unresolved, Mapped) are read for classification

Read Ownership Type (`pei_ownershiptype`) from the active mapping row

Manual Override gate per ADR-048: before any write, check the CP's `pei_owningbumanual`; if Yes -> skip the write entirely and preserve the existing value

Branch on Ownership Type - BU-owned (890920000): write the CP's `pei_owningbu` = the mapping row's Target BU (the actual BU lookup, not the choice value)

Branch on Ownership Type - Horizontal (890920001): write the CP's `pei_owningbu` = NULL (anchors to BP; the anchor mechanism is downstream L1-B work, out of L1-A09 scope)

Branch on Ownership Type - Unresolved (890920002): write the CP's `pei_owningbu` = NULL, increment the "BP unclassified" counter, append a warning to the summary

Branch on Ownership Type - no matching active mapping row (none, or row Ignored/Inactive): write the CP's `pei_owningbu` = NULL, increment the "BP missing/inactive" counter, append a distinct warning (a different audit signal than Unresolved)

Manual Override column: add `pei_owningbumanual` (Yes/No, default No, Audit ON, description references ADR-036 + ADR-048) to the Control Procedure table

BL-017 folded scope: extend Flow 1's decom sweep (per L1-A15/A16) to also clear `pei_ownershiptype` on the Status -> Inactive write (per ADR-051, Inactive rows must have empty Ownership Type)

Summary counters: CPs by outcome (BU-owned-inherited / Horizontal / Unresolved-BP / Missing-BP / Manual-skip), written to the run summary Compose at the end of Section 6

**Definition of Done**

Section 6.5 "CP BU Inheritance" shipped - 13 actions (C1-C13) + 7 new variables; a four-way Ownership Type Switch with the Manual-Override gate; runs every cycle regardless of CP file presence

`pei_owningbumanual` Yes/No column added to the CP table (Manual Override now consistent across Application / Parent BP / CP); the BL-017 decom-sweep extension shipped

Display-name -> identifier translation layer added (Approach 1): Archer's CP file carries BP display names but the mapping is keyed on Process IDs - 2 new actions translate, 3 existing actions rebound to the translated identifier; hash logic verified to exclude Parent BP so there is no staging blast

End-to-end test (60 active CPs): Inherited=19, Horizontal=0, Unresolved-BP=40, Missing=1, Manual-Skipped=0 (sum 60); spot-checks confirmed (process_007 CPs -> Canadian Engineering); two mid-build bugs fixed (carry-forward 2000-char truncation -> substring-before-concat, logged BL-018; Owning BU lookup binding -> OData entity-set-with-key syntax)

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A05, L1-A08, ADR-040, ADR-048, ADR-051

## [L1-A10] Backfill BU on existing records

**Status:** Superseded

**As a** System Admin, **I want** to populate Owning BU on all existing apps, BPs, and CPs, **so that** the new architecture works against existing data.

**Acceptance criteria**

One-time admin flow that iterates all active apps, BPs, CPs

Applies the same resolution logic as Flow 1

Reports count of resolved vs unresolved records

Idempotent (safe to re-run)

**Definition of Done**

Migration executed in dev environment

Pre/post counts match

Spot-check on 20+ random records confirms correctness

Existing reports/views still function

Rollback rehearsed and documented

Production migration runbook authored

**Jira fields** · Status: Superseded · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A07, L1-A08, L1-A09

## [L1-A11] BU Mapping admin notification

**Status:** Parked

**As a** System Admin, **I want** to be notified when new unresolved Org Units or BPs appear, **so that** I can resolve them before the next cycle relies on them.

**Acceptance criteria**

Daily digest flow runs every morning

Counts unresolved entries in `pei_buorgunitmapping` and `pei_bptobumapping`

If any exist → send email digest to admin with counts and links to mapping views

No email sent if no unresolved entries

**Definition of Done**

Daily digest flow runs every morning, counts unresolved entries across both mapping tables, and emails the admin with the counts plus links to the mapping views

No email is sent when both unresolved counts are zero (verified)

Flow documented in the flow reference; smoke-tested with seeded unresolved rows and with a clean (zero-unresolved) state

**Jira fields** · Status: Parked · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A02, L1-A03

## [L1-A12] Manual BU override on Application

**Status:** Superseded

**As a** Risk Manager, **I want** to manually override an application's Owning BU when needed, **so that** edge cases (cross-BU apps, mis-classified apps) can be handled.

**Acceptance criteria**

BU field on Application form is editable by Risk Manager role

Override creates audit log entry capturing prior value, new value, user, timestamp, reason

Override sets a flag indicating "manually overridden" so Flow 1 doesn't overwrite it on next sync

Override persists across sync cycles

**Definition of Done**

Table deployed to dev environment

All fields, choices, lookups, alternate keys created

Default form, default view, list view created

Smoke test record can be created and saved

Schema added to data model documentation

**Jira fields** · Status: Superseded · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A04

## [L1-A13] Re-resolve BU on existing records

**Status:** Not Started

**As a** System Admin, **I want** to trigger BU re-resolution on records when I update mappings, **so that** previously-unresolved apps/CPs get their BU populated without waiting for next cycle.

**Acceptance criteria**

"Re-resolve BU" button on BU Org Unit Mapping form

When clicked, runs resolution flow for all records using that mapping

Updates `pei_owningbu` where currently NULL

Does not override manual overrides

Reports count of records updated

**Definition of Done**

"Re-resolve BU" button on the BU Org Unit Mapping form runs the resolution flow for all records using that mapping and populates `pei_owningbu` only where it is currently NULL

Manual overrides are never overwritten (records with the A04b override flag = Yes are skipped); the action reports the count of records updated

Verified against a mix of NULL, resolved, and manually-overridden records; replaces the superseded L1-A10 backfill story (Pattern B re-resolves every cycle; this gives admins an on-demand path)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A07, L1-A12

## [L1-A14] BU resolution testing

**Status:** Not Started

**As a** Builder, **I want** comprehensive tests covering BU resolution paths, **so that** I can trust the resolution logic in production.

**Acceptance criteria**

Test cases covering: resolved match, unresolved auto-create, manual override, NULL cascade, re-resolution

Tests run against synthetic data (5 BUs, 20 apps, 50 CPs, 10 BPs)

All test cases pass

Documented in test reference doc

**Definition of Done**

All enumerated test cases run against the synthetic data and pass (resolved match, unresolved auto-create, manual override, NULL cascade, re-resolution)

Results recorded in the test reference doc with the fixture and expected-vs-actual for each case

Any defect found is logged as a backlog item rather than silently fixed in the test pass

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A07, L1-A08, L1-A09, L1-A13

## [L1-A15] Flow 1 decom sweep robustness fix (Mark BP Removed)

**Status:** Done

**As a** System, **I want** Flow 1's BP decom sweep to correctly resolve the Row ID for each BP being marked Removed, **so that** BPs missing from the Excel source file are correctly transitioned to EMS Lifecycle Status = Removed without runtime errors.

**Acceptance criteria**

`Mark BP Removed` action in `Check BP Removals` loop successfully updates each BP that has been removed from the Excel source

No `WorkflowOperationParametersRuntimeMissingValue` errors on `recordId` parameter at runtime

Behavior verified end-to-end via test where 1+ BP is in Active state in Dataverse but missing from the Excel source file (the BP should land at EMS Lifecycle Status = Removed after the run)

Decom sweep idempotent: re-running the flow against the same source should not error on already-Removed BPs (i.e. the `BP Not In File` filter and `Mark BP Removed` are scoped to Active BPs only)

Fix scope: ONLY the BP decom sweep in Section 5. Equivalent decom sweeps for RC, CP, App must be inspected for the same defect and called out — but separate stories if remediation is needed for them too

**Definition of Done**

Root cause identified (a column-name typo, not a Select-columns omission): the Row ID referenced `pei_parentbusinessprocessid`, which doesn't exist; the Parent BP table's GUID is `pei_businessprocessid` (the original author conflated the mapping table's identifier with the table GUID - exactly the BL-002 risk)

Fix applied to `Mark BP Removed` (correct Row ID column); verified end-to-end (removed BP -> Removed) and idempotent (re-run, no error); sibling RC/CP/App decom sweeps inspected and called out as separate stories if remediation is needed

Actual ~30 min (vs the 1.5-hr estimate) because the action card surfaced the fields directly

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-A · Labels: L1, L1-A

## [L1-A16] Mapping table decom cleanup for orphaned BP-to-BU rows

**Status:** Done

**As a** System, **I want** BP-to-BU mapping rows whose Parent BP has been decom'd to be soft-marked Inactive, **so that** the BP-to-BU mapping table stays honest about which rows reflect currently-Active BPs, while preserving an audit trail of historical mappings.

**Acceptance criteria**

New choice value `Inactive` (890920003) added to `pei_mappingstatus` choice column on `pei_bptobumapping` table

Flow 1's BP decom sweep (`Mark BP Removed` action area, Section 5) extended with a parallel Update row action that soft-marks the BP's mapping row Inactive

Soft-marked rows are NEVER deleted (preserves audit trail per ADR-025 immutability principle)

If a Parent BP transitions Removed → Active again (re-introduction via Excel), the orphan-Inactive mapping must be detectable. **Decision on whether to auto-reactivate or require admin action is deferred** — out of scope for L1-A16, captured as future work in BL-013

**Definition of Done**

`Inactive` (890920003) added to `pei_mappingstatus` (existing Unresolved/Mapped/Ignored preserved); table published

3 new actions in Section 5 between `Mark BP Removed` and the counter increment: `Find BP Mapping For Decom` (lowercase OData per ADR-049), `BP Mapping Exists For Decom`, and `Soft Mark Mapping Inactive` (minimal write per A15 discipline; empty If-no branch since override-Yes BPs may have no mapping)

End-to-end test passed (reactivation path verified); App-side scope dropped after schema verification (~1.5 hrs vs the 3-hr estimate)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-A · Labels: L1, L1-A · Depends on: L1-A07, L1-A08, L1-A15

# L1-B — Rule Engine (~65 hrs)

2 of 15 done

## [L1-B01] Create Rule table

**Status:** Done

**As a** System Admin, **I want** a Rule table for storing applicability rules, **so that** the system has a single source of truth for policy definitions.

**Acceptance criteria**

Dataverse table `pei_rule` created

Fields: Name, Description, Conditions JSON (multi-line text), Plain-English Rendering (multi-line text), Output (choice), Collection Scope (choice: Per app — all / Per app — same BU / Per BU/BP), Priority (number), Terminating (yes/no), Status (Active/Inactive/Draft), Effective From, Effective To, Current Version (number)

Form, view, list created

Audit log enabled

**Definition of Done**

`pei_rule` table deployed to the dev environment with all fields, choices, and the alternate key created

Default form, default view, and quick-create form generated and smoke-tested by saving one sample rule record

Audit logging enabled on the table and verified by editing a field and viewing the audit history

Schema doc updated to move Rule from the Forward-Planned section into the live-tables section

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B

## [L1-B02] Create Rule Version table

**Status:** Done

**As a** System Admin, **I want** every rule edit to create a new version snapshot, **so that** we can reconstruct what rules were active at any point in history.

**Acceptance criteria**

Dataverse table `pei_ruleversion` created

Fields: Rule (lookup), Version Number, Conditions JSON Snapshot, Output Snapshot, Collection Scope Snapshot, Effective From/To, Changed By, Change Reason

Auto-created on every Rule update via plugin or business rule

Read-only (no manual edits to past versions)

**Definition of Done**

`pei_ruleversion` table deployed to the dev environment with all snapshot fields, the Rule lookup, and the alternate key created

Default form and a read-only view generated and smoke-tested by creating one sample version row linked to a Rule

Past-version immutability enforced (no manual edit/delete path on the view) and verified by attempting an edit as a non-system user

Audit logging enabled and verified

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B01

## [L1-B03] Hidden admin form for Rule authoring

**Status:** Not Started

**As a** System Admin, **I want** a dedicated form for authoring rules with JSON editor, **so that** I can write rule expressions in a controlled environment.

**Acceptance criteria**

Custom form "Rule Admin Form" created

All fields visible including JSON Conditions text area

Form hidden from Risk Manager security role

Visible to System Admin role only via subarea in sitemap

Form has helper text describing JSON schema for conditions

**Definition of Done**

"Rule Admin Form" added to the app with all fields including the Conditions JSON text area, plus helper text describing the JSON schema

Sitemap subarea added and scoped so the form is reachable by System Admin only

Role-based visibility verified by logging in as each role: System Admin sees the form; Risk Manager does not

Helper text links to the L1-B05 schema doc (forward-link noted if B05 is not yet built)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B01

## [L1-B04] JSON validation on Rule save

**Status:** Not Started

**As a** System Admin, **I want** the system to validate my rule's JSON syntax on save, **so that** malformed rules don't reach Stage 5 evaluation.

**Acceptance criteria**

Plugin or business rule validates Conditions JSON on Rule create/update

Checks: parseable JSON, recognized operators, valid attribute names, balanced groups

If invalid → save fails with descriptive error message

If valid but referencing non-existent attribute → save warns

**Definition of Done**

Validation registered on `pei_rule` create and update

Tested across the valid case plus each invalid case: malformed JSON, unknown operator, and unbalanced group each cause the save to fail with a descriptive message naming the fault

Unknown-attribute case verified: the save succeeds with a warning surfaced

Behaviour verified end-to-end by saving sample rules covering each case

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B01

## [L1-B05] Rule expression schema documentation

**Status:** Not Started

**As a** System Admin, **I want** clear documentation of the JSON schema for rule conditions, **so that** I can author rules confidently without trial and error.

**Acceptance criteria**

Markdown doc capturing: schema, supported operators (equals, not equals, in, not in, contains, is null, is not null), supported attributes per entity type, AND/OR/NOT/group syntax

Example rules covering common patterns

Linked from the admin form helper text

**Definition of Done**

Markdown doc committed covering the schema, supported operators, per-entity attribute lists, and AND/OR/NOT/group syntax, with at least 3 worked examples

Linked from the L1-B03 admin-form helper text

Accuracy reviewed against the L1-B08 parser so the doc and the parser describe the same operator and attribute set

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B04

## [L1-B06] Plain-English rule rendering flow

**Status:** Not Started

**As a** Risk Manager, **I want** to read each rule in plain English, **so that** I can confirm rules without parsing JSON.

**Acceptance criteria**

Flow triggered on Rule create/update

Parses Conditions JSON

Generates plain-English summary like: "If CP.SOX = Yes AND App.SOX = Yes AND CP.OwningBU equals App.OwningBU, applicability is Applicable"

Writes to `pei_plainenglish` field

Re-runs if Rule is updated

**Definition of Done**

Flow triggers on `pei_rule` create and update, parses the Conditions JSON, and writes a correct plain-English summary to `pei_plainenglish`

Re-runs and overwrites on update

Verified on at least 3 sample rules of differing complexity (simple, AND/OR, and a nested group with a cross-entity comparison)

Rendered output reads correctly for a non-technical Risk Manager

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B01, L1-B04

## [L1-B07] Risk Manager-facing read-only Rule view

**Status:** Not Started

**As a** Risk Manager, **I want** to see active rules in a read-only view, **so that** I can review what rules will execute without risk of editing.

**Acceptance criteria**

Custom view "Active Rules" created, visible to Risk Manager role

Shows: Name, Plain-English rendering, Output, Collection Scope, Status, Last Modified

JSON Conditions field hidden from this view

Read-only — no New/Edit buttons available to Risk Manager

**Definition of Done**

"Active Rules" view added and made visible to the Risk Manager role

View shows the agreed columns with JSON Conditions hidden; verified by opening it as a Risk Manager

Read-only verified by logging in as Risk Manager: no New or Edit commands available on the view or its records

Filter confirmed to show active rules only

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B06

## [L1-B08] Rule expression parser

**Status:** Not Started

**As a** System, **I want** a Boolean expression parser that can evaluate rules against data, **so that** Stage 5 can determine applicability outcomes.

**Acceptance criteria**

Parser handles AND, OR, NOT, nested groups

Operators supported: equals, not equals, in, not in, contains, is null, is not null

Cross-entity comparisons supported (e.g., CP.OwningBU equals App.OwningBU)

Returns boolean result given a rule and a CP × App pair as input

Comprehensive unit tests (>30 cases covering combinations)

**Definition of Done**

Parser handles AND, OR, NOT, and nested groups, all supported operators, and cross-entity comparisons

Returns a correct boolean for a Rule plus a CP × App pair

More than 30 unit tests covering operator and nesting combinations are green

Parser behaviour matches the L1-B05 schema doc (any divergence reconciled)

**Jira fields** · Status: Not Started · Type: Story · Points: 1.25 · Estimate: 10.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B04

## [L1-B09] Rule evaluation engine with priority + termination

**Status:** Not Started

**As a** System, **I want** to evaluate rules in priority order with terminating-rule short-circuit, **so that** exclusions correctly override permissive rules.

**Acceptance criteria**

Engine iterates rules sorted by priority ascending

For each rule: evaluate condition; if matches, capture outcome

If matched rule is terminating → stop iteration, use that outcome

If all rules evaluated → Union: any matched non-terminating Applicable → Applicable; otherwise Not Applicable

Returns: outcome + list of all matched rules + Collection Scope from first non-terminating Applicable rule

Logs each evaluation step for debugging

**Definition of Done**

Engine iterates rules by priority ascending and short-circuits on the first terminating match

Unions non-terminating results (any matched non-terminating Applicable → Applicable; otherwise Not Applicable) and returns outcome plus matched rules plus the Collection Scope from the first non-terminating Applicable rule

Logs each evaluation step for debugging

Verified against bootstrap-library scenarios (B11 exclusions short-circuit; B12–B14 drivers and patterns union correctly)

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B08

## [L1-B10] Rule version snapshot on edit

**Status:** Not Started

**As a** System Admin, **I want** every rule edit to create a Rule Version snapshot automatically, **so that** historical rule states are preserved.

**Acceptance criteria**

Plugin triggered on Rule update

Captures pre-update state to new Rule Version row

Sets Effective To on prior version, Effective From on new version

Increments Current Version on Rule

Captures user, timestamp, change reason (if provided)

**Definition of Done**

Plugin registered on `pei_rule` update; captures the pre-update state into a new `pei_ruleversion` row

Sets Effective To on the prior version and Effective From on the new version; increments Current Version on the Rule

Captures user, timestamp, and change reason (when provided)

Verified end-to-end: editing a Rule creates exactly one version row with correct effective dates, an incremented version, and captured metadata

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B02, L1-B01

## [L1-B11] Bootstrap rule library — exclusions

**Status:** Not Started

**As a** Risk Manager, **I want** common-sense exclusion rules in place from day one, **so that** decommissioned, vendor-managed, and test/dev environments don't generate evidence requirements.

**Acceptance criteria**

Rule "Decommissioned apps excluded" — terminating, priority 1

Rule "Vendor-managed apps excluded" — terminating, priority 2

Rule "Test/Dev environment excluded" — terminating, priority 3

Rule "Inactive CPs excluded" — terminating, priority 4

Rule "Unresolved BU app excluded" — terminating, priority 5

All authored, validated, plain-English rendered

**Definition of Done**

Each named exclusion authored as a `pei_rule` record with the correct Output, Collection Scope, Priority (1–5), and Terminating = Yes

Each passes L1-B04 JSON validation on save

Each renders correct plain-English via the L1-B06 flow

The set short-circuits correctly on sample CP × App pairs (a decommissioned, vendor-managed, test/dev, inactive-CP, or unresolved-BU case is excluded)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B03, L1-B04, L1-B06

## [L1-B12] Bootstrap rule library — compliance drivers

**Status:** Not Started

**As a** Risk Manager, **I want** compliance-driver applicability rules, **so that** SOX/PCI/HIPAA controls map to relevant apps automatically.

**Acceptance criteria**

Rule "SOX → SOX same BU" — Per app — same BU

Rule "PCI → PCI any BU" — Per app — all (or per app — same BU per policy)

Rule "HIPAA → PHI apps" — Per app — same BU

Rule "Customer-facing → external-accessible apps" — Per app — same BU

Each authored, validated, plain-English rendered

**Definition of Done**

Each compliance-driver rule (SOX, PCI, HIPAA, customer-facing) authored as a `pei_rule` record with the correct Output, Collection Scope, Priority (higher band), and Terminating = No

Each passes L1-B04 JSON validation on save

Each renders correct plain-English via the L1-B06 flow

The set unions correctly on sample CP × App pairs (a SOX same-BU app and a PCI app each resolve Applicable at the right scope)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B03, L1-B04, L1-B06

## [L1-B13] Bootstrap rule library — BU patterns

**Status:** Not Started

**As a** Risk Manager, **I want** default BU-specific rules, **so that** controls owned by a BU apply to apps in that BU.

**Acceptance criteria**

Rule "BU-specific control → apps in same BU" — Per app — same BU

Rule "Enterprise security controls (IT BU) → all apps" — Per app — all

Each authored, validated, plain-English rendered

**Definition of Done**

Each BU-pattern rule authored as a `pei_rule` record with the correct Output, Collection Scope, Priority (driver/pattern band), and Terminating = No

Each passes L1-B04 JSON validation on save

Each renders correct plain-English via the L1-B06 flow

The set unions correctly on sample CP × App pairs (a BU-owned control maps to same-BU apps; an IT-BU control maps to all apps)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B03, L1-B04, L1-B06

## [L1-B14] Bootstrap rule library — organization-level

**Status:** Not Started

**As a** Risk Manager, **I want** rules for organization-level controls (collected once, not per-app), **so that** policies and frameworks are evidenced at the right scope.

**Acceptance criteria**

Rule "Common Unit = Enterprise → Per BU/BP scope" producing one record at the BU level

Rule "Policy/framework controls → Per BU/BP scope"

Each authored, validated, plain-English rendered

**Definition of Done**

Each organization-level rule (Common Unit = Enterprise; policy/framework controls) authored as a `pei_rule` record with Output, Collection Scope = Per BU/BP, the correct Priority (driver/pattern band), and Terminating = No

Each passes L1-B04 JSON validation on save

Each renders correct plain-English via the L1-B06 flow

The set produces one record at the BU/BP level (not per app) on sample data, confirming the Per BU/BP scope resolves correctly

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B03, L1-B04, L1-B06

## [L1-B15] Create Cycle Rule Execution Log table

**Status:** Not Started

**As a** System Admin, **I want** a Cycle Rule Execution Log table that records every rule firing during a cycle, **so that** the platform has an immutable, queryable audit trail of which rule version evaluated which CP × App pair to which outcome.

**Acceptance criteria**

Dataverse table `pei_cycleruleexecutionlog` created (corrected spelling — the schema doc placeholder `pei_cyclereexecutionlog` is fixed as part of this story)

Fields per the D-06 cycle-pinning contract (ADR-054, authored before this story builds): Rule Version (lookup to `pei_ruleversion`), Rule Version JSON Snapshot (multi-line text — embedded immutable copy), Cycle (lookup to Import Cycle), Control Procedure (lookup), Application (lookup), Evaluation Result (choice: Applicable / Not Applicable / Error), Error Message (multi-line text — populated when D-01a NULL-as-error fires), Evaluated At (datetime), Evaluator Version (text — engine version identifier for forward-compat)

Read-only at the platform level (no manual edits; rows created only by the L1-C05 evaluation flow once that ships)

Audit log enabled

Schema doc updated: placeholder row replaced with full column inventory; typo correction logged

**Definition of Done**

`pei_cycleruleexecutionlog` table deployed to dev with the full D-06 column set, both lookups, and the embedded JSON snapshot column

Read-only at the platform level confirmed — no manual create/edit path; rows are written only by the L1-C05 evaluation flow once it ships — and smoke-tested by inserting one sample log row via the system context

Audit logging enabled and verified

Schema doc updated: the placeholder row replaced with the full column inventory and the `pei_cyclereexecutionlog` typo correction logged

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-B · Labels: L1, L1-B · Depends on: L1-B01, L1-B02, ADR-054

# L1-C — Stage 5 Evaluation Flow (~25 hrs)

0 of 6 done

## [L1-C01] Stage 5 evaluation flow skeleton

**Status:** Not Started

**As a** System, **I want** a flow that triggers when Stage 4 gate is ticked, **so that** rules execute deterministically on cycle data.

**Acceptance criteria**

Flow triggered when `pei_rulesconfirmed` flips Yes on Import Cycle

Race protection: re-fetch cycle and check Stage 4 still Yes; check Stage 5 still No

Sets a "Evaluation In Progress" status

Logs start time

**Definition of Done**

Flow `EMS Stage 5 Evaluation` deployed in dev with trigger on `pei_rulesconfirmed` → Yes on Import Cycle

In-flow race guard present: re-fetch cycle, terminate cleanly if Stage 4 ≠ Yes or Stage 5 ≠ No

"Evaluation In Progress" status written to the cycle per the locked field convention

Start timestamp logged on the cycle

Smoke-tested by toggling `pei_rulesconfirmed` Yes twice on the same record: only one downstream evaluation path runs end-to-end

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-B09

## [L1-C02] Iterate CP × App pairs

**Status:** Not Started

**As a** System, **I want** to iterate every CP × App combination in scope for the cycle, **so that** rules are evaluated against all relevant pairs.

**Acceptance criteria**

Get list of active CPs (with resolved BU)

Get list of active Apps (with resolved BU)

Iterate the Cartesian product

Skip pairs where either side has NULL BU

Skip pairs where either entity is in Removed status

**Definition of Done**

Active + resolved-BU CP list and Active + resolved-BU App list both retrieved (NULL Owning BU excluded; Removed status excluded — verified by inspecting the query filter)

Cartesian iteration produces the expected pair count on the F01 fixture (50 apps × 100 CPs = 5,000 pairs)

No timeouts at F01 scale; chunking or pagination strategy in place if F02 scale exceeds PA's apply-to-each default

One pair = one downstream rule-evaluation call (deterministic count when wired to C03)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-C01

## [L1-C03] Evaluate rules per pair

**Status:** Not Started

**As a** System, **I want** to evaluate the rule engine against each CP × App pair, **so that** applicability outcomes are determined.

**Acceptance criteria**

Calls rule evaluation engine for each pair

Captures outcome (Applicable / Not Applicable), Collection Scope, list of matched rules

Continues to next pair on individual failures (don't fail whole flow on one error)

**Definition of Done**

Rule evaluator invoked for each pair from C02

Per-pair outcome captured: outcome value + Collection Scope + list of matched rules

Failure isolation verified: a deliberately-broken rule on one pair does not halt the cycle; remaining pairs continue and report

Outcomes available for C04 to consume via the agreed handoff shape (in-memory variable, return value, or staged-record write)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-C02, L1-B09

## [L1-C04] Materialize Applicability records

**Status:** Not Started

**As a** System, **I want** to create or update Applicability records based on rule outcomes, **so that** downstream Stage 5 review and Stage 6 evidence creation has data to work with.

**Acceptance criteria**

For each evaluated pair: find existing Applicability record (CP + App + Cycle)

If outcome = Applicable, no existing record → create new with rule provenance

If outcome = Applicable, existing exists → update if state changed

If outcome = Not Applicable, existing was Applicable → flip to "Was Applicable, Now Not Required"

Per BU/BP scope: create one record at BU level, not per-app

Idempotent: safe to re-run

**Definition of Done**

For Applicable outcomes with no existing record: Applicability row created on `pei_applicability` table with rule provenance (matched rule lookup + Rule Version snapshot per ADR-054 pinning)

For Applicable outcomes with an existing record: updated only when state changed (no-op churn suppressed in audit log)

For Not Applicable outcomes where existing record was Applicable: flipped to "Was Applicable, Now Not Required" per the agreed field mapping

BU/BP-scoped Collection Scope produces one record at the BU level, not per-app (verified by record count on a mixed-scope fixture pair set)

Idempotent: a second run of C04 over the same pair set produces zero new records and zero spurious updates (verified by re-trigger on the F01 fixture)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-C03

## [L1-C05] Write Cycle Rule Execution Log

**Status:** Not Started

**As a** Auditor, **I want** every rule's execution to be logged per cycle, **so that** I can reconstruct what rule versions ran when.

**Acceptance criteria**

For each rule that participated in the cycle: write Cycle Rule Execution Log row

Captures: Cycle, Rule Version (snapshot lookup), Execution Started/Completed, Pairs Evaluated, Matches Produced, Terminations Triggered

Read-only after cycle close

**Definition of Done**

For each rule that participated in the cycle, one Execution Log row written

All required fields populated: Cycle lookup, Rule Version snapshot lookup, Started + Completed timestamps, Pairs Evaluated count, Matches Produced count, Terminations Triggered count

Read-only-after-cycle-close enforced and verified by attempting an edit as Risk Manager — blocked

Smoke-tested against the F01 fixture: row count equals rules-that-fired count; the count fields match independent tallies of pairs / matches / terminations

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-C04

## [L1-C06] Generate evidence requirements

**Status:** Not Started

**As a** Control Owner, **I want** evidence collection requirements created for each Applicable applicability, **so that** I know what to provide.

**Acceptance criteria**

For each new Applicable Applicability: create Evidence record with Status = Gap

Capture snapshot fields per ADR-025: CP title, CP description, app attributes, producing rule version

Generate SharePoint folder per scope (per app for app-scoped, per BU for BU-scoped)

Idempotent: don't duplicate Evidence for existing applicabilities

**Definition of Done**

For each new Applicable Applicability, one Evidence record created on `pei_evidence` with `pei_evidencestatus` = Gap, written by the service-principal flow per ADR-034 (no human direct write)

Snapshot fields populated per ADR-025: CP title, CP description, app attribute snapshot, producing rule version

SharePoint folder created per Collection Scope (per-app or per-BU) at the agreed path

Idempotent: re-running C06 over the same Applicability set creates zero new Evidence and zero duplicate SharePoint folders

Smoke-tested against the F01 fixture: Evidence count equals new-Applicable count from C04; all expected folders present at the agreed paths

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-C · Labels: L1, L1-C · Depends on: L1-C04

# L1-D — UI Redesign for 6-Stage Cycle (~40 hrs)

0 of 11 done

## [L1-D01] Update Import Cycle BPF to 6 stages

**Status:** Not Started

**As a** Risk Manager, **I want** a 6-stage Business Process Flow on Import Cycle, **so that** the cycle progression matches the new architecture.

**Acceptance criteria**

BPF stages: Detect Changes / Verify App BU / Verify CP BU / Confirm Rules / Review Output / Sign-off

Each stage has its required field (gate flag)

Stage advances only when current gate ticked Yes

BPF visible on Import Cycle form

**Definition of Done**

Business Process Flow `EMS Import Cycle` deployed with the 6 stages in order

Each stage has its required gate field bound (one stage → one flag)

Forward progression verified: a stage only advances when its gate is ticked Yes; the next stage gates appropriately

BPF visible and functional on the Import Cycle form for the Risk Manager role

Smoke-tested on a fresh Import Cycle record: progression through all six stages happens in order, no skip is possible

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-D · Labels: L1, L1-D

## [L1-D02] Add new gate fields to Import Cycle

**Status:** Not Started

**As a** System, **I want** dedicated gate fields for each new stage, **so that** Flow 2 (gate validation) and Stage 5 evaluation can trigger correctly.

**Acceptance criteria**

Fields added: `pei_appbuverified`, `pei_cpbuverified`, `pei_rulesconfirmed`, `pei_outputreviewed`

Existing fields preserved: `pei_impactreviewed`, `pei_cycleconfirmed`

Old fields deprecated: `pei_classificationreviewed`, `pei_applicabilityreviewed`, `pei_evidencereviewed`

**Definition of Done**

`pei_appbuverified`, `pei_cpbuverified`, `pei_rulesconfirmed`, `pei_outputreviewed` deployed on `pei_importcycle` with consistent Two Options type, Audit ON, default No

`pei_impactreviewed` and `pei_cycleconfirmed` preserved (no schema change confirmed by inspecting the table post-deploy)

Deprecated fields (`pei_classificationreviewed`, `pei_applicabilityreviewed`, `pei_evidencereviewed`) handled per the agreed deprecation strategy

Schema doc updated to record the new four fields and reflect the deprecations

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01

## [L1-D03] Stage 1 view: Detect Changes

**Status:** Not Started

**As a** Risk Manager, **I want** Stage 1 to show me what changed in this cycle, **so that** I can acknowledge the change set before proceeding.

**Acceptance criteria**

Tab "Stage 1 — Changes" on Import Cycle form

AI Assessment displayed prominently as headline content

Counts shown (CP New/Updated/Removed/Reactivated; App same)

Staged Records sub-grid collapsible (hidden by default; expand on user action)

Gate "Impact Reviewed = Yes" tickbox

**Definition of Done**

Tab "Stage 1 — Changes" added to the Import Cycle main form

AI Assessment displayed prominently as headline content within the tab via a native MDA control

Counts shown (CP New / Updated / Removed / Reactivated; App same) using calculated columns or related-record counts — not script

Staged Records sub-grid present, collapsible, hidden by default; sub-grid record clicks navigate to the full-page form

Gate `pei_impactreviewed` tickbox surfaced on the tab

Role visibility verified against the 7-role model: Risk Manager sees the tab; other roles per the agreed matrix

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01

## [L1-D04] Stage 2 view: Verify App BU

**Status:** Not Started

**As a** Risk Manager, **I want** Stage 2 to show app BU resolution status, **so that** I can confirm BUs resolved correctly before proceeding.

**Acceptance criteria**

Tab "Stage 2 — App BU" on Import Cycle form

Shows count: "X of Y apps resolved, Z unresolved"

Sub-grid showing only unresolved apps (linked to BU Mapping for admin action)

Gate "App BU Verified = Yes" tickbox

**Definition of Done**

Tab "Stage 2 — App BU" added to the Import Cycle main form

Count "X of Y apps resolved, Z unresolved" displayed via a native MDA control

Sub-grid showing only unresolved apps (NULL Owning BU); each row's click navigates to the full-page app form, and a link out to BU Mapping is present per the agreed visibility

Gate `pei_appbuverified` tickbox surfaced on the tab

Role visibility verified against the 7-role model

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01, L1-A07

## [L1-D05] Stage 3 view: Verify CP BU

**Status:** Not Started

**As a** Risk Manager, **I want** Stage 3 to show CP BU resolution status, **so that** I can confirm CPs have BUs assigned before proceeding.

**Acceptance criteria**

Tab "Stage 3 — CP BU" on Import Cycle form

Shows count: "X of Y CPs resolved, Z unresolved"

Sub-grid showing only unresolved CPs (linked to Parent BP mapping)

Gate "CP BU Verified = Yes" tickbox

**Definition of Done**

Tab "Stage 3 — CP BU" added to the Import Cycle main form

Count "X of Y CPs resolved, Z unresolved" displayed via a native MDA control

Sub-grid showing only unresolved CPs with a link to Parent BP mapping; row clicks navigate to the full-page CP form

Gate `pei_cpbuverified` tickbox surfaced on the tab

Role visibility verified against the 7-role model (Risk Manager primary)

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01, L1-A09

## [L1-D06] Stage 4 view: Confirm Rules (read-only)

**Status:** Not Started

**As a** Risk Manager, **I want** Stage 4 to show me all active rules in plain English, **so that** I can confirm the rule set before evaluation runs.

**Acceptance criteria**

Tab "Stage 4 — Rules" on Import Cycle form

Sub-grid of Active Rules (read-only): Name, Plain-English rendering, Status, Last Modified

"View Rules Catalog" button for navigation to admin governance page

Gate "Rules Confirmed = Yes" tickbox

**Definition of Done**

Tab "Stage 4 — Rules" added to the Import Cycle main form

Sub-grid of Active Rules displays Name, Plain-English rendering, Status, Last Modified; sub-grid is read-only on this tab

"View Rules Catalog" navigation present and resolves to L1-D09 admin page per the agreed role gating

Gate `pei_rulesconfirmed` tickbox surfaced on the tab; ticking Yes triggers the downstream L1-C01 evaluation flow

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01, L1-B07

## [L1-D07] Stage 5 view: Review Output

**Status:** Not Started

**As a** Risk Manager, **I want** Stage 5 to summarize what rules produced and surface anomalies, **so that** I can confirm output is sensible before sign-off.

**Acceptance criteria**

Tab "Stage 5 — Output" on Import Cycle form

Summary section: count of new applicabilities, removed applicabilities, evidence requirements generated

Filters: by BU, by CP, by App, by rule

Anomaly section: Unresolved BU records, volume changes >X%, mass removals, mass new, zero-fire rules, no-match apps

Drill into Applicability records via sub-grid

Gate "Output Reviewed = Yes" tickbox

**Definition of Done**

Tab "Stage 5 — Output" added to the Import Cycle main form

Summary section displays counts: new applicabilities, removed applicabilities, evidence requirements generated (Evidence count from L1-C06)

Filters wired to Applicability sub-grid: BU, CP, App, rule

Anomaly section surfaces each defined anomaly type per the locked thresholds

Drill into Applicability records via sub-grid; sub-grid clicks navigate to the full-page Applicability form

Gate `pei_outputreviewed` tickbox surfaced on the tab

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01, L1-C04

## [L1-D08] Stage 6 view: Sign-off

**Status:** Not Started

**As a** Risk Manager, **I want** a clean Stage 6 sign-off ceremony, **so that** I can close the cycle deliberately.

**Acceptance criteria**

Tab "Stage 6 — Sign-off" on Import Cycle form

Final summary of cycle outcomes

Gate "Cycle Confirmed = Yes" tickbox

On tick → triggers Stage 6 closure flow

**Definition of Done**

Tab "Stage 6 — Sign-off" added to the Import Cycle main form

Final summary of cycle outcomes displayed per the agreed content set

Gate `pei_cycleconfirmed` tickbox surfaced on the tab

On tick: the downstream closure flow fires and the cycle progresses to closed state — verified by ticking on a smoke-test cycle

Gate one-way behavior present (cannot be unticked once Yes) per L1-Z01 Decision 1, enforced by L1-G39 — verified by attempting to untick

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D01

## [L1-D09] Rules Catalog admin page

**Status:** Not Started

**As a** System Admin, **I want** a dedicated Rules Catalog page where I can author and edit rules, **so that** rule governance is centralized.

**Acceptance criteria**

Sitemap subarea "Rules Catalog" visible to System Admin role

Lists all rules with status, priority, terminating, last modified

Filter by Active / Inactive / Draft

Edit form opens admin Rule form (L1-B03)

Rule version history accessible via related grid

**Definition of Done**

Sitemap subarea "Rules Catalog" present and visible only to System Admin per the 7-role model

List view shows status, priority, terminating flag, last modified

Filters available: Active / Inactive / Draft

Row click opens the L1-B03 admin Rule form

Rule version history accessible via a related-records grid on the Rule form, sourcing from `pei_ruleversion`

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-B03, L1-B07

## [L1-D10] BU Mapping admin pages

**Status:** Not Started

**As a** System Admin, **I want** dedicated pages for managing BU and BU mappings, **so that** I can maintain the resolution data.

**Acceptance criteria**

Sitemap subarea "BU Configuration" visible to System Admin role

Sub-pages: Business Units, Org Unit Mappings, BP Mappings, Unresolved Items

Each shows list view + form for CRUD

Link to "Re-resolve BU" actions

**Definition of Done**

Sitemap subarea "BU Configuration" present and visible only to System Admin per the 7-role model

Four subpages present: Business Units, Org Unit Mappings, BP Mappings, Unresolved Items — each with list view + form for CRUD on its underlying table

"Re-resolve BU" action linked from the appropriate page and verified to invoke the resolution flow as service principal

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-A02, L1-A03

## [L1-D11] Sitemap restructure for new architecture

**Status:** Not Started

**As a** Risk Manager, **I want** the sitemap reorganized to reflect new entities and workflows, **so that** I can find what I need.

**Acceptance criteria**

Top-level groups: Cycle Management / Master Data / Rules & Mappings / Evidence / Admin

Risk Manager sees Cycle Management + Master Data + Evidence

Admin additionally sees Rules & Mappings + Admin

Old subareas (Scope Classifications, etc.) removed

**Definition of Done**

Top-level groups appear as named: Cycle Management, Master Data, Rules & Mappings, Evidence, Admin

Role visibility verified: Risk Manager sees Cycle Management + Master Data + Evidence and nothing else; System Admin additionally sees Rules & Mappings + Admin

Legacy subareas (Scope Classifications and any others on the removal list) no longer appear in the published sitemap

Smoke-tested by signing in as each of the two key roles and confirming the visible navigation matches the matrix

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-D · Labels: L1, L1-D · Depends on: L1-D09, L1-D10

# L1-E — Migration from POC (~15 hrs)

1 of 6 done

## [L1-E01] Inventory existing applicability data

**Status:** Superseded

**As a** Builder, **I want** to understand the volume of existing data, **so that** I can plan the migration approach.

**Acceptance criteria**

Report counts: existing Applicabilities by status, existing Evidence records by status, existing Scope Classifications

Export sampling for analysis

Document size of migration challenge

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Superseded · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-E · Labels: L1, L1-E

## [L1-E02] Migration strategy decision

**Status:** Done

**As a** Builder, **I want** to commit to a migration strategy, **so that** the migration flow has clear requirements.

**Acceptance criteria**

ADR captured: "wipe and re-evaluate" vs "preserve as Cycle 0" vs "hybrid"

Decision rationale documented

Stakeholder review and approval

**Definition of Done**

ADR-063 captured the decision (wipe, no preservation, no Cycle-0); POC data classified as test-only; production applicabilities originate fresh from the rule engine at Cycle 1

Rationale documented in ADR-063 with explicit note that the decision does not weaken ADR-025 (scoped to pre-production test fixtures, not real evidence)

Stakeholder review and approval recorded; L1-E03 re-scoped same day to reflect "wipe, no preservation" (the cleanup path follows from this decision)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-E · Labels: L1, L1-E · Depends on: L1-E01

## [L1-E03] Retire obsolete Scope Classification table

**Status:** Not Started

**As a** Builder, **I want** to retire the obsolete Scope Classification table from the production model, **so that** the new rule-driven model isn't carrying a dead table.

**Acceptance criteria**

Test Scope Classification records cleared (no preservation needed — test data per ADR-063)

`pei_scopeclassification` deprecated / hidden / removed from the production model

No impact on the new rule-engine applicability model

**Definition of Done**

Test Scope Classification records cleared (no preservation, per ADR-063); pre-clear count and post-clear count both recorded

`pei_scopeclassification` deprecated per the agreed retirement path (hidden from the production model, removed from sitemap, or deleted as the agreed path dictates)

No impact on the new rule-engine applicability model verified by re-running a smoke evaluation cycle (or an equivalent post-retirement smoke test) and confirming applicability outcomes unchanged

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-E · Labels: L1, L1-E · Depends on: L1-E02

## [L1-E04] Existing Applicability data migration

**Status:** Superseded

**As a** Builder, **I want** existing Applicabilities to align with the new schema, **so that** new architecture works against existing data.

**Acceptance criteria**

Existing Applicabilities updated with: rule provenance (synthetic "Pre-rule-engine" rule for legacy), Collection Scope (inferred from existing Scope Type), Owning BU (resolved at migration time)

No deletion of existing records (per ADR-025)

Migration is idempotent and reversible

**Definition of Done**

Migration executed in dev environment

Pre/post counts match

Spot-check on 20+ random records confirms correctness

Existing reports/views still function

Rollback rehearsed and documented

Production migration runbook authored

**Jira fields** · Status: Superseded · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-E · Labels: L1, L1-E · Depends on: L1-E02, L1-A07, L1-A08, L1-A09, L1-B01

## [L1-E05] Existing Evidence preservation

**Status:** Superseded

**As a** Auditor, **I want** existing Evidence records to remain unchanged, **so that** ADR-025 immutability is honored throughout migration.

**Acceptance criteria**

Evidence records untouched in migration

SharePoint files untouched

New snapshot field "Producing Rule (snapshot)" populated retroactively as "Pre-rule-engine"

Audit log captures migration action

**Definition of Done**

All acceptance criteria verified

Edge cases tested

Documentation updated

Self-reviewed against acceptance

Deployed to dev environment

**Jira fields** · Status: Superseded · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-E · Labels: L1, L1-E · Depends on: L1-E04

## [L1-E06] Migration verification testing

**Status:** Superseded

**As a** Builder, **I want** confidence that migration didn't corrupt data, **so that** production goes live safely.

**Acceptance criteria**

Pre/post counts match

Spot-check on 20 random records confirms correct field migration

Existing reports/views still function

No NULL Owning BU on migrated records (or all NULL flagged for admin)

**Definition of Done**

Migration executed in dev environment

Pre/post counts match

Spot-check on 20+ random records confirms correctness

Existing reports/views still function

Rollback rehearsed and documented

Production migration runbook authored

**Jira fields** · Status: Superseded · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-E · Labels: L1, L1-E · Depends on: L1-E04, L1-E05

# L1-F — Testing Across Permutations (~25 hrs)

0 of 7 done

## [L1-F01] End-to-end cycle test (small scale)

**Status:** Not Started

**As a** Builder, **I want** to run a complete cycle through all 6 stages with known data, **so that** the architecture works end-to-end.

**Acceptance criteria**

5 BUs, 50 apps, 100 CPs, 5 rules

Cycle runs all 6 stages without errors

Output matches expected applicability count

Evidence records created correctly

**Definition of Done**

Cycle runs through all 6 stages without errors on the small-scale fixture

Output applicability count matches the expected count (zero false positives, zero false negatives)

Evidence records created correctly: count matches expected, fields populated per ADR-025 snapshot, SharePoint folders present at the agreed paths

Run artifacts recorded (run timestamp, gate-tick timestamps, counts at each stage) so subsequent F-series stories can compare against this baseline

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-A14, L1-B11, L1-C04, L1-D01

## [L1-F02] End-to-end cycle test (production scale)

**Status:** Not Started

**As a** Builder, **I want** to validate scale with realistic data volumes, **so that** I trust the system in production.

**Acceptance criteria**

700 apps, 500 CPs, 50 rules

Cycle runs in < 30 minutes total

No flow timeouts

All output queryable in < 2 seconds

**Definition of Done**

Cycle runs through all 6 stages without flow timeouts on the production-scale fixture

Total cycle runtime measured at < 30 minutes

Output queryable: each query in the agreed test set returns in < 2 seconds

Run artifacts recorded (per-stage timings, total pair count, total Applicability count, total Evidence count) for ongoing capacity planning

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-F01

## [L1-F03] Boolean expression edge case testing

**Status:** Not Started

**As a** Builder, **I want** rule evaluation tested across all expression types, **so that** complex rules work correctly.

**Acceptance criteria**

Test cases: simple AND, simple OR, NOT, nested groups (3+ levels), cross-entity comparisons, NULL handling, type mismatches

All cases produce expected outcomes

Edge cases documented

**Definition of Done**

Every test case in the enumerated set executed

Every test case produces its expected outcome (zero discrepancies — or, if found, logged as a defect and either fixed or backlogged)

Edge cases documented at the agreed location with case input, expected outcome, observed outcome, and any deviation rationale

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-B08

## [L1-F04] Cross-BU applicability testing

**Status:** Not Started

**As a** Builder, **I want** to test cross-BU edge cases, **so that** BU partitioning works correctly without false positives or negatives.

**Acceptance criteria**

Apps in BU A with CPs from BU B → not applicable (default)

Cross-BU rule explicitly fires for shared services

Manual BU overrides honored

Test cases pass

**Definition of Done**

Apps in BU A with CPs from BU B produce Not Applicable as the default outcome

Cross-BU rule explicitly fires Applicable for the shared-services case

Manual BU overrides honored — the override produces the expected outcome that supersedes the default

All defined test cases recorded with input pair, expected outcome, observed outcome, and pass/fail mark

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-F01

## [L1-F05] Unresolved BU path testing

**Status:** Not Started

**As a** Builder, **I want** to test what happens when BU mappings are missing, **so that** the cycle gracefully handles incomplete data.

**Acceptance criteria**

App with NULL Owning BU → skipped from rule evaluation

CP with NULL Owning BU → skipped

Stage 5 surfaces unresolved as anomaly

Cycle progresses to Stage 6 anyway

Test cases pass

**Definition of Done**

App with NULL Owning BU → skipped from rule evaluation in the run

CP with NULL Owning BU → skipped from rule evaluation in the run

Stage 5 (L1-D07) surfaces those unresolved records in its anomaly section

Cycle progresses to Stage 6 anyway and signs off cleanly

Test outcomes recorded per case

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-F01

## [L1-F06] Rule version migration testing

**Status:** Not Started

**As a** Builder, **I want** to test rule version capture during cycle execution, **so that** audit reconstruction works.

**Acceptance criteria**

Cycle executed with Rule v1

Rule edited mid-month, becomes v2

Cycle Rule Execution Log shows v1 was active for that cycle

Subsequent cycle uses v2

**Definition of Done**

Cycle 1 executed with Rule v1; Cycle Rule Execution Log shows v1 was the active version for Cycle 1

Rule edited mid-month, version snapshot row written as v2

Cycle 2 executed and uses v2 (verified via the Execution Log for Cycle 2)

Test outcome recorded per the agreed scenario script

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-B10

## [L1-F07] Regression test suite

**Status:** Not Started

**As a** Builder, **I want** a documented regression test suite for ongoing maintenance, **so that** future changes don't break Layer 1.

**Acceptance criteria**

Documented test cases covering all 6 stages

BU resolution scenarios

Rule evaluation scenarios

Migration scenarios

Edge cases (concurrent edits, race conditions)

Run-time < 2 hours total

**Definition of Done**

Documented test cases present, covering all 6 stages, BU resolution, rule evaluation, migration, and edge cases (concurrent edits, race conditions)

Suite executes end-to-end in < 2 hours total

Test outcomes captured per case; failures (if any) logged as defects with reproduction steps

Suite documented at the agreed location so subsequent maintenance can run it from a single entry point

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-F · Labels: L1, L1-F · Depends on: L1-F01

# L1-G — Surrounding Production Hardening (~104 hrs, often overlooked)

0 of 40 done

## [L1-G01] Status field FSP

**Status:** Not Started

**As a** System Admin, **I want** Import Cycle Status field locked via FSP, **so that** Risk Managers can't manually flip Status to bypass the workflow.

**Acceptance criteria**

Field-level security profile blocks update on `pei_status` for all non-system-principal users

Service principal can update via flows

Tested by attempting manual edit (should fail)

**Definition of Done**

FSP deployed blocking Update on `pei_status` for all non-System roles; the service principal can update it via flows

Verified a human in each non-System role cannot edit `pei_status` at the form (and API) while a service-principal flow write succeeds

Tested per the locked field (manual edit attempt blocked)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G02] Evidence cannot be manually deleted

**Status:** Not Started

**As a** Auditor, **I want** Evidence records protected from deletion, **so that** ADR-025 immutability is enforced.

**Acceptance criteria**

FSP blocks Delete privilege on `pei_evidence` for all roles

Bulk delete blocked

Tested by attempting delete (should fail)

**Definition of Done**

FSP deployed blocking the Delete privilege on `pei_evidence` for all roles; bulk delete also blocked

Verified a delete attempt (single and bulk) by a human role fails at the form and API paths

ADR-025 immutability confirmed enforced at the delete boundary

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G03] Evidence cannot be manually created

**Status:** Not Started

**As a** System Admin, **I want** Evidence records only creatable via flows, **so that** evidence has proper rule provenance.

**Acceptance criteria**

FSP blocks the Create privilege on `pei_evidence` for all roles except the service principal (System role)

The service principal retains Create via the L1-G18 FSP bypass so flows can still produce Evidence with proper rule provenance

Verified by attempting a manual create as a human role (form and API/Advanced Find paths) - blocked - while a service-principal flow create succeeds

**Definition of Done**

FSP deployed blocking the Create privilege on `pei_evidence` for all non-System roles; the service principal retains Create (via L1-G18)

Verified a human in each non-System role cannot create an Evidence record at the form or API/Advanced Find paths, while a service-principal flow create succeeds

Provenance guarantee confirmed (no human-originated Evidence)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G04] Gate ordering business rules

**Status:** Not Started

**As a** Risk Manager, **I want** gates can only be ticked in order, **so that** stages can't be skipped.

**Acceptance criteria**

Stage 2 gate read-only when Stage 1 gate = No

Stage 3 gate read-only when Stage 2 gate = No (and so on)

BR's enforce on form

Flow 2 enforces on save

**Definition of Done**

Business Rules deployed: each stage gate read-only when its prior gate = No; Flow 2 enforces the same ordering on save

Verified out-of-order ticking is blocked at the form and rejected on save across the stage sequence

Tested per gate transition

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-D01

## [L1-G05] Master record manipulation rules

**Status:** Not Started

**As a** System Admin, **I want** master records (CP, App, BP) protected from inappropriate edits, **so that** source data integrity is preserved.

**Acceptance criteria**

Most fields on CP, App, BP are read-only for Risk Manager (only updated via Flow 1)

Specific exceptions: Owning BU manual override, EMS Lifecycle Status, Reviewed flag

Audit log enabled on all master tables

**Definition of Done**

Field-level read-only enforced for Risk Manager on CP/App/BP except the three named exceptions; Auditing enabled on all master tables

Verified Risk Manager cannot edit a locked master field but can set the three exceptions, and Flow 1 writes succeed

Tested per exception and per a representative locked field

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G06] Concurrency control on flows

**Status:** Not Started

**As a** System, **I want** flows to handle concurrent execution gracefully, **so that** race conditions don't corrupt data.

**Acceptance criteria**

Flow 1 limited to 1 concurrent run

Stage 5 evaluation flow limited to 1 concurrent run per cycle

Re-fetch patterns in flows that depend on prior state

Idempotency in all create/update operations

**Definition of Done**

Concurrency Control enabled with degree-of-parallelism 1 on Flow 1 and per-cycle on the Stage 5 evaluation flow.

Re-fetch added wherever a flow depends on prior state; create/update operations made idempotent (guard on an existing record before create).

Verified by triggering two overlapping runs on a representative cycle with no duplicate or corrupted records, and no regression to the previously-tested Flow 1.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G07] Flow 1 file cleanup

**Status:** Not Started

**As a** System Admin, **I want** Flow 1 to delete source files after successful processing, **so that** the SharePoint inbox doesn't accumulate stale files.

**Acceptance criteria**

After successful Flow 1 run, source files moved to Archive folder (per existing pattern)

On failure, files remain in inbox for retry

Archive folder structured by date

**Definition of Done**

On a successful run, source files are moved to a date-structured Archive folder; on a forced failure, files remain in the inbox for retry.

Archive folder is organized by date as specified.

Runs end-to-end on a representative file set with no regression to Flow 1's tested staging behavior.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G08] Flow 1 HTML stripping in AI output

**Status:** Not Started

**As a** Risk Manager, **I want** AI Assessment text rendered cleanly, **so that** I can read it without HTML markup.

**Acceptance criteria**

Flow 1 strips HTML tags from AI response

Handles edge cases: nested tags, unclosed tags, entity encoding

Stored as plain text in `pei_aiassessment`

**Definition of Done**

HTML tags are stripped from the AI response before write, with nested/unclosed tags and entity encoding handled with no leftover markup.

Value is stored as plain text in pei_aiassessment.

Verified against a representative AI response containing markup, with no regression to Flow 1.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G09] Flow 1 production-scale test

**Status:** Not Started

**As a** Builder, **I want** Flow 1 tested with full production-scale data, **so that** I trust it in production.

**Acceptance criteria**

Test with 700-app file + 500-CP file + 50 RC + 50 BP

Flow completes in < 10 minutes

No timeouts, no errors

All records correctly staged

**Definition of Done**

Flow 1 run against the full-scale fixture completes in under 10 minutes with no timeouts and no errors.

All records are correctly staged when checked against the oracle.

Run timing and outcome are recorded, with no regression to the tested small-input behavior.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-A07

## [L1-G10] Application form rebuild

**Status:** Not Started

**As a** Risk Manager, **I want** the Application form clean and tab-organized, **so that** key fields are easy to find.

**Acceptance criteria**

Tabs: Overview / Source Attributes / BU & Classification / Lifecycle / Audit

15 evidence-affecting fields grouped on Source Attributes tab

Owning BU on BU & Classification tab

Form renders cleanly

**Definition of Done**

Form rebuilt with the five tabs; the 15 evidence-affecting fields grouped on Source Attributes and Owning BU on BU & Classification.

Published in the app and renders cleanly.

Role-based field visibility verified.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-A04

## [L1-G11] Control Procedure form rebuild

**Status:** Not Started

**As a** Risk Manager, **I want** the CP form clean and tab-organized, **so that** key fields are easy to find.

**Acceptance criteria**

Tabs: Overview / Source Data / BU / Reference Controls / Audit

Reference Controls sub-grid (from Control Mapping table)

Owning BU on BU tab

Deprecated classification fields hidden

Form renders cleanly

**Definition of Done**

Form rebuilt with the five tabs; Reference Controls sub-grid present (from Control Mapping), Owning BU on BU tab, deprecated classification fields hidden.

Published and renders cleanly.

Sub-grid record clicks navigate to the full-page form (not a side panel).

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-A05

## [L1-G12] Reference Control form rebuild

**Status:** Not Started

**As a** Risk Manager, **I want** a clean RC form, **so that** I can navigate framework controls.

**Acceptance criteria**

Tabs: Overview / Implementing CPs / Audit

Implementing CPs sub-grid (from Control Mapping)

Form renders cleanly

**Definition of Done**

Form rebuilt with the three tabs and the Implementing CPs sub-grid (from Control Mapping).

Published and renders cleanly.

Sub-grid record clicks navigate to the full-page form.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G13] Parent BP form rebuild

**Status:** Not Started

**As a** Risk Manager, **I want** a clean BP form, **so that** I can see process-level information.

**Acceptance criteria**

Tabs: Overview / BU / Implementing CPs / Audit

Owning BU on BU tab

Implementing CPs sub-grid

Form renders cleanly

**Definition of Done**

Form rebuilt with the four tabs; Owning BU on BU tab and Implementing CPs sub-grid present.

Published and renders cleanly.

Sub-grid record clicks navigate to the full-page form.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-A06

## [L1-G14] Evidence form rebuild

**Status:** Not Started

**As a** Risk Manager, **I want** the Evidence form to show snapshot data clearly, **so that** I can audit historical evidence accurately.

**Acceptance criteria**

Tabs: Overview / Snapshot Data / SharePoint / History / Audit

Snapshot fields prominently displayed (CP at collection, App at collection, Rule version)

SharePoint URL clickable

Form renders cleanly

**Definition of Done**

Form rebuilt with the five tabs; snapshot fields prominently displayed and the SharePoint URL clickable.

Published and renders cleanly.

Snapshot data reads correctly against a representative Evidence record.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G15] Control Mappings auto-population

**Status:** Not Started

**As a** Risk Manager, **I want** Control Mappings populated automatically from CP Reference Controls text, **so that** the relationship is queryable.

**Acceptance criteria**

Flow runs on CP create/update

Parses Reference Controls text field

Creates/updates rows in Control Mapping table

Removes outdated mappings if RC reference removed

Idempotent

**Definition of Done**

A flow runs on CP create/update, parses the Reference Controls text, and creates/updates rows in the Control Mapping table.

Outdated mappings are removed when an RC reference is dropped, and the operation is idempotent.

Verified by re-running on the same CP with no duplicate mappings and by querying actual Control Mapping records rather than a delayed rollup.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G16] Power BI cycle dashboard

**Status:** Not Started

**As a** Stakeholder, **I want** a dashboard showing cycle progress and outcomes, **so that** I have visibility without opening the form.

**Acceptance criteria**

Dashboard tiles: Active Cycle Status, Stage Progress, Applicabilities Created, Evidence Status, Anomaly Counts

Auto-refreshes

Filterable by cycle, by BU

Embedded in Import Cycle form Overview tab (or separate dashboard area)

**Definition of Done**

Dashboard built with the five tiles, auto-refreshing, and filterable by cycle and by BU.

Embedded in the chosen location and rendering correctly.

Verified against a representative cycle's data with tile values reconciling to the underlying records.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-D03

## [L1-G17] Last Flow Activity field

**Status:** Not Started

**As a** System Admin, **I want** to see when each flow last ran on a cycle, **so that** I can troubleshoot operational issues.

**Acceptance criteria**

Field `pei_lastflowactivity` (multi-line text) on Import Cycle

Each flow writes start + end + status to this field

Visible in Admin view

Cleared on cycle creation

**Definition of Done**

pei_lastflowactivity added on Import Cycle and each in-scope flow writes start, end, and status to it.

The field is visible in the Admin view and cleared on cycle creation.

Verified by running a representative cycle and confirming each flow's entry appears.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G18] Service principal FSP bypass config

**Status:** Not Started

**As a** System Admin, **I want** the service principal to have FSP bypass on all locked fields, **so that** flows can write to fields that humans cannot manually edit (Status, counters, snapshot fields, etc.).

**Acceptance criteria**

FSP profile created for the service principal: bypass on all fields locked by L1-G33 through L1-G38

Bypass scope - Import Cycle: Status, counter fields, AI Import Assessment, gate fields

Bypass scope - Scope Classification: create/write/delete bypass

Bypass scope - Applicability: create/write/delete bypass + lookup field write

Bypass scope - Evidence: create bypass, snapshot fields write (for set-on-create)

Bypass scope - Staged Records: create bypass

Bypass scope - Master records (CP/App/RC/BP): create/write/delete bypass + Reviewed flag write + Lifecycle Status write

Service principal assigned to the FSP profile

Smoke test: run Flow 1 end-to-end on a small test cycle; confirm no FSP-related write errors

Smoke test: run Flow 4A end-to-end; confirm cycle close still completes

Document the FSP bypass profile in the security model docs

**Definition of Done**

FSP bypass profile created and the service principal assigned; bypass spans Import Cycle, Scope Classification, Applicability, Evidence, Staged Records, and Master records exactly as locked by G33-G38

Smoke tests pass: Flow 1 end-to-end on a small test cycle with no FSP write errors, and Flow 4A completes cycle close

The bypass profile documented in the security model docs; verified a service-principal flow writes a locked field while a human role still cannot (bypass scope limited to the service principal)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z02, L1-G33-G38

## [L1-G19] Refactor Flow 3A/3B/3C/3D for new architecture

**Status:** Not Started

**As a** Builder, **I want** old flows decommissioned or refactored, **so that** the new architecture has clean flow inventory.

**Acceptance criteria**

Flow 3A (Create Scope Classifications) deactivated

Flow 3B (AI Classify) deactivated (AI not needed for classification)

Flow 3C (Create Applicability) replaced by Stage 5 evaluation flow

Flow 3D (Evidence Generation) folded into Stage 5 evaluation flow

All flows documented as deprecated

**Definition of Done**

Flow 3A and 3B are deactivated; 3C is replaced by and 3D is folded into the Stage 5 evaluation flow with equivalent output verified on a representative cycle.

All four flows are marked deprecated in the flow reference and the flow inventory is clean.

No live dependency still points at any retired flow.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-C01

## [L1-G20] Refactor EMS Confirmation flow as Stage 6 Closure

**Status:** Not Started

**As a** Builder, **I want** EMS Confirmation flow refactored to Stage 6 closure, **so that** the closure logic is preserved under the new gate.

**Acceptance criteria**

Flow trigger updated: `pei_cycleconfirmed` (was `pei_importcycleconfirmed`)

Same closure actions: Status = Completed, Reviewed flags, deactivation, notifications

Race protection preserved

Tested

**Definition of Done**

Trigger updated to pei_cycleconfirmed with all closure actions preserved and firing (Status, Reviewed flags, deactivation, notifications) and race protection intact.

Verified end-to-end on a representative cycle, producing the same closure outcome as the pre-refactor flow.

No regression to the prior confirmation behavior.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-D01

## [L1-G21] Cycle reopen capability

**Status:** Not Started

**As a** System Admin, **I want** to reopen a closed cycle when corrections are needed, **so that** rare governance situations can be handled.

**Acceptance criteria**

Admin command bar action "Reopen Cycle" on Completed cycles

Action flips Status back to "In Progress"

Audit log captures reopen with reason

Reviewed flags on master records may be reverted

Restricted to System Admin role only

**Definition of Done**

A "Reopen Cycle" command-bar action appears only on Completed cycles and flips Status back to In Progress.

The reopen and its reason are captured in the audit log and the designated Reviewed flags are reverted as specified.

The action is restricted to System Admin (verified with a non-admin role) and tested on a closed cycle with no side effects on other cycles.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-G18

## [L1-G22] Stage 6 email digest

**Status:** Not Started

**As a** Risk Manager, **I want** an email summary when a cycle closes, **so that** I have a record of what happened.

**Acceptance criteria**

Email triggered on Status = Completed

Includes counts: applicabilities, evidence requirements, anomalies

Sent to cycle owner + admin

Plain HTML formatting

**Definition of Done**

An email fires on Status=Completed with correct applicability, evidence-requirement, and anomaly counts.

It is sent to the cycle owner and admin with plain-HTML formatting that renders cleanly.

Verified on a representative closed cycle, with no regression to the closure flow.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-G20

## [L1-G23] Staged Record Quick View redesign (Option Q)

**Status:** Not Started

**As a** Risk Manager, **I want** to see related entity details (CP/App/RC/BP) inline when reviewing a Staged Record, **so that** I don't navigate away to understand what changed.

**Acceptance criteria**

4 lookup columns added on Staged Records: pei_linkedcp, pei_linkedapp, pei_linkedrc, pei_linkedbp

Flow 1 populates appropriate lookup at every Staged Record creation point (~6-8 locations)

4 Quick View forms built: CP Summary, App Summary, RC Summary, BP Summary

Quick Views embedded in Staged Record form with business rule showing the right one based on Entity Type

Backfill plan executed for existing Staged Records (or accepted that older cycles lack Quick View)

**Definition of Done**

Four lookup columns added on Staged Records and Flow 1 populates the appropriate lookup at every creation point.

Four Quick View forms built (CP / App / RC / BP Summary) and embedded in the Staged Record form with a business rule selecting the correct one by Entity Type.

Backfill plan executed or the documented acceptance recorded; verified on a representative cycle with no regression to Flow 1 staging.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L1-G · Labels: L1, L1-G

## [L1-G24] Classification History view refinement

**Status:** Not Started

**As a** Risk Manager, **I want** the Classification History sub-grid on the CP form to show story-telling columns, **so that** I can distinguish actionable rows from carry-forwards and cancelled-cycle rows.

**Acceptance criteria**

Custom view created for Classification History sub-grid (replaces current bare view)

Columns: Cycle Name, Cycle Status, Carried Forward (flag), Scope Type, Review Decision, Reviewed Date, Reviewed By

Rows from Cancelled cycles visually distinguished

Sorted by cycle (most recent first)

Bound to Stage 2 sub-grid on CP form

**Definition of Done**

A custom view replaces the bare Classification History view with the specified columns and Cancelled-cycle rows visually distinguished.

Sorted most-recent-cycle-first and bound to the Stage 2 sub-grid on the CP form.

Renders cleanly in the app.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-G29

## [L1-G25] Flow 1 command bar trigger

**Status:** Not Started

**As a** System Admin, **I want** to trigger Flow 1 (EMS Monthly Sync) from inside the MDA via a command bar button, **so that** flow execution is an in-app action instead of requiring a trip to Power Automate.

**Acceptance criteria**

Flow 1 trigger changed from "Manually trigger a flow" to "When a flow is run from the command bar"

Bound to Import Cycles table → All Records grid (not specific record)

Button labeled "Trigger Monthly Sync" appears on Import Cycles list view command bar

Tested end-to-end: button click → flow runs → cycle created

Documentation updated in Definitive_Flow_Reference.md

**Definition of Done**

Flow 1 trigger is changed to command-bar and the "Trigger Monthly Sync" button is bound to the Import Cycles list-view command bar (All Records grid, not record-specific).

End-to-end verified: button click → flow runs → cycle created.

Definitive_Flow_Reference.md is updated, with no regression to Flow 1 logic.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G26] Verify Flow 3B "Classify with AI" command bar button

**Status:** Not Started

**As a** Risk Manager, **I want** the "Classify with AI" button to appear on the Scope Classification form command bar, **so that** I can trigger AI classification per-record from inside the MDA.

**Acceptance criteria**

Flow 3B trigger confirmed as "When a flow is run from the command bar" on Scope Classification table

Button visible on Scope Classification form command bar (added via Command Designer if missing)

Tested: button click → Flow 3B fires → Scope Type, AI Confidence, Copilot Reasoning populate

**Definition of Done**

Flow 3B trigger is confirmed as command-bar on Scope Classification and the "Classify with AI" button is visible on the form command bar (added via Command Designer if it was absent).

Verified: button click → Flow 3B fires → Scope Type, AI Confidence, and Copilot Reasoning populate.

No regression to Flow 3B's classification behavior.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G27] "What Changed" labeling bug fix

**Status:** Not Started

**As a** Risk Manager, **I want** Unreviewed Detection records labeled correctly, **so that** the What Changed value matches the Impact text and the cycle digest is accurate.

**Acceptance criteria**

New choice value `Unreviewed` (890920004) added to pei_whatchanged on Staged Records table

Flow 1 modified at 2 locations (CP Unreviewed Loop UR-5, App Unreviewed Loop UR-12) to use new value instead of "New"

AI Assessment email body updated to include Unreviewed counts (Control Procedures + Applications)

Tracking variables added: varCPUnreviewed, varAppUnreviewed

Regression test passes with cycle containing fresh New + fresh Updated + Unreviewed-from-prior-cancelled

**Definition of Done**

Choice value Unreviewed (890920004) added to pei_whatchanged and Flow 1 updated at both locations to use it instead of "New".

The AI Assessment email body includes Unreviewed counts (Control Procedures + Applications) via the new tracking variables.

Regression test passes on a cycle containing fresh New + fresh Updated + Unreviewed-from-prior-cancelled, with What Changed matching the Impact text and no side effects on the other labels.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G28] Hide empty Validation Message + Import Warnings (Phase D5/D6)

**Status:** Not Started

**As a** Risk Manager, **I want** Validation Message and Import Warnings sections hidden when empty, **so that** the Cycle form doesn't show empty boxes during normal operation.

**Acceptance criteria**

Business rule added on Import Cycle form: hide Validation Message field when empty

Business rule added on Import Cycle form: hide Import Warnings field when empty

Rules activate on form load and field change

Tested with cycles in Draft, In Progress (with warnings), In Progress (no warnings), Completed states

**Definition of Done**

Business rules added on the Import Cycle form to hide Validation Message and Import Warnings when empty, activating on form load and field change.

Verified across Draft, In Progress (with warnings), In Progress (no warnings), and Completed states.

No empty boxes shown during normal operation and no side effects on the populated states.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-D01

## [L1-G29] Carried-forward visibility on Scope Classification

**Status:** Not Started

**As a** Risk Manager, **I want** to see when a Scope Classification was carried forward from a prior cycle, **so that** I can distinguish new-this-cycle classifications from continuations.

**Acceptance criteria**

Field `pei_carriedforward` (Yes/No) added to Scope Classification table

Field `pei_originatingcycle` (lookup to Import Cycle) added to Scope Classification table

Flow 3A populates both fields on creation (distinguishes "new to this cycle" vs "carried forward from prior cycle")

Display on Classification History sub-grid: "↺ Carried forward from Cycle 2026-04-18" pattern

Tested with at least 2 sequential cycles to verify carry-forward behavior

**Definition of Done**

pei_carriedforward and pei_originatingcycle added to Scope Classification and Flow 3A populates both on creation, correctly distinguishing new-this-cycle from carried-forward.

The carry-forward indicator displays on the Classification History sub-grid.

Verified across at least two sequential cycles.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G

## [L1-G30] Full file regression test (679 apps)

**Status:** Not Started

**As a** System Admin, **I want** Flow 1 validated against the full production file (679 apps), **so that** we know how the system behaves at production scale before cutover.

**Acceptance criteria**

Test cycle run with full 679-app file + full CP file

Flow 1 completes successfully (or fails with documented timeout/error pattern)

Performance metrics captured: total duration, action counts, timeout points if any

Stage 2/3 BU resolution scaled correctly

Stage 5 evaluation flow (rule engine) tested at scale

All Applicabilities created correctly

Evidence creation scales (Flow 3D)

Cycle close (EMS Confirmation) completes without timeout

Issues logged for any scale-related failures

**Definition of Done**

A test cycle is run with the full 679-app + full CP file; Flow 1 completes, or fails with a documented timeout/error pattern.

Performance metrics are captured (duration, action counts, any timeout points), and Stage 2/3 BU resolution, the Stage 5 rule engine, Applicability creation, and Flow 3D evidence creation all scale correctly.

Cycle close completes without timeout and any scale-related failures are logged as issues.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-A14, L1-F02

## [L1-G31] Custom navigation icons

**Status:** Not Started

**As a** Risk Manager, **I want** the sitemap nav items to have meaningful icons, **so that** the app looks polished and entries are visually scannable.

**Acceptance criteria**

Custom SVG/web resource icons sourced or commissioned for each sitemap group

Icons applied to: Workflow group, Reference Data group, Classification & Scope group, My Work group

Per-table icons applied where appropriate (Import Cycles, CPs, Applications, etc.)

Tested across light/dark themes if applicable

**Definition of Done**

Icons applied to the Workflow, Reference Data, Classification & Scope, and My Work groups, plus per-table icons where appropriate (Import Cycles, CPs, Applications, etc.).

Icons display correctly across light/dark themes where applicable.

Sitemap is visibly polished and scannable.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-D11

## [L1-G32] Flow 4B Evidence Reuse AI

**Status:** Not Started

**As a** Risk Manager, **I want** AI to suggest reusing existing evidence across similar CP × App pairs, **so that** Control Owners aren't asked to re-upload the same evidence multiple times.

**Acceptance criteria**

New flow `EMS Evidence Reuse Suggestions` built

Triggered on Evidence record creation OR on a manual command bar action

AI Builder prompt designed: given a new Evidence record, find similar Evidence (same CP family, same App family, recent date) and suggest reuse

Suggestions surfaced on Evidence form as a related sub-grid or banner

Risk Manager can accept (link the existing evidence) or dismiss

Reuse linkage tracked in a new `pei_evidencereuse` junction table

Tested with a cycle producing duplicate-eligible evidence

**Definition of Done**

The EMS Evidence Reuse Suggestions flow is built and triggered as specified, and the AI prompt returns similar-evidence suggestions.

Suggestions are surfaced on the Evidence form; the Risk Manager can accept (linking existing evidence) or dismiss, with reuse linkage recorded in pei_evidencereuse.

Verified on a cycle producing duplicate-eligible evidence, with no regression to tested evidence flows.

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-C06, L2-C01

## [L1-G33] Import Cycle integrity rules (FSP + Business Rules)

**Status:** Not Started

**As a** Auditor, **I want** Import Cycle records protected against manual tampering, **so that** the cycle workflow is enforceable and stakeholders can't accidentally manipulate cycle state.

**Acceptance criteria**

FSP applied: `pei_importcycle` table — Create privilege restricted (only Flow 1 may create)

Business Rule: Import Cycle Name field read-only after creation

FSP applied: All counter fields (`pei_rcnew`, `pei_rcupdated`, `pei_rcremoved`, `pei_appnew`, `pei_appupdated`, `pei_appremoved`, `pei_cpnew`, `pei_cpupdated`, `pei_cpremoved`, etc.) — read-only after Flow 1 sets them

Form-locked: System fields (`pei_triggeredby`, `pei_triggeredon`, `pei_completedby`, `pei_completedon`) verified read-only

FSP applied: AI Import Assessment field (`pei_aiimportassessment`) — read-only after Flow 1 sets it

All rules tested: attempt manual creation/edit blocked at form, API, and Excel paths

(Gate reversion lock split out into L1-G39 — implemented separately with its own DoR/DoD per L1-Z01 Decision 1)

**Definition of Done**

FSP deployed: Create restricted to the service principal; counters + AI Import Assessment read-only after Flow 1 sets them; Import Cycle Name read-only after creation via Business Rule

Verified a human in each non-System role cannot create an Import Cycle or edit a locked field at the form/API/Excel paths, while the service-principal flow can

System fields verified form-locked; no backward transitions

Source items (Rules_And_Validations_Tracker.md Category 1: 1.10-1.15) mapped and ticked; gate reversion confirmed out of scope (lives in L1-G39)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z02, L1-G18

## [L1-G34] Scope Classification integrity rules (FSP + Business Rules)

**Status:** Not Started

**As a** Auditor, **I want** Scope Classification records protected against manual tampering, **so that** classification provenance and decisions are auditable.

**Acceptance criteria**

FSP applied: `pei_scopeclassification` Create privilege — only Flow 3A may create

FSP applied: Delete privilege — blocked entirely (no manual deletion)

Business Rule: `pei_finalscopetype` cannot be changed after parent Import Cycle's Stage 2 gate is ticked (Classification Complete = Yes)

Business Rule: `pei_reviewdecision` cannot revert from Accepted/Overridden back to Pending after Stage 2 gate

Form-locked: AI Reasoning field (`pei_aireasoning`) read-only after creation

Form-locked: AI Suggested Scope Type (`pei_aisuggestedscopetype`) read-only after creation

Business Rule: Review Decision = Pending until Final Scope Type is set (cannot accept unclassified)

All rules tested via deliberate manipulation attempts

**Definition of Done**

FSP + Business Rules deployed per all 7 Category 2 rules (create/delete restriction, scope-type freeze, review-decision one-way, AI-field read-only, accept-only-when-classified)

Verified a human in each non-System role cannot create/edit a Scope Classification or revert a locked field, while Flow 3A (service principal) can

Tested via deliberate manipulation attempts per rule

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z02, L1-G18

## [L1-G35] Applicability integrity rules (FSP + Business Rules)

**Status:** Not Started

**As a** Auditor, **I want** Applicability records protected against manual tampering, **so that** the relationship between controls and applications is preserved per ADR-025 immutability principle.

**Acceptance criteria**

FSP applied: `pei_applicability` Create privilege — only Flow 3C (or new rule evaluation flow) may create

FSP applied: Delete privilege — blocked. Per ADR-025, applicabilities are deactivated, never deleted.

FSP applied: Lookup fields (`pei_cp`, `pei_application`, `pei_importcycle`) — read-only after creation

Business Rule: `pei_reviewdecision` one-way state machine (Pending → Accepted, Pending → Overridden — no backward transitions)

FSP applied: `pei_applicabilitystatus` (Active/Inactive) — only flows may toggle

Business Rule: `pei_applicability` field (Applicable/Not Applicable) editable only when Review Decision = Pending OR Overridden

All rules tested

**Definition of Done**

FSP + Business Rules deployed per all 6 Category 3 rules (create restriction, no delete, lookup freeze, review-decision one-way, status flow-only, applicability-editable-when-pending)

Verified a human in each non-System role cannot create an Applicability, delete one, repoint a lookup, or toggle status, while the rule-evaluation flow (service principal) can

Tested per rule

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z02, L1-G18, L1-C04

## [L1-G36] Evidence integrity rules (ADR-025 enforcement, additional FSP)

**Status:** Not Started

**As a** Auditor, **I want** Evidence records protected against tampering beyond the existing delete/create FSP, **so that** ADR-025 immutability is fully enforced including snapshot fields, lookup integrity, and the Status state machine.

**Acceptance criteria**

FSP applied: Evidence snapshot fields (CP title at collection, CP description at collection, App name at collection, App attributes at collection, Scope type at collection, Producing Rule snapshot — per ADR-025) — read-only after creation

FSP applied: Evidence lookup fields (`pei_applicability`, `pei_cp` if exists, `pei_application` if exists, `pei_importcycle`) — read-only after creation (no relationship rewriting)

FSP applied: `pei_evidencestatus` — Create/Update privileges restricted to service principal only. **No human role can directly write this field, period.** Single rule, no exceptions per Decision 5.

FSP applied: `pei_collectedby`, `pei_collectedon` — write restricted to service principal only (set by Approve flow); read-only for human roles

FSP applied: `pei_filename`, `pei_sharepointurl`, `pei_sharepointfolderpath` — write restricted to service principal only (set by Upload flow); read-only for human roles after creation

Backward transition guard (enforced via flow logic, not FSP): each transition flow checks current status before flipping. If current ≠ expected source state, flow logs the violation and aborts. Examples:

**Definition of Done**

FSP deployed: snapshot + lookup + collection-metadata fields read-only after creation; `pei_evidencestatus` write restricted to the service principal (no human role writes it, period)

Backward-transition guards enforced in each transition flow (Upload requires Gap; Approve/Reject require Pending or Suggested; Daily-Expiry requires Provided; Not-Required any source)

Verified: manual status flip (Gap->Provided) as System Admin blocked by FSP; flow flip Provided->Pending blocked by the guard; snapshot edit blocked; lookup repoint blocked; Upload on Provided and Reject on Gap both blocked by source-state checks

Source items (Category 4: 4.3-4.5) mapped; ADR-025 + Decision 5 enforcement confirmed

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-G02, L1-G03, L1-Z02, L1-G18

## [L1-G37] Staged Records integrity rules (FSP)

**Status:** Not Started

**As a** Auditor, **I want** Staged Records protected as immutable detection records, **so that** the audit trail of "what Flow 1 saw at each cycle" is preserved.

**Acceptance criteria**

FSP applied: `pei_stagedrecord` Create privilege — only Flow 1 may create

FSP applied: All field write privileges blocked after creation (informational records, no edits)

FSP applied: Delete privilege — blocked entirely

Test: attempt manual create/edit/delete from form, API, Advanced Find — all blocked

Note any exceptions if Flow 1 itself needs to update fields post-creation (e.g., if Flow 3A needs to flag a Staged Record as "processed")

**Definition of Done**

FSP deployed: Create restricted to Flow 1; field writes blocked after creation; Delete blocked entirely

Verified manual create/edit/delete from the form, API, and Advanced Find are all blocked for human roles while Flow 1 (service principal) can create

Any required Flow-1 post-creation update exception documented; Category 5 rules (5.1-5.3) ticked

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z02, L1-G18

## [L1-G38] Master records integrity rules (FSP for ADR-023 source-of-truth boundary)

**Status:** Not Started

**As a** Auditor, **I want** master records (CP, App, RC, BP) protected from manual edits, **so that** ADR-023's source-of-truth boundary is enforced — EMS doesn't own this data.

**Acceptance criteria**

FSP applied: `pei_controlprocedure`, `pei_application`, `pei_referencecontrol`, `pei_parentbusinessprocess` — Create + Write privileges restricted (only Flow 1 may create/update via service principal)

FSP applied: `pei_reviewed` flag — only EMS Confirmation flow may flip (no human user, including System Admin)

FSP applied: `pei_emslifecyclestatus` (Active / Removed / Decommissioned) — only flows may change (no human user, including System Admin)

**No manual override capability — strict immutability per L1-Z01 Decision 4.** All corrections to bad-state records must route through service-principal-run Power Automate flows. No UI override path exists.

Override flag (`pei_admioverride`) field — **NOT created** per Decision 4 lock (was previously a TBD option)

All rules tested, including negative tests (System Admin attempts manual edit → blocked)

**Definition of Done**

FSP deployed: Create/Write on the 4 master tables restricted to Flow 1 (service principal); Reviewed flag writable only by EMS Confirmation; Lifecycle Status writable only by flows

Verified ALL human roles (including System Admin) are blocked from creating/editing master records and from flipping Reviewed/Lifecycle Status (negative tests pass), while the flows can

Confirmed no `pei_admioverride` field exists (Decision 4 lock); Category 6 rules (6.1-6.3) ticked; ADR-023 source-of-truth boundary enforced

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z01, L1-Z02, L1-G18

## [L1-G39] Gate reversion lock + warning dialog (per L1-Z01 Decision 1)

**Status:** Not Started

**As a** Auditor, **I want** ticked gates to be permanently locked from being unticked, **so that** cycle progression is one-way and the audit trail of "this stage was confirmed at this date by this user" is unambiguous.

**Acceptance criteria**

6 Business Rules created on the Import Cycle table - one per gate field - each with a single condition: if `pei_<gate>` = Yes, set `pei_<gate>` read-only on the form

Gate fields covered: Stage 1 `pei_impactreviewed`, Stage 2 `pei_appbu_verified`, Stage 3 `pei_cpbu_verified`, Stage 4 `pei_rulesconfirmed`, Stage 5 `pei_outputreviewed`, Stage 6 `pei_signedoff` (or current field names)

Form-level warning dialog on each gate tick attempt, text: "Once you tick this stage, it cannot be reverted. To redo this stage, cancel the cycle and start a new one. Continue?" - Continue proceeds with the tick; Cancel reverts the field to No

Dialog mechanism chosen in priority order: preferred Business Rule (error + revert; limited, no interactive dialog); acceptable minimal Form Script (`OnSave`/`OnChange`, the second JS exception after the BPF<->tab script, justified in a code comment); alternative native `confirmDialog` (research feasibility)

Test: tick a gate No -> Yes -> dialog -> Continue -> field becomes read-only on save

Test: tick a gate No -> Yes -> dialog -> Cancel -> field stays at No

Test: attempt to flip a Yes gate back to No -> field is read-only, change rejected

Test: behavior consistent across all 6 gates

Test: behavior verified across cycles in Draft, In Progress (any stage), and Completed states

Updated form documentation noting the lock + dialog behavior

**Definition of Done**

6 Business Rules deployed (one per gate field) making a ticked gate read-only; a form-level warning dialog confirms the irreversible tick (Continue proceeds, Cancel reverts to No)

The dialog mechanism implemented per the priority order (Business Rule preferred; minimal Form Script acceptable as the justified second JS exception; native confirmDialog as the researched alternative)

Verified across all 6 gates and across Draft / In Progress / Completed cycle states: tick->Continue locks on save; tick->Cancel stays No; flipping a Yes gate back to No is rejected; form documentation updated

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z01, L1-D01

## [L1-OPS01] Operational runbook: fixing master records in bad state

**Status:** Not Started

**As a** System Admin, **I want** a documented procedure for correcting master records that end up in an invalid state, **so that** when production incidents happen, there is a clean, auditable path to fix data without manual UI overrides (which Decision 4 prohibits).

**Acceptance criteria**

Runbook document created at `EMS_Project/05_Building_Blocks/05_Operational_Runbooks/01_Master_Record_Correction.md`

Detection section covers how a System Admin recognizes a master record is in a bad state (signals: stuck in Removed, missing Reviewed flag after a confirmed cycle, lookup pointing to wrong record, and similar patterns)

Triage section provides a decision tree: is this a one-off or a class of records; is this a Flow 1 bug that needs a code fix or a transient data issue

Fix paths section documents three paths in priority order: Path A (fix the underlying flow bug, redeploy, wait for next sync — preferred for systemic issues), Path B (trigger an existing repair flow as service principal), Path C (build a one-off correction Power Automate flow that runs as service principal, performs the specific fix, logs to the correction log, and is then disabled or deleted)

Authorization section specifies who approves a Path B or Path C fix before it runs (e.g., second System Admin sign-off, change ticket — to be defined per Pei's process)

Documentation requirement: every Path B / Path C fix must be logged to `EMS_Project/05_Building_Blocks/05_Operational_Runbooks/02_Correction_Log.md` (or equivalent) with incident date, affected record(s), root cause, fix path used, who authorized, who executed

Post-mortem requirement: for any Path C fix, a brief note added on whether the underlying flow needs a permanent fix (Path A) so the same correction does not keep recurring

Runbook reviewed by Ahmad before being declared canonical

Reference to the runbook added to L1-G38 Source field and ADR-033 consequences section

**Definition of Done**

Runbook document committed at the agreed path

All six required sections present and named: Detection, Triage, Fix paths (with three documented paths A / B / C), Authorization, Documentation, Post-mortem

Correction log template created at the agreed path (or equivalent) with the required logging fields: incident date, affected record(s), root cause, fix path used, who authorized, who executed

Cross-reference added in the L1-G38 Source field and in the ADR-033 consequences section

Runbook reviewed by Ahmad and declared canonical before this story is closed

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L1-G · Labels: L1, L1-G · Depends on: L1-Z01

# L2-A — Evidence Upload Lifecycle (~40 hrs)

0 of 14 done

## [L2-A01] Control Owner Portal page

**Status:** Not Started

**As a** Control Owner, **I want** a single page showing all my evidence requirements, **so that** I can track what I owe.

**Acceptance criteria**

Custom MDA page or model-driven app

Lists all Applicability records where current user is Control Owner

Shows Status (Gap, Pending, Collected, Expiring)

Filter by status, by CP, by app, by overdue

Search

**Definition of Done**

MDA page deployed in dev; lists Applicability records where current user = Owner; role-gated to Control Owner

Status column displays the live `pei_evidencestatus` enum value; filters work for status / CP / app / overdue; search box implemented per AC

Role-gating verified: Control Owner sees only their own records (not other Control Owners'); Risk Manager BU-scope and Auditor engagement-scope visibility are out of scope for this story

Smoke-tested with sample Applicabilities in each of the 6 states; each state surfaces under its expected display label

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L1-C04

## [L2-A02] Evidence file upload

**Status:** Not Started

**As a** Control Owner, **I want** to upload evidence files directly, **so that** I don't have to navigate to SharePoint manually.

**Acceptance criteria**

Upload control on Applicability or Evidence record

File uploaded to correct SharePoint folder

Status flips to Pending

Snapshot fields preserved

File type/size validation

**Definition of Done**

Upload control rendered on the form per AC; clicking it uploads the file into the correct SharePoint folder following the agreed convention

File-type and file-size validation enforced (the AC requirement); validation failures surface to Control Owner with the file rejected before any flow invocation (no orphan state)

Power Apps action wired to invoke L2-A02b on successful SharePoint upload; passes the Evidence record ID; status flip happens inside the flow per Decision 5

Smoke-tested end-to-end: Control Owner uploads → file lands in SharePoint folder → L2-A02b runs → status visible as Pending in the Control Owner Portal (L2-A01)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A01

## [L2-A03] Evidence approval workflow

**Status:** Not Started

**As a** Risk Manager, **I want** to approve uploaded evidence, **so that** Status flips to Collected when valid.

**Acceptance criteria**

Pending evidence visible in Risk Manager queue

Approve action → Status = Collected, sets Collected By + Collected On

Reject action → Status = Gap with rejection reason

**Definition of Done**

Pending queue view deployed; visible to Risk Manager role; BU-scoped (sees own BU's queue)

Approve button on the form / view wired to invoke L2-A03b flow (passes Evidence record ID + approving user); button label and confirmation dialog implemented

Reject button wired to invoke L2-A03c flow (passes Evidence record ID + rejection reason text + rejecting user); reason input is required before submit

Smoke-tested both branches: Approve → status Provided (890920001) + collected metadata populated by A03b; Reject → status Gap (890920003) + reason captured by A03c + L2-A04 email dispatched

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A02

## [L2-A04] Evidence rejection notification

**Status:** Not Started

**As a** Control Owner, **I want** notification when my evidence is rejected, **so that** I know to upload corrected evidence.

**Acceptance criteria**

Email triggered on rejection

Includes rejection reason

Link back to Applicability for re-upload

**Definition of Done**

Email template deployed; rendered correctly with the rejection reason text and a working deep-link back to the Applicability record

L2-A03c flow's send-email branch dispatches via the SP-run mail action; verified in run history (Decision 2 / ADR-032)

Smoke-tested end-to-end: Risk Manager clicks Reject → A03c runs → email arrives in Control Owner's inbox with reason text and a functioning re-upload link

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A03

## [L2-A02b] Upload-trigger flow (Gap → Pending status flip)

**Status:** Not Started

**As a** System, **I want** the file upload action to trigger a flow that performs the status flip as service principal, **so that** Decision 5's flow-based-only-writes constraint is honored — Control Owner triggers the action via UI but the actual `pei_evidencestatus` write is performed by the flow.

**Acceptance criteria**

Power Automate flow created, runs as service principal (per L1-Z02)

Trigger: Power Apps action invoked from L2-A02 upload control (passes Evidence record ID)

Source state guard: flow checks current `pei_evidencestatus` = Gap (890920003); if not, log violation and abort

Action: file already uploaded to SharePoint by L2-A02; this flow performs the status flip + populates `pei_filename` + `pei_sharepointurl` + `pei_sharepointfolderpath` snapshot

Sets `pei_evidencestatus` = Pending (890920000)

Success → returns success to L2-A02 caller

Failure → returns error; L2-A02 surfaces error to Control Owner (file remains in SharePoint as orphan; correction runbook applies per L1-OPS01-style pattern for evidence)

**Definition of Done**

Flow deployed in dev; run-history identity column shows the service principal (Decision 2 / ADR-032 — no personal-account writes)

In-flow source-state guard implemented: re-fetch the Evidence record and assert `pei_evidencestatus` = Gap (890920003) before any write; on mismatch, log violation and terminate cleanly without writing (the no-backward-transitions guard, parallel to L1-G39's cycle-gate pattern)

Single status flip writes Gap (890920003) → Pending (890920000); same run populates the snapshot fields `pei_filename`, `pei_sharepointurl`, `pei_sharepointfolderpath` per ADR-025 (Dataverse stores metadata + snapshot copies; file already in SharePoint via L2-A02)

End-to-end test from L2-A02 upload control → flow run → status visible as Pending in the Control Owner Portal (L2-A01); the orphan-file failure path is exercised once and the correction-runbook entry is captured per L1-OPS01-style pattern

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A02, L1-Z02, L1-G18, L1-G36

## [L2-A03b] Approve-trigger flow (Pending → Provided status flip)

**Status:** Not Started

**As a** System, **I want** the Risk Manager Approve action to trigger a flow that performs the status flip as service principal, **so that** Decision 5's flow-based-only-writes constraint is honored — Risk Manager triggers via UI but the actual `pei_evidencestatus` write is performed by the flow.

**Acceptance criteria**

Power Automate flow created, runs as service principal (per L1-Z02)

Trigger: Power Apps action invoked from L2-A03 Approve button (passes Evidence record ID + approving user)

Source state guard: flow checks current `pei_evidencestatus` = Pending (890920000) OR = Suggested (890920002); if not, log violation and abort (this is the no-backward-transition guard)

Sets `pei_evidencestatus` = Provided (890920001)

Sets `pei_collectedby` = approving user, `pei_collectedon` = current timestamp

Sets `pei_expirydate` = current + applicable retention period (from CP or default policy)

Success → returns success to L2-A03 caller; UI refreshes to remove from Pending queue

**Definition of Done**

Flow deployed in dev; run-history identity column shows the service principal (Decision 2 / ADR-032 — no personal-account writes)

In-flow source-state guard implemented: re-fetch and assert state = Pending (890920000) OR Suggested (890920002) before write; on mismatch, log violation and terminate (the no-backward-transitions guard — Provided is forward-only from these two predecessors)

Single status flip writes Provided (890920001); same run populates `pei_collectedby` (approving user), `pei_collectedon` (timestamp), `pei_expirydate` (current + applicable retention from CP / default policy)

End-to-end test from Approve button → flow run → status Provided, evidence removed from Pending queue; the L2-B freshness pipeline subsequently sees the Provided + expiry-date pair (the upstream that B01 watches for Provided → Expired)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A03, L1-Z02, L1-G18, L1-G36

## [L2-A03c] Reject-trigger flow (Pending → Gap status flip with reason)

**Status:** Not Started

**As a** System, **I want** the Risk Manager Reject action to trigger a flow that performs the status flip as service principal and captures the rejection reason, **so that** rejection state changes are audited consistently and Decision 5's flow-based pattern is honored.

**Acceptance criteria**

Power Automate flow created, runs as service principal (per L1-Z02)

Trigger: Power Apps action invoked from L2-A03 Reject button (passes Evidence record ID + rejection reason text + rejecting user)

Source state guard: flow checks current `pei_evidencestatus` = Pending (890920000) OR = Suggested (890920002); if not, log violation and abort

Sets `pei_evidencestatus` = Gap (890920003)

Captures rejection reason in audit-friendly field (`pei_rejectionreason` or equivalent — verify exists in tenant; create if not)

Captures rejecting user + timestamp

Triggers L2-A04 notification email to Control Owner with reason and re-upload link

Success → UI refreshes to remove from Pending queue; record reverts to Gap status visible in Control Owner Portal as work-to-redo

**Definition of Done**

Flow deployed in dev; run-history identity column shows the service principal (Decision 2 / ADR-032 — no personal-account writes)

In-flow source-state guard implemented: re-fetch and assert state = Pending (890920000) OR Suggested (890920002) before write; on mismatch, log violation and terminate (the no-backward-transitions guard)

Single status flip writes Gap (890920003); same run captures rejection reason + rejecting user + timestamp; the L2-A04 notification email is dispatched with the reason text + a re-upload link

End-to-end test from Reject button → flow run → status Gap, email delivered to Control Owner, record reappears in the Control Owner Portal (L2-A01) as work-to-redo (the Gap-state listing the Portal already surfaces)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A03, L2-A04, L1-Z02, L1-G18, L1-G36

## [L2-A04b] AI-Suggestion-Decision flow (Suggested → Provided or Gap)

**Status:** Not Started

**As a** System, **I want** the Risk Manager Accept-Suggestion / Reject-Suggestion actions on AI-suggested evidence reuse to trigger flows that perform the status flip as service principal, **so that** AI reuse decisions follow the same flow-based pattern as manual approval/rejection per Decision 5.

**Acceptance criteria**

Power Automate flow created, runs as service principal (per L1-Z02)

Trigger: two Power Apps actions (Accept-Suggestion, Reject-Suggestion) from the AI Suggestion review UI; both invoke this flow with a decision parameter

Source state guard: flow checks current `pei_evidencestatus` = Suggested (890920002); if not, log violation and abort

If decision = Accept: sets `pei_evidencestatus` = Provided (890920001), populates `pei_collectedby` + `pei_collectedon` + `pei_expirydate` (same as manual approval); also captures the AI match reasoning into a snapshot field for audit ("evidence reused via AI suggestion match against Evidence ID X")

If decision = Reject: sets `pei_evidencestatus` = Gap (890920003); captures rejection reason if provided

Success → UI refreshes appropriate queue

**Definition of Done**

Single parameterized flow deployed in dev; run-history identity column shows the service principal; decision parameter (Accept / Reject) routes to the correct write block

In-flow source-state guard implemented: re-fetch and assert state = Suggested (890920002) before write; on mismatch, log violation and terminate (the no-backward-transitions guard — Provided is forward-only)

Accept branch writes Provided (890920001) + `pei_collectedby` + `pei_collectedon` + `pei_expirydate` (same shape as A03b) + captures AI match reasoning into the snapshot field; Reject branch writes Gap (890920003) + captures rejection reason if provided

End-to-end test from both Accept-Suggestion and Reject-Suggestion buttons on the AI Suggestion review UI; both routes hit the correct target enum, both surface in the right downstream queue (Accept → freshness pipeline; Reject → Control Owner Portal as Gap work-to-redo)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L1-Z02, L1-G18, L1-G36

## [L2-A05] Bulk upload from SharePoint

**Status:** Not Started

**As a** Control Owner, **I want** to drop multiple files in SharePoint and have them auto-linked, **so that** I can collect evidence efficiently.

**Acceptance criteria**

SharePoint folder watcher flow

New files auto-linked to corresponding Evidence record (matched by folder structure)

Status flips to Pending

Notifies Risk Manager

**Definition of Done**

SharePoint folder-watcher flow deployed; runs as service principal (verified in run-history identity column); matches new files to corresponding Evidence records by folder structure

For each matched file: invokes L2-A02b for the Gap → Pending status flip + populates the snapshot fields per ADR-025 (`pei_filename`, `pei_sharepointurl`, `pei_sharepointfolderpath`); no direct `pei_evidencestatus` writes happen in this flow

Risk Manager notification dispatched per the agreed pattern; unmatched files surface to a triage location (rather than failing silently)

Smoke-tested by dropping 3+ files in different folders simultaneously: all auto-link, all flip to Pending (890920000), RM receives the notification

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A02

## [L2-A06] Evidence reassignment

**Status:** Not Started

**As a** Risk Manager, **I want** to reassign Control Owner on evidence, **so that** organizational changes can be reflected.

**Acceptance criteria**

Reassign action on Evidence form

Sets new Control Owner

Notifies new owner via email

Audit log captures change

**Definition of Done**

Reassign command/button on the Evidence form; role-gated to Risk Manager; BU-scoped (cannot reassign records outside own BU)

Action updates the Owner lookup on the underlying Applicability; new owner receives the configured email

Audit log captures the user transition (verified by viewing audit history on the record); the prior Owner is preserved in the audit row

Smoke-tested: Risk Manager reassigns from User A → User B → audit history shows the transition + User B receives the email + Control Owner Portal visibility shifts accordingly

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A02

## [L2-A07] Evidence collection bulk operations

**Status:** Not Started

**As a** Risk Manager, **I want** to bulk-approve or bulk-reject evidence, **so that** I can process volume efficiently.

**Acceptance criteria**

Multi-select on Pending Evidence view

Bulk approve with confirmation

Bulk reject with reason

Audit log per record

**Definition of Done**

Multi-select bulk-approve and bulk-reject commands deployed on the Pending Evidence view; role-gated to Risk Manager

Each selected record routes through L2-A03b (approve) or L2-A03c (reject) — verified by the flow run-history showing one run per record

Confirmation dialog appears with the selected count; reject path prompts for the reason text per the agreed pattern before any flow invocation

Smoke-tested with 5+ records selected on each branch: every record reaches the correct target enum (Provided=890920001 or Gap=890920003), every record has its own audit row, no Decision 5 violation in any run

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A03

## [L2-A08] Upload history and versions

**Status:** Not Started

**As a** Auditor, **I want** to see history of evidence uploads, **so that** I can verify provenance.

**Acceptance criteria**

Each upload event logged with user, timestamp, file name

Replaced files preserved in SharePoint (versioning enabled)

Visible in Evidence history sub-grid

**Definition of Done**

SharePoint versioning verified on; each new upload preserves prior versions on the same SharePoint item (no overwrite, no deletion — ADR-025 immutability holds end-to-end)

Evidence history sub-grid renders on the Evidence form showing user + timestamp + file name per upload event

Role-gated visibility: Auditor sees the sub-grid within their engagement scope per ADR-032 / L3-A07; Control Owner sees their own evidence's history

Smoke-tested: upload the same Evidence record's file three times → all three versions visible in SharePoint and in the sub-grid; the first version is still retrievable from SharePoint's version history

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A02

## [L2-A09] Email notifications on Gap creation

**Status:** Not Started

**As a** Control Owner, **I want** notification when new Gap is assigned to me, **so that** I know what to provide.

**Acceptance criteria**

Email triggered on Evidence creation with Status = Gap

Includes CP, app, due date (if any)

Link to Control Owner Portal

**Definition of Done**

Trigger flow deployed; runs as service principal on Evidence-row-create where `pei_evidencestatus` = Gap (890920003); verified in run-history identity column

Email template renders correctly with CP / app / due-date / Portal link; the Portal deep-link lands the user on the right Applicability row

Smoke-tested by creating a Gap Evidence record manually: the email arrives at the Owner with the right context and a working Portal link; no email is sent for non-Gap status creations

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L1-C06

## [L2-A10] Evidence collection testing

**Status:** Not Started

**As a** Builder, **I want** end-to-end testing of evidence lifecycle, **so that** I can trust the upload + approval flow.

**Acceptance criteria**

Test: create gap → upload → approve → state Collected

Test: create gap → upload → reject → state Gap

Test: bulk operations

All tests pass

**Definition of Done**

Test plan documented covering the full L2-A surface; each test names the asserted final `pei_evidencestatus` enum value

All AC happy-path tests pass: (a) create gap → upload → approve → Provided (890920001); (b) create gap → upload → reject → Gap (890920003); (c) bulk operations across multi-select view

Each test verifies the SP-flow identity in run-history (Decision 2 / ADR-032 — no personal-account writes) and confirms the source-state guard fires correctly on at least one deliberate out-of-state attempt per status-flip flow (the no-backward-transitions guarantee)

Test results captured in a test-run artifact alongside the tracker; any failures logged as new BLs rather than silently fixed in-flight (scope-discipline per the BL-068-style 4-box pattern)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L2-A · Labels: L2, L2-A · Depends on: L2-A01

# L2-B — Evidence Freshness & Expiry (~25 hrs)

0 of 6 done

## [L2-B01] Evidence expiry tracking

**Status:** Not Started

**As a** Risk Manager, **I want** evidence to expire based on rule's Collection Frequency, **so that** old evidence isn't trusted as current.

**Acceptance criteria**

Field `pei_expirydate` calculated from rule + collection date

Daily flow flips Status from Collected → Expired when expiry reached

Expired evidence visible in Risk Manager queue

**Definition of Done**

`pei_expirydate` populated on Provided evidence at the moment of A03b / A04b approval (collection date + applicable retention from CP / default policy); same calculation rule applies here

Daily scheduled flow deployed; runs as service principal (verified in run-history identity column per Decision 2 / ADR-032)

In-flow source-state guard: for each candidate record, re-fetch and assert state = Provided (890920001) AND `pei_expirydate` ≤ today before any write; on mismatch, skip the record without writing (the no-backward-transitions guard — only Provided is a valid predecessor for Expired)

Single status flip writes Expired (890920005); the Risk Manager queue view shows expired evidence (filtered to Expired enum); smoke-tested by manually backdating one record's `pei_expirydate` and observing it flip on the next run

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L1-C06

## [L2-B02] Expiry warning notifications

**Status:** Not Started

**As a** Control Owner, **I want** notification before my evidence expires, **so that** I have time to refresh it.

**Acceptance criteria**

Notification 30 days before expiry

Notification 7 days before expiry

Notification on expiry day

Configurable thresholds

**Definition of Done**

Daily scheduled flow deployed; runs as service principal (verified in run-history identity column per Decision 2 / ADR-032)

Each of the three notification points fires exactly once per Evidence record per cycle through its threshold (no duplicate emails on subsequent days — idempotent via a "last-warned-at" snapshot field or equivalent)

Threshold values are read from the configuration source (not hardcoded); changing the config without code change shifts the warning windows on the next run

Smoke-tested by backdating `pei_expirydate` on three records to land in the three different windows simultaneously; each Control Owner receives exactly the right template once

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L2-B01

## [L2-B03] Evidence renewal workflow

**Status:** Not Started

**As a** Control Owner, **I want** to upload renewed evidence to replace expired, **so that** my Status returns to Collected.

**Acceptance criteria**

Upload to expired Evidence creates a new Evidence record (preserving immutability)

Old evidence marked Expired (preserved for audit)

New evidence has new collection date and expiry

Audit log captures renewal

**Definition of Done**

Renewal entry point on the Expired Evidence record (a "Renew" command/button) creates a new Evidence record bound to the same Applicability; old Expired record left untouched and visible in history (ADR-025)

The new record's upload flows through L2-A02 → L2-A02b → L2-A03 → L2-A03b exactly like a first-time upload — proving the renewal path reuses the standard state machine rather than introducing a parallel one

New record has its own fresh `pei_collectedon` and `pei_expirydate` (set by A03b at Approve time); the old record retains its original collection date and Expired status

Audit history on the Applicability shows the chain: old Expired → new Gap → new Pending → new Provided; smoke-tested end-to-end with one renewal cycle

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L2-B01, L2-A02

## [L2-B04] Freshness dashboard

**Status:** Not Started

**As a** Risk Manager, **I want** a dashboard showing evidence freshness across the org, **so that** I can prioritize remediation.

**Acceptance criteria**

Dashboard with: Total / Collected / Pending / Gap / Expired counts

Filter by BU, by CP family, by criticality

Drill into specific records

Updated daily

**Definition of Done**

Dashboard deployed in dev; surfaces the per-enum counts (Total / Provided / Pending / Gap / Expired at minimum; Suggested and Not Required surfaced if agreed) with the display labels per the deferred naming

Filters work for BU / CP family / criticality; role-gating limits visibility to the Risk Manager's BU scope

Drill-into-specific-records works: clicking a count cell navigates to a filtered view of those records (the AC requirement)

Smoke-tested with sample data across all 6 enum values; refresh cadence verified to match the "updated daily" AC

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L2-B01

## [L2-B05] Stale-evidence escalation

**Status:** Not Started

**As a** Risk Manager, **I want** escalation when evidence stays expired too long, **so that** compliance gaps are surfaced to leadership.

**Acceptance criteria**

Escalation flow runs weekly

Identifies evidence Expired > 30 days

Sends digest to Risk Manager + Control Owner manager

Configurable threshold

**Definition of Done**

Weekly scheduled flow deployed; runs as service principal (verified in run-history identity column)

Each run identifies all Evidence records with `pei_evidencestatus` = Expired (890920005) AND days-since-expiry > the configured threshold (default 30)

Digest dispatched to Risk Manager (BU-scoped recipient list) + each Control Owner's manager; the digest groups by Control Owner so each manager receives only their own reports' overdue evidence

Smoke-tested by backdating a sample record's `pei_expirydate` to >30 days ago; weekly run produces the expected digest with that record listed; changing the configured threshold to 7 days picks up records that the 30-day threshold missed

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L2-B01

## [L2-B06] Freshness testing

**Status:** Not Started

**As a** Builder, **I want** to test expiry and renewal flows, **so that** the lifecycle works correctly.

**Acceptance criteria**

Test: collected → expired (time-based)

Test: expired → renewed

Test: notifications fire correctly

All tests pass

**Definition of Done**

Test plan documented covering the full L2-B surface; each test names the asserted final `pei_evidencestatus` enum value

All AC happy-path tests pass: (a) Provided → Expired via B01 daily flow with the source-state guard verified by one deliberate out-of-state attempt (the no-backward-transitions guarantee); (b) Expired → renewed produces a new Provided record while the old Expired one is preserved per ADR-025; (c) B02 notifications fire at the 30-day, 7-day, and day-of thresholds exactly once each per record

Each test verifies the SP-flow identity in run-history (Decision 2 / ADR-032 — no personal-account writes); B05 digest verified for one record past the configured threshold

Test results captured in a test-run artifact alongside the tracker; any failures logged as new BLs rather than silently fixed in-flight

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-B · Labels: L2, L2-B · Depends on: L2-B01

# L2-C — AI Evidence Review (~30 hrs)

0 of 6 done

## [L2-C01] AI evidence review prompt design

**Status:** Not Started

**As a** Risk Manager, **I want** AI to assess uploaded evidence, **so that** I can focus review on questionable cases.

**Acceptance criteria**

AI Builder prompt: given CP description + evidence file content, assess fit

Returns: confidence score + reasoning

Tested across various evidence types (config snapshots, attestations, screenshots)

**Definition of Done**

AI Builder prompt created with the locked input shape (CP description + evidence content); prompt published and callable from a Power Automate flow

Prompt output returns confidence score (numeric, 0.0–1.0 or equivalent) + reasoning text per AC; output retrievable via the documented extraction path `body()?['responsev2']?['predictionOutput']?['text']`

Tested manually across the three AC-named evidence types (config snapshots, attestations, screenshots); at least one positive-fit and one negative-fit case captured per type; rough qualitative accuracy noted (formal calibration is L2-C06's job)

Prompt versioned and documented so downstream stories (L2-C02 upload flow, L2-C03 auto-approval, L2-D02 reuse suggestions) can reference a stable surface

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L2-C · Labels: L2, L2-C

## [L2-C02] AI review on upload flow

**Status:** Not Started

**As a** System, **I want** AI to review every uploaded evidence file, **so that** review burden is reduced.

**Acceptance criteria**

Flow triggered on Evidence upload (Status flip to Pending)

Reads file content (or extracts via OCR/parse)

Calls AI Builder prompt

Stores AI assessment + confidence on Evidence record

**Definition of Done**

Flow deployed; runs as service principal per Decision 2 / ADR-032 (verified in run-history identity column); triggers on `pei_evidencestatus` = Pending (890920000)

Flow reads the file content from SharePoint via the agreed extraction surface (L2-C04 handles unsupported types); calls the L2-C01 AI Builder prompt with CP description + extracted content

AI assessment + confidence written to the agreed Evidence fields via this flow (not via human input) — this is a read of `pei_evidencestatus` and a write of the AI snapshot fields; no `pei_evidencestatus` mutation in this flow (that stays the responsibility of L2-A03b / L2-A04b / L2-C03)

Smoke-tested end-to-end: Control Owner uploads → A02b flips to Pending → this flow fires → AI assessment + confidence visible on the Evidence record within the agreed SLA

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L2-C · Labels: L2, L2-C · Depends on: L2-C01

## [L2-C03] AI confidence-based auto-approval

**Status:** Not Started

**As a** Risk Manager, **I want** high-confidence AI assessments to auto-approve, **so that** I only review uncertain cases.

**Acceptance criteria**

AI confidence ≥ 0.85 + AI says "fits" → Status = Collected automatically

AI confidence < 0.85 → flag for human review

AI says "doesn't fit" → flag for human review regardless of confidence

Configurable threshold

**Definition of Done**

Routing logic deployed (extension of the L2-C02 flow or a sibling flow); runs as service principal per Decision 2 / ADR-032 (verified in run-history identity column)

High-confidence path (AI confidence ≥ configured threshold AND AI says "fits"): invokes L2-A03b with a synthetic "approving user" = service principal — the resulting Pending → Provided (890920001) write is performed by A03b exactly as it is for human approvals (no Decision 5 bypass)

Low-confidence path AND "doesn't fit" path: no `pei_evidencestatus` write; record remains at Pending (890920000) and surfaces in the standard L2-A03 Risk Manager queue for manual review

Threshold configurability verified: changing the configured value at runtime shifts the auto-approval cutoff on the next flow run; smoke-tested with three records spanning the threshold (one well above, one near, one below)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-C · Labels: L2, L2-C · Depends on: L2-C02

## [L2-C04] Multi-modal evidence handling

**Status:** Not Started

**As a** Control Owner, **I want** to upload screenshots, PDFs, and documents, **so that** I'm not constrained by file type.

**Acceptance criteria**

AI handles: PDF, PNG/JPG screenshots, Word docs, Excel sheets

OCR for image-based content

Text extraction for documents

Error handling for unsupported types

**Definition of Done**

Extraction implemented for each supported type per the agreed approach; results returned in a uniform text shape that L2-C02 / L2-C01 can consume

OCR path verified on at least one PNG and one JPG screenshot with embedded text; text-extraction path verified on at least one Word doc and one Excel sheet; PDF path verified on both a text-PDF and a scanned (image) PDF

Unsupported file type at upload surfaces a clear error to the Control Owner in L2-A02's validation gate before A02b runs — no orphan Evidence records with un-AI-reviewable content

Smoke-tested end-to-end: uploading one file of each supported type lands a valid AI assessment on the Evidence record via L2-C02; uploading an unsupported type is rejected at the upload gate with a meaningful message

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L2-C · Labels: L2, L2-C · Depends on: L2-C02

## [L2-C05] AI review audit trail

**Status:** Not Started

**As a** Auditor, **I want** AI assessments logged per evidence, **so that** I can verify why something was auto-approved.

**Acceptance criteria**

AI confidence + reasoning stored permanently on Evidence record

Visible in Evidence form

Captured in snapshot fields

**Definition of Done**

AI confidence (numeric) + reasoning text (full output, not truncated) stored on Evidence in the agreed snapshot fields; written once by L2-C02 / L2-C03 and not subsequently mutated by human users (parallel to FSP pattern but applied to AI-source fields)

Snapshot fields visible on the Evidence form section, role-gated so Auditor sees them within engagement scope and Control Owner sees them for their own records

Dataverse audit log records the write timestamp and the writing identity (the service principal); smoke-tested by opening the audit history on a sample Evidence record and observing the AI fields populated by the SP

The audit-trail content is preserved through the L2-B03 renewal path (new record's history; old record's history both visible) per ADR-025

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L2-C · Labels: L2, L2-C · Depends on: L2-C02

## [L2-C06] AI review testing & calibration

**Status:** Not Started

**As a** Builder, **I want** AI accuracy validated, **so that** auto-approval doesn't accept bad evidence.

**Acceptance criteria**

Test set of 50 evidence samples (mix of valid + invalid)

AI accuracy measured (target: >90% on valid, >85% on flagging invalid)

Confidence threshold tuned based on results

Documented

**Definition of Done**

Test corpus run through the live L2-C02 → L2-C03 pipeline; confidence + assessment captured per sample; confusion matrix computed against ground-truth labels

Accuracy targets met per AC (>90% valid, >85% invalid-flagging); if not met by initial threshold, threshold tuned (possibly multiple times) and the final tuned value committed to the L2-C03 configuration source

Calibration write-up documented alongside the tracker: corpus composition, ground-truth methodology, confusion matrix, threshold-tuning trail, final calibrated threshold value

Any prompt-level defects (where threshold tuning is insufficient) logged as new BLs against L2-C01 rather than silently re-tuned in this story — scope-discipline preserved

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-C · Labels: L2, L2-C · Depends on: L2-C01

# L2-D — Evidence Reuse Detection (~25 hrs)

0 of 5 done

## [L2-D01] Evidence reuse data model

**Status:** Not Started

**As a** Auditor, **I want** to know when one piece of evidence satisfies multiple controls, **so that** the same artifact isn't requested twice.

**Acceptance criteria**

Junction table linking Evidence to multiple Applicabilities

Backward-compatible: existing 1:1 relationship preserved

Reuse flag on Evidence

**Definition of Done**

Junction table deployed in dev with the `pei_` publisher prefix, FK pair to Evidence and Applicability, and the originating-evidence reference for the snapshot-match trail

Existing 1:1 Evidence → Applicability lookup preserved (no field deletion, no migration of existing records); the junction is additive — verified by querying an existing pre-junction Evidence record and observing it still resolves to its Applicability without a junction row

Reuse flag on Evidence written by the L2-D03 linking flow (not by humans — Decision 5 / ADR-034 pattern extended to the reuse flag); the flag surfaces in the Control Owner Portal and the Auditor view

Schema doc updated to add the new junction table + reuse flag; the snapshot-matching mechanic per ADR-025 documented as the detection anchor (no hash / no filename heuristics) so downstream stories (L2-D02 / L2-D03) build on the right foundation

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-D · Labels: L2, L2-D

## [L2-D02] AI-driven evidence reuse suggestions

**Status:** Not Started

**As a** Control Owner, **I want** the system to suggest existing evidence I can reuse, **so that** I don't re-upload the same file.

**Acceptance criteria**

AI Builder prompt: given new gap + existing evidence catalog, suggest matches

Returns ranked list with confidence

Surface in Control Owner Portal

**Definition of Done**

AI Builder prompt created for reuse matching: input = new gap CP description + candidate evidence snapshot set; output = ranked list with confidence per candidate; output retrievable via the documented extraction path

Flow deployed; runs as service principal per Decision 2 / ADR-032 (verified in run-history identity column); triggered on Gap creation (or on the Control Owner opening the Gap, depending on the agreed cadence) to populate the suggestion set

Suggestion set surfaces in Control Owner Portal per AC; clicking a candidate routes to the L2-D03 linking workflow which lands the Evidence in Suggested (890920002) — then L2-A04b owns the Accept/Reject decision per Decision 5

Smoke-tested with at least three Gaps that have plausible reuse candidates (and one Gap with no plausible reuse) — suggestions ranked sensibly, low-confidence threshold filters out noise

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L2-D · Labels: L2, L2-D · Depends on: L2-D01, L2-C01

## [L2-D03] Evidence reuse linking workflow

**Status:** Not Started

**As a** Control Owner, **I want** to link existing evidence to multiple gaps, **so that** one upload satisfies many requirements.

**Acceptance criteria**

"Link existing evidence" action on gap

Searchable list of existing collected evidence

On link: gap Status flips to Collected with reuse pointer

Audit log captures reuse

**Definition of Done**

"Link existing evidence" action on Gap deployed in Control Owner Portal + on the Evidence form; role-gated to Control Owner (per ADR-032)

Action invokes a service-principal flow per Decision 2 / ADR-032 that: (a) creates a new Evidence record on the target Gap pointing to the source Evidence via the L2-D01 junction; (b) places the new Evidence in Suggested (890920002); (c) writes the reuse flag; (d) captures the AI / manual selection reasoning into the snapshot field

The L2-A04b AI-Suggestion-Decision flow then owns the Accept (→ Provided 890920001) / Reject (→ Gap 890920003) transition — this story does NOT directly write Provided; the AC's "Status flips to Collected" is satisfied via the standard A04b chain (no Decision 5 bypass)

Audit log captures the reuse linkage end-to-end: the source Evidence ID, the target Applicability, the linking user, the AI match reasoning (where applicable), and the final A04b resolution; smoke-tested with one AI-suggested link and one manual-search link

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L2-D · Labels: L2, L2-D · Depends on: L2-D01

## [L2-D04] Reuse impact on freshness

**Status:** Not Started

**As a** Auditor, **I want** linked evidence to share freshness/expiry, **so that** all dependent gaps update consistently.

**Acceptance criteria**

When linked evidence expires, all dependent gaps flip to Expired

When linked evidence renewed, dependent gaps update

All linked Applicabilities show same evidence status

**Definition of Done**

Expiry-cascade flow deployed (extension of L2-B01 daily run OR a sibling flow triggered by it); runs as service principal per Decision 2 / ADR-032 (verified in run-history identity column); writes Provided → Expired on each linked dependent in lock-step with the source

Renewal-cascade flow deployed: when a new source Evidence reaches Provided via the L2-B03 → L2-A03b chain, the dependent Gap records are re-bound to the new source (junction rows updated) and re-routed through the L2-A04b Accept-Suggestion path so the dependent records reach Provided (890920001) via the standard SP-flow pattern — no direct writes

Source-state guards present on both flows: re-fetch the source + dependent before write; abort on any unexpected state; log the violation (parallel to the A02b / A03b / A04b guard pattern — the no-backward-transitions guarantee extends to the cascade)

Smoke-tested with one source Evidence linked to three dependent Gaps: expiring the source flips all four (source + 3 dependents) to Expired (890920005) in one run; renewing the source produces a new source Provided record and all three dependents reach Provided via A04b within the agreed SLA

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-D · Labels: L2, L2-D · Depends on: L2-D01, L2-B01

## [L2-D05] Reuse testing

**Status:** Not Started

**As a** Builder, **I want** to validate reuse logic, **so that** evidence consistency holds across linked records.

**Acceptance criteria**

Test: create one evidence linked to 3 gaps

Test: expire evidence → all 3 flip to expired

Test: renew → all 3 flip back to Collected

Tests pass

**Definition of Done**

Test plan documented covering the full L2-D surface; each test names the asserted final `pei_evidencestatus` enum value across source + dependents

All AC happy-path tests pass: (a) one Evidence linked to 3 Gaps via D03 — all 3 land in Provided (890920001) via A04b after Accept-Suggestion; (b) expire source via B01 → source + all 3 dependents flip to Expired (890920005) in one run with the source-state guard verified on all 4; (c) renew source via B03 → new source Provided record + all 3 dependents back to Provided via the A04b chain

Each test verifies the SP-flow identity in run-history (Decision 2 / ADR-032 — no personal-account writes) and confirms ADR-025 immutability (source Evidence and old dependents preserved across the renewal cascade)

Test results captured in a test-run artifact alongside the tracker; any failures logged as new BLs rather than silently fixed in-flight

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L2-D · Labels: L2, L2-D · Depends on: L2-D01

# L3-A — Engagement Schema & Configuration (~25 hrs)

0 of 7 done

## [L3-A01] Engagement table

**Status:** Not Started

**As a** Risk Manager, **I want** an Engagement table to model audits/assessments, **so that** evidence reviews can be scoped formally.

**Acceptance criteria**

Dataverse table `pei_engagement`

Fields: Name, Engagement Type, Scope (BU, BP, framework, time window), Status, Start Date, End Date, Lead Auditor, etc.

Form, view, list created

**Definition of Done**

`pei_engagement` table deployed to dev with all AC2 fields, the Status choice, and the Lead Auditor lookup; one sample Engagement record saved successfully

Default form, default view, and quick-create form generated and smoke-tested by creating a record from the model-driven app

Audit logging enabled on the table; field edits captured in the audit history (the L3-A06 state-transition log builds on this)

Schema doc updated to move Engagement from any Forward-Planned section into the live-tables section

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-A · Labels: L3, L3-A

## [L3-A02] Engagement Type configuration

**Status:** Not Started

**As a** System Admin, **I want** different engagement types (SOX, internal audit, regulatory exam, etc.), **so that** workflows differ by type.

**Acceptance criteria**

Choice on Engagement: 8 types (SOX Quarterly Review, Annual Internal Audit, Regulatory Exam, External Audit, Vendor Risk Assessment, Operational Review, Compliance Survey, Spot Check)

Each type has configurable workflow stages

Per-type defaults for scope filters

**Definition of Done**

Choice column added to `pei_engagement` with all 8 values; the choice surfaces in the form and a record can be saved with each value

Per-type workflow-stage configuration stored (table or JSON field on the type metadata) and read by the L3-B01 creation flow when the type is selected

Per-type default scope filters surface on engagement creation: selecting a type pre-populates the L3-A04 filter UI; defaults remain editable before activation

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A01

## [L3-A03] Scope freeze on Engagement activation

**Status:** Not Started

**As a** Auditor, **I want** engagement scope frozen at activation, **so that** mid-engagement source changes don't affect what's in scope (per ADR-024).

**Acceptance criteria**

On activation: snapshot CP × App pairs in scope

Snapshot stored as junction records

Stays frozen even if source data or rules change

Tested with mid-engagement Flow 1 run

**Definition of Done**

Activation transition fires a service-principal flow that writes the CP × App pair snapshot as junction records; one sample engagement activated, snapshot row count matches the expected in-scope count

Snapshot rows verified unchangeable: a mid-engagement Flow 1 run is executed and the junction row set is asserted byte-identical before and after — no rows added, removed, or value-changed (the ADR-024 unchangeable test)

Snapshot survives source data change: a downstream rule edit or app-side change is staged after activation and the snapshot is reasserted unchanged

Write-protection in place: only the activation flow (service principal) can populate the snapshot; any other write attempt fails (parallel to the L1-G18/G36 FSP write-protection pattern)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A01

## [L3-A04] Engagement scope filters

**Status:** Not Started

**As a** Auditor, **I want** to scope an engagement by BU + BP + framework + time window, **so that** I focus on relevant evidence.

**Acceptance criteria**

Filter UI on Engagement form

Filter by BU (multi-select), BP, RC framework family, evidence date range

Preview shows in-scope CP × App count

Saved with engagement

**Definition of Done**

Filter UI surfaces on the Engagement form with all 4 dimensions; each dimension's selector works (multi-select BU; lookup BP; choice framework family; date-range pickers)

Preview count refreshes when filters change and matches a hand-counted query of current in-scope CP × App pairs for the selected filters

Filter values save with the engagement record; reopening the form re-hydrates the selections; filters become read-only on activation (per L3-A03)

Per-type defaults from L3-A02 populate on creation and remain editable before activation

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A01, L3-A03

## [L3-A05] Engagement Evidence linking

**Status:** Not Started

**As a** Auditor, **I want** evidence within scope automatically associated with engagement, **so that** I can review without manual collection.

**Acceptance criteria**

On engagement activation: auto-link all in-scope Evidence

Junction table for Engagement ↔ Evidence

Snapshot evidence state at engagement activation

**Definition of Done**

`pei_engagementevidence` junction table created with lookups to Engagement and Evidence, plus the snapshot fields (status-at-activation, key file-metadata copy per ADR-025)

Activation auto-links in-scope Evidence: the service-principal activation flow populates one junction row per Evidence record covered by the L3-A03 scope freeze; row count verified against the snapshot's pair count

Snapshot integrity verified: subsequent edits to the L2 Evidence record (status flip, re-upload, re-categorization) do NOT alter the junction-row snapshot — the junction reads the state at activation, full stop

Audit logging enabled on the junction so any (expected-zero) post-activation writes are visible

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A03

## [L3-A06] Engagement state management

**Status:** Not Started

**As a** Risk Manager, **I want** engagement lifecycle states, **so that** progress is trackable.

**Acceptance criteria**

States: Draft / Activated / In Progress / Field Work / Reporting / Closed

State transitions enforced via business rules

Audit log on transitions

**Definition of Done**

Business rules (or flows) enforce the allowed-transition graph: invalid transitions blocked with a clear error; valid transitions auto-update the Status field

Activation transition successfully triggers L3-A03 scope-freeze and L3-A05 evidence-linking flows in one run; the engagement lands in Activated with snapshot rows + junction rows populated

Audit log on transitions per AC3: each state change writes an audit-log entry with the from-state, to-state, user, and timestamp; entries are visible in the audit history view

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A01

## [L3-A07] Engagement member junction table

**Status:** Not Started

**As a** Auditor, **I want** to be assigned to one or more engagements as a member, **so that** my engagement-scoped role grants visibility to the right records.

**Acceptance criteria**

Dataverse table `pei_engagementmember` created with publisher prefix `pei`

Fields: Engagement (lookup → `pei_engagement`), User (lookup → System User), Member Role (Choice: Lead Auditor / Team Member / Reviewer / Observer), Assignment Date, Status (Active / Inactive)

Junction relationship configured between `pei_engagement` and System User via this table

Form, default view (per engagement: members), default view (per user: my engagements)

Filter view "My Engagements" available on the engagement table for Auditor role users

Existing `pei_engagement.pei_leadauditor` lookup preserved (backwards compatibility); on engagement creation, the Lead Auditor is also auto-added as a `pei_engagementmember` row with Member Role = Lead Auditor

Audit log enabled on table

**Definition of Done**

`pei_engagementmember` table deployed to dev with all AC2 fields (Engagement lookup → `pei_engagement`, User lookup → System User, Member Role choice, Assignment Date, Status); the junction relationship configured per AC3 in both directions

Form + the two AC4 views created and smoke-tested (per-engagement: members view; per-user: my-engagements view)

"My Engagements" filter view available on the Engagement table per AC5: a test Auditor user sees only their assigned engagements; a second Auditor user sees a disjoint set; an unassigned user sees an empty result

Backwards-compat verified per AC6: creating a new Engagement with a Lead Auditor lookup auto-creates the corresponding `pei_engagementmember` row (Member Role = Lead Auditor, Status = Active); the existing `pei_engagement.pei_leadauditor` value is preserved on the engagement record

Audit logging enabled per AC7; assignment-row changes appear in the audit history; INF-A01 unblocked for Auditor security-role configuration against this junction

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: L3-A · Labels: L3, L3-A · Depends on: L3-A01

# L3-B — Engagement Workflow (~35 hrs)

0 of 7 done

## [L3-B01] Engagement creation flow

**Status:** Not Started

**As a** Risk Manager, **I want** to create a new engagement with guided setup, **so that** scope is configured correctly.

**Acceptance criteria**

Wizard: select type → set scope filters → review preview → activate

Validates required fields per type

Auto-creates evidence links on activation

**Definition of Done**

Wizard UI built as a native MDA Business Process Flow (or equivalent native flow control — no JS/PCF/canvas) covering the 4 AC1 steps; back/forward navigation works; cancel without save discards the draft

Per-type required-field validation per AC2: an attempt to advance past a step with missing required fields surfaces a clear error and blocks progression; each of the 8 types tested with one valid + one invalid case

Final step activates the engagement: the L3-A06 transition fires, the L3-A03 snapshot is written, the L3-A05 evidence-link junction rows are populated — all in one user-triggered run; row counts match the preview shown in step 3

End-to-end test: a fresh user creates an engagement of each frequently-used type (e.g. SOX Quarterly Review + Annual Internal Audit) through the wizard and lands at Activated with snapshot + evidence-link rows present

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-A01

## [L3-B02] In-scope evidence review queue

**Status:** Not Started

**As a** Auditor, **I want** a queue of evidence to review per engagement, **so that** I can work through them efficiently.

**Acceptance criteria**

Queue view per engagement

Filter by review status (Pending Review / Reviewed / Issue Found)

Bulk-mark reviewed

Drill into Evidence for details

**Definition of Done**

Queue view per engagement built as a native MDA view on the L3-A05 junction, filtered to the active engagement; row counts match the activation snapshot

Filter by review status per AC2 works (three buckets); a row's status flip from Pending Review → Reviewed updates the junction row only, leaving the underlying L2 Evidence record untouched

Bulk-mark reviewed per AC3 works against a multi-select; the action runs as service principal (consistent with the Decision 5 flow-based-writes pattern); audit log captures the operator + selected row IDs

Drill-into Evidence per AC4 opens the full L2 Evidence form; Auditor users see it read-only (the ADR-032 contract verified here too)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-A05

## [L3-B03] Audit findings and issues

**Status:** Not Started

**As a** Auditor, **I want** to log findings against engagement evidence, **so that** issues are tracked.

**Acceptance criteria**

Issue table: Engagement, Evidence/CP, Description, Severity, Status (Open/Closed), Owner

Form for creating issue

Issue queue per engagement

**Definition of Done**

`pei_issue` table deployed with all AC1 fields and the correct lookups (Engagement → `pei_engagement`, Evidence/CP context); audit log enabled

Form for creating issue per AC2 surfaces from the L3-B02 review queue (per-row "Log finding" action); a saved issue appears in the queue per AC3

Issue queue view per engagement per AC3 lists all open issues for the active engagement; filter by Severity and Status works

Auditor write-scoping verified per ADR-032: a test Auditor user assigned to engagement X can create issues on engagement X but a parallel create attempt on engagement Y (where they are not a member) fails with a security exception — this is the canonical contract test

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-B02

## [L3-B04] Issue remediation workflow

**Status:** Not Started

**As a** Control Owner, **I want** notification of issues against my controls, **so that** I can remediate.

**Acceptance criteria**

Email on issue creation

Issue visible in Control Owner Portal

Remediation upload triggers issue update

Risk Manager closes issue with verification

**Definition of Done**

Power Automate flow on `pei_issue` create sends email to Owner with subject/body/link per AC1; flow runs as service principal (Decision 2 / ADR-032)

Issue surfaces in the Control Owner Portal (L3-D08) issues panel per AC2; clicking opens the issue form

Remediation upload via L2-A02 from the portal triggers an issue update per AC3: a flow watches the L2 Evidence-create event scoped to a CP with open issues and moves the linked issue to Remediation-Submitted; the audit log captures the operator + the linked Evidence record

Risk Manager closure per AC4: a Close action on the issue is permitted only for users in the Risk Manager role and only when the issue has reached Remediation-Submitted; closure writes the verification reason and a closure-by user-stamp; audit log captures the closure

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-B03

## [L3-B05] Engagement progress dashboard

**Status:** Not Started

**As a** Stakeholder, **I want** dashboard view of engagement progress, **so that** I have visibility.

**Acceptance criteria**

Tiles: Evidence Reviewed (X of Y), Issues (Open / Closed), Days Remaining

Per-engagement and aggregate views

Updates real-time

**Definition of Done**

Per-engagement dashboard built as a native model-driven dashboard with the 3 AC1 tiles; tiles render correct values against a test engagement with seeded data (e.g. 4-reviewed-of-10, 2-open-1-closed, 14-days-remaining)

Aggregate view per AC2 sums correctly across engagements; an Auditor user sees aggregates over their L3-A07-assigned engagements only; a Risk Manager sees aggregates over all in their BU

Refresh-on-load and the explicit refresh button per AC3 both pull current data; the time-to-refresh is acceptable (~few seconds) under a representative data load

Color rules applied per the EMS palette: Issues-Open tile uses Amber when >0 and Coral when severity-critical issues are present; Reviewed tile uses Green when 100%; the Green=Complete-only rule honored

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-B02, L3-B03

## [L3-B06] Engagement closure workflow

**Status:** Not Started

**As a** Auditor, **I want** to formally close an engagement, **so that** results are finalized.

**Acceptance criteria**

Close action available when all in-scope evidence reviewed + all issues addressed

Generates closure summary

Locks engagement (read-only after close)

Final sign-off ceremony

**Definition of Done**

Close action visible only when AC1 preconditions hold; an attempt to fire it earlier returns a clear error or is simply not surfaced; both precondition failure modes tested

Closure summary auto-generates per AC2 on the Close action and is attached to the engagement record (handoff to L3-C01 for the PDF); content verified against a test engagement

Engagement locks read-only after close per AC3: a post-close edit attempt on the engagement, any linked junction row, or any linked issue fails with a security exception; audit log captures the close event

Sign-off ceremony per AC4: the final attestation step is exercised end-to-end (Auditor performs the attestation, Closed state lands); the attestation record (operator, timestamp) is stored on the engagement

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-B02, L3-B03

## [L3-B07] Multi-engagement concurrency

**Status:** Not Started

**As a** Builder, **I want** apps to be in scope of multiple concurrent engagements, **so that** the system supports realistic audit overlap.

**Acceptance criteria**

App can appear in multiple Activated engagements

Evidence links per engagement (separate junction rows)

Issue tracking per engagement

No interference between engagements

**Definition of Done**

Test fixture created with one app appearing in two Activated engagements X + Y simultaneously; both engagements show the app in their L3-A04 scope and their L3-A05 evidence-link rows

Per-engagement review state isolated per AC2: Evidence E is marked Reviewed in engagement X; the same Evidence row in engagement Y's junction still shows Pending Review — independent rows, independent state

Per-engagement issue tracking isolated per AC3: a finding is logged against E in engagement X; engagement Y's issue queue does not show it; closure of the issue in X does not affect Y

Engagement X is closed (full L3-B06 flow); engagement Y's review queue, issue list, and L3-B05 dashboard tiles are unaffected — the AC4 no-interference assertion verified end-to-end

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-B · Labels: L3, L3-B · Depends on: L3-A05, L3-B03

# L3-C — Engagement Reporting (~30 hrs)

0 of 5 done

## [L3-C01] Engagement summary report

**Status:** Not Started

**As a** Stakeholder, **I want** a PDF summary of an engagement's outcome, **so that** I have a portable artifact.

**Acceptance criteria**

Generate PDF on engagement close

Sections: Scope, Findings, Evidence Reviewed, Issues Resolved, Outstanding Items

Branded template

Stored on Engagement record + SharePoint

**Definition of Done**

Power Automate flow on the L3-B06 closure transition generates the PDF per AC1 — flow runs as service principal (per Decision 2 / ADR-032) so the engagement record's read-only lock doesn't block the writer

All 5 AC2 sections render with live data from a test closed engagement; section ordering and section headers match the branded template

Branded template applied per AC3: cover, header/footer, no internal product names; one visual review confirms the artifact is exec-presentable

File stored to both targets per AC4: a file column on the `pei_engagement` row + a copy to the EMS SharePoint per-engagement folder; both copies open and render identically

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L3-C · Labels: L3, L3-C · Depends on: L3-B06

## [L3-C02] Per-CP control assessment report

**Status:** Not Started

**As a** Auditor, **I want** detailed per-CP report, **so that** I can drill into control-level audit findings.

**Acceptance criteria**

Generate PDF per CP within engagement

Sections: CP description, scope, evidence collected, AI assessments, findings, conclusions

Bulk-generate option

**Definition of Done**

Per-CP PDF generates per AC1 from an action on either the CP form (single CP) or the engagement (bulk); all 6 AC2 sections render with live data from a test engagement

AI Assessments section pulls the `pei_copilotassessment` text per Evidence record under this CP and renders it; missing assessments show "Not generated" rather than a blank

Bulk-generate per AC3 produces N PDFs for N in-scope CPs in one run; deterministic filenames; results land in the SharePoint per-engagement folder alongside the L3-C01 summary

Performance acceptable on a representative engagement (e.g. ≤20 CPs in scope) — the bulk run completes inside a reasonable time and does not partial-fail (full success or clear error per CP)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-C · Labels: L3, L3-C · Depends on: L3-C01

## [L3-C03] Auditor portal (read-only access)

**Status:** Not Started

**As a** External Auditor, **I want** read-only access to my engagement evidence, **so that** I don't need full Risk Manager access.

**Acceptance criteria**

Custom security role: Auditor

Sees only their assigned engagements

Read-only on Evidence, CPs, Apps

Cannot edit anything except adding findings to their assigned engagements

**Definition of Done**

Custom security role per AC1 created in the dev environment with the precise privilege matrix: Read on `pei_evidence`/`pei_controlprocedure`/`pei_application`; Read on `pei_engagement` filtered via L3-A07 membership; Create/Read/Update on `pei_issue` scoped to assigned engagements; no privileges elsewhere

Engagement-scoping verified per AC2: a test Auditor assigned to engagement X sees engagement X (and only X) in the portal's engagement list; a parallel Auditor assigned to engagement Y sees engagement Y only; an unassigned Auditor sees an empty list

Read-only enforcement verified per AC3 with three negative-case tests: (a) Auditor user can read records on the assigned engagement but gets no result outside it; (b) every write attempt to Evidence/CP/App (Create/Update/Delete) fails with a security exception; (c) finding-add (`pei_issue` Create) on the assigned engagement succeeds — this is the canonical ADR-032 contract test

Auditor-scoped MDA app or sub-area surfaces only the role's usable views; the unauthorized navigation paths (Risk Manager admin, L3-D07) are not in the sitemap for this role

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-C · Labels: L3, L3-C · Depends on: L3-A01

## [L3-C04] Evidence export for auditor

**Status:** Not Started

**As a** External Auditor, **I want** to export evidence files in bulk, **so that** I can review offline.

**Acceptance criteria**

Bulk download action on engagement evidence

ZIP file with folder structure matching engagement scope

Includes manifest CSV

Audit log captures export

**Definition of Done**

Bulk download action per AC1 surfaces on the engagement form for Auditor users on their assigned engagements; firing it produces a downloadable ZIP from the flow's run history (no manual download from SharePoint required)

ZIP folder structure per AC2 matches the engagement scope's CP × App tree; opening the ZIP shows the expected hierarchy and every in-scope file is present (with the immutable snapshot per ADR-025 — the file content matches what L3-A05 captured at activation)

Manifest CSV per AC3 present at the ZIP root with all AC3 columns populated; row count matches the file count under the per-CP subfolders

Audit log captures the export per AC4: every export action writes one entry capturing operator, engagement ID, timestamp, and ZIP-file size or hash; the entry is queryable in the audit history

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-C · Labels: L3, L3-C · Depends on: L3-C03

## [L3-C05] Engagement metrics and trending

**Status:** Not Started

**As a** Risk Manager, **I want** historical metrics across engagements, **so that** I can spot patterns.

**Acceptance criteria**

Dashboard: engagements over time, findings by category, average remediation time

Filter by year, by type

Power BI or model-driven dashboard

**Definition of Done**

Dashboard built per AC1 with the 3 metrics rendering from live data; numbers tie back to the source tables on a hand-counted sample (e.g. one specific year's engagement count matches a manual count of closed engagements in that year)

Year and engagement-type filters per AC2 work; switching the filter updates all 3 metrics; an empty filter combination returns an empty-but-not-broken state

Surface per AC3: native MDA dashboard built (no JS / no PCF / no canvas per the EMS architectural rule); Power BI route is recorded as a deferred follow-up if/when needed but is not in this story's scope

Color rules applied where status-coded: severity buckets use the EMS palette (Coral for high-severity counts; the Green=Complete-only rule honored — no green on partials)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-C · Labels: L3, L3-C · Depends on: L3-B06

# L3-D — Package C Screens (~60 hrs — was deferred from POC; subset for production-ready)

0 of 8 done

## [L3-D01] S1 Dashboard

**Status:** Not Started

**As a** Stakeholder, **I want** an overview dashboard, **so that** I see EMS health at a glance.

**Acceptance criteria**

Tiles: Active Cycle, Active Engagements, Open Issues, Evidence Status Aggregate

Auto-refresh

Drill into details

**Definition of Done**

Screen built as a native MDA dashboard and added to the model-driven app's sitemap (top-level "Dashboard" or equivalent); no JS, no PCF, no canvas

All 4 AC1 tiles render with correct live values against a seeded test environment; counts tie back to a hand-counted query of the underlying tables

Auto-refresh per AC2 verified: the tiles update on view-load after a known data change (e.g. a new issue is logged in another browser tab); the explicit refresh button works

Drill-into per AC3: clicking each tile navigates to the correct landing screen; navigation preserves the user's role-gated scope (Auditor sees only their L3-A07-assigned engagements; Risk Manager sees their BU; per-tile color rules applied — Green=Complete-only, Amber=Pending, Coral=Missing, Dark red=Gap, Blue=IDs/links)

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L1-G16, L3-B05

## [L3-D02] S2 Evidence Collection (by CP)

**Status:** Not Started

**As a** Control Owner, **I want** to see all my evidence requirements grouped by CP, **so that** I work through one control at a time.

**Acceptance criteria**

Page grouped by CP, showing all gaps + collected evidence

Filters and search

Direct upload from this view

**Definition of Done**

Screen built as a native MDA view or dashboard surface grouping rows by CP; the card-per-row expand pattern works (purple for expanded accordion per the EMS palette)

Filters and search per AC2 work and compose; an empty result returns an empty-but-not-broken state

Direct upload per AC3 from the page-level action invokes the existing L2-A02 control → L2-A02b flow chain; the status flips Gap (890920003) → Pending (890920000) without any new direct-write path (Decision 5 honored)

Color rules verified: Green only on Complete evidence (Provided rows fully reviewed); Amber on Pending; Coral on Missing; Dark red on Gap; the role-gating scopes the page to the Control Owner's owned CPs only

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L2-A01

## [L3-D03] S3 Compliance Posture (5 tabs)

**Status:** Not Started

**As a** Risk Manager, **I want** compliance posture views by RC, CP, App, BU, Unmapped, **so that** I can analyze coverage from multiple angles.

**Acceptance criteria**

5 tabs (RC / CP / App / BU / Unmapped)

Each tab shows compliance status with metrics

Read-only

**Definition of Done**

Screen built as a native MDA dashboard or sub-area with 5 tabs (no JS / no PCF / no canvas); tab switching does not re-fetch the unchanged data

All 5 AC1 tabs render with correct pivots from the live source tables; the Unmapped tab is non-empty against a seeded fixture with intentional gaps (orphan app without BU; CP without owner)

AC2 metrics per tab tie back to a hand-counted query against the underlying records; color rules applied per the EMS palette (Green=Complete only, Amber=Pending, Coral=Missing, Dark red=Gap, Blue=IDs/links)

Read-only verified per AC3: a Risk Manager (read in their BU) and an Auditor (read on their assigned engagement's records) both see the screen scoped to their role; no write actions are surfaced on any tab

**Jira fields** · Status: Not Started · Type: Story · Points: 1.5 · Estimate: 12.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L1-C04

## [L3-D04] S4 Engagements

**Status:** Not Started

**As a** Risk Manager, **I want** an engagements landing page, **so that** I see all engagements at a glance.

**Acceptance criteria**

List of engagements with state, dates, owner

Filter by status, by type, by year

Create new from this page

**Definition of Done**

Screen built as a native MDA view on `pei_engagement` with the AC1 columns; the view is added to the model-driven app's sitemap

Filters per AC2 work and compose; the Year filter correctly buckets engagements by their Start Date year; an empty filter returns the unfiltered list (not empty)

"Create new" per AC3 from a page-level command bar action invokes the L3-B01 wizard (if available) or the quick-create form (fallback); the action is hidden for roles without create privilege on `pei_engagement` (Auditor, Stakeholder)

Color rules applied: state buckets render with the EMS palette where status-coded (Activated/In Progress = neutral or Amber; Closed = Green only when truly closed; the Green=Complete-only rule honored)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L3-A01

## [L3-D05] S5 Evidence Freshness

**Status:** Not Started

**As a** Risk Manager, **I want** evidence freshness landing page, **so that** I prioritize remediation.

**Acceptance criteria**

Aggregated freshness state

Drill into specific records

Trend over time

**Definition of Done**

Screen built as a native MDA dashboard or sub-area; AC1 aggregated tiles render correct counts from a seeded fixture across all freshness states; per-App and per-BU roll-ups computed correctly

Drill-into per AC2 lands on the underlying records list (or per-CP/per-App view); the navigation preserves role-gated scope

Trend-over-time per AC3 renders a time-series with at least 6 months of data on a representative environment; the data source is live (queries refresh on view-load)

Color rules applied: Coral on Missing/Stale aggregates; Dark red on Expired (Gap-equivalent); Amber on Aging; Green only on Fresh full-complete

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L2-B04

## [L3-D06] S6 GRC Catalog (4 tabs)

**Status:** Not Started

**As a** Stakeholder, **I want** a catalog view of RCs, CPs, Apps, BPs, **so that** I can browse the GRC inventory.

**Acceptance criteria**

4 tabs (RC / CP / App / BP)

Search and filter

Read-only

**Definition of Done**

Screen built as a native MDA dashboard or sub-area with 4 tabs (no JS / no PCF / no canvas); the catalog is reachable from the flat top nav per the Package C navigation shell

All 4 AC1 tabs render rows from their source tables; row counts match a hand-counted query

Search per AC2 returns expected results on each tab (e.g. a known RC ID surfaces the row); per-tab filters narrow correctly; an empty result returns an empty-but-not-broken state

Read-only per AC3 verified: no command-bar actions for edit/create surface on any tab for any role; Stakeholder navigates the catalog with no write affordances anywhere

**Jira fields** · Status: Not Started · Type: Story · Points: 1.25 · Estimate: 10.0h · Epic: L3-D · Labels: L3, L3-D

## [L3-D07] S7 Admin

**Status:** Not Started

**As a** System Admin, **I want** an admin landing page with key tools, **so that** I can find admin functions easily.

**Acceptance criteria**

Sub-pages: Sync controls, Engagement Types, Workflows

Links to Rules Catalog, BU Mapping

Visible only to System Admin role

**Definition of Done**

Screen built as a native MDA sub-area with the 3 AC1 sub-pages; each sub-page link navigates to its canonical surface

The 2 AC2 link targets (Rules Catalog, BU Mapping) navigate to their respective surfaces and render correctly

Role-gating verified per AC3 with two tests: (a) a System Admin user sees the sub-area in the sitemap and can navigate every sub-page; (b) a non-admin user (Risk Manager, Auditor, Stakeholder, Control Owner, Control Tester) does not see the sub-area, and a direct-URL attempt fails with a security exception

No write actions surface to non-admin roles even by accident; the sitemap visibility and the underlying privilege matrix agree

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L1-D09, L1-D10

## [L3-D08] S8 Control Owner Portal

**Status:** Not Started

**As a** Control Owner, **I want** a portal showing only what's relevant to me, **so that** I'm not overwhelmed by unrelated data.

**Acceptance criteria**

Lists my CPs and their evidence requirements

Notifications and alerts

Quick upload action

My open issues from engagements

**Definition of Done**

Screen built as a native MDA dashboard or sub-area; the user's owned CPs render correctly per AC1 against a seeded test user (e.g. CO-1 owns CP-001 + CP-002 and sees exactly those rows)

Notification + alert tiles per AC2 fire on the expected triggers (evidence about to expire; new issue logged on an owned CP); the matching email from L3-B04 also lands in the user's inbox

Quick upload per AC3 from a CP-row action invokes the L2-A02 → L2-A02b chain; the status flips Gap (890920003) → Pending (890920000) without any new direct-write path

My open issues per AC4 renders the filtered list with engagement context; clicking a row opens the issue form (Control Owner can update Owner's portion of the remediation but cannot close the issue per L3-B04 AC4); color rules applied (Coral on Open, Amber on Remediation-Submitted)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: L3-D · Labels: L3, L3-D · Depends on: L2-A01

# INF-A — Security Model (~22 hrs)

0 of 5 done

## [INF-A01] Define security roles (7-role production design)

**Status:** Not Started

**As a** System Admin, **I want** seven distinct Dataverse security roles defined per the L1-Z01 Decision 3 lock, **so that** least-privilege access is enforced and EMS supports its production user model.

**Acceptance criteria**

Seven custom Dataverse security roles created and configured per the specification below; each role's name, description, and scope written into its Dataverse Description field for runtime visibility

Custom security role "EMS - System Admin" created in Dataverse with org-wide scope, full org-wide read/write on all EMS tables, and inheritance from out-of-box Basic User

System Admin is the only role with admin-only sitemap subareas (Rules Catalog, BU Configuration, Naming Standard) visible and the only role with access to the Rule Admin form (L1-B05)

System Admin is assignable to named individuals only (not groups); typical production population 1–3 people

Custom security role "EMS - Risk Manager" created with BU-scoped access via the `pei_owningbu` field on each filtered record, single-BU-per-assignment (not multi-BU per L1-Z01 Decision 3 Q3), with the user's BU determined by their Dataverse Business Unit assignment

Risk Manager filtered records: Application, Control Procedure, Parent BP, Applicability, Evidence — visible only where the record's `pei_owningbu` equals the user's BU

Risk Manager unfiltered records: Reference Control catalog (read-only), Import Cycle (read-only — consume not create), Rule Catalog (read-only via L1-B07)

Risk Manager sitemap shows Cycle Management + Master Data + Evidence (per existing L1-D11 design); Rules & Mappings and Admin areas are hidden

Risk Manager has access to standard forms only; the Rule Admin form is hidden (per L1-B05); typical production population 5–50 depending on org size

Custom security role "EMS - Control Owner" created with record-level scope via the `pei_controlowner` lookup; users see only records where they are listed as the Control Owner

Control Owner filtered records: Control Procedure (where user is `pei_controlowner`), Applicability (where user is `pei_controlowner`), Evidence (where parent Applicability's `pei_controlowner` is the user)

Control Owner unfiltered records: Reference Control catalog (read-only for context)

Control Owner primary surface is the Control Owner Portal (L2-A01), not the standard EMS sitemap; standard CP/Applicability/Evidence forms are read-only except for the evidence-upload control

Control Owner write access is limited to Evidence file uploads plus the Gap→Pending status flip on their own Applicabilities; typical production population 50–500 (one per CP at minimum)

Custom security role "EMS - Control Tester" created with org-wide read on Application, Control Procedure, Reference Control, Parent BP, Applicability, Evidence, and SharePoint files; no write, create, or delete privileges anywhere in EMS

Control Tester CP-level assignment lives upstream in their team's testing tooling and is NOT enforced by EMS — this is a deliberate scoping decision per L1-Z01 Decision 3, not a gap; test results live outside EMS by design per ADR-032

Control Tester primary surface is a read-only Control Tester Portal showing the catalog; typical production population 10–100

Custom security role "EMS - Auditor" created with engagement-scoped access via the `pei_engagementmember` (or equivalent) junction table; users see only records linked to engagements they are assigned to; covers both internal and external auditors

Auditor filtered records: Engagement (where user is a member), Engagement Evidence (transitively via engagement), Engagement Findings (parent Engagement in user's filtered set)

Auditor read access via engagement: CPs, Apps, Evidence linked to in-scope engagements

Auditor write access: Engagement Findings within assigned engagements only, plus bulk evidence export per L3-C04

Auditor cannot access records outside assigned engagements, Rules, BU/mapping admin areas, or Cycle records (cycles are operational, not audit-relevant); sitemap visibility limited to engagement-related areas

Custom security role "EMS - Stakeholder" created with org-wide read on aggregates only; no detail-level filter, no detail forms, no raw evidence file access

Stakeholder read access: Dashboards (Cycle Status, Engagement Progress, Evidence Aggregate, EMS Overview per L1-D08 / L3-B05 / L3-D01), GRC Catalog read-only browse (RC/CP/App/BP per L3-D02), engagement-close PDF summaries (L3-B06)

Stakeholder sitemap visibility: Dashboards subarea + Catalog subarea only; cannot drill into individual records; typical production population 5–20 (executive sponsors, leadership, board)

Custom security role "EMS - System" (service principal) created as an Azure AD App Registration per L1-Z02 with org-wide elevated privileges; NOT a human user account

System role has Create/Read/Write/Delete on all EMS tables required by flows, plus FSP bypass per L1-G18 to permit field updates that human roles cannot make

System role audit-log attribution distinguishes service-principal actions from human user actions for forensic review; assignable to the service principal only, never to a human user

Each of the 7 roles tested by assigning to a test user and verifying that expected reads/writes succeed and forbidden operations fail with the expected error

**Definition of Done**

All 7 roles created in Power Platform admin centre with name, description, and scope per spec, with the description text written into each role's Description field for runtime visibility

ADR-032 (Security role architecture) authored and committed to `01_Architecture/01_Decision_Log.html` with the canonical sections

Role definitions document published at `05_Building_Blocks/04_Security_Model/01_Role_Definitions.md` (new folder created)

Tracker role table at `_All_Layers_Tracker_2026-04-25.md` lines 33–42 reconciled to the 7-role design

Each role assigned to a test user and the expected access patterns validated by attempted reads/writes on filtered and unfiltered records

Schema doc updated to reflect any role-related fields added during configuration (e.g., `pei_controlowner` lookup if it doesn't exist yet)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 6.0h · Epic: INF-A · Labels: INF, INF-A · Depends on: L1-Z01, L1-Z02

## [INF-A02] Role-based table privileges (full CRUD matrix per role × per table)

**Status:** Not Started

**As a** System Admin, **I want** each role to have appropriate table-level + field-level privileges, **so that** users can read and write only what their role design permits per L1-Z01 Decision 3.

**Acceptance criteria**

All cells of the role × table privilege matrix configured in Dataverse per the matrix tables below; the legend and the 5 privilege matrix tables plus the FSP field-restriction table are preserved below this acceptance bullet run as the canonical specification

System Admin role configured with Create/Read-Org/Write-Org/Delete on all 13 EMS tables (master data, mapping, cycle pipeline, rules, engagement), per the matrix

Risk Manager role configured BU-scoped (R-BU or R-BU/W-BU as the matrix dictates) on Application, Control Procedure, Parent BP, Applicability, Evidence, Engagement; Org read on Reference Control, Business Unit, Rule (via L1-B07 read-only filtered view, no admin form); no access to mapping tables or Rule Version write

Risk Manager write on Application is restricted to the BU field only; on Cycle and Stage records, write is restricted to gate ticks only — per the FSP field-restriction table

Control Owner role configured User-scoped via the Owner lookup (R-U where user is `pei_controlowner` on CP / Applicability / Evidence parent); no access to Parent BP, Business Unit, mapping tables, cycle records, scope classifications, rule tables, or engagement records

Control Tester role configured Read-Org on Application, Control Procedure, Reference Control, Parent BP, Applicability, Evidence (including SharePoint files); no access to Business Unit detail, mapping tables, cycle records, scope classifications, rule tables, or engagement records

Auditor role configured engagement-scoped (R-U where engagement member; transitive read on Engagement Evidence and Findings) plus org-wide read on CP/App/Reference Control/Parent BP/Applicability/Evidence within in-scope engagements; write on Engagement Findings only within assigned engagements; read on Rule Version where engagement-scoped (for "what rule version produced this finding")

Stakeholder role configured Read-Org on aggregate views only (dashboards, catalog) for Application, Control Procedure, Reference Control, Parent BP; aggregate-only read on Applicability and Evidence (no detail forms); dashboard-tile read on Import Cycle and Engagement; no access to mapping tables, scope classifications, rules, or rule versions

System (service principal) role configured Create/Read-Org/Write-Org on all EMS tables required by flows; FSP bypass per L1-G18 to permit field writes that no human role can make

`pei_reviewed` on all master records is read-only for every human role; only the EMS Confirmation flow (via the service principal) flips it

`pei_emslifecyclestatus` on all master records is read-only for every human role; only flows may change it

`pei_evidencestatus` on Evidence is flow-controlled (state machine); the one human exception is the Control Owner Gap→Pending flip on their own Applicabilities; all other transitions service-principal only

`pei_applicabilitystatus` is read-only for every human role; only flows toggle Active/Inactive

Snapshot fields on Evidence are immutable after creation per ADR-025; FSP enforces read-only for all roles

Counter fields on Import Cycle (rcnew, appnew, etc.) are writable by Flow 1 (service principal) only

AI Assessment fields on Import Cycle and Applicability are writable by AI Builder flows (service principal) only

`pei_aiassessment`, `pei_aireasoning`, and `pei_aisuggestedscopetype` on Applicability are set by Flow 3B only

Gate fields on Import Cycle become read-only when their value is Yes (per L1-G39 and Decision 1)

`pei_owningbu` on Application can be set by Risk Manager initially but is locked after the first cycle (FSP)

Lookup fields on Evidence and Applicability (CP, App, etc.) are read-only after creation per ADR-025

Test users (one per role) created and the matrix validated by attempting allowed and forbidden actions per row; results documented at `05_Building_Blocks/04_Security_Model/02_Privilege_Test_Results.md`

Any discrepancies between this matrix and runtime behavior flagged and fixed before INF-A02 closes

**Definition of Done**

All cells of the role × table matrix configured in Dataverse for each of the 7 roles per the canonical specification below

Test users attempt allowed and forbidden actions per table-row and the matrix is validated end-to-end with results captured

Test result document committed at `05_Building_Blocks/04_Security_Model/02_Privilege_Test_Results.md` (new file)

Any discrepancies between the matrix and runtime behavior surfaced during testing are resolved before close

FSP field-restriction boundary (the field-level table) verified by attempted writes from non-system roles failing with the expected error; service principal bypass confirmed working on each restricted field

**Jira fields** · Status: Not Started · Type: Story · Points: 1.0 · Estimate: 8.0h · Epic: INF-A · Labels: INF, INF-A · Depends on: INF-A01, L1-Z02

## [INF-A03] Field-level security profiles

**Status:** Not Started

**As a** System Admin, **I want** sensitive fields protected, **so that** non-admin users can't modify protected data.

**Acceptance criteria**

FSPs: Status (locked), Reviewed flags (locked), Owning BU (Risk Manager only), Rule fields (Admin only)

Service principal has bypass

Tested

**Definition of Done**

FSPs created in Power Platform for Status (locked from every human role), Reviewed flags (locked from every human role), Owning BU on Application (writable by Risk Manager only after initial set, locked thereafter), and Rule-table fields (writable by System Admin only)

Service principal bypass verified working on every restricted field by a successful write from the SP identity

Each FSP validated by a non-privileged user attempting a write and the write failing with the expected error message

FSP catalogue captured under `05_Building_Blocks/04_Security_Model/` so the active FSP set is discoverable without reading Dataverse admin UI

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: INF-A · Labels: INF, INF-A · Depends on: INF-A01, L1-G18

## [INF-A04] Record-level security (BU partitioning)

**Status:** Not Started

**As a** Risk Manager, **I want** to see only my BU's records (when applicable), **so that** focus and security are aligned.

**Acceptance criteria**

Business Units owning records

Risk Manager sees only records for their assigned BU (single BU per L1-Z01 Decision 3)

Dynamic based on user's BU assignment

**Definition of Done**

Business Units own records via the `pei_owningbu` lookup populated on every filtered record type

Risk Manager security role reads filter records where `pei_owningbu` equals the user's assigned Dataverse BU — verified by assigning a test RM to BU-A and confirming only BU-A records are visible

Dynamic behaviour confirmed by reassigning the test user to BU-B and observing the filter switching without any code change

BU-partitioning behaviour documented in the Security Model folder alongside the role definitions

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: INF-A · Labels: INF, INF-A · Depends on: L1-A01

## [INF-A06] Security testing

**Status:** Not Started

**As a** Builder, **I want** to test access control across all roles, **so that** I'm confident in production security.

**Acceptance criteria**

Test cases per role

Verify cannot access denied tables/fields

Verify can access allowed

All tests pass

**Definition of Done**

Test case set executed end-to-end against the production-shaped environment with all positive cases passing and all negative cases failing with the expected error

Every restricted table or field flagged in INF-A02 / INF-A03 verified inaccessible by a non-privileged role and accessible by the privileged role or the service principal

Test results documented at `05_Building_Blocks/04_Security_Model/03_Security_Test_Results.md` so future regression runs have a baseline to compare against

Any test failure traced to a configuration gap is fed back to the originating INF-A0x story for remediation before this story closes

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: INF-A · Labels: INF, INF-A · Depends on: INF-A01

# INF-B — Operational Tooling (~25 hrs)

0 of 6 done

## [INF-B01] Failure notifications

**Status:** Not Started

**As a** System Admin, **I want** alerts when flows fail, **so that** I can intervene quickly.

**Acceptance criteria**

All major flows wrapped with try-catch

Failures logged + email alert sent

Includes flow name, error, run URL, timestamp

**Definition of Done**

Every flow in the agreed set wrapped with try-catch at action boundaries; uncaught exceptions surface to the catch path rather than silent run failure

Failure-log record written with the full agreed payload on every catch invocation; verified by inducing a controlled failure in each flow

Email alert fires from the catch path with the flow name, error excerpt, run URL, and timestamp; recipient verified in the inbox after an induced failure

Failure-log retention configured to match the audit-log retention target (cross-reference INF-B05) so historical failure investigation is possible

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: INF-B · Labels: INF, INF-B

## [INF-B02] Daily operational digest

**Status:** Not Started

**As a** System Admin, **I want** a daily digest of system state, **so that** I have proactive visibility.

**Acceptance criteria**

Email at scheduled time daily

Sections: Yesterday's flow runs, Errors, Active cycles, Pending reviews, Unresolved BUs

Metrics over 7-day trend

**Definition of Done**

Scheduled flow runs daily at the configured time and emits the digest email to the agreed distribution list

Digest contains all five sections — Yesterday's flow runs, Errors, Active cycles, Pending reviews, Unresolved BUs — each with current count and 7-day-trend metric

A sample digest reviewed against runtime state and confirmed accurate per section

Failure path of the digest flow itself logs without breaking the schedule (digest flow appears in the INF-B01 catch coverage)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: INF-B · Labels: INF, INF-B · Depends on: INF-B01

## [INF-B03] Cycle SLA tracking

**Status:** Not Started

**As a** Risk Manager, **I want** cycles tracked against SLA, **so that** stale cycles are surfaced.

**Acceptance criteria**

Configurable SLA per stage (e.g., Stage 4 must complete within 5 days)

Notifications when SLA breaching

Dashboard view of breached cycles

**Definition of Done**

SLA-per-stage configuration table populated with the agreed thresholds; values readable by the SLA-evaluation flow

Scheduled flow evaluates active cycles against the SLA configuration daily and writes a breach record when the threshold is crossed

Notifications fire to the agreed recipient on each new breach record; verified by an induced breach in a test cycle

Dashboard view of breached cycles published showing cycle ID, breaching stage, days over SLA, and owning Risk Manager — linked from the existing cycle dashboards

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: INF-B · Labels: INF, INF-B · Depends on: L1-D01

## [INF-B04] Data quality checks

**Status:** Not Started

**As a** System Admin, **I want** automated checks for data integrity, **so that** issues surface before causing problems.

**Acceptance criteria**

Daily: orphan applicabilities, evidence without applicability, NULL BUs, duplicate detection

Issues logged + alert if threshold exceeded

Admin dashboard of data quality

**Definition of Done**

Daily flow runs every rule in the agreed catalogue and writes findings to the findings table with rule ID, affected record reference, severity, and timestamp

Alerts fire when any rule's finding count exceeds its configured threshold for the day

Admin dashboard shows current state per rule plus a 30-day trend so improving / degrading rules are visible

Each rule individually tested by seeding a fixture row that should trigger it and confirming the finding lands with the correct severity

**Jira fields** · Status: Not Started · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: INF-B · Labels: INF, INF-B

## [INF-B05] Audit log retention

**Status:** Not Started

**As a** Auditor, **I want** audit logs preserved for required retention period, **so that** historical investigations are possible.

**Acceptance criteria**

Audit logging enabled on all sensitive tables

Retention policy: 7+ years

Periodic export to long-term storage

**Definition of Done**

Audit logging enabled on every table in the sensitive-table inventory; verified by editing a sample row and inspecting the audit history

Retention policy configured to retain audit history for the required period; setting captured in the admin runbook

Scheduled export flow runs at the agreed cadence and writes audit-history extracts to the long-term storage location with date-stamped filenames

One full export cycle verified end-to-end: extract written, integrity checked (row count matches source), retention applied at destination

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-B · Labels: INF, INF-B

## [INF-B06] Operational runbook

**Status:** Not Started

**As a** System Admin, **I want** documented procedures for common operations, **so that** operations are reliable.

**Acceptance criteria**

Runbook covering: starting a cycle, recovering from flow failure, reopening a cycle, adding a BU mapping, authoring a rule, handling an integration outage

Step-by-step with screenshots

Stored in admin area

**Definition of Done**

Runbook covers each of the agreed procedures end-to-end with step-by-step instructions and annotated screenshots: starting a cycle, recovering from a flow failure, reopening a cycle, adding a BU mapping, authoring a rule, handling an integration outage

Runbook stored in the admin area at the agreed location and linked from the EMS landing page and sitemap

Dry-run by a non-author admin completes one sample procedure (typically "recovering from a flow failure") without external help; any friction points fed back into the runbook

Cross-references to the operational dependencies (INF-B01 alerts, INF-B04 data-quality findings, INF-C resilience patterns) added so admins can navigate from a triggered alert to the matching procedure

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Epic: INF-B · Labels: INF, INF-B

# INF-C — Integration Resilience (~12 hrs)

0 of 5 done

## [INF-C01] Archer feed retry logic

**Status:** Not Started

**As a** System, **I want** Flow 1 to retry on transient Archer errors, **so that** ingestion is resilient.

**Acceptance criteria**

Retry 3 times with exponential backoff on file read failures

After 3 failures → notify admin

Successful retry logs delay metadata

**Definition of Done**

Flow 1 retries the Archer call 3 times with exponential backoff on the catalogued failure classes; verified by an induced failure (file removed mid-run) recovering successfully on retry

After the third failure the admin notification fires with the file path, the error context, and the run URL; verified by a persistent induced failure

Successful retry writes delay metadata to the run log (attempt number + elapsed-ms per attempt) so post-hoc tuning of the backoff schedule has real data to work from

Retry behaviour does not produce duplicate Staged rows on success (idempotency confirmed by row-count comparison before/after a triggered retry)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: INF-C · Labels: INF, INF-C

## [INF-C02] LeanIX feed retry logic

**Status:** Not Started

**As a** System, **I want** Flow 1 to retry on transient LeanIX errors, **so that** ingestion is resilient.

**Acceptance criteria**

Retry 3 times with exponential backoff on LeanIX endpoint failures (timeouts, 5xx responses, malformed payloads)

After 3 failures → notify admin with a LeanIX-specific subject line and the endpoint identifier in the alert body

Successful retry logs delay metadata (attempt number + elapsed-ms) plus the LeanIX endpoint version captured at the time of the call for diagnostics

**Definition of Done**

Flow 1 retries the LeanIX call 3 times with exponential backoff on the catalogued failure classes; verified by an induced failure (endpoint pointed at an unreachable URL) recovering successfully when the URL is restored

After the third failure the admin notification fires with the LeanIX endpoint identifier, error context, and run URL; verified by a persistent induced failure

Successful retry writes delay metadata plus the captured LeanIX endpoint version to the run log

Retry behaviour does not produce duplicate Staged rows on success (idempotency confirmed parallel to C01)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Epic: INF-C · Labels: INF, INF-C

## [INF-C03] SharePoint outage handling

**Status:** Not Started

**As a** System, **I want** flows to gracefully handle SharePoint unavailability, **so that** evidence operations don't corrupt state.

**Acceptance criteria**

Flows detect SP unreachable

Mark dependent operations Pending Retry

Auto-retry on schedule

Alert if persistent

**Definition of Done**

Every SharePoint-touching flow detects unreachable / timeout responses and marks the dependent operation Pending Retry rather than failing the parent run

Scheduled auto-retry flow processes Pending Retry items at the agreed cadence; verified by simulating SharePoint unavailability and observing recovery on restoration

Alert fires when an item exceeds the persistent-outage threshold (e.g., still Pending Retry after N attempts); verified by inducing a non-recoverable outage

State machine is corruption-free: a Pending Retry item that recovers transitions to a clean terminal state with no stale intermediate flags

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-C · Labels: INF, INF-C

## [INF-C04] AI Builder rate limit handling

**Status:** Not Started

**As a** System, **I want** AI Builder calls respect rate limits, **so that** expensive prompts don't fail unpredictably.

**Acceptance criteria**

Implement queueing or rate-limit-aware batching

Backoff on 429 errors

Track AI usage per cycle for cost monitoring

**Definition of Done**

AI calls funnel through a queueing or rate-limit-aware batching pattern that respects the tenant cap; verified by a load test that would have tripped the limit without the wrapper

429 responses trigger exponential backoff per the agreed schedule; verified by an induced 429 (or simulated 429) being followed by a successful retry after the backoff window

Per-cycle AI usage counter increments on every call and is queryable via the cycle record; verified at the end of a test cycle that the counter matches expected call count

Cost-monitoring dashboard or admin-runbook query documented so the System Admin can spot anomalous usage day-over-day

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-C · Labels: INF, INF-C

## [INF-C05] Integration testing

**Status:** Not Started

**As a** Builder, **I want** to test integration failure modes, **so that** I have confidence in resilience.

**Acceptance criteria**

Simulate: Archer file missing, LeanIX malformed, SP unreachable, AI Builder timeout

Verify graceful handling in each case

Tests pass

**Definition of Done**

Each of the four simulated failure modes executed end-to-end against the resilience-equipped flows; the agreed graceful behaviour observed in each case (retry on Archer, retry on LeanIX, Pending Retry on SharePoint, backoff on AI Builder)

Test results captured per failure mode with timestamps, observed behaviour, and the run URLs that demonstrate it

Any deviation between expected and observed behaviour fed back to the originating INF-C0x story for remediation before this story closes

Test results document committed under `05_Building_Blocks/04_Security_Model/` adjacent territory or a dedicated `INF-C/Test_Results/` location so future regression runs have a baseline

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.5h · Epic: INF-C · Labels: INF, INF-C · Depends on: INF-C01

# INF-D — Performance (~11 hrs)

0 of 4 done

## [INF-D01] Pagination on Stage 5 evaluation

**Status:** Not Started

**As a** System, **I want** Stage 5 evaluation paginated, **so that** large CP × App matrices don't time out.

**Acceptance criteria**

Process in batches of 1000 pairs

Persistent state across batches (resumable)

Within Power Automate run time limits

**Definition of Done**

Stage 5 evaluation processes the CP × App matrix in batches of 1000 pairs; verified at the production-scale corpus with the full evaluation completing across multiple batches

Persistent state tracks the last-completed batch so an interrupted run resumes from the next un-evaluated batch rather than re-processing completed pairs

Each batch completes within the Power Automate run-time limit with documented headroom; recorded in the performance log

Idempotency confirmed: a re-run of a completed cycle produces no duplicate Applicability rows and no double-counted evaluations

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-D · Labels: INF, INF-D · Depends on: L1-C02

## [INF-D02] Indexed views

**Status:** Not Started

**As a** Risk Manager, **I want** views to load quickly even at production scale, **so that** I'm not waiting on the system.

**Acceptance criteria**

Composite indexes on Applicability (Cycle + CP), (Cycle + App), (BU + Status)

Composite indexes on Evidence (Status + Expiry), (Owner + Status)

View load < 2 seconds at 100k records

**Definition of Done**

Composite indexes created in Dataverse on the locked column sets for Applicability and Evidence

View load time confirmed < 2 seconds at the 100k-record corpus across the indexed views; captured per view with measured timing

Before / after performance comparison documented in the performance log so the index payoff is recorded for future tuning

Rollback procedure (drop-index syntax + when to use it) added to the operational runbook (INF-B06)

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-D · Labels: INF, INF-D

## [INF-D03] Batch operations for bulk creates

**Status:** Not Started

**As a** System, **I want** bulk create operations to use batched API calls, **so that** large data loads complete quickly.

**Acceptance criteria**

Use Dataverse batch API for create operations >100 rows

Throughput target: 1000 records/min

Tested at production scale

**Definition of Done**

Bulk create operations of > 100 rows route through the Dataverse batch API rather than per-row create actions

Measured throughput meets or exceeds 1000 records/min on the production-scale test corpus; result captured in the performance log

Behaviour validated at production-shape volumes (full Applicability creation pass for a representative cycle) with no Power Automate run-time-limit violations

Failure mid-batch handled gracefully: a partial batch failure leaves the table in a consistent state and the failure surfaces to the INF-B01 catch path

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-D · Labels: INF, INF-D · Depends on: L1-C04

## [INF-D04] Performance regression testing

**Status:** Not Started

**As a** Builder, **I want** performance benchmarks captured, **so that** future changes don't degrade performance.

**Acceptance criteria**

Benchmark suite: Flow 1 runtime, Stage 5 evaluation runtime, view load times

Captured per release

Threshold alerts if degradation > 20%

**Definition of Done**

Benchmark suite scripted and runs on demand against the agreed environment; covers Flow 1 runtime, Stage 5 evaluation runtime, and view load times

Current-release baseline captured with all three benchmarks within their target threshold; result archived as the comparison baseline for the next release

Threshold alerts wired so any subsequent run showing > 20% degradation against the prior baseline notifies the System Admin

Capture protocol documented in the operational runbook (INF-B06) so future releases run the benchmark without ad-hoc decisions

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: INF-D · Labels: INF, INF-D · Depends on: INF-D01

# INF-M — Meta-Arc (Meta 100% Resolve Arc, ~17-21 hrs)

6 of 6 done

## [INF-M01] Meta Arc Session 1: Object inventory framework

**Status:** Done

**As a** Builder, **I want** the object inventory framework live, **so that** any object-creating BL work has inventory discipline.

**Acceptance criteria**

BL-086 (EMS Object Inventory, forward-first / legacy-opportunistic) Resolved with hygiene gate

Inventory framework operational and ready to receive future object-creating BL work

Hygiene gate 4-box recorded in BL ledger

Optionally ships as v48 OR an intermediate point release per arc-level discipline

**Definition of Done**

BL-086a (EMS Object Inventory framework) Resolved with hygiene gate: `06_Inventory/` created with all 9 type subdirs plus the framework `README.md` capturing purpose, the forward-only rule (LOCKED), folder map, naming convention, universal entry template, per-type capture matrix, and the three-layer drift defense

`check_and_log.py` extended to hash-watch `06_Inventory/` and the `PP_MIRROR_FILES` set (dispatch with no generators) and to add trigger 6 (PP-mirror doc changed without matching inventory change → forward-only prompt); 5 → 6 ask-triggers; 5/5 trigger-6 unit checks pass; integrated `--dry-run` clean

Inventory framework validated end-to-end on `06_Inventory/choices/pei_scopetype.md` (design-confirmed; build-verification pending a screenshot)

Hygiene gate 4-box recorded in the BL ledger (BL-086 entry): Schema N/A · ADR N/A · Registry YES · File Inventory deferred-to-next-audit

BL-086b (legacy backfill, ~55 objects) left opportunistic — not started, never mandatory — so future object-creating work has discipline without retroactive enforcement on the legacy population

Canonical story count confirmed at 279 (61 L0 + 218 forward) via `build_v3.py` against the v47.1 baseline tracker; mirror's stale 273 attributed to a pre-INF-M-addition input on the mirror side, not a parser bug

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-M · Labels: INF, INF-M

## [INF-M02] Meta Arc Session 2: Source-debt cluster

**Status:** Done

**As a** Builder, **I want** post-April-25-pivot source documentation reconciled, **so that** source-of-truth docs match current architecture and the schema doc can be trusted.

**Acceptance criteria**

BL-002 (Schema doc reconciliation against tenant) Resolved

BL-073 (EMS_Business_Capabilities.md source refresh post-April-25 pivot) Resolved

BL-074 (EMS_Complete_System_Context.md cycle-flow source refresh) Resolved

BL-075 (_System_Overview.md two-layer / three-layer framing bridge) Resolved

BL-076 (_System_Overview.md publisher-prefix typo pei. → pei_) Resolved

BL-080 (_System_Overview.md §10 internal ADR-count contradiction) Resolved

Multiple edits folded into a single editing pass where source files overlap

Hygiene gate 4-box recorded per BL closed

**Definition of Done**

All six in-scope BLs Resolved with 4-box hygiene gates: BL-076 (publisher-prefix typo `pei.` → `pei_`), BL-080 (`_System_Overview.md` §10 ADR-count reconciled to 54 ADRs / max ADR-063), BL-075 (two-layer / three-layer bridge clause prepended at `_System_Overview.md` §3 intro), BL-073 (`EMS_Business_Capabilities.md` full reconciliation: layer framing, scope types, CAP 3 rule-driven rewrite, CAP 5 6-stage rewrite, CAP 8 engagement layer + type-count fixes), BL-074 (`EMS_Complete_System_Context.md` Full User Journey ASCII rewritten to canonical 6-stage cycle plus DOC-09 status banner update), BL-002 (schema-HTML internal-consistency pass with 4 drift items fixed)

Multiple edits folded into single editing passes where source files overlapped (e.g., `_System_Overview.md` saw BL-075, BL-076, and BL-080 edits absorbed into one pass)

Schema-doc trust statement captured: DOC-13/14 baseline holds; DOC-15/16 are tenant-gated and remain the only outstanding schema reconciliation work

BL-097 (12 broken Decision Log links surfaced during the pass) logged Promoted and routed to INF-M04 per the no-scope-expansion discipline

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-M · Labels: INF, INF-M · Depends on: INF-M01

## [INF-M03] Meta Arc Session 3: Internal tooling consistency

**Status:** Done

**As a** Builder, **I want** internal tooling drift retired, **so that** the build pipeline is consistent and high-payoff automation (canonical manifest writer) replaces hand-rebuild work.

**Acceptance criteria**

BL-077 (build_v3.py Done-count disagrees with load_context) Resolved

BL-083 (No canonical manifest hash-table writer) Resolved

BL-084 (Registry parser duplication + Navigation `---` truncation) Resolved

BL-085 (check_and_log trigger 3 — no-estimate is coarse) Resolved

BL-092 (Tracker hash captured stale in v44 PACKAGE_MANIFEST.md + dispatch-gap audit) Resolved

Dispatch-gap audit closes the "how many edges are missing" question

Hygiene gate 4-box recorded per BL closed

**Definition of Done**

BL-077 Resolved: `build_v3.py` L245 renamed the L0 priority bucket from `Done` to `Foundation` so the stdout no longer visually conflates with the canonical `By status: Done: 87`; `load_context.done_count` preserved

BL-083 Resolved (highest payoff): `tools/build_manifest.py` created (~280 lines) as the canonical writer with codified exclusion set, preserves manifest preamble byte-for-byte, replaces only the `## File hashes` table; byte-identity verified against the v47.3 reference; modes default / `--no-tracker-rebuild` / `--dry-run` / `--verify` all functional; Session_End prompt Step 5(c) repointed; Registry +1 entry

BL-084 Resolved: stray `---` at registry L151 (inside 🧭 Navigation) removed and replaced with an HTML-comment boundary marker; renderer count 100 → 101 artifacts; preflight Check 4 WARN → OK; absorbed BL-079

BL-085 Resolved: `check_and_log.py` trigger 3 (no-estimate) now diffs against `.last_check_state.json`'s persisted no-estimate ID set; STATE_SCHEMA bumped 2 → 3; fires only on new additions; 3/3 unit cases pass; cured the 22-item noise dump on every backlog edit

BL-092 Resolved: Phase-4 tracker re-render discipline absorbed into `build_manifest.py` (default invocation rebuilds before hashing); dispatch-gap fixes applied to `_Backlog.md` → added `tracker` and to `_system/WHAT_CHANGED.md` → added `["dashboard"]`; handover / WHAT_CHANGED dependency documented as intentionally session-end-only

Hygiene gate 4-box recorded per BL closed; the canonical manifest writer is the v47.4 ship's headline deliverable

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-M · Labels: INF, INF-M · Depends on: INF-M02

## [INF-M04] Meta Arc Session 4: Display + small bugs

**Status:** Done

**As a** Builder, **I want** display drift and UX papercuts retired, **so that** published surfaces are honest and consistent.

**Acceptance criteria**

BL-009 (Mark BP Removed WorkflowOperationParametersRuntimeMissingValue) investigated first; if scope exceeds estimate, rescope or defer with explicit reasoning

BL-042 (Cycle Counters section on form) Resolved

BL-055 (SC3 doesn't verify next-up consistency across published surfaces) Resolved

BL-059 (Dashboard italic-detail parser truncates ledger summaries) Resolved

BL-070 (Dashboard traffic light vs 8-check inconsistency) Resolved

BL-071 (Manual closing line duplicated in regenerated output) Resolved

BL-072 (Tracker deep-link doesn't switch tabs) Resolved

BL-078 (OPERATING_MANUAL.md "Latest package" version lags by one ship) Resolved

BL-081 (build_v3.py hardcoded absolute project path breaks portability) Resolved

BL-097 (12 broken Decision Log links in `_System_Overview.md` from the BL-051 folder reorg) Resolved — bulk replace `../09_Architecture_Decisions/01_Decision_Log.html` → `01_Decision_Log.html`

Hygiene gate 4-box recorded per BL closed

**Definition of Done**

Nine in-scope BLs Resolved with hygiene 4-boxes: BL-042 (Cycle Counters status reconciliation), BL-055 (SC3.2.h cross-surface next-up check + `_gotchas.md` data-flow doc), BL-059 (dashboard italic-parser `_system/` truncation), BL-070 (dashboard traffic light: amber on WARN-only, red only on FAIL), BL-071 (manual closing line de-duplicated at the §15 template true-source), BL-072 (tracker `#tab-<name>` deep-links via `handleHashNavigation` → `switchTab`; `#story-*` preserved), BL-078 (manual Latest-package sourced from the ship tag, not the lagging manifest), BL-081 (capstone — `build_v3.py` and `render_html_v4.py` hardcoded paths made `__file__`-relative; symlink retired), BL-097 (12 broken Decision Log links repointed)

BL-009 investigated first per the AC and ROUTED rather than resolved in-session: identified as a Power Automate flow-runtime defect, not a Cluster D display / UX papercut, so it stays Promoted under its proper product home (L1-A15 flow work)

5 adjacent findings logged and routed to INF-M06 Cluster F triage: BL-098 (manifest preamble file-count lag), BL-099 (remaining post-BL-051 broken links + adr-030 dangling anchor), BL-100 (forms-ref frozen-vs-live disposition), BL-101 (switchTab wrong-button highlight), BL-102 (00_INDEX displays superseded L1-E01 as next-up — caught on first run by the new SC3.2.h check, validating BL-055)

Verification used interim regens (dashboard / manual / tracker), each restored to the v47.4 baseline; W8 regenerates authoritatively at ship

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Epic: INF-M · Labels: INF, INF-M · Depends on: INF-M03

## [INF-M05] Meta Arc Session 5: Big enrichments

**Status:** Done

**As a** Builder, **I want** the hierarchy view layer and Jira export tool live, **so that** L1-B / L2 / L3 work has substantive infrastructure that pays off across the remaining product arc.

**Acceptance criteria**

BL-095 (Hierarchy view layer — capability / feature / roadmap views) Resolved with hygiene gate

BL-096 (Story-to-Jira export tool — engineer handoff workflow) Resolved with hygiene gate

Both treated as substantive infrastructure (originally deferred-until-painful; now done per arc commitment)

Hygiene gate 4-box recorded per BL closed

**Definition of Done**

BL-096 Resolved: `tools/export_to_jira.py` shipped with single-story + feature-prefix + Jira CSV modes; reads `/tmp/all_stories_enriched.json` with the `intake.py` X2 hollow-gate guard; conservative dep parsing extracts only story-ID-shaped tokens from narrative deps; stdout-only with no clipboard dependency; +1 featured-tier §13 phrase

BL-095 Resolved: 3-module set under `tools/tracker_build/` — `_capability_feature_map.py` with the 12-capability ↔ feature-prefix mapping plus shared helpers including the story-ID fallback that fixed a 25-story coverage gap on unfeatured DOC / INF stories; `render_hierarchy.py` producing capability strip + layer accordion + per-feature panels in one tab; `render_roadmap.py` bucketing features into Done / In Flight / Next Up / Blocked / Deferred per layer; minimal hooks into `render_html_v4.py` so future tracker edits don't merge-conflict; +3 alias-tier §13 phrases

All three v47.5 carry-forwards cleared: CARRY 1 INF-M04 row backfilled in the Meta Arc status table; CARRY 2 BL-103 logged with disposition options (document-the-floor vs refactor-to-3.10-compat); CARRY 3 `tools/ship_verify.py` built as the deterministic local companion to the Cowork independent-verification pattern (17 checks, anomaly classification, exit codes 0/1/2, validated by eating-own-dogfood against the v47.5 zip)

One real bug caught during dogfood: hash-table regex didn't handle backtick-wrapped md5s — fixed and re-validated

§13 catalog moved 33 → 37 phrases (3 featured + 34 alias); Registry +3 entries (Ship Verifier, Story-to-Jira Export Tool, Hierarchy & Roadmap Renderers) with the in-session catch on the dropped Live Ledger Helper entry restored before continuing

Promoted moved 12 → 11 effective across the arc (+1 BL-103 logged, −2 BL-095 / BL-096 resolved); Resolved 42 → 44

**Jira fields** · Status: Done · Type: Story · Points: 0.75 · Estimate: 5.0h · Epic: INF-M · Labels: INF, INF-M · Depends on: INF-M04

## [INF-M06] Meta Arc Session 6: Triage + ship v48

**Status:** Done

**As a** Builder, **I want** remaining Meta BLs dispositioned honestly and v48 shipped, **so that** the Meta substrate is 100% complete and L1-B01 begins on a clean foundation.

**Acceptance criteria**

BL-062 (Tenant state snapshot — Dataverse tables + Power Automate flows) re-evaluated: Resolved OR Parked with explicit trigger conditions

BL-063 (Live Dataverse via MCP) re-evaluated: Resolved OR Parked with explicit trigger conditions

BL-087 (Purge POC/test data before production go-live) re-evaluated: Resolved OR Parked tied to Product cutover dependency

BL-100 (`MDA_Forms_Views_Reference.md` frozen-vs-live) Resolved via the **frozen-snapshot** disposition: explicit "frozen as of April 20, 2026" header + pointer to live Power Platform forms / DOC-10 for authoritative current state. The **live-currency pass remains deferred (tenant-gated)** and carries the do-not-promote-until-tenant-work trigger. [Reconciliation note: the arc plan's reserved "BL-100 (new) framework-extraction park" placeholder and this *logged* BL-100 are **different items** — the number was assigned to the forms-ref finding during INF-M04. Framework extraction stays parked at the arc level per the plan's "Framework extraction (NOT in this arc)" section; it does not need a BL number to remain parked.]

v48 ships clean: 8-check green, BRD invariant tracked, manifest LAST, 0 backups/bytecode/symlinks

`00_State/_Meta_100_Resolve_Arc.md` marked **Closed** with actual hours vs estimate noted

Next-up story in tracker = L1-B01

userMemories updated to reflect Meta-complete state and Product-arc-starting state

**Definition of Done**

Nine backlog items Resolved with hygiene 4-boxes: BL-098 (manifest preamble figure computed + injected by `build_manifest.py`; `--verify` gains stale-preamble detection), BL-099 (4 remaining post-BL-051 links repointed + 2 bare-paths corrected + adr-030 dangling anchor softened to DOC-05 forward-ref), BL-100 (forms-ref frozen-snapshot disposition with explicit "frozen as of April 20, 2026" header), BL-101 (`switchTab` highlights active button by its `onclick` target across all 12 tabs), BL-102 (00_INDEX next-up `L1-E01 → L1-B01` across hero card + critical-path viz + summary), BL-103 (`render_html_v4.py` L2840 PEP-701 backslash-in-f-string refactored to local var → 3.10/3.11-compatible, output byte-identical), BL-104 (✓ COMPLETE markers backfilled for Clusters A + E), BL-105 (Check 17 extended to assert cluster narrative marker; count stays 17; dogfood vs v47.6 correctly FAILed on missing Cluster E marker), BL-106 (Check 1 recognises known-exclusion delta as PASS; dogfood vs v47.6 → PASS)

Three items Parked with explicit unpark triggers: BL-062 (tenant snapshot — tenant-introspection-gated), BL-063 (live Dataverse MCP — security-review + multi-tenant-gated), BL-087 (purge POC data — cutover-gated)

Two items named as honest out-of-scope residuals: BL-009 (Power Automate flow-runtime defect, routed to product home L1-A15) and BL-086 (the ~10h legacy object-inventory backfill — opportunistic; the BL-086a framework already shipped at INF-M01); the arc thus reached 100% resolution of every in-scope Meta BL with the two residuals honestly out of scope

v48 shipped clean: BRD literal-hold released (BRD regenerates from its templates); NFR / SECURITY / DIAGRAMS re-blessed on count / date-only deltas; manifest written LAST; verified by both `tools/ship_verify.py` (17 PASS) and the Cowork independent-verification pass

`00_State/_Meta_100_Resolve_Arc.md` marked Closed with actual hours vs estimate noted; next-up story in tracker = L1-B01; userMemories updated to reflect Meta-complete state and Product-arc-starting state

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.0h · Epic: INF-M · Labels: INF, INF-M · Depends on: INF-M05

# DOCUMENTATION & TRAINING (~34 hrs)

6 of 21 done

## [DOC-01] Risk Manager user guide

**Status:** Not Started

**As a** Risk Manager, **I want** documentation explaining each cycle stage, **so that** I can do my job.

**Acceptance criteria**

Markdown / HTML user guide

Per-stage walk-through with screenshots

Common scenarios + troubleshooting

**Definition of Done**

Markdown source + HTML render published covering all 6 cycle stages with per-stage walk-through and annotated screenshots

Common scenarios + troubleshooting section present covering at minimum: cycle stall, source-system outage during a cycle, evidence-completeness review, sign-off escalation

Reviewed by a Risk Manager test user with feedback incorporated; review comments archived alongside the doc

Linked from the EMS landing page and the admin sitemap so it is discoverable without external pointers

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Labels: DOC

## [DOC-02] Admin runbook

**Status:** Not Started

**As a** System Admin, **I want** comprehensive admin documentation, **so that** I can administer the system.

**Acceptance criteria**

BU mapping coverage: how to add a new BU, how to map an existing BU to an Organisational Unit, how to retire a BU without breaking historical records

Rule authoring coverage: how to open the Rule Admin form, how to author the Conditions JSON, how to set Collection Scope and Priority, how to activate a new rule version

Role management coverage: how to assign a user to one of the 7 production roles, how to validate the user's effective access after assignment, how to rotate ownership of a Control Owner record

Troubleshooting coverage: how to diagnose a stuck cycle, how to inspect a failed flow run, how to read the failure log (INF-B01), how to interpret data-quality findings (INF-B04)

Recovery procedures coverage: how to recover from a Flow 1 failure mid-cycle, how to reopen a closed cycle, how to restore a master record from audit history, how to roll back a bad rule version

Step-by-step instructions throughout with annotated screenshots for every multi-click sequence

**Definition of Done**

All five topic areas (BU mapping, rule authoring, role management, troubleshooting, recovery procedures) documented end-to-end with step-by-step instructions and annotated screenshots

Runbook stored in the admin area and linked from the EMS sitemap so admins discover it via the standard navigation, not a one-off pointer

Dry-run by a non-author admin completes one sample procedure (typically "recover from a Flow 1 failure") without external help; friction points fed back into the runbook

Cross-references to INF-B06 (operational runbook), INF-B04 (data-quality findings), and the security model (INF-A01/A02) added so admins can navigate between adjacent procedures

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 4.0h · Labels: DOC

## [DOC-03] Control Owner training

**Status:** Not Started

**As a** Control Owner, **I want** training on evidence collection, **so that** I know what to do.

**Acceptance criteria**

Slide deck or video

Covers: receiving notifications, uploading evidence, expiry handling

Self-paced

**Definition of Done**

Training artefact published in the chosen medium covering at minimum: receiving notifications when evidence is requested, uploading evidence into the Control Owner Portal, handling evidence expiry / refresh, where to ask for help

Self-paced: a Control Owner can complete the training without a live trainer present; verified by the reviewer completing the run from a cold start

Training material accessible from the Control Owner Portal (L2-A01) landing page so the audience finds it in the natural surface they already use

Feedback mechanism in place (a "report unclear step" link or equivalent) so future Control Owners can flag friction without an out-of-band channel

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC · Depends on: C04

## [DOC-04] ADR consolidation and updates

**Status:** Not Started

**As a** Builder, **I want** all architecture decisions documented, **so that** rationale is preserved.

**Acceptance criteria**

ADR-026 (rule-driven architecture) authored

All prior ADRs reviewed for currency

Decision log up to date

**Definition of Done**

ADR-026 (rule-driven architecture) description authored as a story deliverable describing what the future ADR-026 entry will document; the actual ADR entry is created separately by the ADR-capture process and is not counted as part of this story's closure

Every prior ADR reviewed for currency against the post-April-25-pivot state with each marked current, superseded, or needs-update in the review pass log

Decision Log index regenerated reflecting the review pass outcomes; any superseded ADRs have explicit superseded-by pointers

Review pass log committed alongside the Decision Log so the audit trail of who-reviewed-what-when is preserved for future passes

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC

## [DOC-05] ADR-029: Collection Scope as rule property

**Status:** Not Started

**As a** Architect, **I want** ADR-029 formally written, **so that** the rationale for storing Collection Scope on rules (not on Control Procedures) is preserved and the deprecation of Common/Hybrid/App-Level labels is documented.

**Acceptance criteria**

ADR document authored: `ADR-029_Collection_Scope_as_Rule_Property.md`

Sections: Context, Decision, Consequences, Alternatives Considered, Implementation Notes

Documents that Common Control / Application-Level / Hybrid scope labels are removed from CP table; Collection Scope becomes inherent to each rule

Lists impacts on Stage 5 output language ("AC-2 produced 47 evidence collection points across 47 apps in Finance BU")

Lists tables/fields affected (deprecating `pei_finalscopetype` on CP table or repurposing as denormalized last-cycle field)

Cross-referenced from `_Layer1_Architecture_Decisions.md` and from old documents superseded by it

Linked from main ADR index

**Definition of Done**

ADR description authored covering the canonical sections so the future ADR-029 entry has source material to import from

The deprecated Common Control / Application-Level / Hybrid scope labels documented as removed-from-CP with Collection Scope inherent-to-rule replacement

Stage 5 output language sample captured as an example consequence ("AC-2 produced 47 evidence collection points across 47 apps in Finance BU")

Tables / fields affected listed (deprecating `pei_finalscopetype` on CP table or repurposing as denormalised last-cycle field)

Cross-references reciprocated from the rule schema doc and the previously-affected artifacts so a future ADR-capture pass picks up a coherent description with its links already in place

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.75h · Labels: DOC

## [DOC-06] ADR-030: Six-stage cycle replaces five-stage

**Status:** Not Started

**As a** Architect, **I want** ADR-030 formally written, **so that** the rationale for expanding the BPF from 5 stages to 6 stages is preserved.

**Acceptance criteria**

ADR document authored: `ADR-030_Six_Stage_Cycle.md`

Sections: Context, Decision, Consequences, Alternatives Considered, Migration Notes

Documents the new 6 stages: Detect Changes / Verify App BU / Verify CP BU / Confirm Rules / Review Output / Sign-off

Records the rationale: separate housekeeping (1-3) from policy execution (4-5) from finalization (6)

Migration impact noted: existing in-flight cycles need handling per L1-E migration stories

Cross-referenced from architecture deck and Stage views (L1-D03 through L1-D08)

**Definition of Done**

ADR description authored covering the canonical sections so the future ADR-030 entry has source material to import from

The new six stages enumerated by name (Detect Changes / Verify App BU / Verify CP BU / Confirm Rules / Review Output / Sign-off) with the housekeeping / policy / finalisation grouping rationale captured

Migration impact on existing in-flight cycles described with the responsible L1-E story IDs cited

Cross-references reciprocated from the architecture deck and the Stage view specs so a future ADR-capture pass picks up a coherent description with its links already in place

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Labels: DOC

## [DOC-07] ADR-031: Stage 5 read-only/exception-driven evaluation

**Status:** Not Started

**As a** Architect, **I want** ADR-031 formally written, **so that** the rationale for Stage 5 being read-only (no manual decisions per record) is preserved.

**Acceptance criteria**

ADR document authored: `ADR-031_Stage_5_Read_Only_Evaluation.md`

Sections: Context, Decision, Consequences, Alternatives Considered

Documents that Stage 5 (Review Output) is exception-driven not record-by-record

Risk Manager verifies "system output looks correct" rather than approving each Applicability

Exceptions only surface where rules produced ambiguous or low-confidence results

Links to Stage 5 view spec (L1-D07)

**Definition of Done**

ADR description authored covering the canonical sections so the future ADR-031 entry has source material to import from

The exception-driven (not record-by-record) Stage 5 design captured with the Risk Manager's "system output looks correct" framing rather than per-record approval

The exception surface defined (ambiguous or low-confidence rule outputs) so the description distinguishes routine completion from exception review

Cross-references reciprocated from the Stage 5 view spec (L1-D07) so a future ADR-capture pass picks up a coherent description with its links already in place

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 0.5h · Labels: DOC

## [DOC-08] Rewrite Definitive_Flow_Reference.md for new Layer 1 architecture

**Status:** Done

**As a** Builder, **I want** the Definitive_Flow_Reference document updated to reflect the rule-driven architecture, **so that** it remains the authoritative flow reference and doesn't mislead future sessions.

**Acceptance criteria**

Document updated to reflect: 6-stage BPF (not 5-stage), rule-driven Collection Scope (not classification labels), Flow 3A's new role (Scope Classification deprecated or repurposed), new rule evaluation flow at Stage 5, new flows added per L1-A and L1-C

Old 5-stage references either rewritten or banner-flagged as historical

Section added documenting which legacy flows are superseded vs. retained

Action counts updated for refactored flows

Cross-references to ADR-026, ADR-029, ADR-030, ADR-031 added

Tested by reading top-to-bottom and confirming a new builder could follow it

**Definition of Done**

Original `Definitive_Flow_Reference.md` archived under `99_Archive/00_Session_Handoffs/superseded/Definitive_Flow_Reference.md` (May 2; consolidated to standard archive May 3 during Full Audit)

New flow reference structure created at `05_Building_Blocks/03_Flow_Reference/` with `00_Master_Flow_Reference.md` (index of all 7 production flows) plus `01_Flow1_EMS_Monthly_Sync.md` (comprehensive 598-line action-by-action reference for Flow 1)

HTML renders generated via `build_flow_reference.py` pipeline

Project Artifacts Registry updated 31 → 32 artifacts (-1 stale entry, +2 new entries for Master + Flow 1 detail)

Power Automate Flow Build prompt updated: 5 references to the archived file replaced with pointers to the new structure

All cross-references in active docs verified resolving

Flow detail files for Flows 2 / 3A / 3B / 3C / 3D / 4A captured as future work, not blocking

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 3.0h · Labels: DOC · Depends on: L1-G19, L1-G20, DOC-05

## [DOC-09] Rewrite EMS_Complete_System_Context.md for new Layer 1 architecture

**Status:** Not Started

**As a** Builder, **I want** the System Context document updated for the new architecture, **so that** new sessions get an accurate picture of the system without confusion from deprecated framing.

**Acceptance criteria**

Two-layer mental model removed; three-layer model (L1/L2/L3 plus L0 foundation) used throughout

Capability 04 references renamed to Layer 2

Old Layer 2 (Engagements) references renamed to Layer 3

Rule-driven applicability described accurately

Collection Scope (rule property) described correctly; classification labels removed or marked deprecated

ADR cross-references updated to ADR-026 through ADR-031

Tested: read top-to-bottom, no contradictions with Layer1 Architecture Decisions doc

**Definition of Done**

Two-layer mental model removed throughout the doc; three-layer model (L1 / L2 / L3 plus L0 foundation) used in every framing reference

Capability 04 references renamed to Layer 2; old Layer 2 (Engagements) references renamed to Layer 3 with no residual conflations

Rule-driven applicability described accurately per the post-April-25 design; Collection Scope (rule property) described correctly with classification labels removed or explicitly marked deprecated

ADR cross-references updated to ADR-026 through ADR-031 (descriptions authored in DOC-04..07; live cards added by the separate ADR-capture process)

Top-to-bottom read by another builder produces no contradictions with `_Layer1_Architecture_Decisions.md`; review note archived

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC · Depends on: DOC-05

## [DOC-10] Update MDA_Forms_Views_Reference.md for new forms

**Status:** Not Started

**As a** Builder, **I want** the MDA Forms & Views reference updated, **so that** it documents the actual forms/views built in Layer 1 (6-stage cycle, BU forms, rule forms, etc.).

**Acceptance criteria**

Document includes specs for all forms built in L1-D (Stage 1-6 views), L1-A (BU mapping forms), L1-B (rule authoring/viewing forms), L1-G10-G14 (rebuilt entity forms)

Each form: tab structure, fields, sub-grids, business rules referenced

Each view: columns, filters, sort, sub-grid bindings

Old 5-stage references removed or banner-flagged

Screenshots updated where relevant

**Definition of Done**

Document covers specs for every form built in L1-D (Stage 1-6 views), L1-A (BU mapping forms), L1-B (rule authoring / viewing forms), and L1-G10-G14 (rebuilt entity forms)

Per form: tab structure, fields, sub-grids, and any referenced business rules captured

Per view: columns, filters, sort, sub-grid bindings captured

Old 5-stage references either rewritten to 6-stage or banner-flagged as historical so a reader is never silently misled

Screenshots updated where the underlying form / view changed shape; capture date noted alongside each updated screenshot

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC · Depends on: L1-D08, L1-G10-G14, L1-D11

## [DOC-11] Update AI_Builder_Prompts_Reference.md

**Status:** Not Started

**As a** Builder, **I want** the AI Builder Prompts reference updated for current prompts, **so that** prompt engineering decisions are preserved and the doc reflects the actual prompts in use.

**Acceptance criteria**

All current AI Builder prompts inventoried (Flow 1 AI Assessment, Flow 3B AI Classify Scope, future Layer 2 evidence review)

Each prompt: input variables, output format, tested behaviors, confidence handling

Note where HTML stripping is applied vs. raw output used

Update for any new prompts added in L1-B (rule rendering) or L2-C (evidence review)

Document prompt versioning approach

**Definition of Done**

Every current AI Builder prompt inventoried: Flow 1 AI Assessment, Flow 3B AI Classify Scope, Flow 4A AI Evidence Review (per L2-C01), Flow L1-B06 Plain-English rule rendering, plus any others surfaced during the audit

Per prompt: input variables, output format, tested behaviours, and confidence handling captured

HTML-stripping notes accurate per prompt: where the raw HTML output is consumed downstream, where the `Strip HTML For Form` action removes tags, and where neither applies

Prompt versioning approach documented so future prompt changes have a recorded procedure for archiving the prior version

New prompts from L1-B06 and L2-C01 added with cross-references back to their originating stories

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Labels: DOC · Depends on: L1-B06, L2-C01

## [DOC-12] Outcomes documentation backfill for completed L0 stories

**Status:** Not Started

**As a** Project Manager, **I want** "Outcomes" sections written for the ~58 completed L0 stories that don't yet have them, **so that** the project tracker captures real lessons-learned and decisions made during POC build, not just what was built.

**Acceptance criteria**

Each L0 story (L0-Z, A, B, C, D, E, F, G) has an "Outcomes" section in the source markdown using the standard format (10-12 outcomes, with sublines, bold inline emphasis, code spans where relevant)

Outcomes capture: insights gained, decisions made, dead-ends avoided, signals that reframed the problem, what would do differently in retrospect

Pace: a few stories per session, not all at once (deliberately gradual to maintain quality)

Tracked progress: count of L0 stories with outcomes vs. total

Final state: 100% of L0 stories have outcomes documented

**Definition of Done**

Every L0 story (L0-Z, A, B, C, D, E, F, G layers) has an Outcomes section in the source markdown using the standard format

Outcomes capture genuine retrospective material: insights gained, decisions made, dead-ends avoided, signals that reframed the problem, what would do differently

Progress tracked per session so the cumulative outcomes-coverage percentage moves forward visibly

Final state: 100% of L0 stories have Outcomes documented; the final coverage count recorded in the closing session's Outcomes note for this story

**Jira fields** · Status: Not Started · Type: Story · Points: 1.5 · Estimate: 12.0h · Labels: DOC

## [DOC-13] Schema doc reconciliation against tenant — column pass (BL-002a)

**Status:** Done

**As a** Project Manager (Ahmad), **I want** the canonical schema doc rebuilt from verified tenant truth, **so that** Sprint 10's table-creation work (L1-A01 onwards) builds against a reliable schema reference instead of a doc that drifted across the April 25 architecture pivot.

**Acceptance criteria**

Pre-reconciliation snapshot saved to `99_Archive/02_Production_Schema_v4_pre_BL002.html`

Schema doc rewritten as v4.1 from 18 tenant screenshots (IMG_1605–1623) covering all 12 tenant tables

All 218 columns documented with verbatim tenant logical names (including any tenant-side typos)

Forward-planned tables (Business Unit, Rule, Rule Version, etc.) segregated into a separate "Forward-Planned" section with creator-story pointers

Two previously-undocumented tenant tables added: Scope Classification and Import Cycle Process

Schema doc bug fixed: PBP logical name corrected from `pei_parentbusinessprocess` to `pei_businessprocess`

Schema doc embeds a "Maintenance Discipline" section with 5 rules, build pipeline reference, and change-risk table

Schema Currency Check post-reconciliation drift baseline established

**Definition of Done**

v4.1 HTML parses cleanly and renders correctly

Schema Currency Check baseline documented (147 pre → 85 post drift items, case-insensitive)

All 85 residual drift items triaged (categorized as forward-planned / prompt placeholder / plural set / real mismatch / regex partial)

4 supporting prompts updated with v4.1-aware references (Schema_Discipline, Tracker_Currency_Check, Tracker_Maintenance, Live_Update_Discipline)

Build pipeline source files (`/tmp/bl002_tenant_schema.py`, `/tmp/build_schema_v4_1.py`) preserved for future updates

`_File_Inventory.md` execution log entry written

BL-002 backlog entry updated to status `Promoted` with cross-references to follow-up stories

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC

## [DOC-14] Schema doc reconciliation — Control Procedure + Evidence tail columns (BL-002b)

**Status:** Done

**As a** Project Manager (Ahmad), **I want** the tail columns of Control Procedure and Evidence captured from tenant, **so that** the v4.1 schema doc covers all columns of all tables (currently 2 tables flagged "Tail Unverified").

**Acceptance criteria**

Tenant screenshots received for: Control Procedure columns S onwards (post-"SOX") and Evidence columns S onwards (post-"Source Evidence")

All revealed columns added to `/tmp/bl002_tenant_schema.py` with verbatim tenant names, types, required flags

Schema doc rebuilt; affected table cards flip from `Tail Unverified` badge to `Complete`

Schema Currency Check rerun; verify drift hasn't grown beyond the 85-item baseline (any new tenant columns should *reduce* drift, not increase it)

**Definition of Done**

Both tables marked `complete: True` in source dict

Schema doc rebuilt; both tables show `Complete` badge

Schema Currency Check shows drift at-or-below 85

Outcomes captured

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 0.5h · Labels: DOC · Depends on: DOC-13

## [DOC-15] Schema doc reconciliation — choice values + relationships (BL-002c)

**Status:** Not Started

**As a** Project Manager (Ahmad), **I want** every Choice column's value set documented (display name + numeric code) and every Lookup's relationship details captured (direction, cascade, schema name), **so that** flow expressions referencing choice values (e.g. `equals(..., 890920000)`) and relationship navigation (e.g. expand queries) have a single source of truth.

**Acceptance criteria**

Choice value definitions captured for every Choice column across all 12 tenant tables (e.g. Evidence Status: Pending=890920000, Approved=890920001, ...)

Relationship details captured for every Lookup column: direction (1:N, N:1, N:N), cascade behavior, schema name

Source dict (`/tmp/bl002_tenant_schema.py`) extended with `choice_values` and `relationships` keys per table

Build script (`/tmp/build_schema_v4_1.py`) extended to render two new sections per table card: "Choice Values" and "Relationships"

Schema doc rebuilt; new sections visible

Schema Currency Check Phase E (choice values) and Phase F (relationships) updated to reference these new structured fields rather than free-grep the docs

**Definition of Done**

All Choice columns documented with display + numeric pairs

All Lookups documented with direction + cascade + schema name

Schema doc rebuilt and renders correctly with new sections

Schema Currency Check Phase E + F updated and reflect verified data

Outcomes captured

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: DOC · Depends on: DOC-13

## [DOC-16] Schema doc reconciliation — investigate 5 real flow-doc mismatches (BL-002d)

**Status:** Not Started

**As a** Project Manager (Ahmad), **I want** the 5 real mismatches between active flow-build docs and tenant column names investigated and resolved, **so that** flow code documented in `App_Processing_Build_Guide.html`, `Definitive_Flow_Reference.md`, and related artifacts won't fail at runtime when run against the tenant.

**Acceptance criteria**

Each of the 5 distinct field-name mismatches investigated: which docs reference which name, whether the actual built flow uses tenant-correct or doc-version, what fix is needed

The 5 items: `pei_informationclassification` (vs tenant `pei_InformationClasification`); `pei_soxapplication` (vs tenant `pei_SOXRelevant`); `pei_ssoavailability` (vs tenant `pei_SingleSignOnAvailability`); `pei_parentbusinessprocessid` (vs tenant `pei_BusinessProcessId`); `pei_leanixapplicationid` — 16 file occurrences, requires sub-classification into anti-pattern callouts ("don't use this as match key" — keep) vs real flow code references (fix)

For each item, disposition: (a) doc updated to verbatim tenant name, (b) tenant column tested in Power Platform to confirm it is what's actually used by built flow, (c) anti-pattern callout left intact

Schema Currency Check rerun: drift drops below 82-item baseline by the count of items resolved

**Definition of Done**

All 5 distinct mismatches have a written disposition (committed in Outcomes), including the per-file sub-classification for `pei_leanixapplicationid`'s 16 occurrences

All "fix doc to match tenant" items applied

Schema Currency Check baseline updated downward to reflect resolutions

Outcomes captured

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 1.5h · Labels: DOC · Depends on: DOC-13

## [DOC-17] Decision Log v2 — interactive layout (Option C)

**Status:** Done

**As a** Project Manager (Ahmad), **I want** the Architecture Decision Log to match the design language of the tracker and schema doc (interactive filters, collapsible cards, TL;DR summaries), **so that** ADRs can be browsed efficiently as the project grows past 35 decisions and so adding a new ADR doesn't require hand-editing complex HTML.

**Acceptance criteria**

Decision Log rebuilt with tab-bar filters by Layer (L1/L2/L3/Cross), Domain (Schema/Workflow/Architecture/Source-Systems/Data-Lifecycle/Security/UI), and free-text search

Each ADR displayed as a collapsible card with ID, title, layer chip, domain chip, status badge, and TL;DR visible by default; full sections (Context/Decision/Alternatives/Consequences/Implementation) hidden until expanded

Hero stat-cards in the header: Total ADRs, Cross-cutting count, Layer 1 count, Layer 2+3 count, Most Recent ID

All 32 existing ADRs preserved with full content

All anchor IDs preserved (so external links to `#adr-001` etc. still work)

Clicking an external anchor link auto-expands the target card and scrolls to it

Build pipeline created: source data in `/home/claude/decision_log_build/adrs_extracted.json`, builder in `/home/claude/decision_log_build/build_decision_log.py` — adding a new ADR is now an edit to the JSON + rebuild rather than hand-edit of complex HTML

**Definition of Done**

File rebuilt and parses as valid HTML

All 32 ADRs render

Filters tested: clicking each layer chip shows correct subset

Anchor compatibility verified (e.g. `#adr-025` from a prior link still scrolls + expands)

Pre-rebuild snapshot archived at `99_Archive/01_Decision_Log_v1_pre_OptionC.html`

Build pipeline location documented in this story

Outcomes captured

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 1.5h · Labels: DOC · Depends on: ADR-035

## [DOC-18] Import Process Walkthrough — narrative deepening, prerequisites bookend, drift framing

**Status:** Done

**As a** Project Manager (Ahmad), **I want** the Import Process Walkthrough rebuilt so it tells the story honestly — what runs today, what's planned, how foundations are populated, how cycle closure handles unresolved data, and what makes the design defensible to auditors, **so that** the artifact is something I can hand to leadership, auditors, or new team members and have them understand both the architectural intent and the operational reality without me being there.

**Acceptance criteria**

Walkthrough rebuilt at `/mnt/user-data/outputs/EMS_Import_Process_Walkthrough.html`

Phase 4 (Reference Controls) and Phase 5 (Business Processes) reframed honestly: status pills changed from `implemented` to `partially implemented` / `partial` reflecting that data structures run today but value-creating consumers (completeness rollups, AI evidence reuse, classification mechanic) are planned

"Three reasons RCs live in the platform" replaced with project-grounded reasoning (atomic unit of completeness per L0-D06; first-class form section per MDA Forms Views Reference; semantic anchor for AI per ADR-041) — generic compliance-platform reasoning dropped

Phase 5 slimmed: removed three-card density problem; added explicit "BP updates are silent" + "Why silent" callouts; classification description deferred to Phase 6 where the terms are introduced

Concepts panel for ownership terms relocated from before-Phase-5 to before-Phase-6 (where the terms are first used); restructured as three nested concepts (Business Process / BP Ownership / BP Classification) per Option B; analogies dropped per Option 3

Synthesis panel added between Phase 6 and Phase 7: full 2×2 matrix of evidence patterns (Horizontal Common / Horizontal Per-App / BU Common / BU Per-App), with explicit honesty callout about which axis comes from BP classification (Phase 6) vs rule scope (Stage 5, post-import)

Prerequisites bookend at top of doc: 5 foundation panels covering BU Master List, BU Match Tokens, Rules Catalog Authoring, BU Org Unit Mapping, BP Classification

Bookend restructured into two sub-sections: **Part 1 — Authored ahead of time** (Master List, Match Tokens, Rules Catalog) and **Part 2 — Grown by the flow and admin together** (Org Unit Mapping, BP Classification); architectural distinction surfaced between true prerequisites and collaboration-boundary foundations

Part 2 intro carries the cycle-closure semantic: cycle never blocks on unresolved rows; resolved records get full treatment; unresolved get explicit "skipped" report at Stage 5 and surface for resolution before next cycle

BU Master List, BU Match Tokens, BU Org Unit Mapping panels rebuilt with new structure: role-based tag (no jargon), four-to-six-section lead (what / where / how it gets populated / how matching works / honest status today), collapsible depth (lifecycle, edge cases, ops metadata)

Match Tokens repositioned before Org Unit Mapping reflecting locked Tier 1 / Tier 2 architecture (ADR-038): tokens are primary resolver, Org Unit Mapping is deterministic fallback

"How the matching actually works" sections are accurate to the artifacts: exact-string equality on `Org Unit Display Name` for Org Unit Mapping; path tokenization on `/` then exact-token match for Match Tokens; both deterministic, both audit-friendly

Honest-status-today sections surface implementation reality: Tier 1 (Match Tokens) is dormant scaffolding (L1-A07 Phase C blocked by PA's 8-level nesting cap); every app currently pays Tier 2 cost; behavior is correct but not the design intent

Drift section at end of bookend covers 5 drift types between foundations: referential integrity (caught by design), semantic, coverage, lifecycle (partially caught), maintenance asymmetry — each with concrete examples and what catches them

Ongoing maintenance bookend at bottom of doc (teal, parallel structure to amber prereq bookend): Manual BU Overrides, Source File Pre-submission Discipline, Match Token Catalog Refresh

Phase 0 keeps the Risk Manager pre-submission flow; Phase 3 keeps the carry-forward concept; concepts panel #1 (Import Cycle / Staged Record / Carry-Forward) preserved before Phase 3

Status pills consistent across the doc: `implemented` (green) for fully-running, `partially implemented` (purple, new) for structure-built-consumers-planned, `planned` (orange) for not-yet-started

All five foundation panels link conceptually to the canonical Control Scope Reference page (`05_Building_Blocks/Control_Scope_Reference.html`) for the full architectural treatment

**Definition of Done**

Doc renders cleanly; all phase cards, concepts panels, synthesis panel, prereqs bookend, drift section, and maintenance bookend present

Prerequisites bookend reads as one cohesive section with two visually distinct sub-sections

Status discipline is uniform across the doc (no remaining lies-by-omission about what's implemented vs planned)

Outcomes captured

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Labels: DOC · Depends on: ADR-038, ADR-040, ADR-041, ADR-042, L1-A07

## [DOC-19] KDD-001 authoring — Foundation Platform Decision document for Tech Architecture Board

**Status:** Done

**As a** Project Lead / Architect (Ahmad), **I want** a formal Key Design Decision (KDD) document that defends the choice of native Microsoft Power Platform as the EMS foundation platform, framed as architectural commitment for the production build informed by POC and foundation findings, **so that** the EMS platform decision can be submitted to the organization's Technology Architecture Board as a governance artifact, with all the required template sections (Problem Statement, Motivation, Options Description, Decision Criteria, Implications, Assumptions, Constraints, Related Decisions, Outstanding Action Items, Final Decision, Participants), supported by side-by-side options comparison and a full EMS solution architecture diagram embedded inline.

**Acceptance criteria**

KDD file authored at `/home/claude/EMS_Project/09_Architecture_Decisions/01_KDDs/KDD-001_EMS_Foundation_Platform.html`

New `01_KDDs/` sub-folder created under `09_Architecture_Decisions/` as the canonical home for future KDDs

Document follows the organization's KDD template structure exactly — 13 sections including Cover, Problem Statement, Motivation, Options Description, Decision Criteria, Implications (5+ subsections), Assumptions, Constraints, Related Decisions, Outstanding Action Items, Final Decision, Participants

Two options compared in pros/cons format: (1) Native Microsoft Power Platform on the org's strategic stack [chosen]; (2) Modern-stack pro-code (Next.js + PostgreSQL + Azure AI Services + Azure Functions). No SaaS option — out of scope for this KDD per separate buy/build governance process

Decision Criteria table with 8 criteria: strategic alignment, workload fit, integration ecosystem, supportability, reversibility, AI capability headroom, operational continuity, cost (informational)

Side-by-side options comparison diagram (SVG) embedded showing both options with shared external interfaces and asymmetric interiors (platform inherits vs. pro-code builds)

Full EMS solution architecture diagram (SVG) embedded showing foundation source systems (Archer, LeanIX), target evidence sources (GitHub, ServiceNow, Qualys, SailPoint IIQ, Application APIs) marked as roadmap, ingestion layer, Dataverse operational data layer, user surface, AI stack, and strategic Microsoft cross-cutting services

Document framed as "architectural commitment for the production build, informed by POC and foundation findings" — not retrospective validation

Automated evidence consumption trajectory addressed as stated production trajectory (not committed scope of each specific integration)

Honest "Findings from foundation build informing the production architecture" subsection covering the 8-level nesting cap encounter, AI Builder HTML output handling, Manual Override telemetry noise, and pending ADR insertions

DLP not mentioned anywhere in the KDD (per architectural rule: DLP is environment configuration, not architectural constraint)

Copilot Studio acknowledged as part of strategic Power Platform AI stack (available for advanced use cases on production trajectory, not constrained to AI Builder)

KDD registered in Project Artifacts Registry under Governance category

Light theme, professional typography, print-friendly layout — designed for eventual Word doc conversion before board submission

**Definition of Done**

KDD renders cleanly as standalone HTML

Both diagrams embedded inline and visually clean

Document complies with all 13 sections of the organization's KDD template

Registered in Project Artifacts Registry (40 artifacts total)

Tracker rebuilt and shows KDD-001 in Project Artifacts tab

Outcomes captured

**Jira fields** · Status: Done · Type: Story · Points: 0.5 · Estimate: 4.0h · Labels: DOC · Depends on: L1-A07, ADR-038

## [DOC-20] Risk & Controls deep-dive demo — May 15 stakeholder demo authoring (deck + director's cut + tracking infrastructure)

**Status:** In Progress

**As a** Project Lead (Ahmad), **I want** a 45-60 minute risk-and-controls deep-dive demo package including a stakeholder deck (auditor-framed, no internal nomenclature) and a separate director's cut walkthrough document covering click-by-click demo path, talk track, recovery moves, and time-pressure cuts, **so that** the May 15 demo to a risk-and-controls / auditor audience can land its goal of getting them excited to invest in expanding EMS scope to more applications.

**Acceptance criteria**

Deck file authored at `98_Presentation/May15_Risk_Controls_Deep_Dive.html` following the captured deck design pattern (navy chrome, gold accent, 1280×900 canvas, auto-scale, keyboard nav)

Director's cut companion authored at `98_Presentation/May15_Demo_Directors_Cut.html` — separate doc with the click-by-click instructions, talk track, recovery moves, and time-pressure cuts

Deck content respects user constraint: **no internal nomenclature anywhere** — no workflow names, no story IDs, no ADR numbers in slide-visible content. Auditor language only (controls, evidence, scope, applicability, audit traceability, lines of defense, business processes)

Slide structure: Cover → Audit-readiness problem → Vision (continuous evidence) → The model (controls × applications × BUs × cycles) → Scope as rule property (not judgment) → Capability map → Evidence lifecycle + chain of custody → Defensible AI assistance → What's working today (demoable surface) → Live demo anchor slide → Trajectory (continuous evidence, engagement workspace, technical-source ingestion) → Investment case (position: expand scope to more apps) → Closing

Investment case takes a position: expand scope to more applications (per user direction)

New `📺 Demos` category created in Project Artifacts Registry; May 15 demo registered as first entry in that category

This DOC-20 story created in tracker to provide planning visibility

Speaker notes on every slide — verbatim talking points, not "I would explain here" placeholders

Demo path uses only what's actually demoable today (end-to-end import cycle: source-system pull → automatic applicability derivation → evidence collection point creation → AI-assisted assessment → review). No pretending features exist that don't.

Director's cut includes a "what to skip if time runs short" section so the demo can compress to 30 min or expand to 60 min in real time

Director's cut includes "recovery moves" — what to say if Flow 1 fails to run, if Dataverse is slow, if a record doesn't appear where expected

**Definition of Done**

Both files render cleanly in browser

Slide count matches registered slide_data entries

HTML parses without errors

Speaker notes panel works

Demo path tested mentally against current build state — every claim is verifiable in the actual environment

Registry updated to reflect both files

Outcomes captured AFTER the demo (audience reaction, questions asked, decisions made, follow-ups committed) — outcomes section is empty pre-demo, populated post-demo

**Jira fields** · Status: In Progress · Type: Story · Points: 0.5 · Estimate: 4.0h · Labels: DOC · Depends on: DOC-19, KDD-001

## [DOC-21] KDD-001 currency review + LLM prompt for §§1-7 edits

**Status:** In Progress

**As a** Project Lead (Ahmad), **I want** a structured review of KDD-001 against project build reality plus an actionable LLM prompt for surgical text edits to sections 1 through 7, **so that** the KDD can be brought into honest alignment with what's actually built (versus what's planned) before it goes to LARB / Technical Architecture Board.

**Acceptance criteria**

Section-by-section audit of KDD-001 §1 through §9 against the tracker, ADRs, and userMemories — flagging in-line vs. drift items

Specific overclaim pattern identified: KDD reads as if foundation is built, reality is foundation is in flight (L1-A 9/16, L1-B 0/14, L1-C 0/6, L1-D 0/11, L2 0/31, L3 0/27)

LLM prompt drafted covering 11 specific edits (find-text / replace-text format) for §§1-7 only

Each edit anchored to a quoted passage; no edits that require LLM invention

ADR references included only where ADRs are anchored (023, 025, 033) — drafted ADRs (045, 046) referenced with flag

Architecture diagram review separately covered: structure correct, "MANULIFE USER DOMAIN (ENTRA ID)" label needs masking decision before external share

Three paths offered for diagram masking: (a) edit source if accessible, (b) edit through Figma MCP if there, (c) rebuild as project-tree-owned SVG

**Definition of Done**

DOC-21 created in tracker (this entry)

Audit notes captured in this story's Outcomes (chat transcript is the substantive record; this story captures the meta)

LLM prompt artifact saved somewhere durable — either inline here or registered as a separate artifact

Architecture diagram decision recorded post-handover

**Jira fields** · Status: In Progress · Type: Story · Points: 0.25 · Estimate: 1.0h · Labels: DOC · Depends on: DOC-19

# PRODUCTION CUTOVER (~10 hrs)

0 of 4 done

## [CUT-01] Production environment provisioning

**Status:** Not Started

**As a** Builder, **I want** a production Power Platform environment, **so that** I can deploy.

**Acceptance criteria**

Production environment created with appropriate licensing

DLP policies configured

Solution architecture deployed

Smoke test passes

**Definition of Done**

Production Power Platform environment provisioned and named per convention with appropriate licensing applied

DLP policy applied to the environment and verified by attempting a forbidden connector use (failure observed as expected)

Managed solution imported successfully with no missing dependency warnings; solution import log archived

Smoke test passes: one sample rule authored, one Cycle stub created, Stage 1 detection runs without error against a minimal seeded input

Environment configuration captured in the operational runbook (INF-B06) so re-provisioning is a runbook step

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Labels: CUT

## [CUT-02] Production cutover: clean start (no data migration)

**Status:** Not Started

**As a** Builder, **I want** production to start clean — test data purged, no legacy carry-over, **so that** Cycle 1 produces the first real applicabilities with no contamination.

**Acceptance criteria**

All test/POC data purged before go-live (per BL-087); zero residual test rows confirmed

Rule engine produces Cycle 1 fresh in production (first real applicabilities)

No legacy/synthetic provenance carried into production

Rollback plan documented

**Definition of Done**

All test / POC data purged from the production environment with zero residual test rows confirmed via a row-count query per table (per BL-087 expectation: no carry-over)

Cycle 1 produced fresh in production from the rule engine with the first real applicabilities written; cycle metadata shows clean provenance (rule version, source-system snapshot timestamps)

No legacy or synthetic provenance carried into production — verified by auditing the Source field on a sample of new records and by absence of test-marker values in the production cycle

Rollback procedure documented and dry-run tested in a non-prod environment: the rollback restores a known-clean state within the documented time target

Cutover communication sent to stakeholders per the template; acknowledgements captured

**Jira fields** · Status: Not Started · Type: Story · Points: 0.5 · Estimate: 3.0h · Labels: CUT · Depends on: L1-B15, L2-D05

## [CUT-03] UAT cycle

**Status:** Not Started

**As a** Stakeholder, **I want** to validate the system in production-like conditions, **so that** I'm confident before go-live.

**Acceptance criteria**

Risk Manager runs a complete cycle

Control Owner uploads sample evidence

Auditor reviews engagement

Sign-offs collected

**Definition of Done**

Risk Manager runs a complete cycle end-to-end in production: Stage 1 → Stage 6, all gate ticks captured, no flow failures

Control Owner uploads sample evidence against a generated Applicability; evidence lands in SharePoint and the Dataverse snapshot matches per ADR-025

Auditor reviews an engagement that consumes the produced Applicabilities and Evidence; engagement findings authored without privilege errors

Sign-off form signed by all three personas (Risk Manager, Control Owner, Auditor) capturing the cycle ID, evidence sample ID, and engagement ID for traceability

UAT result archived alongside the cycle artefacts so future audits can trace the production-readiness attestation

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: CUT · Depends on: CUT-01, CUT-02

## [CUT-04] Go-live + rollback plan

**Status:** Not Started

**As a** Builder, **I want** documented go-live and rollback procedures, **so that** the cutover is controlled.

**Acceptance criteria**

Step-by-step go-live runbook

Rollback to POC environment in < 4 hours if needed

Communication plan for users

**Definition of Done**

Step-by-step go-live runbook committed under the documentation path covering pre-go-live checks, the cutover sequence, post-cutover validation, and the rollback decision point

Rollback procedure validated to complete within the documented < 4-hour target via a fresh dry-run in a non-prod environment that mirrors production shape

User communications sent on the cutover schedule per the approved template with acknowledgements captured from the named distribution

Post-go-live monitoring window agreed and the on-call ownership for that window documented so any escalation has a named owner

**Jira fields** · Status: Not Started · Type: Story · Points: 0.25 · Estimate: 2.0h · Labels: CUT · Depends on: CUT-03

# STAKE — Stakeholder Materials (~6 hrs, evergreen — periodic refresh)

3 of 3 done

## [STAKE-01] EMS Technical Review v3.0

**Status:** Done

**As a** Builder presenting to governance and architecture audiences, **I want** a current technical review document that reflects the production-ready architecture, the ownership model, Evidence Reuse, freshness design, and the capability roadmap, **so that** governance reviews, architecture committees, and security/compliance audits can engage with EMS at the right depth without me re-explaining the system from scratch.

**Acceptance criteria**

Foundation + Roadmap architecture diagram (KDD-derived, redrawn as clean SVG)

Five-stage cycle covered as Layer 1

Engagement scenarios covered as Layer 2 (Happy Path, Gap, Edge Case)

BU Classification covered as first-class section (BU-Owned, Horizontal, Unresolved)

Evidence Reuse covered with all three framings

Evidence Freshness covered (rule engine + open question)

Capability swimlane roadmap (Now / GA / +6mo / +12mo)

No internal references (no hours, story IDs, ADR numbers, internal terminology)

**Definition of Done**

1100+ line single-file HTML document delivered at `05_Building_Blocks/04_Demo_Materials/EMS_POC_Technical_Review_v3.html` in dark-ink theme with 12 sections from problem statement through closing

Visual-heavy build: layered KDD-derived architecture diagram redrawn as clean SVG with Foundation/Roadmap badges, end-to-end system-context diagram, and a 2×2 four-shape evidence collection matrix

Six-stage rule-driven cycle authored as Layer 1 (Detect Changes / Verify App Data / Verify CP Data / Confirm Rules / Review Output / Confirm Cycle); engagement scenarios as Layer 2 (Happy Path / Gap / Edge Case); Evidence Reuse covered in all three framings; rule-based Evidence Freshness covered with the snapshot-isolation vs auto-flag-stale open question preserved; capability swimlane roadmap (Now / GA / +6mo / +12mo) across four tracks

BU Classification authored as a first-class section using BP-ownership × Collection Scope as orthogonal primitives composing into Horizontal Common / Horizontal Per-App / BU Common / BU Per-App; old Common / Hybrid / Application-Level labels noted parenthetically as the current POC interface's scheme that retires when the rule engine ships

Two-state framing (original 5-stage POC interface in production today vs locked 6-stage architecture as the next major build, with backend BU-ownership resolution noted as already live) carried throughout so a reader is never confused about what is current versus next

Zero internal references throughout — no story IDs, no hours, no ADR numbers, no flow action counts — acceptance criterion enforced line-by-line

Currency Check prompt authored at `SYSTEM_PROMPT_POC_Artifacts_Currency_Check.md` with seven check items including Check 7b (UI/backend gap framing) and Check 7c (four-pattern model regression watch) so future refreshes do not drift

Project Artifacts Registry (.md + .html) updated: v2.0 originals marked Historical, v3.0 marked 🟢 Active (Current)

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: STAKE · Labels: STK, STAKE

## [STAKE-02] EMS Narrative v3.0

**Status:** Done

**As a** Builder presenting to executive and business audiences, **I want** a current narrative document that frames EMS as a business capability — focused on the operational shift, not on the technical architecture, **so that** executive committees, sponsor briefings, and board-level summaries can absorb the EMS pitch without engineering depth and act on it.

**Acceptance criteria**

The Problem framed in business language (not technical pain)

Three shifts: scattered → connected, projects → queries, files → capital

Simplified five-layer architecture diagram (no plane sub-splits, no component logos)

Ownership Model framed as accountability, not classification

Evidence Reuse framed as compounding asset

Capability swimlane roadmap (Now / GA / +6mo / +12mo) — simplified labels

"What This Unlocks" closing section (by stakeholder)

No internal references

**Definition of Done**

Single-file HTML document delivered at `05_Building_Blocks/04_Demo_Materials/EMS_POC_Narrative_v3.html` in light paper theme, story-driven, ~30 KB

Sections shipped per AC: cover, problem framing in business language, three shifts grid (scattered → connected / projects → queries / files → capital), simplified five-layer architecture diagram (How people work / What thinks / What moves / What's recorded / What's reported — no plane sub-splits, no component logos), Ownership Made Explicit, Evidence Reuse, Roadmap, What This Unlocks

Ownership Made Explicit section closes with one paragraph naming the cross of two questions (ownership × per-app expansion) into four observable shapes — propagating the four-pattern model into executive language without listing the four labels

"How It Works" paragraph carries the two-state framing (5-stage POC interface today, 6-stage rule-driven locked architecture next) so a reader who has also read the Technical Review sees consistent messaging across documents

Closing "What This Unlocks" section breaks the value by stakeholder — risk function / control owners / auditors / organization

Zero internal references throughout, stakeholder-facing language only (acceptance criterion enforced line-by-line)

Project Artifacts Registry entry added

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: STAKE · Labels: STK, STAKE

## [STAKE-03] EMS Live Demo Guide v3.0

**Status:** Done

**As a** Builder running a live EMS demo, **I want** a current presenter's runbook with time-keyed steps, exact "say this / do this / expect this" instructions, and pre-positioned browser tabs, **so that** every live demo runs cleanly, hits the same beats, and ends on the Evidence Reuse moment without improvisation.

**Acceptance criteria**

Meeting timeline (T+00:00 to Q&A)

Browser tab map (pre-positioned, ordered)

Pre-demo preparation stage

The opening (control inventory contrast)

Trigger sync + pivot to deck

Return + AI summary moment

Stages 1-5 walkthrough with Evidence Reuse moment at Stage 5

Wrap + Q&A common questions

Demo language abstracted (no "Flow 1", "Flow 4A", action counts, etc.)

**Definition of Done**

Single-file HTML presenter's runbook delivered at `05_Building_Blocks/04_Demo_Materials/EMS_POC_Demo_Guide_v3.html` in light paper theme, ~47 KB

10 sections shipped per AC: meeting timeline (T+00:00 through Q&A), browser tab map (10 ordered tabs), Stage 01 pre-demo preparation, Stage 02 opening (control inventory contrast), Stage 03 trigger sync, Stage 04 return + AI summary + UI/backend framing moment (Step 4.4), Stages 05–09 walkthrough of cycle stages 1–5 with the Evidence Reuse moment at Stage 5, Stage 10 wrap + Q&A

Two-state UI/backend gap callout placed before the timeline so the presenter holds the framing throughout; explicit ~50-word script moment at Step 4.4 acknowledging the 5-stage POC visible in the MDA vs the 6-stage locked architecture in the deck

Four-pattern model in script at Step 4.4 — frames today's three labels (Common / Hybrid / Application-Level) as "a useful approximation that conflated two questions" and previews the four observable shapes that emerge after the rule engine ships

Known Issues callout explicitly names the New / exists-but-never-reviewed labeling contradiction (BL-020) and points the presenter at the new Step 1.0 cleanup

Step 1.0 — Pre-baseline cleanup procedure added: filter Apps and CPs on `Reviewed = false AND Active`, decide per-record (keep with Reviewed=true vs hard-delete), run the source-sync once to verify a clean Staged Records sub-grid

Q&A script item added at end for the New/exists question — ~50-word delivery prepared for graceful in-meeting handling

Demo language fully abstracted throughout — no flow names, no action counts, no story IDs ("the sync" / "the cycle-close automation" replace internal references); acceptance criterion enforced line-by-line

May 29 Currency Check pass corrected four residual abstraction leaks in presenter prep sections (BL-020 and Flow 1 references abstracted to "documented labeling bug in the backlog" and "source-sync flow"); remainder verified against current state, sub-1% content change → no version bump

Project Artifacts Registry entry added

**Jira fields** · Status: Done · Type: Story · Points: 0.25 · Estimate: 2.0h · Epic: STAKE · Labels: STK, STAKE
