# SPEC-004 — Sandbox Evidence and Growth Lifecycle

**Project:** Structural Intelligence Framework (SIF)  
**Document status:** Candidate Research Specification — not an adopted standard  
**Specification version:** 0.1.0  
**Repository release target:** v1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0  
**Path:** `specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md`

> **Design principle:** Discovery may be open; evidence must be traceable; evaluation must be challengeable; action must be separately authorized.

## Abstract

The Structural Intelligence Framework (SIF) proposes an open architecture for locating, composing, evaluating, and evolving heterogeneous intelligence structures. This candidate specification defines a **Sandbox Evidence and Growth Lifecycle (SEGL)** for proposed structural changes. It connects the Multi-Intelligence Adversarial Sandbox (MIAS), Structural Counter-Evidence (SCE), Structural Precedent Registry (SPR), Structural Intelligence Contracts (SIC), and Universal Naming, Typing, and Relay (UNT-R).

SEGL treats an intelligence-growth proposal as a falsifiable, versioned structural claim rather than an automatically deployable improvement. It defines roles, lifecycle states, immutable evidence references, challenge procedures, release gates, and conformance tests. The goal is reproducible decision-making across exploratory, shadow, and production environments—not a claim that adversarial testing can prove general safety or correctness.

**Keywords:** structural intelligence, adversarial sandbox, counter-evidence, evaluator governance, recursive self-improvement, structural growth, evidence provenance, authorization, conformance.

---

## 1. Scope and normative language

This specification addresses:

- registering a proposed new or revised intelligence structure;
- testing structural claims under declared contexts and budgets;
- recording supporting and disconfirming evidence;
- governing evaluators and preventing metric-only promotion;
- separating validation from operational authorization;
- monitoring, revising, rolling back, and retiring deployed structures.

It does **not** prescribe a model architecture, claim universal proof of safety, standardize an industry protocol, or grant a sandbox authority to deploy itself.

The terms **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** express requirements for an implementation that *claims conformance to this candidate specification*. They do not imply external standardization.

### 1.1 Related specifications

- `SPEC-001-SIF-Structural-Intelligence-Contract.md`: capability, context, evidence, policy, and lifecycle contracts.
- `SPEC-002-Universal-Name-Type-and-Relay-API.md`: identity, type compatibility, relay sessions, and provenance.
- `SPEC-003-Structural-Precedent-Registry-Schema.md`: capability, case, evidence, counter-evidence, and lineage records.

Related manuscripts include SIF-007, SIF-009, SIF-012, SIF-013, SIF-014, SIF-015, and SIF-017. If terminology diverges, implementations MUST publish their local profile and mapping; this draft does not silently override other drafts.

## 2. Architectural position

SIF distinguishes three complementary systems:

1. **Structural Intelligence Registry:** what capabilities, precedents, evidence, and boundaries are known.
2. **Structural Intelligence Runtime:** how eligible capabilities are composed and executed under policy.
3. **Structural Intelligence Evolution Laboratory:** how proposed improvements are challenged, measured, and qualified.

SEGL is the boundary protocol between the third system and the first two. Its central invariant is:

**Candidate generation ≠ validation ≠ authorization ≠ successful deployment.**

A candidate may be registered without passing validation; pass a scoped evaluation without receiving permission to execute; or receive conditional authorization and later be suspended when counter-evidence emerges.

### 2.1 Conceptual flow

```text
Problem / capability residual
          |
          v
  Growth proposal + SIC
          |
          v
  Isolated exploratory MIAS
    Builder | Challenger
    Evaluator | Formal checker
    World/simulation engine
          |
          v
 Evidence ledger + counter-evidence
          |
          v
 Independent review + scoped qualification
          |
          v
  Shadow / non-actuating validation
          |
          v
 Separate policy authorization
          |
          v
 Monitored production (limited scope)
          |
          +----> incident / drift / counter-evidence
          |                  |
          +<--- rollback / revise / retire
          |
          v
  SPR precedent and lineage update
```

