# EMS — A Guide to the System

### Everything a new team member needs to understand EMS, in plain language

*Written in the voice of Horos, the team's business analyst. No codes, no shorthand, no internal references — just what EMS is, why it exists, how it works, and how its most important pieces actually behave. It reads in about half an hour.*

**What's in this guide.** **Part One** is the full story — what EMS is and how it works, end to end. **Part Two** is a closer look at the three things people always want to see next: how a rule is written, what the monthly screen feels like to use, and how an audit is set up. **Part Three** is the complete map of everything EMS does, so the whole team shares one picture of the system.

---

# Part One — The Full Story

## The one-sentence version

EMS is the system that keeps a large organization **permanently ready to prove it follows its own rules** — by automatically working out which rules apply to which pieces of software, gathering the proof, and keeping that proof current and audit-ready, all the time, in the background.

If you remember nothing else: **EMS is a standing readiness system for compliance.** Not a once-a-year scramble. A quiet machine that keeps the house in order every single month, so that whenever someone comes to inspect, the answer is already there.

## Why it exists — the problem in human terms

Picture a big company. It runs hundreds of different software applications — for payroll, for email, for customer records, for finance, for everything. Separately, it has a long list of **information-security controls**: the security rules it must obey. Some come from law, some from regulators, some from its own security policy. "Customer data must be encrypted." "Privileged access must require multi-factor authentication." "User access must be reviewed every quarter." There are hundreds of these too.

Now the hard part. Every rule does not apply to every application. A rule about securing a data centre's doors doesn't apply to a cloud service nobody can walk into. A customer-data-encryption rule applies to the systems that store sensitive information, but not to a public marketing page. So somebody has to answer, over and over: *which rules actually apply to which applications, and what proof do we need to show we're following them?*

If you do that by hand, the numbers are brutal. Hundreds of applications multiplied by hundreds of rules is **tens of thousands of possible combinations** — and only a fraction of them are real and relevant. The old way left one overworked person (call them the risk manager) to look at that entire field every period, decide what was in scope, chase dozens of busy colleagues for evidence, nag the ones who hadn't replied, and then assemble it all into a tidy package whenever an audit loomed. It was slow, it was error-prone, and it had to be redone again and again because the software list and the rules both kept changing.

**EMS takes that manual, repetitive, error-prone job and turns it into something steady, consistent, and mostly automatic.**

## What EMS actually is

EMS sits in the **middle** of two things the company already has:

- **The list of rules** — the official catalogue of every control the organization must follow. (Another system owns this list; the company keeps it in a tool called Archer.)
- **The list of software** — the master inventory of every application the company runs, with details like who owns it, how critical it is, and how it's hosted. (Another system owns this too; the company keeps it in a tool called LeanIX.)

EMS does **not** own either list. It never changes them. It simply **reads from both** and lives at the point where they meet. Its whole job is to answer the question those two lists imply but neither one answers on its own: *given these rules and this software, what must we prove, have we proved it, and is the proof still good?*

Think of EMS as a meticulous **records office** standing between the rule-makers and the software owners — keeping a live, trustworthy ledger of who owes what proof, what's been provided, what's been approved, and what's about to go stale.

It's built as a business application on the company's standard low-code platform, so it looks and feels like the other internal tools people already use — forms, lists, dashboards, and an inbox of tasks.

## The big idea that makes it work: rules instead of hand-sorting

Here is the cleverest part, and the thing most worth understanding.

The old way was to look at every rule-and-application combination, one at a time, every period, and decide by hand whether it applied. Unworkable at scale.

EMS works differently. The organization writes a set of **plain-English rules once**, describing *when* a control applies — something like: "This control applies to any application that stores sensitive customer data." The system then applies those rules **consistently and automatically** to every application, every period, and produces the list of what's in scope — without a person re-sorting the whole field each time.

Two things make this trustworthy rather than mysterious:

