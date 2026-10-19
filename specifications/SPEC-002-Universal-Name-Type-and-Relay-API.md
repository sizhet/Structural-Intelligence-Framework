# SPEC-002 — Universal Name, Type, and Relay API

**Project:** Structural Intelligence Framework (SIF)  
**Status:** Candidate Research Specification — v0.1.0 (non-normative, experimental)  
**Authors:** Sizhe Tan & GPT-Obot  
**Date:** 2026-10-18  
**License:** Apache-2.0  
**Companion:** `SPEC-001-SIF-Structural-Intelligence-Contract.md`

> **Design principle:** Standardize the boundary, not the intelligence. Naming makes a structure addressable; typing makes its claims interpretable; relay makes its participation observable and governable.

## Abstract

The Structural Intelligence Framework (SIF) proposes an open architecture in which heterogeneous intelligence structures can be discovered, matched, composed, evaluated, and evolved. This candidate specification defines **Universal Name, Type, and Relay (UNT-R)** as a minimal interoperability boundary. It specifies identifier syntax and resolution expectations, a layered type envelope, six baseline relay operations, message and session semantics, policy checkpoints, evidence and provenance hooks, and a testable conformance profile. It does not prescribe an internal intelligence algorithm, a global centralized registry, a transport protocol, or an unconditional right to invoke any capability. All examples are illustrative design proposals, not evidence of deployed interoperability.

## 1. Scope, Status, and Normative Language

This document defines a **candidate interface contract** for exchanging structural intelligence capabilities among independent systems, including LLM-based agents, rule engines, optimizers, simulators, specialized services, and composite Macro-Intelligence Pieces. It covers:

- Stable references to capabilities, contracts, precedents, evidence, sessions, and revisions.
- Machine-readable type claims, including semantic, contextual, evidence, and governance constraints.
- Discovery, compatibility matching, execution, monitoring, result retrieval, and cancellation.
- Relay across trust boundaries with auditable provenance and explicit authorization.
- Lifecycle, failure handling, and conformance testing.

It does **not** define a universal ontology, a proof that two independently authored semantic types are equivalent, a universal scoring function, or an automated grant of production authority. Requirements using **MUST**, **SHOULD**, and **MAY** are *proposed requirements within this candidate specification*, not claims of external standardization.

## 2. Architectural Position

UNT-R is a cross-cutting interoperability substrate for SIF's four functional domains:

1. **Localization:** resolve intelligence addresses and identify compatible capabilities.
2. **Per-Node Intelligence:** expose heterogeneous algorithms behind typed, declared interfaces.
3. **Control Planes and Scoring:** preserve policy, evaluation, and audit distinctions across relays.
4. **Residual-Based Growth:** capture incompatibilities and failures as diagnosable structural residuals.

Its principal participants are:

| Participant | Responsibility | Not automatically entitled to |
| --- | --- | --- |
| Capability provider | Publish description and implement declared operations | Production invocation by any caller |
| Registry / resolver | Resolve identifiers and versioned metadata | Assert correctness of all declarations |
| Client / orchestrator | Discover, match, invoke, track, and cancel | Override provider policy |
| Policy authority | Decide whether a particular action is permitted | Rewrite independent evaluation evidence |
| Evaluator / challenger | Test claims and register counter-evidence | Grant deployment authority |
| Audit store | Preserve provenance and decision records | Declare every record true |

A SIF Structural Intelligence Contract (SIC) describes a capability's claims and boundaries; UNT-R supplies a portable envelope and exchange protocol for those claims. The **Structural Precedent Registry (SPR)** stores examples of use, including negative cases. The **Problem-Solving Map (PSM)** and **Capability Map (SCM)** use UNT-R references to connect demand to supply.

## 3. Core Data Model

### 3.1 Identifier classes

Every externally referenced object MUST declare an `id`, a `kind`, and a `revision` or an explicit immutable content reference. Suggested kinds are:

- `capability`: an addressable intelligence function or composite unit.
- `contract`: the versioned SIC defining its advertised boundary.
- `type`: a type or schema declaration.
- `precedent`: an observed application or failure case.
- `evidence`: a provenance-bearing test or observation record.
- `session`: an invocation or multi-step relay execution.
- `policy`: an authority-scoped policy declaration.
- `artifact`: a referenced input, output, or trace object.

A proposed interoperable URI pattern is:

```text
sif://<authority>/<kind>/<local-id>@<revision>
```

Examples:

