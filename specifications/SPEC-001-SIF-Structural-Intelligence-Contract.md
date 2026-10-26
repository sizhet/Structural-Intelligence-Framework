# SPEC-001 — SIF Structural Intelligence Contract (SIC)

**Project:** Structural Intelligence Framework (SIF)  
**Document ID:** SPEC-001  
**Status:** Candidate Research Specification — v0.1 (non-normative draft)  
**Repository release:** SIF v1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0  
**Related:** SIF-008, SIF-009, SIF-010, SIF-011, SIF-012, SIF-013, SPEC-002, SPEC-003, SPEC-004

> **Design principle:** Standardize the contract, not the intelligence. A claim of capability is not proof of capability; validation is not authorization.

## Abstract

The Structural Intelligence Contract (SIC) is a proposed, implementation-independent envelope for identifying, discovering, composing, invoking, evaluating, governing, and evolving heterogeneous intelligence capabilities. It applies to language models, deterministic algorithms, rules, simulations, structural search components, PIRP/PIRU units, and macro-intelligence pieces. The contract describes observable interfaces and claims, not internal cognition. This candidate specification distinguishes mandatory discovery metadata from optional execution, evidence, governance, and growth extensions; defines compatibility and lifecycle rules; and provides illustrative YAML, validation checks, and conformance tests. It is a research proposal, **not** a deployed standard or a claim of demonstrated interoperability.

## 1. Scope and non-goals

SIC addresses the boundary between a capability provider and its consumers, including the Structural Capability Map (SCM), Structural Problem-Solving Map (PSM), Structural Precedent Registry (SPR), Universal Naming, Typing and Relay (UNT-R), and Multi-Intelligence Adversarial Sandbox (MIAS).

It does **not** prescribe model architecture, training, optimization strategy, internal representation, a universal ontology, a universal scoring function, or automatic permission to act. It does not assert that a schema alone can prove semantic compatibility, safety, or intelligence. Implementations may use JSON, YAML, protobuf, or other serializations provided the same semantic constraints are preserved.

## 2. Conformance language and maturity

In this draft, **MUST**, **SHOULD**, and **MAY** express *proposed* requirements for experimental implementations. They do not represent ratified standards. A **descriptor** can be published without an executable endpoint; a **runnable unit** requires additional invocation and operational metadata. No external system should treat a descriptor's self-asserted claims as independently verified.

Three proposed profiles are defined:

| Profile | Purpose | Required components |
|---|---|---|
| `discovery` | Catalog and match a capability | Core identity, version, kind, description, signatures, context assumptions |
| `runnable` | Invoke and monitor a capability | Discovery + relay binding, input/output schemas, execution constraints, failure semantics |
| `governed` | Evaluate and control consequential deployment | Runnable + evidence references, policy references, provenance, audit and lifecycle metadata |

A profile is a **declared conformance target**, not a certification.

## 3. Core contract model

An SIC descriptor is a versioned record:

$$
\mathrm{SIC} = (I, T, C, S, X, R, E, P, L, G)
$$

where:

- **I — Identity:** stable identifier, version, provider, ownership, provenance.
- **T — Type:** kind and semantic classification, including representation and granularity.
- **C — Capability:** supported operations and claims, with explicit exclusions.
- **S — Signature:** typed inputs, outputs, effects, and pre/postconditions where expressible.
- **X — Context:** assumptions, jurisdiction/domain, temporal scope, dependencies, uncertainty.
- **R — Relay:** protocol, endpoint binding, status/cancellation, delegation constraints.
- **E — Evidence:** validation references, counter-evidence, coverage, evaluator provenance.
- **P — Policy:** authorization boundary, permissions, risk tier, human approval requirements.
- **L — Lifecycle:** maturity, deprecation, supersession, revocation and compatibility.
- **G — Growth:** observed residuals, adaptation hooks, experiment and candidate links.

The first five groups constitute the conceptual discovery envelope. Fields inside them have different cardinalities and some may explicitly contain `unknown`; see Section 4.

### 3.1 Structural identity

A capability's stable ID MUST be distinct from its human-readable display name. The combination `(id, version)` MUST identify an immutable published descriptor. A provider MAY publish a new descriptor version without changing the stable ID. A content digest SHOULD protect against accidental or malicious replacement. Identifiers are opaque: consumers MUST NOT infer capability, trust, or authorization solely from an identifier's spelling.

### 3.2 Capability versus precedent

A **capability definition** describes a reusable interface and its claims. A **precedent case** describes an observed application under specific conditions. An **evidence record** documents support or counter-evidence for a claim. These are different objects linked by stable references. A successful precedent MUST NOT silently upgrade a capability claim to universal applicability.

### 3.3 Portable pieces and units

