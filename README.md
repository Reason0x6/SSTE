# Software Simplified Technical English (SSTE)

## Standard 1.0 — 2026 Edition

**Status:** First stable edition  
**Language:** International English  
**Short name:** SSTE 1.0

## 1. Purpose

Software Simplified Technical English (SSTE) is a controlled natural language
for software work. Its purpose is to make technical information easier to read,
translate, review, test, and automate.

SSTE applies to text that explains software behavior or directs software work.
It covers requirements, design, development, testing, delivery, operation,
incidents, and tickets. It does not define programming-language syntax.

SSTE has five goals:

1. One instruction has one clear action.
2. One statement has one testable meaning.
3. A term has one meaning in a document set.
4. Literal software text is exact and visually distinct.
5. Risk, conditions, results, and ownership are explicit.

## 2. Independence and attribution

SSTE is inspired by general controlled-language practices and by the goals of
ASD-STE100 Simplified Technical English. SSTE is an independent standard for
software communication. It does not reproduce ASD-STE100, replace it, or grant
ASD-STE100 conformance. “ASD-STE100” and related names may be trademarks of
their respective owners.

## 3. Normative language

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**,
and **MAY** show the force of a rule.

- **MUST** and **MUST NOT** state requirements.
- **SHOULD** and **SHOULD NOT** state recommendations. A writer can depart from
  them only when the writer records a valid reason.
- **MAY** states permission.

Examples marked **Compliant** conform to the rule that they illustrate. Examples
marked **Not compliant** do not conform. An example does not necessarily show
all rules in the standard.

## 4. Terms

For this standard, these terms have the following meanings.

| Term | Meaning |
|---|---|
| approved word | A general-language word permitted by the project dictionary |
| artifact | A file or package that a build or delivery process produces |
| controlled English | English restricted by vocabulary and writing rules |
| document set | Related documents governed by one terminology policy |
| identifier | An exact software name, such as a class, key, route, or variable |
| literal | Text that a person or system must read exactly as shown |
| profile | Rules for one category of software communication |
| project term | A domain term approved for a document set |
| ticket | A tracked unit of work, such as a defect, task, story, or incident |
| writer | A person or system that produces text |

## 5. Scope

SSTE governs natural-language content in:

- product and system requirements;
- architecture and design records;
- user, administrator, developer, and API documentation;
- procedures, runbooks, and playbooks;
- pull requests, code reviews, and source-code comments;
- test descriptions and acceptance criteria;
- build, release, deployment, and rollback instructions;
- alerts, dashboards, status updates, and incident reports;
- tickets, backlog items, and service requests;
- user-interface messages and operational errors.

SSTE does not govern:

- programming-language grammar;
- machine-defined query languages or configuration syntax;
- third-party text quoted for evidence;
- unmodified logs or protocol messages;
- legal notices whose wording is externally controlled;
- informal conversation that is not part of a controlled record.

Writers MUST mark or visually separate excluded literal text. Text around the
literal MUST conform when the document claims conformance.

## 6. Conformance

### 6.1 Conformance statement

A conforming document MUST declare:

1. the SSTE edition;
2. one or more profiles from section 11;
3. a conformance level from section 6.2;
4. the project dictionary or terminology source, if project terms occur;
5. recorded exceptions, if the level permits them.

Use this form:

> This document conforms to SSTE 1.0, [profile] profile, Level [1–3].
> Project terms are defined in [source]. Exceptions: [source or “none”].

### 6.2 Conformance levels

| Level | Name | Requirement |
|---|---|---|
| 1 | Core | Conform to sections 7, 8, 9, 10, 12, and the selected profile. Manual review is sufficient. |
| 2 | Controlled | Meet Level 1. Use an approved project dictionary and a repeatable review checklist or linter. Record exceptions. |
| 3 | Verified | Meet Level 2. Permit no unapproved exceptions. Verify all testable requirements and procedures against their referenced interface or system. |

A repository, organization, or product MUST NOT claim that all content conforms
unless each in-scope document conforms. It MAY claim partial conformance by
naming the exact files, content types, or directories.

### 6.3 Exceptions

An exception MUST contain:

- the rule identifier;
- the affected text or location;
- the reason;
- the approving role;
- an expiry date or the word `permanent`.

An exception MUST NOT make an unsafe procedure ambiguous.

## 7. Vocabulary rules

### VOC-01 — Use approved words

Writers MUST use approved words for general-language meanings. A project MAY
start with a common-English dictionary and then restrict it. The project MUST
record prohibited words and approved alternatives when variation can cause
confusion.

### VOC-02 — Give one meaning to one term

In a document set, an approved word or project term MUST have one technical
meaning. Do not use the same word for different objects.

**Not compliant:** “Open the port in the portal.”  
**Compliant:** “Permit TCP port `443` in the administration console.”

### VOC-03 — Use one term for one concept

Do not alternate synonyms for the same concept. Select one term and use it.

**Not compliant:** “Delete the pod. Remove the pod if it stays in this state.”  
**Compliant:** “Delete the pod if it stays in this state.”

### VOC-04 — Approve project terms

A necessary software, product, business, security, or platform term MAY be a
project term. Before first use, the writer MUST do one of the following:

- define the term;
- link to its definition;
- include it in the project dictionary.

A project-term record SHOULD contain the preferred term, definition, part of
speech, permitted forms, prohibited synonyms, and an example.

### VOC-05 — Preserve exact identifiers

Writers MUST reproduce identifiers exactly. Do not correct their spelling,
capitalization, punctuation, or grammar. Format identifiers as code or another
clearly distinct literal style.

**Compliant:** “Set `max_retry_count` to `3`.”

If an identifier is also a common word, the literal style MUST distinguish it:

**Compliant:** “Set the `default` property to `false`.”

### VOC-06 — Explain unfamiliar abbreviations

At first use in each independently readable document, write the full term before
its abbreviation. Common project-approved abbreviations MAY be exempt.

**Compliant:** “Set the recovery time objective (RTO) to 30 minutes.”

Do not give an abbreviation more than one expansion in a document set.

### VOC-07 — Use verbs consistently

Use a word as one part of speech when practical. Prefer a direct verb to a noun
phrase.

**Not compliant:** “Perform a validation of the token.”  
**Compliant:** “Validate the token.”

### VOC-08 — Avoid phrasal verbs when a clear single verb exists

Prefer `start` to `spin up`, `cancel` to `call off`, and `investigate` to `look
into`. A well-defined project term such as `log in` MAY remain when changing it
would conflict with the interface.

### VOC-09 — Do not invent variants

Do not shorten or change a product term unless the dictionary permits the form.
Do not use playful, metaphorical, or team-specific names in controlled text.

**Not compliant:** “Bounce the box and check whether the canary is happy.”  
**Compliant:** “Restart the server. Verify that the canary deployment passes its
health checks.”

### VOC-10 — Use inclusive and literal terminology

Use terms that state the technical relationship. Prefer `primary/replica`,
`allowlist/denylist`, `parent/child`, and `placeholder value` when those meanings
are correct. Do not mechanically replace a legacy identifier; preserve it as a
literal and explain it if necessary.

## 8. Sentence rules

### SEN-01 — Keep sentences short

A sentence MUST contain no more than 25 words. A title, table cell, code block,
URL, or literal does not count as a sentence. Level 2 and Level 3 documents
SHOULD use no more than 20 words per sentence.

### SEN-02 — State one main proposition

A sentence MUST state one main action, fact, requirement, result, or condition.
Split independent actions into separate numbered steps.

**Not compliant:** “Stop the service, clear the cache, restart it, and then check
the dashboard.”  
**Compliant:**

1. Stop the service.
2. Clear the cache.
3. Start the service.
4. Verify that the dashboard shows `Healthy`.

### SEN-03 — Prefer active voice

Use active voice when the actor is known or important.

**Not compliant:** “The migration must be approved before it is run.”  
**Compliant:** “The database owner MUST approve the migration before the release
engineer runs it.”

Passive voice MAY be used when the actor is unknown, irrelevant, or a security
risk. The result must remain clear.

### SEN-04 — Name the actor

For responsibilities, permissions, and handoffs, name the person, role, service,
or component that acts.

**Not compliant:** “It should be reviewed.”  
**Compliant:** “A maintainer MUST review the pull request.”

### SEN-05 — Use the imperative for instructions

In a procedure, start each action with an imperative verb. Do not add `please`,
`you should`, or `it is necessary to`.

**Not compliant:** “You should now please restart the worker.”  
**Compliant:** “Restart the worker.”

### SEN-06 — Put a condition before an action

When an action depends on a condition, state the condition first. Start with
`if`, `when`, or `unless`.

**Compliant:** “If the health check fails, stop the deployment.”

Use `if` for an uncertain condition. Use `when` for an expected event or time.
Use `unless` only when it is clearer than an equivalent positive condition.

### SEN-07 — Make references explicit

Pronouns MUST have one clear antecedent. Do not use `this`, `that`, `it`, `they`,
or `which` when more than one noun can be the antecedent.

**Not compliant:** “The client sends the token to the service after it starts.”  
**Compliant:** “After the service starts, the client sends the token to the
service.”

### SEN-08 — Use articles and determiners

Use `a`, `an`, `the`, `this`, or another determiner when normal English requires
one. Omit an article only for a proper name, identifier, heading, or established
mass noun.

### SEN-09 — Avoid noun clusters

Do not use more than three consecutive nouns as modifiers. Add prepositions or
define a project term.

**Not compliant:** “production database backup retention policy”  
**Compliant:** “retention policy for production database backups”

### SEN-10 — Use positive instructions

Tell the reader what to do. Use a negative instruction only to prevent an unsafe,
invalid, or irreversible action.

**Less clear:** “Do not leave the feature flag disabled.”  
**Clear:** “Enable the feature flag.”

**Necessary negative:** “Do not delete the old index before validation finishes.”

### SEN-11 — Express obligation with normative words

In normative text, use `MUST`, `SHOULD`, or `MAY` as defined in section 3. Do not
use `shall`, `ought to`, `expected to`, or `normally` to express obligation.

### SEN-12 — Avoid vague qualifiers

Do not use `some`, `several`, `often`, `usually`, `quickly`, `soon`, `large`,
`small`, `appropriate`, `as needed`, or `etc.` when a measurable value or complete
list is necessary.