*Suggested illustration:* `figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` near this flow, and `figures/Fig-007-Structural-Growth-and-Evolution-Loop.png` near Section 5.

## 3. Core concepts

### 3.1 Structural claim

A **structural claim** is a testable assertion about a capability, representation, localization strategy, composition, evaluator, control policy, or growth mechanism. It MUST specify its intended context and comparison basis.

Examples:

- A revised MDT localization policy reduces search cost while preserving retrieval coverage under a defined workload.
- A new PIRU combination improves planning feasibility without increasing unauthorized action risk.
- A revised evaluator better detects distribution shifts without creating unacceptable false rejections.

### 3.2 Residual

A **residual** is a documented mismatch between a requested or expected structural behavior and observed capability. Candidate residual classes include localization, representation, capability, composition, evidence, control, resource, environment, and perspective. A residual is not proof that a new intelligence structure exists or is needed.

### 3.3 Evidence and structural counter-evidence

**Evidence** supports or qualifies a claim under identified conditions. **Structural Counter-Evidence (SCE)** challenges a claim's assumptions, applicability, transferability, causal interpretation, composition, evaluation, or authorization. Both MUST be preserved, including failed, inconclusive, and superseded tests.

### 3.4 Evaluation envelope

An **evaluation envelope** declares workload, data provenance, baseline, metrics, acceptance thresholds, excluded conditions, model and tool versions, computational budget, and known limitations. Evidence MUST NOT be generalized beyond its envelope without additional testing.

### 3.5 Growth artifact

A **growth artifact** is a versioned proposed change: a PIRP, PIRU, Macro-Intelligence Piece, registry adaptation, routing policy, evaluator, contract, or other structure. Every artifact MUST have a resolvable identity and integrity reference.

## 4. Roles, independence, and trust boundaries

| Role | Responsibility | Prohibited shortcut |
|---|---|---|
| Proposer / Builder | Formulate claim, create candidate, supply reproducible package | Self-approve production release |
| Challenger | Seek counterexamples, boundary failures, and competing explanations | Delete inconvenient counter-evidence |
| Independent Evaluator | Apply predeclared criteria and report uncertainty | Redefine success after seeing outcomes without disclosure |
| Formal Checker | Check machine-verifiable invariants where feasible | Treat limited formal proof as proof of general safety |
| World / Simulation Engine | Supply controlled environments and stress scenarios | Present simulated outcomes as real-world validation |
| Evidence Custodian | Preserve provenance, integrity, lineage, and access controls | Modify historical records without an audit trail |
| Policy Authority | Decide whether, where, and under what limits action is permitted | Delegate authorization implicitly to a score |
| Runtime Operator | Enforce approved scope, monitor and rollback | Expand scope without new approval |
| Incident Reviewer | Triage adverse outcomes and trigger re-evaluation | Suppress relevant incident evidence |

One agent or organization MAY fill multiple roles in a low-risk research prototype, but the record MUST disclose such overlap. A production-governed profile MUST implement an independent approval path for authorization. Independence is an organizational and procedural property, not guaranteed merely by running two LLM instances.

## 5. Lifecycle state machine

### 5.1 Canonical states

