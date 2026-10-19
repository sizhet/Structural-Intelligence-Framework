# SIF-010 — Universal Naming, Typing, and Relay

**Structural Intelligence Framework (SIF)**  
**Series:** Interoperability · Paper 010  
**Version:** 1.0.0 · Research architecture proposal  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual specification and research agenda; not an implemented interoperability standard  
**License:** Apache-2.0

> **Core thesis.** Open structural intelligence requires more than a catalog of models or tools. It requires a way to identify heterogeneous intelligence structures, express what they can and cannot do, and relay tasks, context, evidence, and authority across their boundaries without assuming that their internal representations are identical.

## Abstract

The Structural Intelligence Framework (SIF) treats intelligence as an open, evolving ecology of heterogeneous capabilities. A language model, a rule engine, a metric differential tree, a simulator, a scoring forest, and a human-governed decision service may all participate in the same problem-solving process, but they do not share a native ontology, execution model, or trust boundary. This paper proposes **Universal Naming, Typing, and Relay (UNT-R)** as a cross-cutting interoperability architecture for this ecology. Naming provides stable, version-aware identity and resolvable references; typing describes capabilities, inputs, outputs, constraints, and semantic assumptions; relay governs the movement of work and context between participants. A complementary **Structural Intelligence Contract (SIC)** packages these elements with evidence, policy, provenance, and lifecycle metadata. We distinguish discovery from invocation, type compatibility from semantic adequacy, and evaluation from authorization. We outline a minimal relay protocol, compatibility checks, failure semantics, governance controls, a worked conceptual example, and testable hypotheses. UNT-R is presented as an architectural proposal, not a claim of universal semantic interoperability.

**Keywords:** structural intelligence; interoperability; naming; semantic typing; relay; intelligence contracts; provenance; governance; heterogeneous agents; structural growth

---

## 1. The Interoperability Problem

An isolated intelligent component can succeed within its own representation, tooling, and operating assumptions. A structural intelligence system must coordinate components whose assumptions may differ radically. A natural-language planner may express a task as a narrative; an optimizer may require a constrained mathematical program; a simulation engine may accept a stochastic state model; and a policy service may accept only formally typed requests.

A conventional tool call addresses only part of this problem. Knowing an endpoint does not establish that its semantics fit the task, that its inputs can be transformed safely, that its outputs have appropriate evidentiary support, or that its actions are authorized.

SIF therefore asks three linked questions:

1. **Naming:** Which structure, capability, version, or precedent is being referenced?
2. **Typing:** Under what conditions is it meaningful and safe to use that structure?
3. **Relay:** How can a task and its relevant context be handed off, executed, returned, audited, or declined?

UNT-R is intended to answer these questions across the **Structural Problem-Solving Map (PSM)** and **Structural Capability Map (SCM)** introduced in SIF-008. It is an enabling substrate, not a fifth functional domain and not a replacement for domain-specific intelligence.

## 2. Architectural Principles

### 2.1 Standardize the contract, not the intelligence

SIF should not require every intelligence structure to use a common internal model. Instead, a minimal external contract should expose the information necessary for discovery, compatibility assessment, invocation, and accountability. The contract is an interoperability boundary, not a prescription for the algorithm behind it.

### 2.2 Identity is not capability

A stable name answers *which object?* A capability declaration answers *what operation?* An evidence record answers *with what demonstrated reliability and limits?* An authorization decision answers *who may request which action under which policy?* These must remain separate fields and processes.

### 2.3 Syntax is not semantics

Matching JSON schemas or argument types does not establish equivalent meanings. A value labeled `risk` might represent probability, expected loss, or a qualitative score. A compatible interface can still be a semantically invalid substitution. Semantic types therefore require units, scope, assumptions, and, where possible, machine-checkable constraints.

### 2.4 Interoperability is contextual and defeasible

A capability may be suitable in one domain, region, timeframe, or risk regime and unsuitable in another. Compatibility judgments should carry their context, evidence, uncertainty, and counter-evidence. They are revisable claims rather than permanent endorsements.

### 2.5 Discovery freedom does not imply deployment authority

A sandbox may explore candidate relays and adapters. Production execution requires separately established policy permissions, resource limits, and auditability. An evaluator's favorable score cannot itself authorize an external action.

### 2.6 Evolution without silent breakage

New versions, new capability families, and replacement implementations should be admitted without erasing identity, compatibility history, or negative precedents. Relay paths must be inspectable and reversible where feasible.

