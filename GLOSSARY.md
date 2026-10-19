# Glossary — Structural Intelligence Framework (SIF)

**Project:** Structural Intelligence Framework (SIF)  
**Version:** v1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Research terminology; definitions are proposed, not standardized.

## Purpose and reading conventions

This glossary establishes a consistent vocabulary for the SIF research corpus. Terms describe **architectural roles**, **candidate mechanisms**, or **research hypotheses**; they do not imply that an implementation exists or that a performance claim has been validated. Related concepts may overlap in implementation without being synonymous.

- **Architectural concept:** a design abstraction or functional responsibility.
- **Candidate specification:** a proposed interface or schema awaiting interoperability and conformance testing.
- **Research hypothesis:** a proposition requiring empirical or formal evaluation.
- **Authorization:** permission to act under an explicit policy, distinct from technical feasibility or evaluation success.

## A. Framework and functional domains

### Structural Intelligence Framework (SIF)
An open research architecture for identifying, addressing, composing, governing, evaluating, and evolving heterogeneous intelligence structures. SIF is **not** a single model, a closed algorithm catalog, or an assertion that its mechanisms are already proven.

### Open Structural Intelligence
The architectural principle that usable intelligence structures may be introduced, adapted, combined, challenged, replaced, and retired without assuming any present collection is complete.

### Intelligence Structure
A distinguishable and potentially reusable arrangement of representations, procedures, models, interfaces, constraints, or control relationships that contributes to an intelligence task. A structure may be simple or composite.

### Four Functional Domains
Four complementary, **nonexclusive** responsibilities in SIF: (1) Localization and Intelligence Addressing, (2) Per-Node Intelligence, (3) Universal Control Planes and Scoring/Folding, and (4) Residual-Based Structural Growth. A component can participate in several domains.

### Localization and Intelligence Addressing
Discovering and selecting relevant representations, capabilities, precedents, contexts, or execution paths for a problem, including the conditions under which they apply. It is broader than document retrieval.

### Per-Node Intelligence
The computational and reasoning capabilities available at a node of a larger structure: for example LLM inference, rules, optimization, simulation, ANN retrieval, or formal verification. A node is not restricted to one algorithm or one implementation.

### Universal Control Planes
Cross-cutting arrangements for policy and authority, scoring and decision, and evidence and audit. These functions should be distinguishable even when implemented by shared software.

### Residual-Based Structural Growth
The governed process of diagnosing inadequacies in existing structures and proposing, testing, incorporating, revising, or rejecting structural changes. A residual is a research signal, not proof that a novel structure is necessary.

### Structural Intelligence Registry
The conceptual inventory of capability definitions, contracts, precedents, versions, and evidence. The **Structural Precedent Registry** is a more specific component focused on cases and their applicability.

### Structural Intelligence Runtime
The execution and orchestration environment that resolves capabilities, checks contracts and policy, performs authorized relays, and records outcomes. It is conceptually separate from the evolution laboratory.

### Structural Intelligence Evolution Laboratory
The environment for proposing and testing changes to intelligence structures, including adversarial evaluation and evidence capture; it does not itself confer production authority.

## B. Problems, capabilities, and localization

### Structural Problem-Solving Map (PSM)
A graph-like representation of a problem's goals, decomposition, constraints, context, dependencies, and acceptance criteria. Analogous to a task-oriented CallingGraph, but not limited to function calls.

### Structural Capability Map (SCM)
A graph-like representation of available capabilities, interfaces, composition relationships, applicability, versions, and evidence. Analogous to an action-oriented CallingGraph.

### Bidirectional Structural Intelligence Mapping (BSIM)
The proposed mapping between PSM and SCM: **problem → candidate capabilities** and **new or revised capability → candidate problems and applications**. Both directions require applicability and evidence checks.

### Task CallingGraph
A structured representation of task decomposition and dependencies, emphasizing **what work must be accomplished**. It informs PSM but is not identical to every PSM implementation.