| State | Meaning | Permitted next states |
|---|---|---|
| `PROPOSED` | Candidate claim and artifact registered | `TRIAGED`, `REJECTED` |
| `TRIAGED` | Scope, risk, test plan, and resources reviewed | `SANDBOXING`, `REJECTED` |
| `SANDBOXING` | Isolated exploration and adversarial trials | `EVIDENCE_REVIEW`, `REVISE`, `REJECTED` |
| `EVIDENCE_REVIEW` | Evidence and evaluator integrity assessed | `QUALIFIED`, `REVISE`, `REJECTED` |
| `QUALIFIED` | Scoped claim meets declared evaluation criteria | `SHADOWING`, `REVISE`, `RETIRED` |
| `SHADOWING` | Non-actuating validation under realistic inputs | `AUTHORIZATION_REVIEW`, `REVISE`, `REJECTED` |
| `AUTHORIZATION_REVIEW` | Separate policy decision pending | `AUTHORIZED`, `REJECTED`, `REVISE` |
| `AUTHORIZED` | Specific runtime scope and limits approved | `DEPLOYED`, `SUSPENDED`, `RETIRED` |
| `DEPLOYED` | Operating within authorized boundaries | `SUSPENDED`, `REVISE`, `RETIRED` |
| `SUSPENDED` | Execution blocked pending review | `REVISE`, `AUTHORIZED`, `RETIRED` |
| `REVISE` | Candidate or evidence envelope needs modification | `TRIAGED`, `RETIRED` |
| `REJECTED` | Proposal rejected for this revision and envelope | `RETIRED` |
| `RETIRED` | No further use under this artifact revision | none |

An implementation MAY add internal states but MUST preserve the semantic gates between sandbox qualification, shadow validation, and action authorization. State changes MUST be recorded as append-only transition events with actor, time, reason, evidence references, and policy decision reference when relevant.

### 5.2 Transition invariants

1. A `QUALIFIED` transition MUST reference an evaluation envelope, baseline, results, and unresolved counter-evidence disposition.
2. `SHADOWING` MUST NOT permit the candidate to produce externally consequential actions; any side effects require separate explicit authorization and cannot be described as non-actuating shadowing.
3. `AUTHORIZED` MUST reference a named policy authority, scoped resources, expiry/review trigger, and rollback plan.
4. `DEPLOYED` MUST be impossible without a current authorization matching the artifact digest and deployment context.
5. A material contract, model, evaluator, or policy change MUST create a new version or trigger requalification according to documented change-impact rules.
6. `SUSPENDED` MUST prevent new authorized invocations within the affected scope until explicitly restored.
7. Rejected or retired artifacts MUST remain discoverable for audit and counter-evidence; deletion is not the default lifecycle operation.
8. A transition MUST NOT erase earlier evidence or retroactively rewrite its evaluation criteria.

## 6. Required record types

SEGL uses the identities and cross-references defined by SPEC-001–003. This section defines the minimum *logical* records, not a mandatory storage technology.

| Record | Required logical fields |
|---|---|
| `GrowthProposal` | `id`, `revision`, `artifact_ref`, `claim`, `residual_refs`, `sic_ref`, `proposer`, `created_at`, `target_context`, `risk_class` |
| `EvaluationPlan` | `id`, `proposal_ref`, `baseline_refs`, `datasets`, `metrics`, `thresholds`, `challenge_plan`, `budget`, `independence`, `precommitment_time` |
| `TrialRecord` | `id`, `plan_ref`, `artifact_digest`, `environment_digest`, `inputs_ref`, `outputs_ref`, `metrics`, `seed_or_replay`, `cost`, `status`, `timestamp` |
| `EvidenceRecord` | `id`, `claim_ref`, `trial_refs`, `direction`, `strength`, `scope`, `provenance`, `limitations`, `integrity_digest` |
| `CounterEvidenceRecord` | `id`, `claim_ref`, `failure_class`, `reproduction_ref`, `severity`, `affected_scope`, `disposition`, `status` |
| `EvaluatorReview` | `id`, `evaluator_ref`, `reviewer`, `conflicts`, `leakage_checks`, `metric_robustness`, `limitations`, `decision` |
| `AuthorizationDecision` | `id`, `artifact_digest`, `policy_authority`, `allowed_actions`, `context_scope`, `limits`, `expiry`, `revocation_ref`, `decision` |
| `LifecycleEvent` | `id`, `proposal_ref`, `from_state`, `to_state`, `actor`, `reason`, `evidence_refs`, `timestamp` |
| `DeploymentObservation` | `id`, `authorization_ref`, `telemetry_refs`, `drift_indicators`, `incidents`, `scope`, `timestamp` |