## 3. Naming: Identity Across Structures and Lifecycles

### 3.1 What needs a name?

UNT-R distinguishes at least six referent classes:

| Referent | Purpose | Example role |
|---|---|---|
| Intelligence structure | Identifies a model, engine, algorithm, or macro-node | `structure` |
| Capability | Identifies a declared operation or behavior | `capability` |
| Contract | Identifies a particular interface and assumptions | `contract` |
| Precedent | Identifies an observed application or validation case | `precedent` |
| Evidence | Identifies a test, measurement, or counterexample | `evidence` |
| Relay session | Identifies a particular invocation or handoff | `session` |

A conceptual identifier may take the form:

```text
sif://<authority>/<kind>/<local-id>@<version>
```

For example:

```text
sif://research.example/capability/route-risk-estimation@1.2.0
```

This is an **illustrative namespace**, not a registered URI scheme or a normative syntax. Production specifications must decide how to represent authorities, escaping, canonicalization, version selectors, and collision resistance.

### 3.2 Three distinct identifiers

A robust registry should avoid conflating:

- **Logical identity:** the enduring concept or capability family.
- **Version identity:** the immutable contract or implementation revision.
- **Execution identity:** the particular invocation, context, and result.

A mutable alias may resolve to a newer version, but a reproducible precedent must pin the exact version and preferably a content digest. A result should retain the resolved version, not merely the alias used by the caller.

### 3.3 Resolution and provenance

Resolution may return a signed or otherwise authenticated descriptor with the object's contract reference, endpoints or adapters, status, provenance, and supported versions. The resolver is not automatically trusted: callers must validate authority, integrity, revocation status, and policy before use.

Names are not proof of quality. An apparently official name cannot substitute for independent evidence.

## 4. Typing: From Data Shape to Capability Meaning

### 4.1 A layered type model

UNT-R proposes the following layers, each stronger than the previous one but still incomplete on its own:

| Layer | Question | Typical declaration |
|---|---|---|
| Syntactic | Can the payload be parsed? | JSON Schema, typed records |
| Dimensional | Are units and ranges coherent? | currency, seconds, probability interval |
| Semantic | What do fields and operations mean? | domain ontology, metric definition |
| Contextual | When does the meaning hold? | jurisdiction, timeframe, population |
| Behavioral | What effects and guarantees are claimed? | preconditions, postconditions, side effects |
| Evidentiary | What supports the claim? | test coverage, calibration, counterexamples |
| Governance | Is use permitted here? | actor, purpose, resource and action policy |

A relay can pass syntactic validation and still fail at any later layer.

### 4.2 Capability signatures

A capability signature should describe more than an input/output pair. A candidate structure may declare:

```yaml
capability:
  id: "sif://research.example/capability/route-risk-estimation@1.2.0"
  operation: "estimate_route_risk"
  input_type: "route-plan/v2"
  output_type: "route-risk-report/v1"
  assumptions:
    - "road-network snapshot no older than 24 hours"
    - "vehicle class within validated set"
  effects: "read-only"
  uncertainty: "calibrated interval where supported"
  limitations:
    - "not validated for emergency response routing"
  evidence_ref: "sif://research.example/evidence/route-risk-benchmark@3"
  policy_ref: "sif://research.example/contract/risk-service-policy@2"
```

The identifiers and fields above are **non-normative examples**. They illustrate a possible contract vocabulary; SPEC-001 and SPEC-002 are intended to develop a more precise candidate schema.

### 4.3 Compatibility is a judgment, not a Boolean shortcut

Let a task requirement be \(R\), a candidate capability contract be \(C\), and the operating context be \(X\). A compatibility assessor may produce:

\[
J(R,C,X) = (s, A, E, U),
\]

where \(s\) is a status such as `compatible`, `conditional`, `incompatible`, or `unknown`; \(A\) records necessary adaptations; \(E\) references supporting and opposing evidence; and \(U\) records unresolved uncertainty.

The judgment is **not** a proof that the component will succeed. It is an auditable decision input. For consequential uses, independent evaluation and authorization are separate required steps.

### 4.4 Adapters as explicit structural objects

Adapters transform payloads, units, semantics, or interaction protocols. Each adapter should have its own identity, version, contract, provenance, and tests. A chain of individually valid transformations is not automatically end-to-end valid; composition may amplify uncertainty or discard essential information.

An adapter should state whether its transformation is lossless, approximate, or information-losing, and identify which assumptions must be revalidated downstream.

## 5. Relay: A Governed Intelligence Handoff