### Action CallingGraph
A structured representation of executable actions, capabilities, and their composition, emphasizing **what the system can do**. It informs SCM.

### CallingGraph (CG)
A graph of callable operations and dependencies used to represent, compose, dispatch, or unfold tasks and actions. Its exact semantics depend on the associated implementation or research context.

### Large Language Model (LLM)
A learned language-oriented model that can contribute interpretation, reasoning, generation, planning, matching, and interface mediation. In SIF it is a major capability, not a substitute for all other structures.

### Common Concept Core (CCC)
A proposed reusable shared conceptual or structural core, with context-dependent differences represented separately. CCC may support matching, representation, dispatch, and growth; it is not equivalent to an ordinary statistical mean.

### Two-Way CCC
A bidirectional use of shared structural concepts for forward matching or dispatch and backward checking, comparison, or counter-evidence, depending on the application.

### Metric Differential Tree (MDT)
A hierarchical representation of structural differences organized using metrics or comparable criteria, intended to support localization, progressive refinement, and selective computation.

### Two-Phase Search
A search design separating an initial, cheaper localization or candidate-generation phase from a more selective, evidence-intensive refinement or verification phase. The phases and metrics are implementation-specific.

### Core + Delta Growth
A representation and evolution pattern that retains a reusable core while expressing contextual or evolutionary differences as deltas. It does not guarantee that deltas are small or lossless.

### Context-Bound Token (CBT)
A token or unit whose meaning, identity, or interpretation is tied to a specified context rather than treated as globally context-free.

### World Model
A computable representation of relevant world states, dynamics, constraints, and possibly causal relations used for prediction, planning, or simulation. World models can also serve as per-node capabilities.

## C. Structural precedents and reuse

### Structural Precedent Intelligence (SPI)
The proposed use of recorded structural cases—including their conditions, adaptations, evidence, and failures—to guide future problem solving and structural evolution. The legal-precedent analogy is methodological, not a claim of legal equivalence.

### Structural Precedent
A reusable **claim about a structure in a context**, supported or limited by recorded evidence. It is not merely a successful answer or a general guarantee of transferability.

### Structural Precedent Registry (SPR)
A proposed searchable, versioned repository of capability definitions, precedent cases, evidence, counter-evidence, applicability constraints, and lineage. See [SPEC-003](specifications/SPEC-003-Structural-Precedent-Registry-Schema.md).

### Capability Definition
A description of what a structure purports to do, including its signatures, assumptions, interfaces, versions, and applicable constraints. It is distinct from a record showing that it worked in a particular case.

### Precedent Case
A recorded application of a capability or composition to a specific problem and context, with outcomes and supporting or contradicting evidence.

### Applicability Envelope
The set of contexts, assumptions, resource conditions, constraints, and exclusions within which a capability or precedent has been claimed or tested. **Claimed scope** must be distinguished from **validated scope**.

### Structural Adaptation
A modification of a retrieved precedent or capability to suit a new problem or environment. Adaptation requires renewed validation where assumptions or interfaces change.

### Lineage
Versioned provenance and relationships among structural definitions, cases, adaptations, replacements, and retirements.

## D. Contracts, types, and relay

### Structural Intelligence Contract (SIC)
A candidate cross-boundary declaration of identity, type, capability, input/output signature, context, relay, evidence, policy, lifecycle, and growth hooks. A contract makes claims inspectable; it does not itself prove them. See [SPEC-001](specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md).

### Universal Naming, Typing and Relay (UNT-R)
A proposed interoperability foundation for naming structures, checking typed and contextual compatibility, and handing work across heterogeneous intelligence components. See [SPEC-002](specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md).

### Universal Naming
Stable identification, versioning, and resolution of capabilities, contracts, evidence, sessions, and related objects, with provenance and namespace rules.