All references MUST be resolvable within the declared registry or through a documented resolver. Records containing private, proprietary, or security-sensitive data MAY expose access-controlled references and hashes rather than raw content; audit access policy MUST be explicit.

### 6.1 Evidence integrity and reproducibility

Each trial SHOULD retain the code/model and dependency versions, dataset snapshot or immutable reference, tool configuration, evaluation script digest, seeds where meaningful, timing, resource consumption, and known sources of nondeterminism. When exact replay is infeasible, the record MUST say so and provide an alternative reproducibility protocol.

The evidence custodian SHOULD support append-only storage, content digests, signed attestations where available, and audit logs. Cryptographic digests demonstrate integrity of stored bytes, not truth of the claim or independence of the evaluator.

### 6.2 Negative and inconclusive evidence

A registry MUST distinguish `SUPPORTS`, `REFUTES`, `MIXED`, and `INCONCLUSIVE`. Missing evidence MUST NOT be represented as supporting evidence. An unresolved high-severity counterexample MUST block qualification unless a documented and independently reviewed scope exclusion makes the claim strictly narrower.

## 7. Candidate interoperable YAML envelope

The following example is illustrative and **not** a finalized machine-validated schema. Identifier formats, enumerations, and signature algorithms require further alignment with SPEC-001–003.

```yaml
segl_version: "0.1.0"
proposal:
  id: "urn:sif:growth:mdt-routing:proposal-004"
  revision: "1"
  artifact_ref: "urn:sif:capability:mdt-routing:2.1.0"
  artifact_digest: "sha256:<artifact-content-digest>"
  sic_ref: "urn:sif:contract:mdt-routing:2.1.0"
  residual_refs:
    - "urn:sif:residual:retrieval-cost:017"
  claim: >-
    Improve retrieval efficiency without reducing recall below
    the precommitted noninferiority margin on the target workload.
  target_context: "urn:sif:context:catalog-search:2026-q4"
  risk_class: "research-low"
  state: "EVIDENCE_REVIEW"

plan:
  id: "urn:sif:eval-plan:mdt-routing:004"
  precommitted: true
  baseline_refs:
    - "urn:sif:capability:mdt-routing:2.0.0"
  metrics:
    - name: "recall_at_20"
      objective: "noninferiority"
      margin: 0.01
    - name: "median_compute_cost"
      objective: "minimize"
  evaluation_budget:
    max_trials: 300
    max_compute_hours: 20
  challenge_plan:
    - "distribution_shift"
    - "short_query_bias"
    - "rare_category_stress"
  independent_evaluator_ref: "urn:sif:evaluator:retrieval-review:1.2.0"

evidence:
  - id: "urn:sif:evidence:mdt-routing:trial-summary-004"
    direction: "MIXED"
    trial_refs:
      - "urn:sif:trial:mdt-routing:004-001"
    limitations:
      - "Synthetic workloads do not establish production effectiveness"

counter_evidence:
  - id: "urn:sif:counterevidence:mdt-routing:rare-query-002"
    failure_class: "applicability"
    severity: "medium"
    status: "OPEN"
    disposition: "Requires additional stratified evaluation"

authorization:
  decision: "NOT_REQUESTED"
  allowed_actions: []

lifecycle_events:
  - from_state: "SANDBOXING"
    to_state: "EVIDENCE_REVIEW"
    actor: "urn:sif:agent:evidence-custodian:1"
    reason: "Initial evaluation batch complete"
    evidence_refs:
      - "urn:sif:evidence:mdt-routing:trial-summary-004"
```

This example intentionally does **not** claim qualification: an open medium-severity applicability concern and mixed evidence require review.

## 8. Adversarial evaluation protocol

### 8.1 Before testing