**Not compliant:** “Retry the request a few times.”  
**Compliant:** “Retry the request three times at intervals of five seconds.”

### SEN-13 — State comparisons completely

Give the measured property, operator, value, and unit.

**Not compliant:** “Latency must be lower.”  
**Compliant:** “The p95 response latency MUST be less than 200 ms during the test.”

### SEN-14 — Avoid hidden logic

Do not combine multiple conditions with ambiguous `and` or `or`. Use a list,
decision table, or Boolean expression when precedence matters.

**Not compliant:** “Deploy if tests pass and risk is low or approval exists.”  
**Compliant:** “Deploy only if the following conditions are true:

- All required tests pass.
- The change has a low risk, or the release manager approves the change.”

### SEN-15 — Use parallel list items

Items in one list MUST have the same grammatical function. Do not mix actions,
fragments, and complete results in one list.

## 9. Information and formatting rules

### INF-01 — Separate explanation from instruction

Do not put background information inside a numbered procedure step. Put required
context before the procedure or in a note.

### INF-02 — Use one purpose for each information block

A paragraph, list, table, note, warning, or code block SHOULD have one purpose.
Use headings that name that purpose.

### INF-03 — Mark literal content

Format commands, paths, identifiers, field values, status names, keys, code, and
machine output as literals. Use inline code for short literals and fenced blocks
for multi-line literals.

Do not add sentence punctuation inside a literal unless the punctuation is part
of the literal.

### INF-04 — Distinguish placeholders

Use angle brackets for placeholders unless the relevant interface defines a
different syntax. Define each placeholder before or immediately after its first
use.

**Compliant:** `deploy --environment <environment-name>`

Do not use a real-looking secret, account number, hostname, or personal value as
a placeholder.

### INF-05 — Make commands safe to copy

A command block MUST contain only text that the reader can copy to the stated
shell or interface. Put comments on separate lines only when that interface
supports comments. State the shell, tool, working directory, permissions, and
required environment when they affect execution.

### INF-06 — Separate commands from output

Do not put prompts, commands, and output in an unlabeled block. Label each block
or use a format that clearly distinguishes them.

### INF-07 — Use exact interface text

When instructing a reader to select a control or read a message, reproduce its
visible label exactly. State its control type if the context is not clear.

**Compliant:** “Select the `Create deployment` button.”

### INF-08 — Use stable references

Link to a stable heading, requirement ID, ticket ID, or versioned artifact. Do
not use only spatial references such as `above`, `below`, `on the left`, or `here`.

### INF-09 — Use unambiguous time

Use an ISO 8601 date (`YYYY-MM-DD`). Include a time-zone offset or `Z` for an
instant. Use a duration for relative time.

**Compliant:** `2026-08-12T14:30:00Z`  
**Compliant:** “Wait for 30 seconds.”

Do not use `today`, `tomorrow`, `recently`, or `EOD` in persistent records.

### INF-10 — Use unambiguous numbers and units

Use numerals with units. Put a space between a number and an SI unit. Define
whether storage values use decimal units (`MB`) or binary units (`MiB`). Use a
leading zero for a decimal fraction less than one.

**Compliant:** `0.5 s`, `200 MB`, `256 MiB`, `10%`

### INF-11 — State ranges explicitly

State whether range limits are inclusive or exclusive. Prefer inequalities in
requirements and exact validation rules.

**Compliant:** “The value MUST be greater than or equal to `1` and less than
`100`.”

### INF-12 — Identify versions

Name the product, interface, schema, or artifact version when behavior can differ
between versions. Do not use `latest` in a reproducible instruction.

### INF-13 — Identify source and freshness

For generated or observed data, state the source and observation time when they
affect interpretation. A status report SHOULD identify its reporting interval.

### INF-14 — Protect sensitive information

Do not include secrets, private keys, access tokens, personal data, or restricted
production data in examples, tickets, logs, or command history. Use labeled
placeholders. Redact evidence without changing the technical meaning.

### INF-15 — Use warnings consistently

Use these labels:

- **DANGER** for an action likely to cause death or serious physical injury.
- **WARNING** for an action that can cause major data loss, a security breach,
  or a prolonged service outage.
- **CAUTION** for an action that can cause limited data loss, degraded service,
  or difficult recovery.
- **NOTE** for helpful information that is not a hazard.

A warning MUST appear before the hazardous action. It MUST state the hazard,
consequence, and prevention.

## 10. Procedure rules

### PRO-01 — State the goal

A procedure MUST start with a title or sentence that states its single outcome.

### PRO-02 — State prerequisites

Before the steps, list required access, roles, tools, versions, inputs, system
state, backups, and approvals. If there are no prerequisites, state `None`.

### PRO-03 — Give one action per step

Each numbered step MUST contain one user action. A step MAY contain one immediate
system response if the response verifies the action.

### PRO-04 — Number ordered actions

Use a numbered list when order matters. Use bullets only when order does not
matter. Do not encode required order only with `then` or paragraph position.

### PRO-05 — State location before action

When location matters, identify the interface, host, namespace, repository,
branch, or directory before the command or action.

### PRO-06 — State expected results