### Universal Typing
Compatibility assessment across more than syntax: potentially semantics, context, behavior, evidence, governance, and resource requirements. Type agreement alone does not prove behavioral correctness.

### Intelligence Relay
A governed transfer of a task, state, context, or result between intelligence structures, preserving the relevant boundary conditions and traceability.

### Baseline Relay Operations
The six proposed core operations: `describe`, `match`, `invoke`, `status`, `result`, and `cancel`. Their precise request/response schemas remain candidate specifications.

### Extended Relay Operations
Optional operations such as `delegate`, `handoff`, `evaluate`, `counterEvidence`, and `proposeGrowth`; support for one extension does not imply support for all.

### Relay Session
A traceable interaction instance linking caller, callee, contract versions, inputs, context, authorization decisions, results, and cancellation or failure states.

### Context Preservation
Maintaining the assumptions, references, meanings, provenance, and constraints needed for a valid handoff. Copying a payload without its interpretation context is not necessarily preservation.

### Portable Intelligence Runtime Piece (PIRP)
A flexible, potentially exploratory intelligence piece that can be described, shared, adapted, or relayed without requiring full unit-level formalization.

### Portable Intelligence Runtime Unit (PIRU)
A more explicitly bounded and contract-governed intelligence unit intended for dependable portability, composition, and validation. PIRU is not synonymous with a container or microservice.

### Macro-Intelligence Piece (MIP)
A composite intelligence structure exposed as a reusable higher-level piece or node. Its external contract must retain the assumptions, evidence, and governance implications of its composition.

### Structural Folding / Unfolding
Abstraction of a complex structure into a simpler reusable or navigable representation, and selective restoration or refinement of details when needed. Folding can lose information; reversibility must be specified and tested, not assumed.

## E. Scoring, policy, and evidence

### Policy and Authority Plane
The control function that determines **whether an action is permitted**, by whom, under which scope, and subject to what constraints.

### Scoring and Decision Plane
The control function that ranks, selects, or recommends candidates using explicit or learned criteria. A high score is not an authorization.

### Evidence and Audit Plane
The function that collects, links, assesses, and preserves evidence, counter-evidence, provenance, decisions, and execution traces.

### Scoring Tree
A hierarchical structure for evaluating alternatives through nested criteria, contexts, or subproblems. Scores require defined scales, normalization, and aggregation rules.

### Scoring Forest
A collection of scoring trees or evaluators representing multiple perspectives, objectives, or domains. Aggregating a forest does not eliminate conflicts among its criteria.

### Scoring Folding
An abstraction or composition of scoring structures intended to reduce complexity or enable higher-level decisions, subject to information-loss and auditability checks.

### Evidence Record
A traceable statement of a test, observation, result, provenance, methodology, and scope that bears on a structural claim.

### Structural Counter-Evidence (SCE)
Evidence challenging not only a result but also the assumptions, representation, localization, applicability, composition, evaluator, governance, or perspective behind a structural claim.

### Evaluator Governance
Oversight of evaluator design, independence, incentives, validity, drift, and susceptibility to manipulation. It includes bounded challenges to the evaluators themselves.

### Anti-Goodhart
Measures to reduce optimization against proxies that cease to represent the intended objective, such as independent metrics, adversarial tests, withheld cases, and counter-evidence retention.

### Validation
Assessment that a defined claim holds under specified methods and conditions. Validation may be narrow, provisional, and reversible.

### Qualification
A determination that specified evidence gates have been satisfied for a defined context or conformance profile. Qualification is not automatically permission to deploy.

### Action Authorization
A distinct policy decision allowing a specified actor or system to perform specified actions under explicit boundaries. **Capability ≠ validation ≠ authorization.**

## F. Adversarial testing and structural growth

### Multi-Intelligence Adversarial Sandbox (MIAS)
A proposed isolated environment where heterogeneous agents and tools construct, challenge, evaluate, and revise structural claims. Its value is a research hypothesis, not a guarantee of exhaustive falsification.