```text
sif://lab.example/capability/route-optimizer@1.2.0
sif://lab.example/contract/route-optimizer-sic@1.2.0
sif://lab.example/type/delivery-plan@2.0.0
sif://lab.example/evidence/ev-7f39@1
```

The `sif://` scheme is a **research proposal** and is not asserted to be an IANA-registered URI scheme. Implementations MAY use HTTPS identifiers or URNs and MUST retain the declared scheme without silently rewriting identity.

### 3.2 Identity and revision rules

- An identifier MUST be unique within its authority and kind.
- A revision MUST refer to a stable declaration; incompatible contract changes SHOULD require a new revision.
- Resolution MUST return the requested revision or an explicit `not_found` / `revision_unavailable` error; it MUST NOT silently substitute a newer revision.
- A mutable alias such as `latest` MAY exist but MUST resolve to a concrete revision before invocation.
- Resolved declarations SHOULD include integrity information (e.g., content digest) and an authenticated publisher identity where feasible.
- Names are **references**, not trust proofs. A resolver's successful response does not imply correctness, endorsement, or authorization.

### 3.3 Resolution record

```yaml
id: sif://lab.example/capability/route-optimizer@1.2.0
kind: capability
revision: 1.2.0
publisher:
  id: org:lab.example
  authentication: verified-by-deployment-trust-store
contract_ref: sif://lab.example/contract/route-optimizer-sic@1.2.0
endpoint:
  transport: https
  url: https://api.lab.example/sif/relay
integrity:
  algorithm: sha256
  digest: "<illustrative-digest>"
status: active
```

The URL and digest above are placeholders; they are not live endpoints or verifiable digests.

## 4. Universal Typing: A Layered Type Envelope

A wire-format schema alone cannot establish behavioral equivalence. UNT-R therefore separates multiple compatibility dimensions:

| Layer | Question | Typical declaration |
| --- | --- | --- |
| Syntactic | Can the payload be decoded? | JSON Schema / protobuf schema ref |
| Semantic | What do the fields mean? | Units, ontology refs, domain concepts |
| Contextual | Under which assumptions is it valid? | Geography, time horizon, granularity |
| Behavioral | What does the capability promise to do? | Pre/postconditions, side effects |
| Evidence | What supports the claim? | Evaluation references, uncertainty |
| Governance | May this operation be performed here? | Data restrictions, authority scope |
| Resource | Is execution feasible? | Latency, cost, compute budget |

A minimal proposed `type_claim` is:

```yaml
type_claim:
  schema_ref: sif://lab.example/type/delivery-plan@2.0.0
  semantic_profile: logistics.delivery-plan.v2
  units:
    distance: km
    duration: min
  context:
    geography: regional
    planning_horizon: "24h"
  behavior:
    side_effects: none
    deterministic: false
  evidence_refs: []
  policy_tags: [internal-planning]
```

### 4.1 Compatibility is a claim to be tested

For a proposed relay edge from output `A` to input `B`, the compatibility decision is not a Boolean determined by matching labels alone. A candidate decision record SHOULD distinguish:

```text
syntactic_fit
semantic_fit
context_fit
behavioral_fit
evidence_sufficiency
policy_permission
resource_feasibility
```

Each dimension MAY be `pass`, `fail`, or `unknown`, with supporting reasons and evidence references. **Unknown is not pass.** A transformation adapter MAY bridge a mismatch, but its own contract, assumptions, provenance, and validation MUST be tracked. An implementation MUST NOT infer policy permission from a high similarity score.

### 4.2 Type variance and adaptation

A provider MAY accept a broader input type than requested or return a more specific output type, provided a documented compatibility rule validates the substitution. When semantic conversion, unit conversion, or context reinterpretation is needed, a distinct adapter SHOULD be named and versioned. Lossy adaptation MUST declare information lost and conditions under which the result remains usable.

## 5. Relay Envelope

All six baseline operations use a common envelope. Transport bindings MAY map the envelope to HTTP, message queues, local function calls, or other mechanisms, but MUST preserve correlation and error semantics.

```json
{
  "protocol": "sif-unt-r/0.1",
  "message_id": "msg-0042",
  "operation": "match",
  "timestamp": "2026-10-18T16:00:00Z",
  "caller": "org:planning-team",
  "target": "sif://lab.example/capability/route-optimizer@1.2.0",
  "contract_ref": "sif://lab.example/contract/route-optimizer-sic@1.2.0",
  "correlation_id": "trace-9001",
  "session_id": null,
  "context_ref": "artifact:ctx-22",
  "policy_context_ref": "policy:planning-only-v3",
  "payload": {},
  "extensions": {}
}
```