The proposer MUST declare the claim, target context, baseline, success and failure thresholds, intended resource budget, risk assumptions, and expected side effects. Evaluation plans SHOULD be frozen or timestamped before confirmatory trials. Exploratory trials MAY precede precommitment but MUST be labeled exploratory.

### 8.2 Builder–Challenger cycle

The Builder submits a versioned candidate. The Challenger generates targeted counterexamples across input, representation, localization, composition, policy, resource, and perspective boundaries. The Independent Evaluator runs or audits the precommitted protocol. A Formal Checker examines explicit invariants where applicable. The World/Simulation Engine supplies controlled scenarios, while the Evidence Custodian records results without dropping negative outcomes.

The challenger SHOULD be allowed to propose new test dimensions, but post hoc additions MUST be distinguished from precommitted tests. Challenge budgets MUST be bounded to prevent endless self-referential evaluation.

### 8.3 Minimum challenge families

| Family | Example probe | Structural question |
|---|---|---|
| Applicability | Out-of-domain inputs | Does the precedent transfer? |
| Representation | Missing variables or changed granularity | Is the problem described adequately? |
| Localization | Misrouting and ambiguous signatures | Is the correct intelligence reached? |
| Composition | Order, dependency, or interface faults | Does the whole preserve component assumptions? |
| Counterfactual | Alternative causes and baselines | Is improvement attributable to the change? |
| Robustness | Noise, adversarial input, distribution shift | Is the claimed envelope stable? |
| Evaluator | Metric gaming, contamination, leakage | Is the score trustworthy? |
| Governance | Unauthorized action attempts | Are authority boundaries enforced? |
| Resources | Latency, cost, exhaustion, retries | Does the claim survive budget limits? |
| Perspective | Omitted stakeholders or objectives | Is the framing itself too narrow? |

### 8.4 Ablation and comparison

A candidate SHOULD be compared against a strong baseline, a no-change control, and relevant ablations. Experiments SHOULD report uncertainty, sample sizes, costs, and subgroup results rather than a single aggregate score. Evaluator selection and tuning on the same held-out set SHOULD be disclosed and mitigated.

### 8.5 Evaluator governance

An evaluator is itself a structural capability with a contract, version, provenance, applicability envelope, and counter-evidence. Its outputs MUST NOT authorize deployment. Independent review SHOULD examine metric alignment, leakage, incentives, data representativeness, and vulnerability to score optimization. If an evaluator is challenged or replaced, affected qualifications MUST be assessed for revalidation.

**Bounded recursive challenge:** An evaluator MAY be challenged by a second evaluator or audit method, but each recursion MUST have explicit budget, stopping rules, and escalation conditions. Infinite evaluator regress is neither necessary nor operationally acceptable.

## 9. Qualification, shadowing, and authorization gates

### Gate G1 — Evidence qualification

A claim may be `QUALIFIED` only when:

- the claim and evaluation envelope are explicit;
- predeclared acceptance criteria are satisfied or the claim is narrowed and retested;
- reproducibility limitations and counter-evidence are recorded;
- reviewer conflicts and evaluator limitations are disclosed;
- no unresolved counter-evidence invalidates the qualified scope.

Qualification MUST name the precise version and scope; it MUST NOT be inherited automatically by a revised artifact.

### Gate G2 — Shadow validation

Shadowing compares a candidate with live-like workloads without allowing its decisions to cause production side effects. The plan MUST specify data protection, retention, non-actuation controls, drift checks, fallback, and monitoring. A successful simulation alone MUST NOT be represented as successful shadow validation.

### Gate G3 — Action authorization

Authorization is a separate decision by a designated Policy Authority. The decision MUST identify the artifact digest, approved context, allowed actions, resource limits, expiration or review triggers, audit requirements, and revocation mechanism. A numerical score or passing test suite MUST NOT substitute for the authority decision.

### Gate G4 — Continued operation