### Builder
The role proposing a candidate structure, adaptation, or improvement and supplying its supporting rationale and evidence.

### Challenger
The role seeking counterexamples, hidden assumptions, boundary failures, adversarial cases, and alternative explanations.

### Independent Evaluator
A role assessing claims against declared criteria while being organizationally or procedurally separated from the Builder where feasible. Independence is a property to establish, not a label alone.

### Formal Checker
A deterministic or formal-methods component that checks specified properties, invariants, or proofs. Its conclusions extend only to the modeled properties and assumptions.

### World / Simulation Engine
An environment for generating or replaying scenarios and assessing candidate behavior. Simulator fidelity and coverage are themselves validation questions.

### Exploratory Sandbox
An isolated setting for untrusted or unqualified candidates, with constrained access, resources, and side effects.

### Validated Shadow Runtime
A non-authoritative environment for testing qualified candidates against realistic workloads without granting them production decision authority.

### Authorized Production Runtime
The environment in which actions may affect real systems, subject to explicit policy approval, monitoring, rollback, and scope restrictions.

### Structural Residual
An observed or hypothesized mismatch between problem demands and current representations, capabilities, composition, evidence, control, resources, or perspectives. Residual categories are diagnostic aids, not necessarily mutually exclusive.

### Growth Candidate
A proposed new or modified structure motivated by a residual or a new opportunity, pending evaluation.

### Evidence-Gated Growth
A process in which promotion, integration, or deployment of structural changes depends on explicit evidence thresholds and governance decisions.

### Structural Recursive Self-Improvement (Structural RSI)
Improvement of the mechanisms that construct, select, evaluate, compose, or govern intelligence structures, potentially including the improvement process itself. Recursion must remain bounded by validation and authority constraints.

### Collective Structural Learning (CSL)
Learning through exchange and adaptation of structural knowledge, precedents, contracts, and evidence among multiple intelligence systems or BrainUnits, without presuming identical ownership or trust.

### BrainUnit
A bounded intelligence entity or subsystem with its own context, capabilities, responsibilities, and potentially distinct ownership or governance.

### Open-Ended Structural Growth
The capacity to admit unforeseen categories of structure, interfaces, compositions, and perspectives. It does **not** mean unbounded resources, automatic improvement, or guaranteed progress.

## G. Frontiers and research methodology

### Structural Perception Horizon (SPH)
The current boundary of structural distinctions, relationships, scales, and perspectives a system can effectively represent, detect, and evaluate. The boundary is task- and evidence-dependent.

### Worldview
The organizing perspective that determines which entities, relations, scales, distinctions, and causal explanations are considered meaningful. Unlike a world model, a worldview concerns the **choice of representational frame**.

### Worldview Reconstruction
A substantive revision of the conceptual frame used to formulate problems and evaluate possible solutions. Improved task accuracy alone is insufficient evidence of reconstruction.

### Within-Horizon Improvement
Better performance on problems expressible within an existing structural perception horizon.

### Capability Extension
Adding or improving procedures that expand what a system can compute or perform, without necessarily changing its representational perspective.

### Perceptual Extension
Demonstrable ability to detect, represent, or evaluate distinctions that were previously outside the effective perception horizon.

### Perspective
A task- or context-dependent selection of objectives, distinctions, assumptions, metrics, scales, and evidence criteria.

### Perspective-Relative ASI (Perspective ASI)
A proposed, bounded way of discussing superhuman intelligence **relative to specified domains, tasks, metrics, resources, time horizons, and governance conditions**. It is not a universal definition of ASI or evidence that general ASI has been achieved.

### Multi-Axis Scaling
Study of intelligence development across interacting dimensions: large structures, structural depth, precision guidance, computational investment, interoperability, evidence, governance, and collective learning.

### Precision Guidance
Selective routing of attention, search, compute, or verification effort toward promising or consequential structural regions, subject to uncertainty and error costs.

