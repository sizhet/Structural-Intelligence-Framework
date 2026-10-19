# SIF-011 — Structural Intelligence Contracts and Portable Units

**Structural Intelligence Framework (SIF) — Interoperability Series**  
**Version:** 1.0.0 (research architecture)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual proposal; interfaces and schemas are candidate designs, not ratified standards  
**License:** Apache-2.0

## Abstract

Open structural intelligence requires more than an inventory of heterogeneous models, algorithms, services, and reusable artifacts. It requires a way to determine what each structure claims to do, under which conditions, how it can be invoked or relayed, what evidence supports it, and who may authorize its actions. This paper proposes the **Structural Intelligence Contract (SIC)** as a cross-boundary description of such commitments, and connects SIC to **Portable Intelligence Runtime Pieces (PIRP)** and **Portable Intelligence Runtime Units (PIRU)**. A PIRP is a flexible intelligence-bearing piece that may be exploratory or only partially specified; a PIRU is a more formally bounded unit with explicit operational interfaces and conformance expectations. The distinction permits structural discovery without requiring premature standardization. SIC provides the bridge from exploratory pieces to interoperable, evaluable, and governable units. We describe contract dimensions, composition rules, evidence and policy separation, relay semantics, lifecycle transitions, failure modes, and falsifiable validation experiments. Our central principle is: **standardize the contract, not the intelligence**.

**Keywords:** Structural Intelligence Framework; Structural Intelligence Contract; PIRP; PIRU; portability; interoperability; intelligence relay; structural precedent; evidence; governance; conformance.

---

## 1. Motivation: Portability Is Not Merely Serialization

A language model, a differential-tree router, a numerical optimizer, a simulation engine, and a policy evaluator can all contribute to a solution. Yet placing their descriptions in one registry does not make them composable. A successful handoff requires agreement on meaning, inputs, outputs, context, resource limits, evidence, failure reporting, and permissible actions.

Traditional software interfaces help with syntactic interoperability. Structural intelligence introduces additional requirements:

- **Semantic compatibility:** the same field name may represent different quantities, assumptions, or granularity.
- **Context continuity:** an output may be valid only for a specific time, jurisdiction, environment, or model state.
- **Epistemic accountability:** confidence, uncertainty, provenance, and counter-evidence should survive relay.
- **Governed execution:** a capability can be technically callable without being authorized for a particular action.
- **Evolutionary compatibility:** new intelligence structures must be able to enter, compete, improve, and replace predecessors.

SIF therefore treats interoperability as a **contracted structural relationship**, not merely a transport mechanism. The contract describes a claim that can be checked, challenged, and revised; it is not proof that the claim is true.

## 2. Position Within the SIF Architecture

SIF organizes intelligence work into four interacting functional domains: (1) localization and intelligence addressing; (2) per-node intelligence; (3) universal control planes and scoring/folding; and (4) residual-based structural growth. SIC and portable units cross all four domains.

Three engineering responsibilities are also distinct:

| SIF system | Primary question | SIC / portable-unit role |
|---|---|---|
| Structural Intelligence Registry | What structures and precedents exist? | Publish identity, interfaces, evidence, versions, and applicability |
| Structural Intelligence Runtime | How should capabilities be composed and executed? | Validate contracts, relay context, enforce authorization, report outcomes |
| Structural Intelligence Evolution Laboratory | How can better structures be discovered and tested? | Compare candidate pieces, challenge claims, promote or reject units |

The **Structural Problem-Solving Map (PSM)** expresses tasks, constraints, and desired outcomes. The **Structural Capability Map (SCM)** expresses available capacities and their relationships. **Bidirectional Structural Intelligence Mapping (BSIM)** matches the two. SIC provides the inspectable boundary objects needed to make those matches meaningful.

**Figure placement:** `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` may be inserted after this section.

## 3. PIRP and PIRU: Freedom and Formality

### 3.1 Portable Intelligence Runtime Piece (PIRP)

A **PIRP** is a transferable intelligence-bearing structure or artifact that can potentially participate in a runtime or a learning relay. Examples include a heuristic, prompt-and-tool workflow, CCC-derived pattern, scoring fragment, learned policy candidate, simulation configuration, or partial CallingGraph.

A PIRP need not yet have a complete executable interface. It may be a hypothesis, an experimental implementation, or a bounded artifact awaiting adaptation. Its portability is conditional: the receiving environment must be able to interpret the piece or identify what is missing.