A **PIRP** may be an exploratory intelligence piece with partial metadata and no stable execution contract. A **PIRU** is a more formal portable unit with explicit interfaces and validation expectations. The distinction is about contract maturity, not inherent intelligence. A macro-intelligence piece can also expose an SIC; its composite provenance and nested authorization boundaries SHOULD remain discoverable.

## 4. Proposed field schema

The following table identifies required fields by profile. `R` means required; `O` means optional; `—` means not required by that profile. A required field may be an explicit `unknown` only where indicated; unknown is never a substitute for a mandatory executable binding.

| Field | Discovery | Runnable | Governed | Notes |
|---|:---:|:---:|:---:|---|
| `sic_version` | R | R | R | Draft schema version, e.g. `0.1.0` |
| `id`, `version`, `name` | R | R | R | Stable ID, immutable version, display label |
| `kind`, `description` | R | R | R | `model`, `algorithm`, `rule_engine`, `service`, `composite`, `simulation`, `other` |
| `provider.id` | R | R | R | Provenance anchor; not proof of trust |
| `capabilities[]` | R | R | R | At least one declared operation |
| `signatures[]` | R | R | R | Inputs/outputs, including `unknown` for discovery-only semantics |
| `context.assumptions[]` | R | R | R | Empty array means explicitly no known assumptions, not universal applicability |
| `relay.protocol`, `relay.binding` | — | R | R | Binding may be service URI or local adapter reference |
| `relay.operations[]` | — | R | R | Includes `invoke`, `status`, `result`, `cancel` as applicable |
| `execution` | — | R | R | Timeouts, effects, idempotency and resource limits |
| `evidence.references[]` | O | O | R | Can be empty with `evidence.status: unverified` |
| `policy.reference`, `policy.authority` | O | O | R | External policy engine remains authoritative |
| `audit` | O | O | R | Trace correlation, retention classification |
| `lifecycle.status` | R | R | R | `candidate`, `validated`, `authorized`, `deprecated`, `revoked` |
| `growth` | O | O | O | Residual and experiment links |

A conforming consumer MUST distinguish **missing**, **unknown**, **not applicable**, and **verified false**. These are not interchangeable. Where no evidence exists, the descriptor SHOULD say `unverified` rather than imply validation.

## 5. Signatures, semantics, and effects

Each capability signature SHOULD declare:

1. Operation identifier and human-readable intent.
2. Input and output schema references and versions.
3. Semantic types or ontology identifiers where available.
4. Preconditions, invariants, and postconditions when testable.
5. Side effects, data sensitivity, and external action categories.
6. Uncertainty representation, error modes, and timeout behavior.

Schema compatibility is **necessary but not sufficient** for semantic compatibility. Two capabilities can accept the same JSON while interpreting units, dates, ownership, or causal assumptions differently. A composition engine SHOULD therefore check semantic, contextual, evidential, and policy constraints before invocation.

A proposed compatibility predicate is:

$$
operatorname{Compatible}(a,b,q) =
T(a,b) \land X(a,b,q) \land P(a,b,q) \land V(a,b,q)
$$

Here `T` is syntactic/type compatibility, `X` is contextual applicability, `P` is policy admissibility, and `V` is adequate validation for the task's risk tier. This is a *decision template*, not a complete computable algorithm. Unknown or insufficient evidence MUST NOT be treated as `true` in consequential use.

## 6. Relay interface

SIC binds to the UNT-R relay model described in SPEC-002. The proposed baseline operations are:

| Operation | Meaning | Expected behavior |
|---|---|---|
| `describe` | Retrieve descriptor | Returns versioned contract metadata |
| `match` | Evaluate applicability | Returns supported/unsupported/unknown with reasons |
| `invoke` | Start work | Requires authorization for any consequential side effect |
| `status` | Inspect execution | Returns bounded, auditable state |
| `result` | Retrieve outcome | Includes outputs, errors, provenance and trace ID |
| `cancel` | Request termination | Best-effort semantics and cancellation outcome |

Optional operations include `delegate`, `handoff`, `evaluate`, `counterEvidence`, and `proposeGrowth`. Implementations MUST NOT infer permission to delegate or act from the presence of an endpoint. Cross-boundary handoff SHOULD preserve context assumptions, provenance, policy constraints, and uncertainty rather than forwarding only a final answer.

## 7. Evidence and structural counter-evidence

Evidence references SHOULD contain claim ID, dataset or case scope, method, evaluator identity, date, version, metrics, uncertainty, and reproducibility location where permitted. Counter-evidence SHOULD remain attached to the same claim lineage even when the capability is superseded. Evaluator independence SHOULD be disclosed rather than assumed.