### AI Structural Discovery and Growth Stream (AI-SDGS)
A proposed AI-assisted workflow for discovering, evaluating, integrating, and retiring intelligence structures. It is a research direction, not a deployed product category.

### Testable Hypothesis
A specific proposition accompanied by measurable outcomes, baselines, and conditions under which evidence would count against it. See [TESTABLE-HYPOTHESES](research/TESTABLE-HYPOTHESES.md).

### Conformance Profile
A specified subset of candidate interface or process requirements for assessing interoperability or governance readiness. A profile label does not substitute for test results.

### Evidence Levels (E0–E4)
A proposed research maturity ladder from conceptual claims through executable demonstrations and controlled experiments to adversarial assessment and independent replication. Exact criteria belong to the research validation documents.

## H. Frequently confused distinctions

| Do not conflate | Key distinction |
|---|---|
| SIF vs. LLM | SIF is an open architecture; an LLM is one important capability within it. |
| Functional domain vs. software layer | Domains are responsibilities that may overlap, not a mandatory exclusive stack. |
| PSM vs. SCM | PSM describes demand; SCM describes supply. |
| Matching vs. applicability | Similarity retrieves candidates; applicability requires contextual and evidential checks. |
| Precedent vs. capability | A precedent records a contextual case; a capability defines a reusable function or claim. |
| Contract vs. proof | A contract declares boundaries; evidence and tests assess its claims. |
| Type compatibility vs. semantic validity | Compatible interfaces may still produce wrong interpretations or outcomes. |
| Validation vs. authorization | Evidence that something works does not grant permission to act. |
| Residual vs. discovery | A diagnosed gap motivates investigation; it does not establish novelty or improvement. |
| Folding vs. lossless compression | Folding may omit details; restoration and auditability need explicit guarantees. |
| World model vs. worldview | One models states and dynamics; the other frames which distinctions matter. |
| Scaling vs. progress | More components or compute do not guarantee better intelligence or safety. |
| Perspective ASI vs. universal ASI | Bounded superiority under specified criteria does not imply superiority across all contexts. |

## I. Source navigation

**Core manuscripts**

- [SIF-001 — From Isolated Intelligence to Open Structural Intelligence](docs/foundations/SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md)
- [SIF-002 — Four Functional Domains](docs/foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md)
- [SIF-003 — Structural Precedents](docs/foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md)
- [SIF-008 — Dual Maps](docs/interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md)
- [SIF-010 — UNT-R](docs/interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md)
- [SIF-011 — SIC and Portable Units](docs/interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md)
- [SIF-012 — MIAS](docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
- [SIF-015 — Structural Perception Horizon](docs/frontiers/SIF-015-Structural-Perception-Horizon-and-Worldview-Growth.md)
- [SIF-018 — Perspective ASI](docs/frontiers/SIF-018-Perspective-ASI-and-the-Open-Future-of-Intelligence.md)

**Candidate specifications and research files**

- [SPEC-001 — Structural Intelligence Contract](specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md)
- [SPEC-002 — Universal Name, Type, and Relay API](specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md)
- [SPEC-003 — Structural Precedent Registry Schema](specifications/SPEC-003-Structural-Precedent-Registry-Schema.md)
- [SPEC-004 — Sandbox Evidence and Growth Lifecycle](specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md)
- [OPEN-QUESTIONS](research/OPEN-QUESTIONS.md)
- [TESTABLE-HYPOTHESES](research/TESTABLE-HYPOTHESES.md)
- [VALIDATION-ROADMAP](research/VALIDATION-ROADMAP.md)

For the complete document list, see [CONTENTS.md](CONTENTS.md). For suggested reading paths, see [START-HERE.md](START-HERE.md).

---

**Maintenance note:** This glossary is a versioned research reference. When definitions change, update linked manuscripts and candidate specifications and document the change in `CHANGELOG.md`. Do not silently broaden validated claims or conformance guarantees.