### 5.1 Relay is more than function invocation

An intelligence relay may transfer a request, partial plan, model state summary, uncertainty estimate, evidence bundle, policy constraints, or responsibility for a bounded subtask. It may be synchronous or asynchronous; local or remote; between two programs, two models, or a human and a machine.

A relay is **successful** only when the receiving party can interpret the request adequately, process it within its permitted scope, and return an intelligible outcome or a well-defined failure. An HTTP success response alone is insufficient.

### 5.2 Minimal operation vocabulary

The following is a proposed protocol surface, not a deployed standard:

| Operation | Function |
|---|---|
| `describe` | Return identity, capabilities, contracts, constraints, and provenance |
| `match` | Assess contextual compatibility with a task requirement |
| `invoke` | Start a bounded execution under an explicit policy context |
| `status` | Report state, progress, or blocking conditions |
| `result` | Return output, evidence, uncertainty, and completion metadata |
| `cancel` | Request termination and report whether cancellation took effect |

Optional extensions include `delegate`, `handoff`, `evaluate`, `counterEvidence`, and `proposeGrowth`. A service must declare which operations it supports; optional operations should never be assumed.

### 5.3 A relay envelope

A conceptual relay request may be represented as:

```yaml
relay_request:
  session_id: "session-8f2c"
  trace_id: "trace-24ac"
  task_ref: "task:delivery-plan-42"
  capability_ref: "sif://research.example/capability/route-risk-estimation@1.2.0"
  contract_ref: "sif://research.example/contract/route-risk@1.2.0"
  payload_ref: "artifact:route-plan-42"
  context:
    region: "example-region"
    snapshot_timestamp: "2026-10-18T12:00:00Z"
  constraints:
    deadline_ms: 15000
    max_cost_units: 10
    side_effects_allowed: false
  authorization_ref: "authorization:read-only-572"
  evidence_requirements:
    - "method_version"
    - "uncertainty_statement"
    - "input_snapshot_id"
```

A production implementation should specify transport security, authentication, replay prevention, data retention, privacy, idempotency, and error behavior. The example intentionally avoids embedding credentials.

### 5.4 Relay lifecycle

A defensible default lifecycle is:

1. **Discover** candidate capabilities through the SCM and Structural Precedent Registry.
2. **Resolve** exact identities and immutable contract versions.
3. **Match** task requirements, semantic types, assumptions, and context.
4. **Plan** any required adapters and multi-hop relay path.
5. **Validate** path-level constraints and supporting evidence.
6. **Authorize** the intended action and resource budget.
7. **Invoke** with a traceable, bounded relay envelope.
8. **Verify** outputs, effects, evidence, and failure conditions.
9. **Record** results and counter-evidence as candidate precedents.
10. **Grow** the architecture when persistent residuals justify new structures.

This is a logical sequence, not a mandate that all steps occur in one centralized service.

## 6. Relay Across the Problem–Capability Dual Maps

SIF-008 distinguishes the **Problem-Solving Map (PSM)** from the **Capability Map (SCM)**. UNT-R supplies their interoperability substrate.

```text
Problem-Solving Map (requirements, constraints, dependencies)
             |
             v
    Naming + Typing + Match
             |
             v
Structural Precedent Registry <--> Capability Map
             |
             v
     Contracted Relay Path
             |
             v
  Execution + Evidence + Audit
             |
             v
     Residual / New Precedent
```

The mapping is bidirectional. A new task can seek a previously validated capability; a newly registered capability can also suggest previously infeasible tasks. Such reverse discovery is exploratory until tested against real requirements and constraints.

A multi-hop relay path may contain a sequence of capabilities \(C_1,\ldots,C_n\) and adapters \(A_1,\ldots,A_{n-1}\). Path validity cannot be inferred solely from pairwise input/output type compatibility:

\[
\operatorname{ValidPath}(P,X)
\not\Leftarrow
\bigwedge_i \operatorname{TypeMatch}(C_i,A_i,C_{i+1}).
\]

End-to-end validation must also examine preserved meaning, uncertainty, permissions, latency, resource use, and cumulative side effects.

## 7. Structural Intelligence Contracts as the Unit of Interoperability

A **Structural Intelligence Contract (SIC)** is a versioned declaration that binds an intelligence structure to an externally inspectable interface. A candidate contract includes:

| Contract section | Required question |
|---|---|
| Identity and version | What exactly is this structure? |
| Capability and signatures | What can it accept and produce? |
| Context and assumptions | Where are claims applicable? |
| Relay and execution | How is it called, delegated to, or cancelled? |
| Evidence and counter-evidence | What supports or challenges its use? |
| Policy and authority | Who may invoke it and with what effects? |
| Resources and observability | What budgets, traces, and measurements apply? |
| Lifecycle and growth hooks | How is it updated, deprecated, challenged, or replaced? |

SIC is compatible in spirit with the distinction between **Portable Intelligence Runtime Pieces (PIRP)** and **Portable Intelligence Runtime Units (PIRU)**: flexible pieces may enter through adapters and progressive formalization, while more mature units can expose stronger conformance guarantees. UNT-R must not exclude promising intelligence merely because it lacks a complete formal contract; instead, it should restrict what such a component may claim or do until evidence improves.

## 8. Context Relay and Information Preservation

### 8.1 Relay context is selective, not unlimited

Passing all context is expensive and may violate privacy or security boundaries. Passing too little context can invalidate semantics. SIF therefore needs **context sufficiency tests** rather than a simple preference for maximal context transfer.

A relay context manifest should identify:

- source and version of relevant observations;
- assumptions and excluded information;
- provenance, freshness, and uncertainty;
- transformation history and known information loss;
- purpose limitation, confidentiality, and retention policy.

### 8.2 Structural context versus raw context

A receiving capability may need a structured task decomposition, CCC signature, MDT node path, world-state snapshot, or evidence digest rather than a full conversation transcript. Such compression can improve efficiency, but only if the receiving operation's required distinctions are preserved.

A critical research question is how to measure **task-relative semantic preservation** under context folding and relay. No general preservation guarantee is assumed.

### 8.3 Context-bound tokens and progressive naming

Context-bound tokens (CBT) and Universal Type/Name approaches can offer local shorthand within known scopes. UNT-R should make those scopes explicit and support resolution into portable descriptions when crossing a boundary. Local identifiers are useful; silent cross-context equivalence is dangerous.

## 9. Governance, Security, and Failure Semantics

### 9.1 Separate three planes

UNT-R must work with SIF's Universal Control Planes rather than collapse them:

- **Policy and Authority:** determines whether a requested action is permitted.
- **Scoring and Decision:** ranks candidates and plans using contextual objectives.
- **Evidence and Audit:** records why a candidate was selected, what occurred, and what contradicted the expectation.

**Evaluation does not imply authorization.** A highly scored relay path may remain prohibited, and an authorized path may still require independent performance verification.

### 9.2 Threat and failure model

| Failure mode | Consequence | Proposed mitigation |
|---|---|---|
| Identifier collision or spoofing | Wrong structure invoked | Authority verification, immutable version pinning |
| Schema-valid semantic mismatch | Plausible but incorrect result | Semantic constraints, independent validation |
| Context omission | Hidden assumption violated | Context manifests and sufficiency checks |
| Adapter drift | Meaning changes across hops | Versioned adapters and end-to-end tests |
| Policy laundering via delegation | Unauthorized downstream action | Delegation scope and per-hop authorization |
| Evidence laundering | Weak claims appear validated | Provenance, evaluator independence, counter-evidence |
| Partial failure or retry duplication | Repeated side effects | Idempotency keys, compensating actions where possible |
| Unbounded relay loops | Resource exhaustion | Hop limits, budgets, cycle detection |
| Privacy leakage | Sensitive data crosses boundaries | Least privilege, minimization, purpose controls |
| Registry poisoning | Malicious or low-quality precedents | Curation, attestations, challenge and quarantine |

### 9.3 Fail closed for consequential actions

If identity, authorization, or critical semantics cannot be verified, consequential action should be refused or escalated. Lower-risk exploratory matching can retain an `unknown` or `conditional` status without pretending that compatibility has been established.

Cancellation may be best-effort when irreversible side effects have already occurred. Protocols must report that distinction honestly.

## 10. Conceptual Example: Heterogeneous Supply-Chain Planning

Consider a request to propose a distribution plan under cost, timing, and disruption-risk constraints. A candidate structural workflow is:

1. An **LLM planner** translates a natural-language objective into a draft PSM with explicit uncertainties.
2. A **CCC/MDT localization service** identifies relevant precedents and candidate capability signatures.
3. An **optimization engine** proposes feasible plans under declared mathematical constraints.
4. A **simulation or world-model service** tests scenarios and identifies sensitivity to assumptions.
5. A **scoring forest** compares cost, robustness, delay, and risk under the user's policy profile.
6. An **independent evaluator** challenges the plan with adversarial scenarios and counter-evidence.
7. A **policy service** decides whether a plan may be recommended, shadow-tested, or executed.