Evidence states may include `unverified`, `provisionally_supported`, `contested`, `invalidated`, and `superseded`. These labels are registry bookkeeping states, **not** universal scientific truth or authorization decisions.

A structural counter-evidence record may challenge representation, localization, applicability, composition, scoring, evaluator design, policy boundary, or resource assumptions. The presence of counter-evidence SHOULD trigger review of applicability claims and precedent rankings, not automatic deletion of inconvenient observations.

## 8. Policy, authority, and execution boundaries

The contract MUST separate:

- **Capability:** what the component claims it can do.
- **Validation:** what independent evidence supports in a specified context.
- **Authorization:** what a governing authority permits at this moment.

An authorization decision MUST be made by the controlling policy system using current identity, purpose, risk, permissions, and context. A cached `authorized` lifecycle label is insufficient for permission to execute. Authorization can be withdrawn without changing a model's capability descriptor.

Recommended environments are **exploratory sandbox**, **validated shadow runtime**, and **authorized production runtime**. A transition between them requires explicit gate checks; validation results MUST NOT implicitly move a candidate into production. Tool invocation that can affect external systems SHOULD require explicit scope, limits, and auditable identity.

## 9. Lifecycle, versioning, and evolution

A candidate lifecycle is:

```text
proposed → registered → sandbox-tested → validated → deployment-eligible
                                                        |
                                                 policy decision
                                                        |
                                                  authorized
                                                        |
                                          monitored / restricted
                                                        |
                                       superseded / deprecated / revoked
```

The lifecycle is not strictly linear: a candidate may be rejected, contested, revised, or returned to testing. **Validated** does not imply **authorized**. A new version SHOULD be issued for material changes to signatures, semantic assumptions, policy effects, or validation claims. Consumers SHOULD pin descriptor versions and record dependency versions for reproducibility.

Growth hooks MAY refer to residual reports, candidate PIRPs, adversarial test results, and new precedent cases. Growth proposals MUST NOT mutate a deployed contract in place.

## 10. Illustrative YAML descriptor

This is an **illustrative candidate**, not a deployed service, complete JSON Schema, or a validated capability. The `example.invalid` domain is deliberately non-operational.

```yaml
sic_version: "0.1.0"
profile: governed
id: "urn:sif:capability:example:route-risk-assessor"
version: "1.0.0"
name: "Route Risk Assessor"
kind: algorithm
description: "Estimates route risk under declared input assumptions."
provider:
  id: "urn:sif:provider:example-lab"
  provenance: "illustrative-research-example"
capabilities:
  - id: "assess-route-risk"
    claim: "Produces a bounded risk estimate for eligible routes."
    exclusions:
      - "Does not authorize shipment dispatch."
signatures:
  - operation: "assess-route-risk"
    input_schema: "https://example.invalid/schemas/route-risk-input-v1.json"
    output_schema: "https://example.invalid/schemas/route-risk-output-v1.json"
    semantic_types: ["route", "risk-score"]
    effects: ["read-only"]
    error_modes: ["invalid-input", "out-of-scope", "timeout"]
context:
  assumptions:
    - "Input route geometry and observation timestamps are provided."
    - "Score calibration is limited to the declared evaluation distribution."
  excluded_contexts:
    - "Safety-critical autonomous dispatch without independent review."
relay:
  protocol: "sif-relay-draft-0.1"
  binding: "https://example.invalid/relay/route-risk"
  operations: ["describe", "match", "invoke", "status", "result", "cancel"]
execution:
  timeout_seconds: 30
  idempotency: "request-key-required"
  max_parallel_invocations: 2
  side_effects: "none"
evidence:
  status: unverified
  references: []
policy:
  reference: "urn:sif:policy:example:human-review-required"
  authority: "external-policy-engine"
  action_scope: ["advisory-only"]
audit:
  correlation_id_required: true
  retention_class: "local-policy-defined"
lifecycle:
  status: candidate
  supersedes: null
growth:
  residual_report_refs: []
  experiment_refs: []
```

**Interpretation:** Although the example declares the `governed` profile's fields, it remains `candidate` and `unverified`; it is not eligible for production dispatch. A validator checks schema completeness, whereas the policy authority decides whether a particular request is allowed.

## 11. Composition and precedence rules

When composing SIC-described units:

1. Resolve stable IDs to immutable descriptor versions.
2. Check type and semantic compatibility, including units and temporal semantics.
3. Intersect context applicability constraints; do not widen scope by default.
4. Preserve upstream evidence and counter-evidence references.
5. Calculate cumulative resource, privacy, and side-effect exposure.
6. Apply policy checks at each consequential boundary and on delegated actions.
7. Record the composite graph, adapter versions, and execution trace.
8. Revalidate material changes; never infer whole-system validity from valid parts alone.

