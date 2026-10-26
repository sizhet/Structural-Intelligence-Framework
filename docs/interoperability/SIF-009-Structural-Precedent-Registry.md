# SIF-009 — Structural Precedent Registry

**Structural Intelligence Framework (SIF)**  
**Series:** Interoperability — Paper 2  
**Version:** 1.0.0 (research architecture)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual proposal; not an implemented or validated standard  
**License:** Apache-2.0

## Abstract

A structural intelligence system cannot grow reliably by accumulating tools alone. It must preserve the circumstances in which an intelligence structure worked, the boundaries under which it failed, the evidence supporting its reuse, and the conditions under which it may be adapted or replaced. This paper proposes the **Structural Precedent Registry (SPR)**: a versioned, evidence-aware repository of reusable intelligence structures and their application histories. Inspired by legal precedent without equating legal reasoning with computation, SPR connects the **Structural Problem-Solving Map (PSM)** to the **Structural Capability Map (SCM)** through searchable, challengeable precedents. It separates structural identity, capability contracts, case-specific applicability, empirical evidence, counter-evidence, governance, and lifecycle status. We describe registry entities, retrieval and adaptation workflows, compatibility with Universal Naming, Typing and Relay (UNT-R), adversarial validation, provenance, and open-ended growth. The design is offered as a falsifiable research architecture rather than a claim that reliable general-purpose structural retrieval has already been achieved.

**Keywords:** Structural Intelligence Framework; Structural Precedent Intelligence; precedent registry; capability discovery; problem–capability mapping; evidence provenance; counter-evidence; structural growth; interoperability; governance.

---