Required request fields: `protocol`, `message_id`, `operation`, `caller`, `target` (except registry-wide discovery), `correlation_id`, and `payload`. A production binding MUST authenticate the caller and MUST NOT treat the unauthenticated `caller` string as proof of identity. Responses MUST correlate to `message_id` and include `outcome` (`ok`, `rejected`, or `error`).

Large payloads MAY be referenced by content-addressed artifacts rather than inlined. References MUST carry access controls, retention rules, and integrity metadata appropriate to the sensitivity of the content.

## 6. Six Baseline Operations

### 6.1 `describe`

**Purpose:** Obtain a versioned declaration of capability and contract metadata.

**Input:** `target`, optional requested contract revision, and desired fields.  
**Output:** resolved identity, revision, type claims, capability signatures, supported operations, evidence references, policy requirements, and endpoint metadata.

**Requirements:** The response MUST distinguish publisher-declared claims from independently verified evidence. It MUST NOT reveal restricted metadata to unauthorized callers.

### 6.2 `match`

**Purpose:** Evaluate a proposed capability against a task or another capability boundary.

**Input:** task signature or output/input pair, context, required evidence threshold, policy context, resource budget.  
**Output:** per-dimension compatibility assessment, unmet constraints, candidate adapters, evidence, and reasons.

**Requirements:** `match` MUST be non-executing. A favorable result MUST NOT authorize `invoke`. A mismatch SHOULD emit a typed residual for possible SIF growth analysis.

Example response:

```json
{
  "reply_to": "msg-0042",
  "outcome": "ok",
  "match": {
    "syntactic_fit": "pass",
    "semantic_fit": "pass",
    "context_fit": "unknown",
    "behavioral_fit": "pass",
    "evidence_sufficiency": "unknown",
    "policy_permission": "unknown",
    "resource_feasibility": "pass"
  },
  "decision": "needs_review",
  "reasons": ["Planning horizon not established", "Evidence profile not independently validated"],
  "residuals": ["context_gap", "evidence_gap"]
}
```

### 6.3 `invoke`

**Purpose:** Request execution of a declared capability.

**Input:** validated payload, contract revision, context, budget, requested side effects, authorization proof or reference, idempotency key where appropriate.  
**Output:** session reference and initial status, or an explicit rejection.

**Requirements:** The provider MUST perform an invocation-time policy check. It MUST validate the concrete contract revision and input constraints. Non-idempotent actions MUST declare replay behavior. A prior `match` result is insufficient authority. High-impact actions SHOULD require separate approval under the governing deployment policy.

### 6.4 `status`

**Purpose:** Observe an execution session without assuming completion.

**Input:** session reference.  
**Output:** lifecycle state, timestamps, progress where available, resource usage, and error indicators.

Proposed session states: `created`, `authorized`, `queued`, `running`, `completed`, `failed`, `cancel_requested`, `cancelled`, `expired`. Transitions MUST be recorded and SHOULD be auditable.

### 6.5 `result`

**Purpose:** Retrieve a completed or partially available outcome.

**Input:** session reference and desired result scope.  
**Output:** typed output or artifact reference, provenance, versioned contract reference, evidence and uncertainty metadata, side-effect record, and terminal status.

**Requirements:** A `completed` execution state MUST NOT by itself imply that the result is correct or independently validated. Consumers MUST receive sufficient metadata to distinguish observed output from validated claims.

### 6.6 `cancel`

**Purpose:** Request termination of an active session.

**Input:** session reference, reason, requester authority.  
**Output:** accepted/rejected cancellation request, current state, and cleanup semantics.

**Requirements:** Cancellation MUST be treated as a request, not a guarantee of rollback. Providers MUST disclose irreversible side effects and whether cancellation is best-effort. A repeated cancel request SHOULD be idempotent.

## 7. Optional Advanced Operations

The following are extensions and MUST NOT be required for the baseline profile:

| Operation | Function | Additional safeguards |
| --- | --- | --- |
| `delegate` | Grant bounded subtask execution to another capability | Explicit delegated scope and expiry |
| `handoff` | Transfer a session or partial work state | Provenance, context integrity, receiving authority |
| `evaluate` | Submit a result or claim for assessment | Evaluator independence disclosure |
| `counterEvidence` | Register structured refutation or boundary failure | Traceable evidence, contestability |
| `proposeGrowth` | Submit a candidate adapter, capability, or contract revision | Sandbox-only until validated and authorized |