**The rules are written as readable statements, not buried in program code.** This matters enormously for audits. An auditor can be shown, in plain language, the exact rule that decided "this control applies to that application." Nobody has to take a programmer's word for it. The decision is legible.

**Every decision is frozen and kept.** Each time the system runs, it takes a snapshot of the rules it used and the answers it produced, and stores that snapshot permanently. So a year later you can still see exactly which rule, in exactly which form, decided exactly what — even if the rules have since changed.

This is the heart of EMS. Everything else serves it. (Part Two shows exactly how one of these rules is written.)

## The steady rhythm: the monthly heartbeat

EMS runs on a regular cycle — typically once a month. Each cycle walks through a handful of clear steps, and a human approves each step before it moves on. In plain terms, a cycle goes like this:

First, **notice what changed.** The system pulls in the latest version of the rules list and the software list, and works out what's new, what's been updated, and what's been removed since last time. It even writes a short summary so a person can see at a glance what moved.

Then, **sort out ownership** — make sure each affected application and each affected rule is correctly attached to the right part of the business, flagging anything it can't place so a human can resolve it.

Then the **risk manager reviews the rules in plain English** and confirms they're right for this period. Then they **review the results** the system produced — the list of what now applies and what proof is therefore required — and look over anything unusual.

Finally, there's a deliberate **sign-off**: a small ceremony that closes the cycle, locks in the results, and sends out the notifications telling people what they owe.

The striking number here: in steady state, this takes the risk manager somewhere around **fifteen to twenty minutes a month** — down from what used to be hours of grinding work. The system does the heavy sorting; the human does the judging and approving. (Part Two walks through exactly what that monthly screen looks like to use.)

One firm principle runs through every cycle: **once a step is approved, it can't be quietly un-approved.** If something turns out to be wrong, you don't secretly rewrite history — you either cancel the cycle and start fresh, or you correct it openly in the next period. That discipline is what makes the whole record trustworthy.

## The life of a single piece of proof

When the cycle decides a control applies to an application, it creates a request for **evidence** — the proof that the control is actually being followed. Each piece of evidence then travels a one-way path, and it's worth knowing that path because it's the day-to-day texture of the system:

It begins as a **gap** — we know we need this proof, but nobody has provided it yet. When the responsible person uploads a document, it becomes **pending** — provided, but not yet checked. The risk manager reviews it and either **approves** it, at which point it becomes the official record, or sends it back as still missing, with a reason. Over time, proof gets stale, so every piece has an expiry; when that date passes, it's marked **expired** and needs refreshing. And if a control stops applying, its evidence is quietly marked **no longer required** — but never thrown away.

A few details make this trustworthy rather than just tidy:

**People don't stamp the records — the system does.** A person clicks "approve" or "upload," but the actual marking of the official status is done by the system itself, behind the scenes. That sounds like a technicality; it's actually the backbone of trust. It means every status on every record can be traced to an automatic, consistent action rather than someone typing directly into the ledger.

**Nothing is ever deleted, and the past never changes.** The actual documents live in a secure shared library; the records office keeps the details, a link to the file, and — crucially — a **frozen photograph** of what the rule and the application looked like at the moment the proof was approved. Even if everything changes later, you can always see exactly what was true at the time. History is preserved, not overwritten.

**The system spots proof you already have.** A built-in assistant notices when a document already on file would satisfy a new request, and offers it up for the risk manager to accept — so the same evidence isn't chased twice. It only steps in when there's a genuine candidate, to keep it sensible and low-cost.

## The two rhythms, and why they're kept apart

There are really two tempos in EMS, and a lot of the design is about keeping them from interfering with each other.

The **quiet, continuous one** is everything above: the monthly heartbeat that keeps evidence flowing and current, forever, without anyone having to actively manage it.

The **occasional, intense one** is an **audit** — or a regulatory review, or an assessment. These are events, with deadlines and findings. When one begins, it draws on the evidence the quiet rhythm has been steadily gathering.