![Structural Precedent Intelligence](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 1. Why an Intelligence System Needs Precedents

A conventional tool catalog answers a narrow question: *What tools are available?* A mature structural intelligence system must answer several harder questions:

- Which structural solution has addressed a sufficiently similar problem before?
- Under what assumptions, contexts, and resource constraints did it succeed?
- Which parts of that solution can be transferred, and which must be revalidated?
- What negative results or counter-examples limit the analogy?
- Who is authorized to invoke or deploy the resulting composition?
- What should the system learn when no existing precedent applies?

The proposed **Structural Precedent Registry (SPR)** addresses these questions by storing not only capability descriptions but also *situated records of structural use*. It is the persistent, interrogable bridge between intelligence demand and intelligence supply.

The analogy with legal precedent is deliberately limited. Legal systems use prior decisions, distinctions, authority, and changing interpretation. SIF borrows the ideas of **case similarity, applicability, distinction, challenge, and revision**. It does not assume that legal precedent is a mechanically transferable algorithm or that similarity constitutes proof.

> **Core principle:** A precedent is not a reusable answer; it is a reusable structural claim with explicit conditions and evidence.

## 2. Placement Within the SIF Architecture

SIF distinguishes four functional domains:

1. **Localization and Intelligence Addressing:** find the relevant problem region, representation, capability, or relay path.
2. **Per-Node Intelligence:** execute or compose heterogeneous methods, including LLMs, rules, CCC, optimization, simulation, and other specialized intelligence.
3. **Universal Control Planes and Scoring/Folding:** evaluate alternatives while separately enforcing authority and recording evidence.
4. **Residual-Based Structural Growth:** identify unmet needs and develop, test, revise, or retire structures.

SPR intersects all four domains. It is not a fifth mutually exclusive functional domain. Nor is it identical to a runtime or an experiment laboratory.

| SIF subsystem | Primary responsibility | SPR relationship |
|---|---|---|
| Structural Intelligence Registry | What is known and what supports it? | SPR is its precedent-centered knowledge service. |
| Structural Intelligence Runtime | How should capabilities be composed and executed? | Consults precedents but enforces current contracts and policies. |
| Structural Intelligence Evolution Laboratory | Which new structures survive rigorous challenge? | Publishes qualified results, failures, and revisions into SPR. |

The registry mediates between two distinct maps:

- **Problem-Solving Map (PSM):** tasks, constraints, dependencies, context, desired outcomes, and open gaps.
- **Capability Map (SCM):** algorithms, models, services, units, interfaces, evidence, limitations, and compositional relations.

**Bidirectional Structural Intelligence Mapping (BSIM)** uses SPR to match a PSM demand to SCM capabilities. In the reverse direction, a newly validated capability can suggest new applications or expose previously invisible problem categories. Such suggestions remain hypotheses until tested.

**Suggested figure:** `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` — place here to show PSM ↔ SPR ↔ SCM.

---

![Fig-003-Problem-Capability-Dual-Maps.png](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

## 3. What Counts as a Structural Precedent?

A **structural precedent** is a versioned record asserting that a specified intelligence structure, under documented conditions, produced or failed to produce an observed outcome relevant to a problem class.

A precedent may describe:

- a localization strategy (e.g., an MDT-based search path);
- a per-node capability (e.g., a constrained optimizer);
- a composition (e.g., LLM → rule checker → simulation);
- a control configuration (e.g., a scoring forest under a policy profile);
- a structural adaptation (e.g., replacing a weak relay with a typed interface);
- a negative case (e.g., a misleading match that repeatedly fails);
- an exploratory candidate whose effectiveness remains unverified.

A precedent is **not** automatically a universally valid recipe. Its applicability is conditional on context, task semantics, evidence quality, resource budget, model versions, policy, and the available alternatives.

### 3.1 Three distinct objects

To prevent conflation, the registry distinguishes:

**Capability Definition (CD).** What an intelligence structure claims it can do, how to invoke it, and what contracts govern it.

**Precedent Case (PC).** A situated record of using or evaluating one or more capabilities for a particular problem and context.

**Evidence Record (ER).** An attributable observation, test, audit, simulation, or counter-example supporting or limiting claims in a case.

A capability can have many precedent cases; one case can reference many capabilities; one evidence record can support or challenge multiple claims if its scope is explicit.

### 3.2 Positive, negative, and unresolved precedents

The registry should preserve at least three evidence states:

| Precedent state | Meaning | Appropriate use |
|---|---|---|
| Positive | Qualified evidence supports success in a stated context. | Candidate retrieval, with applicability checks. |
| Negative | Evidence identifies failure or a contraindication. | Exclusion, warning, redesign, counter-evidence. |
| Unresolved | Evidence is insufficient, mixed, or contested. | Research prioritization; not production certification. |

An unsuccessful case can be as valuable as a successful one because it helps prevent repeated structural mistakes.

## 4. Canonical Registry Information Model

The following schema is a **research-level logical model**, not a frozen wire protocol. The companion `SPEC-003-Structural-Precedent-Registry-Schema.md` is intended to define a candidate machine-readable specification.

### 4.1 Identity and lineage

Every record requires a stable identifier and explicit version or revision semantics:

- `precedent_id`: globally resolvable or namespace-qualified identifier;
- `revision_id`: immutable revision reference;
- `structure_refs`: references to capability definitions and compositions;
- `parent_precedents`: prior cases adapted, combined, or superseded;
- `created_at`, `observed_at`, `updated_at`: separate temporal meanings;
- `publisher` and `provenance`: accountable source and origin chain.

A record identifier must not be silently reassigned when a model, API, policy, dataset, or evaluation method changes. Immutable historical records and mutable discovery indexes should be separated.

### 4.2 Problem signature

A problem signature should capture more than text similarity:

- intent and expected outcome;
- input and output types;
- task decomposition and dependency topology;
- operating context and environment;
- constraints, tolerances, and failure costs;
- granularity, time horizon, and perspective;
- applicable policy jurisdiction or authority domain.

A natural-language description may be retained, but it should not substitute for structured constraints when the latter are available.

### 4.3 Capability and composition signature

The record references a **Structural Intelligence Contract (SIC)** with:

- capability identity and version;
- accepted types and semantic preconditions;
- output claims and postconditions;
- invocation and relay methods;
- resource envelope and expected cost;
- evidence and known limitations;
- required authorization and safety controls;
- adaptation and growth hooks.

This permits heterogeneous units—including flexible **Portable Intelligence Runtime Pieces (PIRP)** and more formally packaged **Portable Intelligence Runtime Units (PIRU)**—to be indexed without forcing a single internal implementation.

### 4.4 Applicability envelope

A precedent should explicitly define the region in which transfer is plausible:

$$
\mathcal{A}(p) = \{x : C_p(x) \land T_p(x) \land P_p(x) \land R_p(x)\},
$$

where \(C_p\) denotes context assumptions, \(T_p\) type compatibility, \(P_p\) policy eligibility, and \(R_p\) resource feasibility. This is a conceptual predicate, not a promise that all conditions are machine-decidable.

Applicability envelopes may include hard exclusions, uncertain boundaries, and empirical ranges. Unknown applicability should not be represented as confirmed applicability.

### 4.5 Evidence and counter-evidence

Each evidence reference should preserve:

- the claim being tested;
- method, environment, and comparator;
- measured outcome and uncertainty;
- dataset or scenario lineage, where permissible;
- independence and potential conflicts of interest;
- observed failure modes;
- reproducibility instructions or restrictions;
- provenance integrity and timestamp.

Evidence records must distinguish **measured outcomes**, **model-generated estimates**, **expert judgments**, and **unverified assertions**.

### 4.6 Governance and lifecycle

Separate fields are needed for:

- `evaluation_status`: untested, challenged, provisionally supported, validated-for-scope, contradicted;
- `deployment_status`: sandbox-only, shadow-approved, production-authorized, suspended, retired;
- `authority_ref`: the accountable policy decision source;
- `review_due`: expiration or reevaluation trigger;
- `revocation_reason`: if an authorization or claim is withdrawn.

**Evaluation status is not deployment authorization.** A highly ranked precedent may still be prohibited from production use.

## 5. Example: A Precedent Record

The following YAML is illustrative and intentionally incomplete. It must not be treated as an adopted SIF interoperability standard.

```yaml
precedent_id: sif:precedent:supply-chain:route-replanning:case-017
revision_id: rev-003
status: provisionally_supported
problem:
  intent: replan_delivery_routes_after_disruption
  input_types: [typed_road_network, shipment_constraints]
  required_outputs: [feasible_route_plan, explanation, audit_record]
  context:
    disruption: road_closure
    region_class: urban_distribution
  hard_constraints: [vehicle_capacity, delivery_windows]
structure:
  capability_refs:
    - sif:capability:localization:mdt-dispatch@2
    - sif:capability:optimization:vrp-solver@4
    - sif:capability:verification:constraint-checker@1
  composition: dispatch_then_optimize_then_verify
applicability:
  requires: [fresh_road_data, compatible_vehicle_schema]
  excludes: [hazardous_materials_without_special_policy]
evidence:
  supporting: [sif:evidence:experiment-041]
  counter: [sif:evidence:stress-test-009]
  limitation: tested_only_on_simulated_urban_scenarios
governance:
  evaluation_status: provisionally_supported
  deployment_status: sandbox_only
  authority_ref: sif:policy:logistics-research
lineage:
  parent_precedents: [sif:precedent:supply-chain:baseline:case-004]
  source: conceptual_example
```

The example demonstrates why a precedent cannot be reduced to a vector embedding or a single confidence score: the record includes typed interfaces, hard constraints, exclusions, negative evidence, and authority.

## 6. Precedent Retrieval: From Similarity to Qualified Applicability

A useful registry must avoid confusing a semantically similar case with an operationally transferable one.

### 6.1 Candidate generation

Potential retrieval mechanisms include:

1. **LLM semantic interpretation:** identify candidate task intent, missing constraints, and plausible analogies.
2. **CCC / metric-space matching:** compare reusable conceptual cores and residual differences.
3. **MDT localization:** narrow the search through structural distinctions and hierarchical contexts.
4. **Two-Phase Search:** use inexpensive coarse localization before detailed compatibility checks.
5. **CallingGraph matching:** compare task and capability dependency structures.
6. **Typed relay discovery:** locate compatible units through UNT-R identity and interface metadata.

These are complementary strategies, not a claim that one method dominates all tasks.

### 6.2 Hard filters before ranking

Candidate retrieval should first reject known violations of non-negotiable constraints:

```text
function retrieve_precedents(problem, context, policy, budget):
    candidates = multi_view_candidate_generation(problem, context)
    eligible = []

    for p in candidates:
        if not identity_and_version_resolve(p): continue
        if not type_and_semantic_contracts_compatible(p, problem): continue
        if violates_hard_constraints(p, problem, context): continue
        if not policy_allows_consideration(p, policy): continue
        if not resource_feasible(p, budget): continue
        eligible.append(p)

    ranked = evidence_aware_rank(eligible, problem, context)
    return attach_uncertainties_and_counter_evidence(ranked)
```

This pseudocode specifies desired behavior, not a verified algorithm. Unknown constraints may require clarification, simulation, or refusal to promote the candidate.

### 6.3 Multi-objective ranking

Among eligible candidates, a conceptual utility score might be:

$$
U(p\mid q) = w_s S(p,q) + w_e E(p,q) + w_t T(p,q) - w_r R(p,q) - w_c C(p,q),
$$

where \(S\) measures structural relevance, \(E\) evidence strength, \(T\) transferability, \(R\) estimated risk, and \(C\) resource cost. The weights are context-dependent and require calibration. No weighted sum may override a hard prohibition or missing authorization.

A **Scoring Tree/Forest** can preserve multiple perspectives instead of collapsing every tradeoff into one opaque score. Disagreements among perspectives should be inspectable.

### 6.4 Retrieval outputs

A well-formed retrieval result should include:

- matched precedent identifiers and revisions;
- exact matched and unmatched conditions;
- evidence quality and transfer uncertainty;
- relevant negative precedents;
- estimated adaptation effort;
- required validation steps;
- policy and execution eligibility;
- an explicit **no qualified precedent** outcome when appropriate.

The last outcome is essential: the system must be allowed to say that its existing knowledge does not justify a transfer.

## 7. Distinguishing, Adapting, and Composing Precedents

A legal precedent is often useful because a new case can be *distinguished* from it. The analogous SIF operation is **structural difference analysis**.

Given a query \(q\) and precedent \(p\), define a structured residual:

$$
\Delta(q,p) = \Delta_{context} \oplus \Delta_{types} \oplus \Delta_{constraints} \oplus \Delta_{capability} \oplus \Delta_{evidence} \oplus \Delta_{policy},
$$

where \(\oplus\) denotes a collection of typed differences, not necessarily numerical addition.

The residual determines whether to:

- reuse the precedent unchanged within its demonstrated envelope;
- adapt parameters under an existing contract;
- insert a typed adapter or relay;
- compose several precedents;
- perform new evaluation before reuse;
- reject the precedent and record why;
- initiate structural discovery when no justified composition exists.

**Composition is not automatically closed under validation.** Even if components A and B each have strong evidence, the combined system A→B can fail due to mismatched assumptions, feedback, latency, or policy interactions. The composition therefore needs its own precedent and evidence.

**Suggested figure:** `../../figures/Fig-005-Structural-Precedent-Intelligence.png` — place here to depict retrieve → distinguish → adapt → validate → register.

---

![Fig-005-Structural-Precedent-Intelligence.png](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 8. Registry–Runtime Separation and Universal Relay

The registry describes and justifies potential intelligence structures; the runtime executes authorized ones. This separation reduces the risk that a compelling retrieved case becomes an unreviewed action.

The **Universal Naming, Typing and Relay (UNT-R)** foundation supplies:

- stable, namespace-aware identity;
- machine-readable and human-interpretable type descriptions;
- versioned interface signatures;
- context handoff and localization metadata;
- relay endpoint discovery;
- policy and evidence references.

A minimal relay surface can include `describe`, `match`, `invoke`, `status`, `result`, and `cancel`. Advanced systems may support `delegate`, `handoff`, `evaluate`, `counterEvidence`, and `proposeGrowth`. These names are **candidate operations**, not deployed API commitments.

Before invocation, the runtime must independently confirm:

1. the referenced capability and version still exist;
2. input/output types and assumptions are compatible;
3. the current policy authorizes the requested action;
4. resource and safety budgets are available;
5. required monitoring and rollback paths are configured.

The registry should never act as an implicit authority issuer.

**Suggested figure:** `../../figures/Fig-004-Universal-Contracts-and-Relay.png` — place here to show registry references and runtime invocation boundaries.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 9. Structural Counter-Evidence and Adversarial Registry Governance

A registry that only accumulates success stories becomes a mechanism for confirmation bias and Goodhart-style optimization. **Structural Counter-Evidence (SCE)** must be a first-class record type.

Counter-evidence may challenge:

- the problem representation or localization;
- an assumed causal relationship;
- a capability's stated operating envelope;
- the fidelity of a simulation or benchmark;
- the generalization of an adaptation;
- the validity of the evaluator itself;
- resource estimates or governance assumptions.

The **Multi-Intelligence Adversarial Sandbox (MIAS)** can assign distinct roles to a Builder, Challenger, Independent Evaluator, and World/Simulation Engine, optionally supplemented by deterministic validators. Different intelligence models may contribute diverse critiques, but model diversity alone does not guarantee independence.

### 9.1 Challenge protocol

A proposed registry promotion should include:

1. **Claim declaration:** What exactly is asserted, for which context?
2. **Challenge construction:** What plausible cases could falsify it?
3. **Independent evaluation:** Can another method reproduce or refute the result?
4. **Ablation and stress tests:** Which components or assumptions are essential?
5. **Counter-evidence publication:** Which failures remain unresolved?
6. **Scoped decision:** Promote, constrain, defer, reject, or retire the claim.

Recursive challenges to evaluators must be bounded by risk and resource budgets. A never-ending evaluation recursion is not a practical governance policy.

### 9.2 Evidence conflict and trust

The registry should not overwrite conflicting evidence with a single consensus label. Instead, it should retain provenance, method differences, confidence intervals where meaningful, and the exact scope of disagreement.

Trust may depend on reproducibility, independent replication, source integrity, and relevance to the deployment context. Popularity, frequency of reuse, or model-generated enthusiasm are not substitutes for evidence.

**Suggested figure:** `../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` — place here to illustrate registry promotion under adversarial challenge.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 10. Lifecycle: From Candidate to Retired Precedent

A candidate lifecycle is:

```text
Proposed
   ↓
Registered as Unverified
   ↓
Sandbox Challenged
   ├──→ Rejected / Archived (retain negative evidence)
   └──→ Provisionally Supported
              ↓
         Scope-Validated
              ↓
         Shadow Evaluation
              ↓
         Authorized for Defined Use
              ↓
         Monitored / Rechallenged
              ├──→ Revised / Superseded
              ├──→ Suspended
              └──→ Retired
```

These states are not necessarily a universal linear pipeline. For example, a validated research precedent may never receive production authorization, while a previously authorized precedent may be suspended immediately after new counter-evidence.

### 10.1 Versioning and revocation

A registry should support append-only historical evidence and explicit supersession links. Changes in a model, dataset, API, environment, or policy may invalidate previously successful precedents. Revocation must propagate to dependent compositions and cached recommendations.

### 10.2 Privacy, confidentiality, and security

Precedent records may expose sensitive task descriptions, proprietary methods, internal policies, or personal data. Therefore:

- separate public metadata from access-controlled evidence;
- minimize retained inputs and outputs;
- support redaction and retention limits;
- authenticate publishers and protect provenance;
- treat retrieved precedent text as untrusted data, not executable instructions;
- defend against poisoned evidence and forged authority references.

Open interoperability does not require indiscriminate publication of sensitive case details.

## 11. Residuals as Inputs to Open-Ended Structural Growth

When no precedent qualifies, SPR should return a **typed structural residual**, not fabricate a match.

Useful residual classes include localization, representation, capability, composition, evidence, control, resource, environment, and perspective gaps. Each suggests a different research response:

| Residual | Possible response |
|---|---|
| Localization | Improve MDT/CCC routing or introduce another indexing view. |
| Representation | Add a missing type, distinction, or world-state model. |
| Capability | Discover or train a new per-node method. |
| Composition | Develop a relay adapter or new CallingGraph pattern. |
| Evidence | Design an independent benchmark or challenge. |
| Control | Revise authority boundaries or approval workflows. |
| Resource | Seek a more efficient structure or constrained approximation. |
| Environment | Update world-model assumptions and sensing. |
| Perspective | Introduce a new problem framing or granularity. |

A validated new structure becomes a candidate capability definition and precedent; its failures become negative cases. Thus SPR participates in an **open structural growth loop** without asserting that every residual has a solvable or discoverable answer.

**Suggested figure:** `../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png` — place here to show residual → candidate → challenge → precedent update.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 12. Illustrative Case: Supply-Chain Disruption Planning

Consider a logistics operator facing an unexpected road closure and delayed deliveries.

**Step A — PSM construction.** The system identifies route feasibility, vehicle capacities, delivery windows, and the need for auditable replanning.

**Step B — SPR retrieval.** It locates a prior precedent that combined structural localization, vehicle-route optimization, and constraint verification.

**Step C — Distinction.** The precedent used simulated urban road data, while the new request involves a live region with incomplete traffic feeds. This is a significant environment and evidence residual.

**Step D — Adaptation proposal.** A candidate composition adds a freshness check and a fallback conservative route planner. The proposal remains sandbox-only.

**Step E — Adversarial challenge.** A challenger injects stale traffic updates and conflicting delivery windows; an independent constraint checker examines the candidate's outputs.

**Step F — Governance.** The operator's policy determines whether a human must approve the revised plan. Successful sandbox scores do not bypass that requirement.

**Step G — Registry update.** The system records the new case, observed performance, unresolved limitations, and links to both supporting and negative evidence.

This is an **illustrative design scenario**, not a reported experiment or measured performance result.

## 13. Engineering Architecture and Deployment Path

A practical SPR implementation could separate five logical services:

1. **Identity and Contract Service:** resolves names, versions, types, and SIC references.
2. **Precedent Store:** retains cases, lineage, and lifecycle transitions.
3. **Evidence and Counter-Evidence Store:** retains attributed test artifacts and challenge results.
4. **Multi-View Retrieval Service:** supports semantic, structural, typed, and graph-based search.
5. **Governance and Audit Service:** checks policy eligibility and records authorization decisions.

These are functional boundaries, not a requirement for five independently deployed microservices. A prototype may begin with a single store and deterministic filters.

### 13.1 Minimal research prototype

A credible first experiment should prioritize correctness over breadth:

- define a small set of typed problem signatures and capability contracts;
- register positive, negative, and unresolved cases;
- compare keyword/vector retrieval with structured constraint filtering;
- test whether counter-evidence reduces invalid transfer;
- record all decisions and reproducible evaluation artifacts;
- use simulated or otherwise safely controlled workloads.

Only after the registry shows measurable value should it expand toward automated adaptation, multi-agent challenge, or higher-order composition.

### 13.2 Suggested conformance tests

Candidate interoperability tests include identifier uniqueness, revision immutability, type mismatch rejection, hard-policy enforcement, evidence provenance preservation, supersession resolution, revocation propagation, and explicit no-match handling.

The draft companion specification should distinguish **required**, **recommended**, and **optional** fields, with version migration and backward compatibility rules.

## 14. Research Hypotheses and Falsification Criteria

The following hypotheses are proposals for evaluation, not established findings.

| ID | Hypothesis | Test and potential falsifier |
|---|---|---|
| H1 | Structured precedent retrieval reduces invalid capability transfer relative to semantic similarity alone. | Compare matched tasks under hidden constraint shifts; no improvement falsifies the claim. |
| H2 | Negative precedents improve rejection of unsafe or inapplicable candidates. | Ablate counter-evidence; equal rejection accuracy weakens the hypothesis. |
| H3 | PSM–SPR–SCM matching improves cross-domain composition discovery. | Compare with direct tool catalogs on held-out tasks; no generalization gain challenges it. |
| H4 | Typed applicability envelopes reduce costly runtime contract failures. | Measure mismatch rate and latency tradeoff; no net benefit challenges it. |
| H5 | Adversarial challenge improves precedent calibration. | Compare independent test outcomes with and without MIAS; persistent overconfidence refutes it. |
| H6 | Lineage-aware versioning reduces reuse of stale structures. | Introduce model/API changes; failure to catch stale dependencies refutes it. |
| H7 | Residual classification accelerates useful structural improvement. | Compare research cycles with generic failure logging; no improvement challenges it. |
| H8 | Capability-to-problem reverse mapping discovers useful new applications. | Evaluate novelty and independently validated utility; low-value suggestions challenge it. |

Measurements should include not only task success but also false transfer rate, cost, latency, calibration, auditability, policy violations, and the quality of explicit abstentions. Results should be stratified by domain and risk class.

## 15. Failure Modes and Design Limits

### 15.1 Similarity mistaken for applicability

An embedding can retrieve a plausible precedent whose assumptions are incompatible. Hard filters, structural distinction, and evidence review are necessary.

### 15.2 Registry bloat and duplicate cases

Unchecked accumulation can degrade retrieval and obscure failures. Deduplication should preserve distinct contexts and contradictory outcomes rather than erasing them.

### 15.3 Authority laundering

A highly ranked or frequently cited precedent can appear authoritative even when it lacks deployment approval. Evaluation and authorization must remain separate.

### 15.4 Evidence laundering and benchmark overfitting

Repeated self-evaluation can make weak structures look strong. Independent tests, challenge diversity, and evaluator governance are required.

### 15.5 Hidden compositional failure

Validated components may interact unpredictably. Composed structures need dedicated tests and explicit dependency tracking.

### 15.6 Open-world incompleteness

No registry can enumerate all future intelligence structures, problem perspectives, or environmental conditions. The ability to register unknowns and revise the schema is therefore foundational, not an implementation defect.

### 15.7 Unbounded governance cost

Perfectly exhaustive evaluation is infeasible. Validation depth must be proportional to risk, uncertainty, and resource budget.

## 16. Open Research Questions

1. How should applicability envelopes represent partial observability and evolving world models?
2. Which graph, metric, and semantic representations best support cross-domain precedent retrieval?
3. How can evidence strength be calibrated when experiments are heterogeneous or non-reproducible?
4. When should a negative precedent block reuse versus trigger adaptation?
5. What is the minimal SIC sufficient for meaningful cross-organization relay?
6. How can policy constraints remain enforceable through multi-step compositions?
7. How should a registry detect structural novelty rather than merely renamed duplicates?
8. Can capability-to-problem reverse mapping expand a system's **Structural Perception Horizon** in measurable ways?
9. How can collective learning share useful precedents without exposing sensitive contexts or concentrating governance authority?
10. What evidence justifies promotion from an exploratory precedent to a dependable macro-intelligence piece?

## 17. Relationship to the SIF Research Program

This paper extends the foundations in:

- `../foundations/SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md`
- `../foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md`
- `../foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md`
- `../functional-domains/SIF-004-Localization-and-Intelligence-Addressing.md`
- `../functional-domains/SIF-005-Per-Node-Intelligence-and-Multi-Perspective-Capabilities.md`
- `../functional-domains/SIF-006-Universal-Control-Planes-and-Scoring-Folding.md`
- `../functional-domains/SIF-007-Residual-Based-Structural-Growth.md`
- `SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md`

It prepares the ground for:

- `SIF-010-Universal-Naming-Typing-and-Relay.md`
- `SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md`
- `../validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md`
- `../validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md`
- `../../specifications/SPEC-003-Structural-Precedent-Registry-Schema.md`

The intended relationship is complementary: **SIF-003** develops the precedent concept, **SIF-008** defines dual-map matching, and **SIF-009** specifies the registry's information and governance responsibilities.

## 18. Conclusion

A structural intelligence framework needs more than a library of callable functions and more than a ranking system for superficially similar tasks. It needs a disciplined memory of **what structures were tried, why they appeared applicable, what happened, what failed, and who may authorize their future use**.

The proposed Structural Precedent Registry makes this memory explicit. By linking problem signatures, capability contracts, context, evidence, counter-evidence, lineage, and governance, SPR provides a candidate mechanism for reusable and challengeable structural intelligence. Its strongest design commitment is not that every problem has a precedent, but that **the absence or failure of a qualified precedent must remain visible**.

That visibility turns the registry from a static archive into a potential participant in open-ended structural growth:

> **Reuse what has earned evidence; distinguish what has changed; challenge what remains uncertain; and preserve the residual from which a better intelligence structure may emerge.**

---

**Suggested citation:** Tan, S., & GPT-Obot. (2026). *SIF-009: Structural Precedent Registry*. Structural Intelligence Framework, v1.0.0. Repository DOI to be assigned upon release.