### 3.2 Portable Intelligence Runtime Unit (PIRU)

A **PIRU** is a more formally packaged intelligence unit with sufficiently explicit identity, input/output signatures, assumptions, execution or evaluation semantics, and lifecycle controls to support defined forms of conformance testing.

PIRU does **not** mean every unit is safe, correct, or production-authorized. It means that the unit exposes a testable boundary. Formality is a property of its declared contract and evidence, not a guarantee of real-world performance.

### 3.3 A progression, not a rigid hierarchy

A practical development path is:

```text
Observation / residual
        ↓
Candidate intelligence structure
        ↓
PIRP: portable exploratory piece
        ↓  adaptation + contract drafting
Candidate PIRU: bounded executable/evaluable unit
        ↓  conformance + adversarial validation
Validated PIRU (for a specified context)
        ↓  separate policy authorization
Authorized runtime deployment
        ↓  monitoring, counter-evidence, revision
Revised PIRP/PIRU, replacement, or retirement
```

This is not necessarily a linear pipeline. A PIRU can yield new PIRPs; multiple PIRPs can be assembled into one PIRU; and a previously validated PIRU can be demoted after new counter-evidence.

## 4. Structural Intelligence Contract (SIC)

### 4.1 Contract definition

A **Structural Intelligence Contract** is a versioned, machine-inspectable or human-auditable description of an intelligence structure's claimed capabilities, operational boundaries, evidence requirements, and governance constraints.

An SIC should answer at least eight questions:

1. **Identity:** What structure is this, and which version?
2. **Capability:** What does it claim to accomplish?
3. **Signature:** What inputs, outputs, units, and semantics are required?
4. **Context:** Under which assumptions and environments is it applicable?
5. **Relay:** How are calls, state, failures, and handoffs exchanged?
6. **Evidence:** What supports the claims, and what contradicts them?
7. **Policy:** What actions are permitted, forbidden, or require approval?
8. **Evolution:** How can the structure be tested, revised, superseded, or retired?

Additional optional dimensions include cost, latency, privacy classification, dependency graph, granularity, reproducibility, evaluator identity, and provenance of learned weights or source artifacts.

### 4.2 Contract facets

| Facet | Illustrative fields | Primary concern |
|---|---|---|
| Identity and provenance | `id`, `version`, `publisher`, `digest` | Stable reference and traceability |
| Capability | `tasks`, `claims`, `limitations` | Discoverability and expectation setting |
| Typed signatures | `input_schema`, `output_schema`, `semantic_units` | Safe data interpretation |
| Applicability | `context_predicates`, `exclusions` | Boundary conditions |
| Relay | `operations`, `timeouts`, `state_policy` | Handoff and execution |
| Evidence | `evaluations`, `counter_evidence`, `uncertainty` | Epistemic accountability |
| Governance | `requested_permissions`, `approval_gate` | Action control |
| Resources | `cost_estimate`, `compute_limits` | Scheduling and feasibility |
| Lifecycle | `status`, `supersedes`, `rollback` | Evolution and retirement |

**Crucial separation:** evidence that a unit performs well does not authorize its deployment; authorization does not make a unit scientifically validated.

### 4.3 Illustrative candidate contract

The following YAML is a **research example**, not an implemented standard or a promise of API compatibility.

```yaml
sic_version: "0.1-candidate"
identity:
  id: "urn:sif:unit:inventory-replenishment-planner"
  version: "0.3.0"
  publisher: "example-research-lab"
  artifact_digest: "sha256:<artifact-digest>"
kind: "PIRU"
capability:
  tasks: ["propose_replenishment_plan"]
  claims:
    - "Produces candidate replenishment quantities under stated constraints"
  limitations:
    - "Does not issue purchase orders"
signature:
  input_schema: "schema://example/inventory-snapshot/v2"
  output_schema: "schema://example/replenishment-proposal/v1"
  semantic_units:
    quantity: "items"
    horizon: "days"
context:
  required:
    - "inventory_timestamp_present"
    - "supplier_lead_time_distribution_available"
  excluded:
    - "unmodeled_regulatory_restrictions"
relay:
  operations: ["describe", "match", "invoke", "status", "result", "cancel"]
  timeout_seconds: 30
  side_effects: false
evidence:
  evaluation_refs: ["evidence://example/benchmark-run-17"]
  counter_evidence_refs: ["evidence://example/failure-case-04"]
  validation_scope: "simulated demand distributions only"
policy:
  requested_permissions: ["read_inventory_snapshot"]
  prohibited_actions: ["place_purchase_order"]
  deployment_requires_approval: true
resources:
  max_runtime_seconds: 30
lifecycle:
  status: "candidate"
  supersedes: null
```