Implementations MUST NOT interpret support for `delegate` as unlimited onward delegation. Delegation chains SHOULD be depth-limited, budget-limited, and recorded.

## 8. Session and Context Continuity

A relay session binds the invocation to a concrete capability revision, contract revision, caller authority, policy decision, and contextual assumptions. The minimum proposed record is:

```yaml
session_id: session:relay-17
capability_ref: sif://lab.example/capability/route-optimizer@1.2.0
contract_ref: sif://lab.example/contract/route-optimizer-sic@1.2.0
caller_principal: org:planning-team
policy_decision_ref: evidence:authorization-88
context_ref: artifact:ctx-22
input_ref: artifact:input-91
state: running
trace_ref: artifact:trace-17
budget:
  max_runtime_seconds: 60
  max_cost_units: 10
```

### 8.1 Context preservation rules

A handoff SHOULD retain the assumptions, units, confidence and uncertainty descriptors, data lineage, time scope, and unresolved questions relevant to downstream interpretation. It MUST NOT silently discard a known material constraint. When context is truncated or summarized, the relay SHOULD expose a `context_loss` record and identify affected claims.

### 8.2 Cross-boundary failure containment

An unavailable downstream capability MUST NOT be represented as successful execution. Timeouts, partial completion, retries, and duplicate deliveries MUST be separately representable. For multi-node workflows, the orchestrator SHOULD preserve a trace graph linking each relay edge to its contracts and policy decisions.

## 9. Error and Residual Taxonomy

Responses with `outcome: rejected` or `outcome: error` SHOULD use stable error codes:

| Code | Meaning | Possible structural residual |
| --- | --- | --- |
| `not_found` | Unknown identifier | localization_gap |
| `revision_unavailable` | Requested revision missing | version_gap |
| `type_mismatch` | Payload or signature incompatibility | representation_gap |
| `semantic_ambiguity` | Meaning cannot be established | semantic_gap |
| `context_missing` | Required assumptions absent | context_gap |
| `evidence_insufficient` | Required validation unavailable | evidence_gap |
| `policy_denied` | Action not authorized | governance_boundary |
| `budget_exceeded` | Resources inadequate | resource_gap |
| `downstream_unavailable` | Relay target failed or timed out | composition_gap |
| `contract_violation` | Observed behavior conflicts with declaration | structural_counter_evidence |
| `cancel_not_guaranteed` | Cancellation cannot undo side effects | lifecycle_boundary |

**Important:** A policy denial is not necessarily an intelligence deficiency. The growth laboratory MAY record it for analysis but MUST NOT treat governance circumvention as a valid growth objective.

## 10. Trust, Security, and Governance

UNT-R introduces interoperability, not universal trust. Implementations SHOULD adopt a zero-trust posture across organizational boundaries.

1. **Authentication:** verify caller and provider identities independently of envelope text.
2. **Authorization:** evaluate operation, data scope, side effects, budget, and delegated authority at invocation time.
3. **Least privilege:** restrict capability access and data sharing to task-specific necessity.
4. **Integrity:** verify contract and artifact digests or signatures where supported.
5. **Confidentiality:** protect sensitive inputs, outputs, traces, and evidence references in transit and at rest.
6. **Replay safety:** use bounded idempotency keys and explicit retry rules for side-effecting operations.
7. **Auditability:** retain decision provenance and contract revisions subject to retention and privacy policies.
8. **Evaluator separation:** keep performance assessment separate from action authorization.
9. **Sandbox separation:** candidate growth structures MUST NOT receive production authority solely because they passed a local test.

Evidence may be incomplete, biased, fabricated, or stale. A successful transport exchange does not establish epistemic reliability.

## 11. Relationship to SIF Structural Intelligence Contracts

SPEC-001 defines what a Structural Intelligence Contract can claim. This specification defines how such claims are named, interpreted, and exchanged. A proposed compatibility mapping is:

| SIC dimension | UNT-R representation |
| --- | --- |
| Identity | `id`, `kind`, `revision`, publisher |
| Type | `type_claim`, schema and semantic profile |
| Capability | `describe` output and advertised signatures |
| Signature | `match` input/output constraints |
| Context | `context_ref`, contextual fit, loss record |
| Relay | six baseline operations and session envelope |
| Evidence | evidence references, validation status, counter-evidence |
| Policy | authority references and invocation-time checks |
| Lifecycle | status, cancel, revision and deprecation semantics |
| Growth | residuals and optional `proposeGrowth` |