After a critical action, state an observable expected result. Use an exact value,
state, message, metric, or exit code when available.

**Compliant:** “Verify that the command exits with code `0`.”

### PRO-07 — State failure branches

If a step can fail in a known way, state the stop condition and recovery or
escalation action. Do not tell the reader to continue after an unverified critical
step.

### PRO-08 — Make destructive actions explicit

Before a destructive or irreversible action, state:

- the exact target;
- the affected environment;
- the expected impact;
- the backup or recovery state;
- the required confirmation or approval.

Do not use a wildcard, unresolved variable, or broad path for a destructive
target unless the procedure validates its resolved value first.

### PRO-09 — Provide rollback criteria

A production change procedure MUST state measurable rollback criteria, the last
safe rollback time, the rollback owner, and a tested rollback method. If rollback
is impossible, state that fact before approval.

### PRO-10 — End with verification

A procedure MUST end with a verification of its goal. A production procedure
MUST also state how long to monitor the result and which signals to inspect.

### PRO-11 — Keep branching shallow

Do not put more than one nested decision in a step. Use a decision table or a
separate procedure for complex branches.

### PRO-12 — State completion

Define the observable state that means the procedure is complete. Do not use
`done` or `successful` without criteria.

## 11. Software communication profiles

A conforming document MUST select at least one profile. All selected profile
rules apply.

### 11.1 Requirements profile (REQ)

#### REQ-01 — Identify each requirement

Each requirement MUST have a unique, stable identifier.

#### REQ-02 — State one testable obligation

Each requirement MUST state one obligation and an observable result.

**Not compliant:** “The service should be fast and reliable.”  
**Compliant:** “REQ-API-014: The service MUST return 95% of valid requests in less
than 200 ms during the specified load test.”

#### REQ-03 — Name the subject

A requirement MUST name the system, component, role, or process that has the
obligation.

#### REQ-04 — Quantify quality attributes

Performance, availability, reliability, capacity, recovery, and security
requirements MUST state a metric, threshold, conditions, and measurement method
or reference.

#### REQ-05 — Separate rationale

Put rationale after the requirement and label it `Rationale`. Rationale MUST NOT
change the obligation.

#### REQ-06 — Define acceptance evidence

Each requirement SHOULD link to a test, inspection, analysis, or demonstration
that can verify it.

#### REQ-07 — Avoid implementation constraints unless necessary

State required behavior. If a specific implementation is mandatory, state the
reason or governing constraint.

### 11.2 Design and architecture profile (ARC)

#### ARC-01 — Separate fact, decision, and proposal

Label current facts, approved decisions, and proposals. Do not describe a
proposal as current behavior.

#### ARC-02 — State decision context

An architecture decision MUST state the problem, constraints, decision, options,
consequences, owner, date, and status.

#### ARC-03 — Define component responsibilities

State what each component owns, accepts, produces, and does not own.

#### ARC-04 — Describe interfaces precisely

Name the protocol, direction, authentication method, version, data contract,
timeout, retry policy, and failure behavior when they apply.

#### ARC-05 — State trust boundaries

Identify where data or control crosses a trust boundary. State validation,
authorization, encryption, and audit requirements at that boundary.

#### ARC-06 — State consistency and failure assumptions

Describe concurrency, ordering, idempotency, partial failure, data consistency,
and recovery assumptions when they affect the design.

### 11.3 API and developer documentation profile (API)

#### API-01 — Describe behavior before syntax

State what an interface does and when to use it before detailed syntax.

#### API-02 — Define every input

For each input, state its name, type, format, units, required status, default,
valid range, and sensitive-data classification when applicable.

#### API-03 — Define every result

State the success result, status or exit code, schema, side effects, and relevant
state changes.

#### API-04 — Define errors as actions

For each documented error, state its condition, stable identifier or code,
meaning, retry safety, and corrective action.

#### API-05 — State idempotency and retries

State whether repeated requests are safe. Define retry limits, backoff, timeout,
and duplicate-handling behavior.

#### API-06 — Provide complete examples

An example MUST declare assumptions and MUST be syntactically valid for its
stated version. Example secrets and identities MUST be unmistakably fictitious.

#### API-07 — Document lifecycle

State availability, version, deprecation date, replacement, compatibility, and
removal date when applicable.

### 11.4 Code and review profile (CODE)

#### CODE-01 — Explain intent and constraints

A code comment SHOULD explain intent, invariants, tradeoffs, or non-obvious risk.
It SHOULD NOT repeat syntax that the code clearly shows.

**Not compliant:** `i++; // Increment i`  
**Compliant:** `i++; // Skip the reserved header entry.`

#### CODE-02 — Keep comments synchronized

When a code change makes a comment false or incomplete, the change MUST update
or delete the comment.

#### CODE-03 — Identify temporary work

A temporary workaround, `TODO`, or `FIXME` MUST state the reason and a ticket ID
or removal condition. Do not use a person’s name as the only owner.

#### CODE-04 — Make review comments actionable

A blocking review comment MUST state the problem, consequence, required change,
and applicable evidence. Mark optional advice as `Suggestion`.

#### CODE-05 — Describe the change, not the activity

A commit or pull-request summary SHOULD use an imperative verb and name the
observable change.