The key rule between them: **the audit consumes the proof; it never drives the gathering.** An audit looks at what's already there and shows where the gaps are. And the moment an audit begins, it takes its own **frozen snapshot** of what's in scope. After that, anything that changes in the wider system flows into future months — never sideways into the audit already under way. The ground never shifts under the auditor's feet, which is exactly the nightmare a good audit needs to avoid. When the audit finishes, it produces a summary and records its findings — but it only ever **observes** the evidence; it never edits it. (Part Two shows exactly how an audit is set up.)

## The people in the story

EMS is shaped around real roles, and each one sees a different slice of it:

- **The risk manager** is the central character — the person who runs the monthly cycle, checks the rules, approves or rejects evidence, and signs off. Each one looks after a particular part of the business.
- **The control owner** is the colleague responsible for a specific control. They're the one who receives the request and uploads the proof.
- **The control tester** validates that a control is genuinely operating — the hands-on check behind the evidence, distinct from the owner who supplies it.
- **Administrators** are the small handful of people who set up and maintain the rules and the underlying configuration.
- **Auditors** are brought in for a specific review and can see only the records that belong to their review — nothing else.
- **Reviewers and leadership** get read-only views: some browse the catalogue, others watch the high-level dashboards and summaries.
- **The system itself** is the quiet participant — the automated hand that does the actual record-keeping, so that no human has to be trusted to write the official status directly.

## Why it's worth it — what "good" looks like

When EMS is doing its job, the organization is **always ready** instead of perpetually scrambling. Audit preparation stops being a fire drill and becomes a matter of opening a view. The risk manager's monthly burden shrinks from hours to minutes. The decisions about what applies are **consistent and explainable** — the same rules applied the same way every time, and readable by anyone who asks. The trail is **complete and tamper-resistant**, because nothing is deleted and every status change is automatic and attributable. And effort isn't wasted re-collecting proof the company already holds.

In short: less manual grind, fewer mistakes, and a calm, defensible answer ready at any moment for the question "can you prove it?"

## The edges — what EMS deliberately does *not* do

Knowing a system's boundaries is the fastest way to understand it, so here they are plainly:

It **does not own the rules or the software list.** It reads both from elsewhere and never writes back to them. It is the meeting point, not the source.

It **does not decide policy.** It faithfully applies rules that people have written; it doesn't invent what the organization should require.

It **does not let anyone quietly rewrite the past.** Approvals can't be secretly undone; corrections happen openly, going forward, as fresh records.

It **does not let an audit change the evidence.** Audits look; they never edit.

And it **does not finalize anything important without a human.** The system does the sorting and the record-keeping, but a person reviews and approves at every meaningful gate. The machine proposes; the human disposes.

## Going further: gathering the proof automatically

For much of the evidence, EMS doesn't wait for a person to fetch and upload it — it **gathers the proof directly from the systems that already produce it.** A great deal of security proof isn't really a document someone has to go and make; it already exists, as a record, inside another system the company already runs. EMS connects to each of these and reads the proof continuously:

- **GitHub**, the code system — whether code changes were reviewed and approved before they shipped, what the branch-protection rules are, and who signed off on each deployment;
- **ServiceNow**, the IT service-desk system — the change records, the incident fixes, and the access requests;
- **Qualys**, the vulnerability scanner — the vulnerability and configuration-scan findings for each system;
- **SailPoint IdentityIQ**, the identity-governance system — who has access to what, whether that access was certified, the role assignments, and the segregation-of-duties checks;
- and the **applications themselves**, through their own interfaces — configuration snapshots, audit logs, and transaction samples.

EMS reads that proof straight from those systems instead of asking a person to fetch and upload it each time. (Some, like GitHub and ServiceNow, plug in directly; others, like Qualys and IdentityIQ, whose data is larger and more involved, are brought in through a small helper layer first — but to the people using EMS, it all simply arrives.) People's role becomes that of the **exception-handlers** — stepping in where automation can't reach, and reviewing what the system gathered for them. That's the full strength of "always ready": a system that doesn't just **organize** the evidence people provide, but **continuously collects** the evidence itself.