This mapping is intentionally minimal. A future version may define canonical JSON Schema files and machine-testable semantic profiles once competing design choices have been evaluated.

## 12. PIRP, PIRU, and Macro-Intelligence Compatibility

A flexible **Portable Intelligence Runtime Piece (PIRP)** MAY publish only a discovery-grade contract while still being exploratory. A more formal **Portable Intelligence Runtime Unit (PIRU)** SHOULD provide typed invocation and verifiable operational boundaries. A **Macro-Intelligence Piece** may expose the same outer contract while internally orchestrating multiple units. However, the macro-unit MUST not hide materially relevant side effects, evidence limitations, or policy requirements of its constituents.

A candidate conformance ladder is:

| Profile | Required support | Intended use |
| --- | --- | --- |
| **U0 — Discoverable** | Stable identity, `describe`, basic type claims | Registry and exploration |
| **U1 — Matchable** | U0 + `match`, contextual constraints, reason codes | Planning and composition |
| **U2 — Runnable** | U1 + `invoke`, `status`, `result`, `cancel`, session trace | Controlled execution |
| **U3 — Governed** | U2 + authenticated authorization, evidence references, auditable decisions, explicit failure semantics | Governed operational deployment |

These profiles are **proposed test targets**, not third-party certifications. A U3 claim requires demonstrated controls; a label alone is insufficient.

## 13. Worked Example: Multi-Node Logistics Planning

Consider a planning workflow involving an LLM problem interpreter, a demand forecaster, a route optimizer, and a simulation-based challenger.

**Step A — Discovery:** The orchestrator resolves each capability to an immutable contract revision and records the available signatures.

**Step B — Match:** The forecaster's output declares daily demand by region. The optimizer requires hourly delivery demand by zone. The semantic labels are related, but `match` returns `context_fit: fail` because temporal and geographic granularities differ.

**Step C — Adaptation:** A separately named, versioned disaggregation adapter is proposed. Its uncertainty assumptions are disclosed; it is not accepted merely because its JSON output conforms.

**Step D — Authorization:** The planning policy allows simulation but prohibits dispatching real vehicles. `invoke` of the optimizer is authorized in simulation mode only.

**Step E — Execution:** Each session records input versions, contracts, policy decisions, runtime budget, and result provenance.

**Step F — Challenge:** A simulator tests demand spikes and disrupted roads. If the plan violates robustness claims, the result is registered as counter-evidence against the relevant precedent and contract assumptions.

**Step G — Growth:** The residual is diagnosed as a missing robust-optimization capability or an inadequate adapter, rather than being hidden behind a successful transport-level invocation.

This example illustrates why naming, typing, relay, and validation must remain distinct.

## 14. Conformance Test Matrix (Proposed)

| ID | Test | Expected result |
| --- | --- | --- |
| UNT-01 | Resolve exact capability revision | Exact declaration or explicit failure |
| UNT-02 | Resolve mutable alias | Concrete revision returned before use |
| UNT-03 | Present invalid caller credentials | Authentication rejection |
| UNT-04 | Request incompatible schema | `type_mismatch` with reason |
| UNT-05 | Request semantically ambiguous mapping | `unknown` / `semantic_ambiguity`, not silent pass |
| UNT-06 | Omit required context | `context_missing` |
| UNT-07 | Call `match` with no execution authority | No side effects |
| UNT-08 | Invoke after positive match but without permission | `policy_denied` |
| UNT-09 | Invoke with stale contract revision | Explicit revision error or authorized renegotiation |
| UNT-10 | Retry non-idempotent invocation | No silent duplicate action |
| UNT-11 | Cancel a running session | Explicit accepted/rejected and side-effect disclosure |
| UNT-12 | Request result before completion | Nonterminal status, not fabricated result |
| UNT-13 | Downstream relay times out | `downstream_unavailable` and trace continuity |
| UNT-14 | Lossy context adapter executes | Recorded `context_loss` |
| UNT-15 | Evaluator finds a contract violation | Traceable counter-evidence record |
| UNT-16 | Candidate sandbox unit requests production action | Denial without separate authorization |
| UNT-17 | Macro-unit hides restricted side effect | Contract/conformance failure |
| UNT-18 | Policy denial is sent to growth analysis | Retained as governance boundary, not bypass target |