Production monitoring MUST detect relevant incidents, distribution shifts, policy violations, and performance degradation. Operators MUST be able to suspend or roll back the approved artifact. Material deviations MUST trigger re-evaluation or scope restriction.

## 10. Growth, lineage, and collective learning

### 10.1 Growth event taxonomy

A growth proposal MAY introduce a new capability, adapt an existing precedent, change localization, alter composition, improve evaluation, revise control, expand a context envelope, or propose a new perspective. It MUST state whether it changes only performance within an existing worldview or claims a genuinely new representational or perceptual capability.

### 10.2 Lineage and precedent update

Following review, the SPR SHOULD record the relationship between prior artifact, candidate, residual, test evidence, counter-evidence, and decision. A rejected candidate may still be a valuable negative precedent. Promotion to a portable PIRU requires compatible SIC/UNT-R contracts and appropriate validation; a flexible PIRP may remain exploratory.

### 10.3 Cross-system sharing

Collective Structural Learning MAY exchange sanitized evidence bundles, contract metadata, and precedent lineage across BrainUnits or organizations. Such exchanges MUST respect data ownership, confidentiality, policy boundaries, and contextual applicability. External evidence MUST NOT be treated as locally valid without checking transfer conditions.

### 10.4 Perception-horizon claims

Claims of expanded Structural Perception Horizon or Worldview Reconstruction require evidence of new useful distinctions or relations—not merely larger model size, more tokens, or improved benchmark scores. Validation SHOULD include independent tasks that require the purported new distinctions and tests that rule out simpler explanations.

## 11. Threat model and failure modes

| Threat / failure | Mitigation direction |
|---|---|
| Metric gaming and Goodhart effects | Multi-objective review, independent holdouts, counter-evidence |
| Evaluator capture or shared model bias | Diverse methods, role disclosure, external audit where feasible |
| Evidence laundering | Integrity references, provenance checks, immutable history |
| Synthetic-to-real transfer failure | Explicit simulation labels, shadow validation, scoped claims |
| Prompt injection or malicious relay payloads | Trust-boundary enforcement, input validation, least privilege |
| Sandbox escape or unintended side effects | Network/tool isolation, deny-by-default actions, resource quotas |
| Silent contract drift | Version pinning, change-impact analysis, requalification |
| Registry poisoning | Provenance, review, access control, dispute and revocation records |
| Recursive evaluation explosion | Budgets, stopping rules, risk-based escalation |
| Hidden negative results | Mandatory negative and inconclusive evidence retention |
| Premature capability promotion | Separate qualification and authorization gates |
| Overgeneralized intelligence claims | Context envelopes, subgroup tests, scope-specific conclusions |

The threat model is non-exhaustive. Higher-risk domains require additional domain-specific controls and expert review.

## 12. Conformance profiles

**SEGL-E (Exploratory):** proposal identity, artifact reference, sandbox isolation, basic trial records, explicit evidence direction, and lifecycle audit.

**SEGL-V (Validated):** all SEGL-E requirements plus precommitted evaluation plan, baseline comparison, independent evaluation disclosure, counter-evidence management, reproducibility protocol, and qualification gates.

**SEGL-G (Governed):** all SEGL-V requirements plus shadow non-actuation controls, separate policy authorization, artifact-bound scope, operational monitoring, suspension/rollback, and auditability.

A system MUST state its claimed profile, supported operations, exclusions, and known nonconformances. A lower profile MUST NOT advertise itself as production-governed merely because it includes a sandbox or a score.

## 13. Candidate conformance test suite