**That's the whole picture.** Once you can see those edges, everything you'll hear in your first meetings has a place to sit. Three questions usually come next — and they're worth answering properly, because they're where the system's character really shows.

---

# Part Two — A Closer Look

## 1. How exactly is an applicability rule written?

Remember the big idea: instead of a person deciding, for every control and every application, whether the control applies — the organization writes a set of **rules once**, and the system applies them consistently. So what is a rule, really?

**A rule is a short, readable sentence in three parts:** a *condition*, a *verdict*, and a *reach*.

- The **condition** describes what an application looks like, using facts the system already knows about it — the kind of thing the application inventory records. Is it internet-facing? Does it store sensitive customer data? Is it business-critical? Does it use single sign-on? Does it require penetration testing? There are about fifteen of these known facts, and a condition is just a combination of them.
- The **verdict** is the simple outcome: *this control applies* (or *does not apply*).
- The **reach** says how widely the evidence is needed: once **centrally** for the whole organization, or once **per application** — and, when it's per application, whether that's every application or only those owned by the part of the business that owns the control.

Put together, a rule reads almost like plain English. For example:

> *"When an application stores sensitive customer data **and** is reachable from outside the company network, the quarterly access-review control applies to it — and we need that evidence once for each such application."*

That single sentence is a rule. The condition is "stores sensitive customer data and is internet-facing," the verdict is "the access-review control applies," and the reach is "once per application."

**Two more dials make rules work together cleanly.** Real compliance isn't one rule — it's many, and they can overlap. So each rule also has:

- An **order**. Rules are checked in a set sequence, lowest number first. This lets you write a broad rule and then a narrower one that refines it.
- A **"final" switch**. You can mark a rule so that once it decides, no later rule can override it for that application. This is how a specific exception can stop a broad rule cleanly — *"this control applies to everything… except, finally, for retired applications, it doesn't."*

That combination — order plus a "final" switch — is deliberately simple. It keeps the rules readable and predictable instead of turning into a tangle of nested "if this and that but not the other" logic that nobody could audit.

**Three things make rules trustworthy, not mysterious:**

- **Every rule is shown in plain English.** Whoever reviews the rules each month reads them as sentences, not as code. An auditor can be handed the exact rule that decided "this control applies to that application" and read it for themselves.
- **The system keeps a frozen copy of every rule it used.** When a rule decides something, the system saves the exact wording of the rule at that moment. So even if the rule is reworded next year, you can always see precisely what was true when the decision was made.
- **Rules are versioned, never quietly changed.** A rule is first written as a draft, then switched on. Editing a switched-on rule saves a new version and keeps the old one. Rules are retired by switching them off — never deleted. The history is always there.

**What happens when a fact is missing?** Applications sometimes have blanks — the inventory doesn't always know whether an app is internet-facing, say. The system is deliberately careful here: rather than guess, a rule that depends on a missing fact is **flagged as an error for that application** and set aside, so a person notices the data gap instead of the system silently making the wrong call.

## 2. What does the risk manager's monthly screen look like?

Once a month, the risk manager does the single most important recurring job in EMS — and they do almost all of it from **one screen**. Here's what using it feels like, start to finish.

**You open it, and the first thing you see is a plain-language summary of what changed.** The system has already pulled in the latest version of the controls list and the application inventory, worked out what's new, what changed, and what's gone, and written you a short briefing — in sentences, not spreadsheets. *"This month: four new applications, two retired controls, one application moved to a new part of the business."* You're never staring at raw data wondering what moved.

**Then the screen walks you through six checkpoints, in order.** This is the heart of the design: you don't get the whole thing at once, you move through it one approved step at a time. Each checkpoint shows the relevant items in a list right below it, and each ends with an approval you click before the next opens:

1. **Acknowledge what changed.** You read the summary and confirm you've seen it.
2. **Confirm who owns the changed applications.** For any application that moved or arrived, the system has worked out which part of the business owns it; you confirm, and anything it couldn't place is flagged for you to sort out.
3. **Confirm who owns the changed controls.** The same check, for controls.
4. **Review the rules.** You read the active rules — in plain English — and confirm they're right for this period. (You're reading here, not editing; rule changes happen separately.)
5. **Review the results.** This is the substance: the system has applied the rules and produced the list of what now applies and what evidence is therefore needed. You look it over, pay attention to anything unusual, and confirm.
6. **Sign off.** A deliberate final step — a small ceremony — that closes the month, makes everything live, and sends out the evidence requests to the people who owe them.

**Most months, this takes about fifteen to twenty minutes.** The system does the heavy sorting; you're doing the judging and approving. The two longer steps are reviewing the rules and reviewing the results; the rest are quick confirmations.

**A few things about how the screen behaves are worth knowing:**

- **It won't let you skip ahead.** You approve each checkpoint before the next becomes available — the order is the discipline.
- **Approvals can't be quietly undone.** Once you've confirmed a step, it stays confirmed. If something's genuinely wrong, you don't secretly reverse it — you cancel the whole month's cycle and start a clean one. That's deliberate: it's what keeps the record trustworthy.
- **You're not the one who stamps the records.** You click "confirm," but the system itself writes the official statuses behind the scenes. It feels seamless, and it means every change is traceable to an automatic, consistent action rather than a person typing directly into the ledger.
- **If nothing changed at all**, the screen recognizes that and can quietly close the month for you — no busywork.

## 3. How does an audit get set up and scoped?

This is the moment everything else exists to serve. An **audit** — or a regulatory review, or an assessment; these are all kinds of the same thing — is how an outside or internal reviewer comes to check that the organization is following its controls. Here's how one is set up, in plain terms.

**Someone starts the audit by saying what it covers.** That's the setup: you define the scope — *which* controls are in, *which* applications, *which* part of the business, and *for what time period*. An audit of access-control evidence across the customer-facing systems for the last quarter is a different scope from a security review of a single newly-onboarded application. The audit is shaped by that definition.

**The instant the audit is activated, its scope freezes.** This is the most important idea in the whole audit side. From that moment, anything that changes in the wider system — a new application, a reworded control, a fresh piece of evidence — flows into *future* months only. It never reaches sideways into the audit already under way. The reviewer is looking at a stable, fixed picture; the ground never shifts under their feet mid-review. (Without this, you'd get the nightmare every auditor dreads: the data moving while they're auditing it.)

**The audit then simply reads the evidence that's already there.** It does not go and collect anything — remember, gathering happens continuously in the background, all the time. The audit consumes what's already on file. It pulls together every relevant piece of evidence, organized so the reviewer can see coverage at a glance, and — just as importantly — it highlights the **gaps**: applicable controls with no evidence yet, evidence that has expired, applications with incomplete coverage. The whole point is to make "are we covered?" answerable in a moment instead of a scramble.

**The audit only ever looks — it never changes the evidence.** It can record its own findings on itself, and flag follow-up actions, but it cannot alter, approve, or delete the underlying proof. The evidence is the organization's record; the audit observes it.

**Only the right people can see it.** Each audit has its own assigned members, and a reviewer assigned to one audit sees only that audit's contents — not everything in the system. So an external auditor brought in for one review is walled into exactly what they're meant to see.

**When it's done, the audit produces a summary** — a packaged view of what was in scope, what was covered, and what the findings were — and closes.

---

# Part Three — Everything EMS Does

This is the complete map of EMS's capabilities — one picture of the whole system, grouped by the part of the work each one serves.

### The monthly engine