UNT-R provides stable references and versioned contracts for each capability, typed adapters between outputs and inputs, and relay envelopes carrying assumptions, budgets, and evidence requirements.

Suppose the optimization engine produces a route plan in kilometers, but the simulation service expects miles. A unit adapter can handle that syntactic/dimensional conversion. More subtle is a mismatch between *average transit time* and *tail-delay risk*: a valid unit conversion cannot resolve that semantic gap. The relay planner must detect the distinction, seek an appropriate risk model, or record a residual rather than quietly treating the metrics as equivalent.

If the simulation service lacks validation for a new geographic region, the registry should preserve that limitation. The architecture may propose sandbox evaluation in that region, but it should not promote the capability to validated production use merely because a relay succeeded technically.

This is an **illustrative workflow**, not an empirical demonstration.

## 11. UNT-R and Open Structural Growth

UNT-R is not only an execution interface; it can expose where the intelligence ecosystem is incomplete.

Examples of interoperability residuals include:

- **Naming residual:** an important capability exists but cannot be discovered or resolved reliably.
- **Typing residual:** available representations cannot express a required distinction.
- **Adapter residual:** translation loses essential semantics or uncertainty.
- **Relay residual:** a task cannot be safely delegated across a boundary.
- **Evidence residual:** compatibility is plausible but unvalidated.
- **Policy residual:** capability exists, but permitted authority is absent or ambiguous.
- **Perspective residual:** the current ontology cannot describe the problem adequately.

A growth proposal may introduce a new adapter, a refined type, a more specialized node, a richer contract, a new evaluation protocol, or a higher-order **Macro-Intelligence Piece**. Every proposal should be tested in the Multi-Intelligence Adversarial Sandbox (MIAS), compared against a baseline, and admitted to production only under appropriate governance.

Open-ended growth therefore does not mean unconstrained automatic deployment. It means the architecture can *propose and evaluate* new intelligence structures without presuming its current vocabulary is complete.

## 12. Proposed Research Hypotheses

The following are testable propositions, not established findings.

**H1 — Discovery quality.** Contextual identity and semantic typing improve relevant capability retrieval compared with name-only or embedding-only search.

**H2 — Relay correctness.** Typed, versioned contracts reduce silent cross-component semantic failures compared with ad hoc tool-call descriptions.

**H3 — Reproducibility.** Immutable version pinning and provenance increase the reproducibility of precedent-based structural workflows.

**H4 — Adapter accountability.** Explicit adapter contracts and end-to-end validation detect more composition errors than pairwise schema checks alone.

**H5 — Governance separation.** Distinguishing evaluation from authorization reduces policy-violating executions under adversarial delegation tests.

**H6 — Context efficiency.** Task-relative structural context manifests can reduce relay payload cost while preserving required decision quality within specified domains.

**H7 — Growth discovery.** Logging typed interoperability residuals yields more actionable candidate improvements than recording undifferentiated execution failures.

**H8 — Openness.** A minimal SIC/UNT-R boundary admits heterogeneous new capability families with lower integration cost than a framework requiring one shared internal representation.

Each hypothesis requires explicit baselines, workload distributions, failure definitions, and independent replication before general conclusions can be drawn.

## 13. Validation Roadmap

### Phase A — Contract vocabulary and conformance

Define a small candidate type system, identity model, relay envelope, and failure taxonomy. Test schema validity, version resolution, cancellation reporting, and negative cases. Publish conformance fixtures rather than declaring a universal standard.

### Phase B — Heterogeneous relay benchmark

Use at least three substantially different component families (for example, LLM, optimizer, and simulator) with controlled semantic mismatches. Measure match precision, false-compatible rates, adapter errors, and end-to-end task outcomes.

### Phase C — Precedent-guided mapping

Connect UNT-R to the PSM/SCM dual maps and Structural Precedent Registry. Compare direct retrieval with contract-aware retrieval and adaptation. Track provenance completeness and reproducibility.

### Phase D — Adversarial sandbox

Challenge identifier integrity, ontology mismatches, context truncation, delegation boundaries, and evaluator reliability. Include independent counter-evidence and explicit rollback or quarantine criteria.

### Phase E — Bounded structural evolution

Allow candidate adapters, new types, and macro-nodes to be proposed in an isolated environment. Evaluate whether the system can improve integration quality without silently expanding deployment authority.