| ID | Test | Expected result |
|---|---|---|
| SEGL-T01 | Register proposal without artifact identity | Reject |
| SEGL-T02 | Register proposal without SIC reference | Reject or mark nonconformant |
| SEGL-T03 | Preserve rejected candidate history | History remains auditable |
| SEGL-T04 | Alter existing trial evidence in place | Reject or append correction event |
| SEGL-T05 | Promote candidate with no baseline | Block qualification |
| SEGL-T06 | Change acceptance threshold after test | Record protocol deviation; require review |
| SEGL-T07 | Omit inconclusive or negative result | Detect evidence completeness failure |
| SEGL-T08 | Claim reproducibility without versions or replay protocol | Fail reproducibility requirement |
| SEGL-T09 | Qualify with unresolved scope-invalidating SCE | Block qualification |
| SEGL-T10 | Attempt external side effect during shadowing | Deny and log incident |
| SEGL-T11 | Attempt production invocation before authorization | Deny |
| SEGL-T12 | Invoke approved artifact outside context scope | Deny |
| SEGL-T13 | Replace artifact bytes without updating digest | Deny or requalify |
| SEGL-T14 | Authorization expired or revoked | Deny new invocation |
| SEGL-T15 | Suspend deployed artifact | Block affected new invocations |
| SEGL-T16 | Evaluator version materially changes | Trigger impact review |
| SEGL-T17 | Register conflicting supporting and refuting evidence | Retain both with dispositions |
| SEGL-T18 | Cross-registry import lacks provenance | Quarantine or reject |
| SEGL-T19 | Recursive challenger exceeds budget | Stop and record exhaustion |
| SEGL-T20 | Claim world-model/perception growth using only aggregate score | Mark claim unsupported pending targeted tests |
| SEGL-T21 | Production drift breaches predeclared threshold | Trigger review/suspension according to policy |
| SEGL-T22 | Operator attempts to override authority via score | Deny |
| SEGL-T23 | Share evidence across organizations without required permission | Deny or redact |
| SEGL-T24 | Roll back to previously approved artifact | Require valid authorization for restored scope |

These are **candidate** tests; a reference harness and executable schema remain future work. Passing them would establish only the stated profile's interface and process conformance, not general intelligence, safety, or scientific validity.

## 14. Testable research hypotheses

**H1 — Counter-evidence retention:** A registry that preserves negative and inconclusive precedents reduces repeated known failures compared with success-only storage.

**H2 — Independent evaluation:** Separating builder and evaluator improves detection of overfitting and misleading performance claims under matched budgets.

**H3 — Precommitted envelopes:** Predeclared scopes and thresholds reduce post hoc claim inflation relative to unrestricted reporting.

**H4 — Structural challenges:** Multi-family structural challenges discover more transferable failure modes than answer-only evaluation at comparable cost.

**H5 — Scoped authorization:** Artifact-bound action grants reduce unauthorized cross-context invocation compared with score-triggered deployment.

**H6 — Evaluator counter-evidence:** Auditing evaluators improves calibration and reduces metric gaming, subject to measurable overhead.

**H7 — Precedent-guided growth:** Residual diagnosis and registry retrieval reduce duplicated candidate discovery effort relative to unguided search.

**H8 — Shadow gating:** Non-actuating shadow validation identifies production-context failures missed by isolated simulation.

**H9 — Collective learning:** Provenance-preserving sharing improves transfer while lowering repeat experiments, conditional on context compatibility.

**H10 — Perception claims:** Explicit tests of novel structural distinctions better separate worldview change from ordinary within-task performance gains.

Each hypothesis requires preregistered metrics, baselines, cost accounting, confidence intervals or equivalent uncertainty characterization, and negative-result reporting. None is established by this draft.

## 15. Validation roadmap

**Phase 0 — Specification alignment:** Reconcile identifiers, enumerations, and field meanings with SPEC-001–003; publish versioned JSON Schema or equivalent validators.

**Phase 1 — Evidence-ledger prototype:** Implement append-only proposal, trial, counter-evidence, and lifecycle records; run SEGL-E tests.

**Phase 2 — Adversarial laboratory:** Add builder/challenger/evaluator separation, ablation, replay, and evaluator audits; run SEGL-V tests.