A schema reference alone is insufficient when the schema lacks semantic units, temporal validity, uncertainty representation, or provenance.

**Figure placement:** `../../figures/Fig-004-Universal-Contracts-and-Relay.png` may be inserted after this section.

## 5. Universal Naming, Typing, and Relay (UNT-R)

SIC is a contractual description; **UNT-R** supplies the common interoperability primitives through which such descriptions can be resolved and acted upon.

### 5.1 Universal naming

Names should distinguish logical identity from immutable artifact versions and from deployment instances. A mutable alias such as `latest` may be convenient for discovery but must resolve to a specific version and digest before a reproducible evaluation or governed execution.

A practical identity relation is:

\[
\text{Logical Unit} \rightarrow \text{Version} \rightarrow \text{Artifact Digest} \rightarrow \text{Deployment Instance}.
\]

Different systems may implement these identities differently; SIF requires explicit mappings, not one universal identifier syntax.

### 5.2 Universal typing

Type compatibility has multiple levels:

- **Syntactic:** does the payload parse?
- **Dimensional:** are units, ranges, and cardinalities compatible?
- **Semantic:** do fields refer to the same concepts and temporal meaning?
- **Contextual:** do assumptions and granularity match?
- **Behavioral:** are side effects, determinism, and failure semantics compatible?
- **Governance:** is the proposed use allowed?

An adapter can repair some incompatibilities, but the adapter itself must carry a contract and evidence. A transformation that silently drops uncertainty or provenance is not a neutral conversion.

### 5.3 Relay operations

A minimal candidate relay interface comprises `describe`, `match`, `invoke`, `status`, `result`, and `cancel`. Optional operations include `delegate`, `handoff`, `evaluate`, `counterEvidence`, and `proposeGrowth`.

The minimal verbs should not be interpreted as a requirement that every PIRP is executable. A non-executable PIRP may support only description and evaluation until wrapped in an adapter or promoted to a PIRU.

### 5.4 Relay envelope

A relay envelope should preserve task identity, contract versions, context reference, provenance, evidence references, authorization scope, budget, and cancellation semantics. Information that cannot be transmitted should be explicitly marked as omitted or unavailable, rather than silently fabricated.

## 6. Contract-Based Composition

### 6.1 Necessary checks

Let a task requirement be \(R\), a candidate unit contract be \(C\), and an execution context be \(x\). A candidate match requires a set of independently checked conditions:

\[
\operatorname{CandidateMatch}(R,C,x)
= T \land S \land X \land G \land B,
\]

where \(T\) denotes type compatibility, \(S\) semantic suitability, \(X\) contextual applicability, \(G\) governance feasibility, and \(B\) resource-budget feasibility. Evidence sufficiency should be evaluated separately and can result in a provisional or sandbox-only classification. This Boolean expression is an illustrative design abstraction, not a complete formal semantics.

### 6.2 Composition patterns

**Sequential relay:** unit A produces an output consumed by B. The composition contract must account for schema conversion, provenance continuity, and compounded uncertainty.

**Parallel comparison:** multiple units address the same task; the runtime must define aggregation, disagreement reporting, and evaluator independence.

**Conditional dispatch:** a router selects units according to a structural signature, context, or policy. Dispatch error becomes a measurable residual.

**Hierarchical composition:** several units become a macro-intelligence piece. Its external contract must state which internal assumptions remain valid and which have been abstracted or folded.

**Delegated exploration:** a unit proposes new candidate structures, but exploration rights do not imply production execution rights.

### 6.3 Compositional evidence is not automatic

If A and B have each been validated separately, the composition \(B\circ A\) is **not** thereby validated. The handoff can introduce distribution shifts, incompatible semantics, cumulative latency, or new failure paths. Composed systems require boundary tests and, when risks warrant, end-to-end adversarial evaluation.

### 6.4 Folding and unfolding

A folded macro-unit can simplify discovery and invocation. However, folding must retain enough lineage to support audit, failure localization, and selective unfolding. The system should distinguish what is preserved explicitly from what may only be recovered through later tests.

## 7. Contracts and Structural Precedents