A composite SIC SHOULD expose its constituent dependencies and failure propagation policy. A structural fold MAY hide internal detail for efficient discovery, but MUST preserve a means of retrieving relevant provenance, policy boundaries, and counter-evidence for audit.

## 12. Validation and conformance tests

The following proposed tests are a minimum research starting point, not sufficient proof of safety or reliability.

| Test ID | Scenario | Expected result |
|---|---|---|
| SIC-C01 | Missing `id` or `version` | Descriptor rejected |
| SIC-C02 | Same `(id,version)` with changed digest | Integrity conflict raised |
| SIC-C03 | Discovery-only descriptor invoked | Invocation rejected |
| SIC-C04 | Syntactically matching but semantically incompatible units | Match rejected or marked unknown |
| SIC-C05 | Context outside declared scope | Match rejected or escalated |
| SIC-C06 | `unverified` candidate requests production action | Authorization denied by default |
| SIC-C07 | Evidence record challenges capability claim | Counter-evidence retained and review triggered |
| SIC-C08 | Policy revocation after prior authorization | New action denied; in-flight handling follows policy |
| SIC-C09 | Composite changes a dependency version | Revalidation triggered |
| SIC-C10 | Cancellation requested during invocation | Bounded cancellation response recorded |
| SIC-C11 | Handoff omits critical context assumption | Handoff rejected or flagged incomplete |
| SIC-C12 | Adversarial evaluator reports metric gaming | Claim marked contested pending independent review |

A useful experimental benchmark compares contract-aware composition against schema-only tool composition on semantic mismatch rates, out-of-scope invocation, evidence preservation, unauthorized actions, and total cost. Hypotheses should be preregistered where practical.

## 13. Security and failure modes

Threats include spoofed provider identities, stale capability claims, forged evidence, prompt injection inside descriptions, semantic type confusion, policy laundering through delegation, registry poisoning, privacy leakage during relay, and evaluator collusion. Descriptors and precedent text are **untrusted inputs**. Implementations SHOULD authenticate publishers, validate signatures/digests, sandbox execution, minimize data transfer, and avoid executing instructions found in descriptive metadata.

The contract cannot solve epistemic uncertainty by itself. Known limitations include ontology drift, incomplete contextual assumptions, contested metrics, non-stationary environments, cross-domain generalization failures, and the cost of independent evaluation. These limitations should be explicit in any empirical report.

## 14. Open design decisions

- Which semantic type vocabulary is minimal enough for adoption yet expressive enough for reliable relay?
- Which fields should be machine-verifiable versus human- or evaluator-attested?
- How should policy references be portable across sovereign BrainUnits without overriding local authority?
- How should composite contracts express non-additive failure modes and emergent risks?
- How can evidence quality be compared without creating a single Goodhart-prone score?
- Which conformance tests are appropriate for purely informational versus action-taking capabilities?
- How should the registry expose competing or contradictory precedents without collapsing them into a false consensus?

These remain open research and engineering questions.

## 15. Relationship to the SIF document set

- **SIF-008:** Dual maps identify demand and supply; SIC makes candidate matches inspectable.
- **SIF-009 / SPEC-003:** The precedent registry records cases and evidence linked to SIC IDs.
- **SIF-010 / SPEC-002:** UNT-R supplies names, semantic types, and transport-neutral relay operations.
- **SIF-011:** Portable pieces and units motivate graduated contract maturity.
- **SIF-012 / SPEC-004:** MIAS generates adversarial validation artifacts and governs lifecycle transitions.
- **SIF-013:** Structural counter-evidence and evaluator governance constrain claims.
- **SIF-014:** Residual-based growth proposes new versions without bypassing authorization.

## 16. Conclusion

SIC is a proposed **boundary discipline for open structural intelligence**: heterogeneous intelligence remains free to evolve internally while its externally visible claims, assumptions, signatures, evidence, and authority boundaries become inspectable. It enables a path from discovery to composition to evaluation, but it does not collapse these stages into one. Its success must be judged by empirical interoperability, safer failure handling, stronger evidence traceability, and the ability to replace or improve components without erasing their limitations.

> **A portable intelligence unit is not trustworthy because it has a contract. The contract makes its claims, boundaries, and failures available for testing and governance.**

---

### Suggested figure placements

- **Fig-004 — Universal Contracts and Relay:** after Section 3 or Section 6 (primary figure).
- **Fig-003 — Problem–Capability Dual Maps:** after Section 11.
- **Fig-005 — Structural Precedent Intelligence:** after Section 7.
- **Fig-006 — Multi-Intelligence Adversarial Sandbox:** after Section 12.

*End of SPEC-001 — Candidate Research Specification v0.1.*