Recommended measurements include compatibility precision/recall, semantic failure rate, unauthorized-action rate, evidence completeness, latency, cost, reproducibility, and improvement under distribution shift. Report negative results and tradeoffs, not only successful demonstrations.

## 14. Open Questions

1. What is the smallest interoperable contract that preserves useful semantic distinctions across heterogeneous intelligence families?
2. Which semantic claims can be checked mechanically, and which require empirical or human judgment?
3. How should identity and authority be federated across independent registries without a single trusted central operator?
4. How can relay preserve uncertainty, counter-evidence, and provenance through long multi-hop chains?
5. What makes two capabilities behaviorally substitutable under a specific context and risk profile?
6. How should partial failures, retries, cancellation, and irreversible effects be represented across nested delegation?
7. When should a new semantic type be introduced rather than adapting an existing type?
8. How can the evaluator itself be challenged without unbounded recursive evaluation cost?
9. Can structural context folding yield measurable efficiency gains without sacrificing crucial distinctions?
10. How should UNT-R evolve as new perspectives make previous ontologies inadequate?

## 15. Relationship to the SIF Research Program

This paper develops the interoperability layer foreshadowed by the SIF foundation and functional-domain papers:

- **SIF-001:** Open Structural Intelligence as an evolving architecture.
- **SIF-002:** Four Functional Domains and their cross-cutting interfaces.
- **SIF-003:** Structural precedents as context-bound, evidence-bearing reusable claims.
- **SIF-004:** Localization and intelligence addressing.
- **SIF-005:** Heterogeneous per-node capabilities.
- **SIF-006:** Universal Control Planes and scoring/folding.
- **SIF-007:** Residual-based structural growth.
- **SIF-008:** Problem–Capability dual maps and bidirectional mapping.
- **SIF-009:** Structural Precedent Registry.
- **SIF-011 (planned):** Structural Intelligence Contracts and Portable Units.
- **SPEC-001 (planned):** Candidate Structural Intelligence Contract.
- **SPEC-002 (planned):** Candidate Universal Name, Type, and Relay API.

UNT-R also builds conceptually on the broader research directions of Metric Differential Trees, context-bound tokens, portable intelligence pieces/units, CallingGraph orchestration, structural folding, and policy-controlled growth. These relationships indicate research continuity; they do not establish implementation interoperability among those projects.

## 16. Conclusion

The intelligence ecology envisioned by SIF cannot be made open merely by adding more models, plugins, or APIs. It needs durable ways to identify structures, express contextual capability claims, relay work across heterogeneous boundaries, and preserve the evidence and authority that make such relays accountable.

**Universal Naming, Typing, and Relay (UNT-R)** proposes that substrate. Naming anchors identity; typing makes assumptions and semantic constraints inspectable; relay carries bounded work, context, and evidence between participants. Structural Intelligence Contracts tie these elements together without demanding uniform internal intelligence.

The long-term ambition is not a universal vocabulary that freezes the future. It is an evolvable interoperability discipline in which new structures and perspectives can enter, be tested, coexist, and eventually replace inadequate precedents—while failures remain visible and action remains governed.

> **Standardize the contract, not the intelligence. Preserve the evidence, not merely the output. Govern the action, not the possibility of discovery.**

---

## Suggested Figure Placement

The following figures are planned assets and are not embedded in this manuscript:

| Figure | Suggested placement | Purpose |
|---|---|---|
| `Fig-004-Universal-Contracts-and-Relay.png` | After §5.4 | Naming–Typing–Relay, SIC, and handoff architecture |
| `Fig-003-Problem-Capability-Dual-Maps.png` | After §6 | PSM–SCM mapping and registry bridge |
| `Fig-005-Structural-Precedent-Intelligence.png` | After §7 | Contract and precedent evidence relationships |
| `Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` | After §11 | Testing new adapters and relay candidates |
| `Fig-007-Structural-Growth-and-Evolution-Loop.png` | After §13 | Residual-to-growth lifecycle |

## Citation and Status Note

**Suggested citation:** Tan, S., & GPT-Obot. (2026). *SIF-010: Universal Naming, Typing, and Relay*. Structural Intelligence Framework, v1.0.0. Repository manuscript. DOI to be added after archival release.

This document is a research proposal. Its illustrative URI scheme, YAML structures, protocol operations, and formal expressions are not ratified standards, deployed services, or empirical performance claims. Any future normative specification should state conformance levels, security requirements, backward-compatibility rules, and validation procedures separately.