**Phase 3 — Shadow-runtime integration:** Connect UNT-R and SIC to a non-actuating runtime; validate context transfer and policy boundaries.

**Phase 4 — Governed limited deployment:** Introduce scoped authorization, monitoring, incident response, and rollback; run SEGL-G tests under expert oversight.

**Phase 5 — Multi-organization replication:** Exchange provenance-preserving precedents and test transferability, cost, failure rates, and governance compatibility.

Progression between phases is contingent on evidence; the roadmap is not a deployment commitment.

## 16. Open design questions

1. Which minimum evidence fields are sufficient across heterogeneous model, symbolic, optimization, and simulation capabilities?
2. How should an evaluation envelope represent changing world models and evolving task distributions?
3. What independence threshold is meaningful when Builder and Evaluator share training data or infrastructure?
4. How should counter-evidence severity interact with risk class, remediation cost, and scope narrowing?
5. Can evidence integrity be verified across federated registries without revealing protected datasets?
6. How can a scoring forest support audit without collapsing plural objectives into a manipulable scalar?
7. When should an evaluator revision invalidate prior qualifications?
8. What measurable criteria distinguish higher-order intelligence emergence from compositional convenience?
9. How should a policy authority govern self-modifying growth mechanisms without preventing exploratory research?
10. Which experiments can distinguish Structural Perception Horizon expansion from improved conventional task performance?

## 17. Integration map

| SIF component | SEGL integration |
|---|---|
| Four Functional Domains | Sources of residuals and targets of structural change |
| Problem–Capability Dual Maps | Identify gaps, proposed matches, and composition paths |
| Structural Precedent Registry | Stores claims, cases, evidence, counter-evidence, lineage |
| UNT-R | Identifies artifacts, evaluators, sessions, and relay boundaries |
| Structural Intelligence Contract | Declares capability, context, evidence, policy, and evolution hooks |
| PIRP / PIRU | Candidate pieces and formally contracted reusable units |
| MIAS | Executes bounded adversarial tests and challenge cycles |
| Universal Control Planes | Separates policy authority, scoring, and evidence/audit |
| Collective Structural Learning | Shares qualified structural experience with provenance |
| Structural Perception Horizon | Supplies ambitious but explicitly falsifiable growth claims |

## 18. Summary

SIF's growth process is useful only if it can distinguish **a promising idea**, **a supported structural claim**, **an authorized capability**, and **a reliable operating result**. SEGL proposes an auditable path between those stages while preserving counter-evidence and allowing the architecture itself to evolve.

Its governing proposition is:

> **Discover freely within bounded sandboxes. Challenge claims structurally. Preserve both evidence and counter-evidence. Qualify only within tested contexts. Authorize action separately. Reopen the case when the world changes.**

---

## Figure placement guidance

- **Fig-001 — SIF Grand Architecture:** after Section 2, to show the Registry–Runtime–Evolution Laboratory separation.
- **Fig-004 — Universal Contracts and Relay:** after Section 6, to show record and contract boundaries.
- **Fig-005 — Structural Precedent Intelligence:** after Section 10, to show evidence and lineage feedback.
- **Fig-006 — Multi-Intelligence Adversarial Sandbox:** after Section 2.1 or at the beginning of Section 8.
- **Fig-007 — Structural Growth and Evolution Loop:** after Section 5 or Section 15.

## References and companion documents

- `docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md`
- `docs/validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md`
- `docs/validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md`
- `docs/functional-domains/SIF-007-Residual-Based-Structural-Growth.md`
- `specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md`
- `specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md`
- `specifications/SPEC-003-Structural-Precedent-Registry-Schema.md`
- `research/TESTABLE-HYPOTHESES.md`
- `research/VALIDATION-ROADMAP.md`

**Status reminder:** This document is a proposed research specification. Its example fields, conformance profiles, and gates require implementation, adversarial testing, and cross-document reconciliation before they can support operational assurances.