A **Structural Precedent Registry (SPR)** records cases in which intelligence structures were applied under specified conditions, with observed results and evidence. SIC and SPR serve different purposes:

- **SIC**: what the structure claims and how it can be used.
- **Precedent case**: what happened in a particular application.
- **Evidence record**: how a claim or outcome was assessed.
- **Counter-evidence record**: where assumptions, outcomes, or generalizations failed.

This distinction prevents the common error of treating a successful demonstration as an unrestricted capability guarantee. The Registry can use SIC signatures for retrieval and distinguish near matches from genuinely applicable precedents.

## 8. Governance: Capability, Evidence, and Authority

SIF separates three planes that must interact but not collapse into one another:

1. **Policy and authority plane:** decides whether an action is permitted in the current context.
2. **Scoring and decision plane:** ranks or selects candidates against declared objectives.
3. **Evidence and audit plane:** records why claims and decisions should be trusted or questioned.

A high score is not permission. A valid schema is not proof of safety. A production permission is not proof of general intelligence.

### 8.1 Permission attenuation

When a parent workflow delegates to a unit, the delegated permission scope should not exceed the intersection of the parent's authority and the unit's authorized scope:

\[
P_{\mathrm{delegated}} \subseteq P_{\mathrm{parent}} \cap P_{\mathrm{unit}}.
\]

This is a governance design rule. Real deployments also require enforcement at the actual resource boundary; declarations alone are insufficient.

### 8.2 Context and evidence integrity

Runtime implementations should protect evidence references and contract digests against accidental substitution or deliberate tampering. Sensitive context should be minimized and appropriately access-controlled. A relay should log when information has been summarized, redacted, transformed, or lost.

### 8.3 Separation of environments

A proposed unit may be permitted in an exploratory sandbox, later in a shadow runtime, and only then in a production environment after separate authorization. Promotion should be reversible when new counter-evidence appears.

## 9. From Residual to New Portable Unit

An unresolved task may expose a **localization residual**, **capability residual**, **semantic mismatch**, **composition residual**, **evidence gap**, **policy conflict**, or **resource shortfall**. These are not interchangeable diagnoses.

A proposed growth process is:

```text
PSM task and constraints
        ↓
BSIM candidate matching against SCM / SPR
        ↓
Mismatch or unresolved residual
        ↓
Diagnose: localization? semantics? capability? policy? evidence?
        ↓
Reuse / adapt existing PIRP or PIRU, or propose new PIRP
        ↓
Draft or revise SIC
        ↓
Sandbox tests + counter-evidence + evaluator challenge
        ↓
Candidate PIRU and context-bounded validation
        ↓
Separate authorization, monitoring, revision, retirement
        ↺
```

The growth mechanism should also be open to revision. An improvement to the matcher, contract language, evaluator, or relay adapter can be as valuable as a new solver.

**Figure placement:** `../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png` may be inserted after this section.

## 10. Multi-Intelligence Adversarial Validation

The proposed **Multi-Intelligence Adversarial Sandbox (MIAS)** evaluates candidate PIRPs, PIRUs, and their compositions with differentiated roles:

| Role | Responsibility | Potential failure |
|---|---|---|
| Builder | Construct or adapt candidate | Overfit to known tests |
| Challenger | Find counterexamples and boundary failures | Produce unrealistic attacks |
| Independent evaluator | Assess outcomes against predefined criteria | Metric bias or evaluator leakage |
| World/simulation engine | Provide test environments and perturbations | Simulation-to-reality gap |
| Formal/deterministic checker | Verify explicit invariants where possible | Incomplete specification |
| Governance gate | Control promotion and action scope | Rubber-stamp weak evidence |

Useful tests include interface conformance, semantic round-trip checks, distribution shifts, adversarial inputs, ablation, A/B comparisons, replay of failed precedents, and evaluator disagreement analysis.

A sandbox cannot establish universal correctness. Its results must be tied to tested distributions, assumptions, versions, and evaluation procedures. For high-stakes contexts, independent external review and domain-specific assurance may be necessary.

**Figure placement:** `../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` may be inserted after this section.

## 11. Worked Conceptual Example: Inventory Planning Relay

Consider a retailer seeking replenishment proposals that balance service level, inventory cost, and supplier constraints.

**Problem map:** demand forecasts, inventory state, supplier lead-time distributions, cash constraints, and human approval requirements.