**Not compliant:** “Worked on auth fixes.”  
**Compliant:** “Reject expired refresh tokens.”

#### CODE-06 — State verification

A pull-request description MUST state the tests performed and their results. It
MUST also state untested relevant behavior.

#### CODE-07 — State compatibility and operational impact

A change description MUST state effects on interfaces, data, configuration,
security, performance, observability, deployment, and rollback when applicable.

### 11.5 Test profile (TST)

#### TST-01 — State preconditions, action, and result

A test case MUST identify its initial state, one tested action or event, and its
expected observable result.

#### TST-02 — Use deterministic evidence

Do not use `works`, `looks correct`, or `behaves normally`. State exact assertions,
allowed tolerances, or referenced snapshots.

#### TST-03 — Identify test data

State the source, classification, setup, and cleanup of test data. Do not use
production personal data unless an approved policy permits it.

#### TST-04 — Separate scenarios

Do not combine unrelated behaviors in one test case. Parameterized cases MAY
share a procedure when each input and expected result is explicit.

#### TST-05 — Record environment and version

A test result MUST identify the tested artifact, configuration, environment, and
time when these can affect the result.

#### TST-06 — Classify non-passing results

Use defined statuses such as `failed`, `blocked`, `skipped`, and `inconclusive`.
State the evidence and reason. Do not report these statuses as `passed`.

### 11.6 Procedure and runbook profile (RUN)

The RUN profile MUST conform to all rules in section 10.

#### RUN-01 — Identify operational scope

State the service, environment, region, tenant, and version when applicable.

#### RUN-02 — State access and audit requirements

Identify the required role, authentication method, approval, and audit record.
Do not instruct readers to share credentials or bypass access controls.

#### RUN-03 — Prefer read-only diagnosis

Put read-only checks before state-changing actions unless delay increases harm.
Mark every state-changing command.

#### RUN-04 — Define escalation

State whom to contact, the trigger, the required evidence, and the maximum wait
time. Use a maintained role or schedule, not only a person’s name.

#### RUN-05 — Preserve evidence

Before an action that can remove evidence, state which logs, metrics, traces,
dumps, or identifiers to save and where to store them.

### 11.7 Build, deployment, and DevOps profile (OPS)

#### OPS-01 — Identify immutable inputs

A release or deployment record MUST identify source revision, artifact digest,
configuration version, dependency lock state, and build provenance when available.
Do not identify a deployable artifact only as `latest`.

#### OPS-02 — Distinguish environments

Name the exact target environment. Do not use `the server`, `the cluster`, or
`production-like` without a definition.

#### OPS-03 — State pipeline gates

For each gate, state the entry conditions, evaluation, owner or automation,
evidence, and pass criteria.

#### OPS-04 — Define deployment strategy

Name the strategy, traffic or instance increments, wait intervals, health
signals, abort thresholds, and completion criteria.

#### OPS-05 — Control configuration changes

State the configuration key, old value, new value, scope, activation method,
validation, and rollback value. Never put a secret value in the change record.

#### OPS-06 — Describe database changes

State compatibility order, lock risk, estimated duration, backfill behavior,
verification, rollback limits, and data recovery method.

#### OPS-07 — Define rollback by observation

Use measurable signals for rollback. Do not use only `if problems occur`.

**Compliant:** “Roll back if the five-minute error rate exceeds `2%` for two
consecutive evaluation periods.”

#### OPS-08 — State change ownership and communication

Identify the change owner, operator, approver, communication channel, start time,
and planned end time.

#### OPS-09 — Verify after deployment

Verify artifact identity, instance health, critical transactions, telemetry,
security controls, and user impact as applicable.

#### OPS-10 — Record outcome

Record the actual start and end times, final version, gate results, incidents,
rollback status, and follow-up tickets.

### 11.8 Observability and incident profile (INC)

#### INC-01 — Describe symptoms as observations

Separate observations from hypotheses and confirmed causes. Label each category.

**Observation:** “The checkout error rate increased from `0.2%` to `8.1%` at
`2026-08-12T14:03:00Z`.”  
**Hypothesis:** “The database connection limit can cause the errors.”

#### INC-02 — State user impact

An incident update MUST state affected capability, user population or scope,
start time, severity, and current workaround. If a value is unknown, write
`unknown` and state the next action to determine it.

#### INC-03 — Use timestamped updates

Each timeline event and status update MUST include an absolute timestamp and
time zone. Do not silently edit a past event; append a correction.

#### INC-04 — Distinguish mitigation from resolution

Use `mitigated` only when impact is controlled but the cause can remain. Use
`resolved` only when the service meets defined health criteria.

#### INC-05 — State alert conditions

An alert description MUST name the signal, query or calculation, threshold,
evaluation period, affected scope, likely user impact, and first response.

#### INC-06 — Make messages operational

An error or alert message SHOULD state what failed, the affected object, a stable
error ID, whether retry is safe, and the next action. Do not expose secrets or
internal details that increase security risk.

#### INC-07 — Use evidence for cause

Do not state a root cause until evidence supports the causal link. Distinguish a
trigger, contributing condition, detection gap, and root cause.

#### INC-08 — Write blameless factual analysis