A future conformance suite SHOULD include adversarial malformed inputs, cross-version tests, federated registry resolution, and independent evaluator disagreement.

## 15. Research Hypotheses and Validation Roadmap

The following are **hypotheses**, not established empirical results:

- **H1:** Layered type compatibility reduces invalid compositions relative to schema-only matching.
- **H2:** Explicit context-loss records improve downstream calibration and failure diagnosis.
- **H3:** Stable versioned identifiers improve reproducibility of structural precedent reuse.
- **H4:** Separation of `match` from `invoke` reduces unauthorized side effects.
- **H5:** Relay traces with contract and policy references accelerate localization of multi-node failures.
- **H6:** Adapter-specific evidence improves robustness under cross-domain transfer.
- **H7:** A shared UNT-R envelope increases interoperability without forcing common internal algorithms.
- **H8:** Counter-evidence-linked relay records improve the quality of residual-driven structural growth.

Suggested evaluation sequence:

1. **Contract review:** compare proposed fields with existing tool/function interfaces and distributed-systems patterns.
2. **Minimal prototype:** implement two heterogeneous capabilities and a resolver with U0–U2 tests.
3. **Adversarial interoperability:** inject semantic mismatches, stale versions, context loss, and permission failures.
4. **Federated trial:** test independent authorities, provenance, and constrained delegation.
5. **Growth-loop experiment:** compare residual capture and adaptation outcomes with/without UNT-R metadata.

Measures SHOULD include invalid composition rate, false-compatible rate, authorization violations, trace completeness, adaptation overhead, latency, and robustness under distribution shift. Baselines and workloads must be published for credible comparisons.

## 16. Open Design Questions

1. Which identifier schemes should be adopted or bridged rather than inventing a new global naming authority?
2. How should semantic types express uncertainty, causality, and perspective-dependent meaning?
3. What is the smallest mandatory evidence envelope that remains useful across domains?
4. How can adapters prove or test compatibility without requiring full formal verification?
5. How should cross-organization delegation and revocation propagate through relay graphs?
6. What privacy-preserving audit patterns allow provenance without exposing sensitive data?
7. How should capability aliases, deprecation, and long-lived precedent references interact?
8. When should a macro-unit reveal its internal structure for audit, and to whom?
9. How can independent evaluators contest the registry's own type and compatibility judgments?
10. Which parts of UNT-R should remain protocol-neutral and which deserve concrete wire bindings?

## 17. Limitations and Non-Claims

UNT-R cannot guarantee that a capability is intelligent, that its output is correct, or that an evaluator is unbiased. Type metadata may be misleading; signatures can be overbroad; registry data can be stale; policy enforcement can be defective; and federated identity can fail. The proposal does not establish a new internet standard, verified security protocol, or deployed reference implementation. The conformance tests are a research agenda until independently implemented and evaluated.

## 18. Related SIF Documents and Figure Placement

- `SPEC-001-SIF-Structural-Intelligence-Contract.md` — companion contract schema and conformance profiles.
- `docs/interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md` — demand/capability graph mapping.
- `docs/interoperability/SIF-009-Structural-Precedent-Registry.md` — case and evidence storage.
- `docs/interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md` — conceptual foundations.
- `docs/interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md` — PIRP/PIRU composition.
- `docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md` — independent challenge and testing.
- `specifications/SPEC-003-Structural-Precedent-Registry-Schema.md` — planned registry schema.
- `specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md` — planned evidence lifecycle.

**Recommended illustration:** `figures/Fig-004-Universal-Contracts-and-Relay.png`, placed after Section 2 or Section 5, with a caption distinguishing the capability contract from the relay envelope. `figures/Fig-003-Problem-Capability-Dual-Maps.png` may be cited near Section 11; `figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` near Section 15.

## 19. Conclusion

Universal Name, Type, and Relay is proposed as the **interoperability membrane** of an open Structural Intelligence Framework. Names allow heterogeneous intelligence to be addressed; layered types make boundary assumptions explicit; relay operations enable controlled composition; and evidence, provenance, and policy preserve accountability across the resulting graphs. The central engineering discipline is to make interoperability **testable without pretending that interoperability implies truth or authority**.

> **Name the structure. Type the boundary. Relay the work. Preserve the evidence. Govern the action.**

---

**Citation:** Tan, S., & GPT-Obot. (2026). *SPEC-002 — Universal Name, Type, and Relay API*. Structural Intelligence Framework, candidate research specification v0.1.0.