**Capability map:** an LLM interprets ambiguous planning requirements; an MDT router identifies product-family structure; a statistical forecaster estimates demand; a mathematical optimizer proposes quantities; a simulation engine stress-tests scenarios; a policy unit enforces authorization boundaries.

**Portable units:** the forecasting procedure may begin as a PIRP, while a bounded optimizer with typed inputs and reproducible solver settings can be packaged as a candidate PIRU. A relay adapter converts forecast distributions into optimizer inputs, preserving horizon, units, timestamps, and uncertainty representation.

**Precedent registry:** previous cases identify conditions in which a similar combination worked or failed. A precedent involving stable demand must not be generalized without qualification to highly intermittent demand.

**Adversarial sandbox:** the challenger perturbs lead times, missing data, and demand regimes. An independent evaluator checks service levels, constraint violations, and calibration rather than accepting only the optimizer's internal objective value.

**Control boundary:** the composite system may recommend orders, but it cannot place purchase orders without a separately authorized action path.

**Residual-driven evolution:** if intermittent demand repeatedly breaks the forecast-to-optimizer interface, the system may propose a specialized PIRP, update the SIC context exclusions, or revise the relay representation. The outcome is a tested hypothesis for structural growth, not automatic proof of improvement.

This example is illustrative; no experiment or benchmark result is claimed.

## 12. Failure Modes and Design Safeguards

| Failure mode | Why it matters | Proposed safeguard |
|---|---|---|
| Contract theater | Descriptions appear formal but are not checked | Executable conformance tests and evidence links |
| False semantic equivalence | Matching schemas hide different meanings | Units, ontology mappings, context predicates, adapter tests |
| Version drift | A mutable unit changes after validation | Immutable digests and version-pinned evaluation |
| Context laundering | Handoffs erase assumptions or uncertainty | Provenance-aware relay envelopes and omission flags |
| Evidence laundering | Weak tests become generalized claims | Scope-limited evidence and counter-evidence records |
| Authority escalation | Callable unit gains unintended permissions | Enforced permission attenuation and separate action gates |
| Composition fallacy | Validated parts produce unvalidated whole | End-to-end and boundary-specific testing |
| Registry ossification | Formality excludes novel approaches | PIRP entry path and provisional contracts |
| Adapter monoculture | Shared adapter defects propagate | Independent adapter tests and alternative implementations |
| Evaluator capture | Candidates optimize a narrow metric | Challenger diversity, blinded evaluation, counter-metrics |
| Resource explosion | Open growth becomes operationally infeasible | Budgets, quotas, selective validation, retirement |

## 13. Testable Hypotheses

The following are **proposals for experiments**, not established findings.

**H1 — Contract-aware matching:** BSIM with SIC context and semantic facets reduces invalid capability matches compared with name-only or schema-only retrieval.

**H2 — Relay integrity:** typed, provenance-preserving relay envelopes reduce undetected semantic or uncertainty loss relative to unstructured handoffs.

**H3 — Portable reuse:** PIRU packaging reduces integration effort across independently developed runtimes, after accounting for the cost of contract authoring.

**H4 — Growth accessibility:** permitting provisional PIRPs increases useful candidate diversity compared with a registry admitting only fully formalized units, without unacceptable evaluation burden.

**H5 — Composition assurance:** end-to-end adversarial tests identify failure modes missed by independent unit tests.

**H6 — Governance separation:** explicit policy gates reduce unauthorized side effects without requiring equivalent restrictions on sandbox exploration.

**H7 — Evidence-aware precedent selection:** retrieval conditioned on evidence scope and counter-evidence yields better out-of-distribution task selection than success-only precedent retrieval.

**H8 — Hierarchical portability:** macro-unit folding improves dispatch or execution efficiency while preserving auditability when lineage and selective unfolding are available.

Each hypothesis needs task-specific metrics, baselines, confidence intervals or uncertainty estimates, and a preregistered failure criterion where feasible.

## 14. Validation Roadmap

### Phase A — Contract vocabulary and conformance fixtures

Define a minimal SIC candidate schema, a corpus of valid and invalid contracts, semantic unit tests, and compatibility fixtures. Measure agreement among independent implementations.

### Phase B — PIRP-to-PIRU promotion studies

Track how exploratory artifacts acquire typed interfaces, evidence, and governance declarations. Measure conversion cost, abandonment rates, and whether formalization changes observed performance.

### Phase C — Cross-runtime relay trials