Describe actions, conditions, decisions, and system behavior. Do not speculate
about a person’s intent, competence, or motivation.

#### INC-09 — Assign follow-up work

Each follow-up action MUST have an owner role, ticket ID, measurable completion
criterion, priority, and due date or scheduling rule.

### 11.9 Ticket profile (TKT)

#### TKT-01 — Use a result-based title

A ticket title MUST name the affected component and the required result or
observed failure.

**Not compliant:** “Login issue”  
**Compliant:** “Authentication API returns `500` for a valid SAML callback.”

#### TKT-02 — State ticket type

Classify the ticket with a defined type, such as defect, feature, task, incident,
service request, risk, or investigation. Do not combine unrelated work types.

#### TKT-03 — Provide reproducible defect evidence

A defect MUST state:

- affected version and environment;
- preconditions;
- minimal reproduction steps;
- expected result;
- actual result;
- frequency or occurrence count;
- evidence, with sensitive data removed;
- impact and known workaround.

#### TKT-04 — Define requested outcomes

A feature, task, or story MUST state the user or system outcome, scope, acceptance
criteria, and relevant constraints. It MUST distinguish required behavior from
implementation suggestions.

#### TKT-05 — Make acceptance criteria testable

Each acceptance criterion MUST contain one observable pass condition. Use a
scenario form only when it improves clarity:

> Given [initial state], when [event], then [observable result].

Do not join independent criteria with `and`.

#### TKT-06 — Define out-of-scope work

State important excluded work when a reader could reasonably assume that it is
included.

#### TKT-07 — Record dependencies and blockers

Link each dependency or blocker. State the required event, owner, and effect on
the ticket. Do not use only `blocked by another team`.

#### TKT-08 — Use workflow states precisely

The project MUST define entry and exit criteria for each workflow state. A state
name MUST have one meaning. Do not use comments to simulate an undefined state.

#### TKT-09 — State priority with rationale

Use the project’s priority scale. State user impact, urgency, risk, and deadline
source. Do not use punctuation or words such as `urgent` as a substitute for the
scale.

#### TKT-10 — Define completion

The project MUST define `done`. A ticket MUST NOT enter the completed state while
required acceptance evidence, documentation, deployment, or follow-up work is
missing.

#### TKT-11 — Preserve decision history

Record material scope, priority, acceptance, and resolution decisions with the
deciding role and date. Do not overwrite history without an audit record.

#### TKT-12 — Use a precise resolution

For a closed ticket, state the outcome, affected version, verification evidence,
deployment state, and reason for any uncompleted scope.

### 11.10 User-interface and error-message profile (UI)

#### UI-01 — State the user’s goal

Use labels and instructions that name the user action or result. Prefer `Save
changes` to `Submit` when saving is the result.

#### UI-02 — Put the problem first

An error message MUST state the problem before its cause or recovery action.

#### UI-03 — Give a recovery action

If the user can recover, state the exact action. If the user cannot recover,
state what the system will do or how to obtain support.

#### UI-04 — Do not blame the user

Describe the invalid value or system condition. Do not use `you made an error`,
`illegal`, or humorous failure text.

#### UI-05 — Preserve useful values safely

Identify the affected field or object. Do not repeat passwords, tokens, payment
data, or other sensitive values.

#### UI-06 — Use consistent action labels

The same action MUST have the same label across related interfaces unless a
platform convention requires a different label.

## 12. Security, accessibility, and localization

### SEC-01 — Do not normalize unsafe shortcuts

Controlled text MUST NOT direct a reader to disable a security control, ignore a
certificate error, expose a secret, or grant excessive access without an approved
exception and compensating controls.

### SEC-02 — Separate public and internal detail

Public messages MUST NOT expose stack traces, topology, identifiers, dependency
versions, or authorization details that create unnecessary risk. Preserve a
correlation ID for authorized investigation.

### ACC-01 — Do not depend on color or position alone

Identify controls and states by text label, symbol with accessible name, or exact
identifier. Do not write only `select the green button` or `see the panel on the
right`.

### ACC-02 — Use descriptive link text

Link text MUST name the destination or action. Do not use `click here` or `more`.

### ACC-03 — Provide text equivalents

An informative image, chart, or diagram MUST have a text alternative or nearby
description that communicates its necessary meaning.

### LOC-01 — Avoid culture-specific language

Do not use idioms, jokes, sports metaphors, or culture-specific references in
controlled content.

### LOC-02 — Keep variables out of grammar when practical

In translatable messages, do not construct sentences from fragments. Provide
complete messages and metadata for plural, gender, and grammatical case when the
localization system supports them.

### LOC-03 — Do not embed presentation formats

Store dates, times, numbers, currency, and units as typed values when possible.
Render them for the reader’s locale. Persistent technical records MUST also keep
an unambiguous canonical value.

## 13. Project dictionary

### 13.1 Required fields

At Level 2 and Level 3, the project dictionary MUST contain these fields:

| Field | Description |
|---|---|
| term | Approved spelling |
| status | `approved`, `deprecated`, or `prohibited` |
| part_of_speech | Grammatical use |
| definition | One project-specific meaning |
| permitted_forms | Approved inflections or abbreviations |
| prohibited_synonyms | Alternatives that writers must not use |
| domain | Product, platform, security, business, or other scope |
| example | One compliant use |
| owner | Role that controls the entry |
| version | Dictionary version that introduced or changed the entry |