- **Automatic monthly synchronization.** Every month, EMS pulls the latest controls and applications from the two source systems and detects what's new, what changed, what was removed, and what came back.
- **Change triage.** It works out which changes actually affect evidence (and so need a human's review) versus cosmetic ones (updated quietly), so the risk manager is never flooded with noise.
- **The monthly change summary.** A built-in assistant writes a short, plain-language briefing of what moved this month, and flags anything unusual.
- **Ownership resolution.** It automatically works out which part of the business owns each application, control, and business process — and flags anything it can't place for a person to decide.
- **The rule engine.** Writing, switching on, versioning, and applying the rules that decide which controls apply to which applications — the heart of the whole system (Part Two walks through how a rule is written).
- **The guided monthly cycle and its safeguards.** The six-checkpoint monthly review, with its no-skip ordering, its can't-be-undone approvals, and the built-in gate-keeper that blocks a checkpoint that isn't genuinely complete.
- **The risk manager's monthly screen.** The single screen where the whole monthly review happens, checkpoint by checkpoint (Part Two walks through it).

### Evidence, end to end

- **Evidence collection.** Control owners receive their assigned requests and upload the proof.
- **The approval workflow.** The full life of a piece of proof — needed, provided, approved, expired, renewed — with the system stamping each step.
- **Automatic evidence reuse.** The assistant proposes reusing proof already on file when it fits a new request, for the risk manager to accept or reject — so the same document isn't chased twice.
- **Evidence freshness tracking.** Watching evidence age, expiry dates, staleness, and overdue requests, and raising alerts *before* anything lapses.

### The people-facing surfaces

- **The control owner portal.** A separate, simplified app so a control owner sees only their own tasks and uploads — without the full system.
- **The compliance dashboard.** Read-only views of how complete coverage is — sliced by control, by application, by business unit — and what's still unmapped.
- **The catalogue browser.** A searchable browse of every control, procedure, application, and business process.
- **Administration.** The settings surfaces — the rules catalogue (where rules are authored), synchronization settings, evidence types, and workflow configuration.

### Audits and engagements

- **Engagement management — audits and reviews.** Setting up and running audits, reviews, and assessments that consume the evidence with their scope frozen (Part Two walks through it), across the six recognized kinds: **SOX quarterly checks, regulator inquiries, internal control reviews, vendor-risk assessments, incident reviews, and external audits.** All six share the same shape; they differ in their scope rules and the kinds of findings they record.

### The connected system

- **Automatic evidence gathering.** EMS connects directly to the systems that already produce the proof — **GitHub** (code reviews, branch policies, deployment approvals), **ServiceNow** (change records, incident remediation, access requests), **Qualys** (vulnerability and configuration scans), **SailPoint IdentityIQ** (access certifications, role assignments, segregation-of-duties checks), and the **in-scope applications' own interfaces** (configuration snapshots, audit logs, transaction samples) — and reads the evidence continuously, so people shift from uploading evidence to handling the exceptions.
- **Requests delivered in your team's own tools.** Evidence requests arrive in the work-tracking system a team already uses, not only by email.
- **Between-cycle changes.** Occasional reclassifications that can't wait for the next monthly cycle are handled as they arise.

### The guarantees underneath

- **Automatic, attributable record-keeping.** Every official status is written by the system, not typed by a person, so every change traces to a consistent, automatic action.
- **Permanent, never-deleted evidence.** Nothing is ever thrown away; evidence that no longer applies is marked, not removed.
- **Frozen point-in-time snapshots.** Every decision keeps a photograph of the rule and the application as they were at the moment it was made.
- **A one-way, no-rewrite history.** Approvals can't be silently reversed; corrections happen openly, going forward. The trail is complete and tamper-resistant by design.

---

## Where to go from here

You now have both the whole picture and a close look at its three most telling pieces. If you want to go further still, the same plain-language approach can open up any of the deeper pieces — how the system decides which part of the business owns a control, how the built-in assistant proposes reusing evidence, or how the whole thing is assembled on the company's standard low-code platform. Ask, and the right part of the team can walk you through it.

And the one image to carry with you: **EMS draws a clear line around an organization's compliance — which rules apply, to what, with what proof, and is that proof still good — answered continuously, automatically, and in a way anyone can read and trust.** It turns a vague, recurring anxiety ("are we covered?") into a plain, visible, always-current answer.