Integrate independently implemented LLM, optimizer, simulator, and deterministic checker units. Evaluate version resolution, context preservation, cancellation, error propagation, and reproducibility.

### Phase D — Adversarial composition trials

Test combinations under distribution shifts, contradictory evidence, delayed responses, malicious inputs, and evaluator disagreement. Compare contract-aware and contract-free baselines.

### Phase E — Governed evolution and collective reuse

Operate a bounded research registry that records failed and successful precedents, supports candidate replacement, and measures reuse quality, validation cost, and policy compliance over time.

Promotion to broader use should depend on observed evidence, not a calendar milestone.

## 15. Open Research Questions

1. What is the smallest SIC that meaningfully improves interoperability without excluding exploratory structures?
2. Which semantic and contextual compatibility checks can be automated, and which require domain judgment?
3. How should uncertainty be represented when combining probabilistic, deterministic, symbolic, and language-model outputs?
4. When does a PIRP become sufficiently bounded to qualify as a PIRU, and who certifies that claim?
5. How can a macro-unit expose useful external guarantees without concealing decisive internal failure paths?
6. What forms of evidence can be transferred across environments, versions, or model updates?
7. How can counter-evidence challenge a unit's evaluator without causing unbounded recursive evaluation?
8. How should proprietary, privacy-sensitive, or sovereign intelligence pieces participate in cross-boundary relay?
9. What constitutes a fair benchmark of structural portability rather than merely software packaging quality?
10. How can contract schemas themselves evolve while preserving old precedents and historical reproducibility?

## 16. Relationship to Other SIF Documents

- **SIF-001:** From Isolated Intelligence to Open Structural Intelligence — overall architecture and motivation.
- **SIF-002:** Four Functional Domains of Structural Intelligence — functional organization.
- **SIF-003:** Structural Precedents and Open Intelligence Evolution — reuse and precedent reasoning.
- **SIF-004:** Localization and Intelligence Addressing — discovery and structural addressing.
- **SIF-005:** Per-Node Intelligence and Multi-Perspective Capabilities — heterogeneous capability inventory.
- **SIF-006:** Universal Control Planes and Scoring Folding — evaluation, governance, and folding.
- **SIF-007:** Residual-Based Structural Growth — mechanisms of change.
- **SIF-008:** Dual Maps and Bidirectional Structural Mapping — demand-capability matching.
- **SIF-009:** Structural Precedent Registry — case and evidence records.
- **SIF-010:** Universal Naming, Typing, and Relay — identity, semantics, and handoff primitives.
- **SPEC-001:** SIF Structural Intelligence Contract — candidate formal contract specification.
- **SPEC-002:** Universal Name, Type, and Relay API — candidate interface specification.

The related PIRP/PIRU research line supplies the conceptual distinction between flexible portable pieces and more formally bounded portable units. This paper proposes how that distinction can operate within SIF; it does not supersede those independent research contributions.

## 17. Conclusion

A collection of intelligence structures does not become a coherent intelligence ecosystem merely by sharing a catalog or network protocol. It becomes more interoperable when the boundaries between structures are **named, typed, context-aware, evidence-bearing, governable, and revisable**.

The Structural Intelligence Contract is proposed as that boundary description. PIRP preserves the freedom to explore and exchange incomplete intelligence pieces; PIRU introduces a more testable unit boundary; UNT-R provides interoperable naming, typing, and relay; the Structural Precedent Registry supplies experience and counter-evidence; and the Multi-Intelligence Adversarial Sandbox tests whether claimed compatibility survives contact with difficult cases.

The long-term objective is not one frozen universal intelligence format. It is an open process in which new structures can enter, older structures can be challenged, and useful intelligence can be composed without confusing **capability with evidence, evidence with authority, or portability with correctness**.

> **Standardize the contract, not the intelligence. Preserve the boundary conditions, not merely the payload. Permit discovery broadly; authorize action deliberately.**

---

## Figure Placement Guide

| Figure | Suggested insertion |
|---|---|
| `Fig-003-Problem-Capability-Dual-Maps.png` | After Section 2 |
| `Fig-004-Universal-Contracts-and-Relay.png` | After Section 4 |
| `Fig-007-Structural-Growth-and-Evolution-Loop.png` | After Section 9 |
| `Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` | After Section 10 |

*This manuscript is a research proposal. Its contract examples, classifications, and lifecycle descriptions are candidate designs requiring independent implementation and empirical validation.*