### 13.2 Starter verb set

Projects SHOULD prefer these direct verbs when their meanings apply:

`add`, `allow`, `approve`, `archive`, `assign`, `authenticate`, `authorize`,
`back up`, `build`, `cancel`, `check`, `close`, `compare`, `configure`, `connect`,
`copy`, `create`, `decrypt`, `delete`, `deploy`, `disable`, `disconnect`,
`download`, `enable`, `encrypt`, `enter`, `export`, `fail`, `get`, `import`,
`install`, `investigate`, `log`, `measure`, `merge`, `migrate`, `monitor`, `move`,
`open`, `publish`, `read`, `record`, `reject`, `release`, `remove`, `replace`,
`request`, `restart`, `restore`, `retry`, `review`, `revoke`, `roll back`, `rotate`,
`run`, `save`, `select`, `send`, `start`, `stop`, `store`, `test`, `update`,
`upgrade`, `upload`, `validate`, `verify`, and `write`.

Approval in this starter set does not override the one-meaning rule. A project
MUST define a verb when its technical effect is not its common meaning.

### 13.3 Preferred replacements

| Avoid | Prefer |
|---|---|
| bring up | start or display |
| blow away | delete |
| bounce | restart |
| check out | inspect or clone |
| do a validation | validate |
| execute a rollback | roll back |
| fire | send, emit, or trigger |
| hit an endpoint | send a request to an endpoint |
| hook up | connect |
| kill | stop or terminate |
| look into | investigate |
| nuke | delete |
| sanity check | preliminary check, smoke test, or validation |
| spin up | start or create |
| tear down | stop, delete, or deallocate |
| whitelist / blacklist | allowlist / denylist, when technically correct |

The preferred word MUST describe the actual operation. For example, `stop` and
`delete` are not interchangeable.

## 14. Templates

### 14.1 Ticket template

```text
Title: <component>: <required result or observed failure>
Type: <defined ticket type>
Priority: <project priority and rationale>

Outcome or problem
<One factual paragraph.>

Scope
- In scope: <items>
- Out of scope: <items>

Environment and version
<Exact values or “not applicable”.>

Reproduction (for a defect)
Prerequisites: <state>
1. <Action>
2. <Action>
Expected result: <observable result>
Actual result: <observable result>
Frequency: <count or rate>

Acceptance criteria
- AC-01: <one testable condition>
- AC-02: <one testable condition>

Evidence
<Safe links, correlation IDs, logs, or screenshots.>

Dependencies and risks
<Linked items, owner roles, and effects.>

Verification
<Required test and deployment evidence.>
```

### 14.2 Deployment procedure template

```text
Goal
Deploy <artifact digest> to <exact environment and scope>.

Owner and window
- Change owner: <role>
- Operator: <role>
- Approver: <role>
- Start: <ISO 8601 instant>
- Planned end: <ISO 8601 instant>

Prerequisites
- <Access, approvals, backups, tools, and system state.>

Risk and impact
- Expected impact: <measurable impact>
- Rollback trigger: <signal, threshold, and period>
- Last safe rollback time: <instant or condition>

Procedure
1. <One action.>
   Expected result: <observable result>.
2. <One action.>
   Expected result: <observable result>.

Verification
- <Artifact identity and health checks.>
- <Critical transaction checks.>
- <Monitoring signals and duration.>

Rollback
1. <One action.>
2. <One action.>
Completion criterion: <observable restored state>.

Record
<Actual times, result, version, incidents, and follow-up tickets.>
```

### 14.3 Incident update template

```text
Timestamp: <ISO 8601 instant>
Severity: <defined severity>
Status: <investigating, identified, mitigating, mitigated, or resolved>

User impact
<Affected capability, scope, start time, and workaround.>

Observations
- <Measured fact and source.>

Current hypothesis
- <Hypothesis, evidence, and confidence, or “unknown”.>

Actions
- <Completed action and result.>
- <Next action, owner role, and expected time.>

Next update
<ISO 8601 instant or measurable event>.
```

### 14.4 Requirement template

```text
ID: <stable requirement ID>
Subject: <system or role>
Requirement: <subject> MUST <one testable obligation>.
Conditions: <load, state, input, or “none”.>
Measure and threshold: <metric, operator, value, and unit>.
Verification: <test, inspection, analysis, or demonstration>.
Rationale: <reason that does not alter the obligation>.
```

## 15. Review and automated checks

### 15.1 Required review

A Level 1 review MUST check:

- selected profile rules;
- sentence length and single-purpose sentences;
- ambiguous pronouns and conditions;
- exact formatting of literals;
- measurable values, dates, units, and versions;
- explicit actors, expected results, and failure branches;
- prohibited terms and undefined project terms;
- sensitive information.

A Level 2 review MUST also check the text against the project dictionary and the
exception record. A Level 3 review MUST validate technical claims and executable
procedures against the referenced system or interface.

### 15.2 Linter behavior

An SSTE linter MAY report:

- sentences longer than the configured limit;
- prohibited words or phrases;
- modal verbs outside literals;
- vague qualifiers;
- ambiguous date forms;
- missing units or leading zeros;
- unformatted identifiers and commands;
- undefined abbreviations;
- passive-voice candidates;
- procedure steps without imperative verbs;
- ticket criteria without observable results.

A linter finding is evidence for review, not proof of nonconformance. A linter
MUST NOT automatically change a literal. Semantic rules require human or
system-aware review.

## 16. Worked examples

### 16.1 Defect report

**Not compliant**

> Sometimes login is broken in prod. We tried restarting stuff, but it still
> seems bad. Please fix ASAP.

**Compliant**

> **Title:** Authentication API returns `500` for valid SAML callbacks  
> **Type:** Defect  
> **Environment:** Production, `eu-west-1`, version `auth-api@4.8.2`  
> **Impact:** 31 of 240 SAML login attempts failed between
> `2026-08-12T13:00:00Z` and `2026-08-12T13:15:00Z`.  
> **Expected result:** The API redirects the authenticated user to `/home`.  
> **Actual result:** The API returns HTTP status `500` and error ID `AUTH-2041`.
>  
> **Reproduction:**  
> 1. Open the test identity-provider portal.  
> 2. Start a login for tenant `example-test-01`.  
> 3. Verify that the callback returns HTTP status `500`.  
> **Workaround:** Use password authentication for affected users.  
> **Evidence:** See the redacted trace linked in the ticket.

### 16.2 Deployment instruction

**Not compliant**

> Push the latest image, keep an eye on it, and roll it back if things look bad.

**Compliant**

> Deploy image digest `sha256:<digest>` to production cluster `payments-eu-01`.
> Send 10% of traffic to the new instances for 10 minutes. Roll back if the
> five-minute error rate exceeds `2%` twice. Verify that p95 latency stays below
> `300 ms`. Then increase traffic according to the approved deployment plan.

### 16.3 Review comment

**Not compliant**

> This is weird. Can you clean it up?

**Compliant**

> **Blocking:** `parseToken` accepts an unsigned token when `algorithm` is empty.
> This behavior permits authentication bypass. Reject an empty `algorithm` value,
> and add a test that expects error `TOKEN-003`.

### 16.4 Error message

**Not compliant**

> Oops! Something went wrong. Try again later.

**Compliant**

> The report was not created because the request exceeded 30 seconds. Retry the
> request. If error `REPORT-104` occurs again, contact support and provide the
> correlation ID.

### 16.5 Requirement

**Not compliant**

> The system should quickly notify users when builds fail.

**Compliant**

> REQ-NOTIFY-007: The notification service MUST send a failure notification
> within 60 seconds after the build service records a failed build. Verify the
> interval with the event timestamps in the integration test.

## 17. Governance and versioning

### 17.1 Standard versions

SSTE uses semantic versions:

- A **major** version can change or remove a requirement.
- A **minor** version can add backward-compatible rules, profiles, or guidance.
- A **patch** version can correct errors without changing normative meaning.

A document conforms only to the edition that it declares. A later edition does
not silently change that claim.

### 17.2 Project governance

Each adopting project SHOULD assign these roles:

- a language owner who controls the dictionary and exceptions;
- domain owners who approve technical definitions;
- document owners who maintain conforming content;
- reviewers who evaluate language and technical accuracy;
- tooling owners who maintain automated checks.

The language owner MUST publish dictionary changes and their effective dates.
Deprecated terms MUST include a replacement and migration period.

### 17.3 Change proposals

A proposal to change SSTE SHOULD include:

- the affected rule IDs;
- a concrete software communication problem;
- examples before and after the proposed change;
- effects on existing conforming content;
- effects on localization and automated checks;
- security and accessibility considerations.

## Annex A — Minimum adoption baseline (normative)

An organization that adopts SSTE MUST:

1. select its in-scope content types;
2. select a profile and conformance level for each content type;
3. publish a project dictionary at Level 2 or Level 3;
4. assign a language owner;
5. publish a review method;
6. record exceptions;
7. train writers with domain-relevant compliant and noncompliant examples;
8. review the adoption after its first 90 days.

## Annex B — Quick review card (informative)

Before publication, ask:

- Does each sentence have one clear purpose?
- Is each required action assigned to an actor?
- Is each condition before its action?
- Can a reader measure each threshold and expected result?
- Are commands, identifiers, values, and messages exact?
- Are versions, environments, dates, times, and units explicit?
- Can the reader detect failure and stop safely?
- Does a production change have tested rollback criteria?
- Does each ticket have reproducible evidence or testable acceptance criteria?
- Are observations separate from hypotheses?
- Are secrets and personal data absent?
- Are all project terms defined and used consistently?

## Annex C — Adoption profile example (informative)

| Content type | Profile | Level |
|---|---|---|
| Product requirements | REQ | 2 |
| Architecture decisions | ARC | 2 |
| Public API documentation | API | 3 |
| Pull requests and reviews | CODE | 1 |
| Test cases | TST | 2 |
| Production runbooks | RUN + OPS | 3 |
| Incident records | INC | 2 |
| Engineering tickets | TKT | 2 |
| User-visible errors | UI | 2 |

---

**End of SSTE 1.0**
