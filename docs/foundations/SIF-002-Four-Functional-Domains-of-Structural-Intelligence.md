# SIF-002 — Four Functional Domains of Structural Intelligence

**Structural Intelligence Framework (SIF) — Foundations Series**  
**Version:** 1.0.0 (research framework)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed architecture; conceptual claims require empirical validation  
**Repository:** https://github.com/sizhet/Structural-Intelligence-Framework

## Abstract

The Structural Intelligence Framework (SIF) organizes heterogeneous intelligence capabilities into four interacting functional domains: **(I) Localization**, **(II) Per-Node Intelligence**, **(III) Universal Control Planes and Scoring/Folding**, and **(IV) Residual-Based Structural Growth**. These are *functional domains*, not mutually exclusive software layers, fixed model classes, or a closed taxonomy. The same structure—such as an LLM, world model, concept core, or scoring engine—may serve multiple roles depending on its context and contract. This paper defines the responsibilities, interfaces, feedback paths, and boundaries of the four domains; positions naming, typing, relay, evidence, and governance as cross-cutting infrastructure; and proposes a disciplined route from a descriptive map to a testable engineering architecture. The central proposition is that intelligence should be organized for **discovery, composition, evaluation, and revision**, without assuming any single architecture exhausts future intelligence.

**Keywords:** Structural Intelligence Framework; localization; per-node intelligence; control plane; scoring forest; structural folding; residual growth; interoperability; counter-evidence; open-ended intelligence.

---

## 1. Motivation: From Isolated Algorithms to Functional Organization

Contemporary computational intelligence spans language models, retrieval systems, symbolic engines, numerical solvers, simulations, optimizers, and specialized software. These capabilities are often discussed as separate techniques or arranged in taxonomies based on implementation. Such catalogs are useful, but insufficient for answering four operational questions:

1. **Where** in a problem space should intelligence be applied?
2. **What** capability should perform the local work?
3. **Who or what** evaluates, constrains, and authorizes the result or action?
4. **How** should the system respond when available structures fail or leave important aspects unexplained?

SIF maps these questions to four functional domains. The domains provide a stable organizing vocabulary while remaining open to new algorithms, models, and representations.

The framework does **not** claim that every computation is intrinsically intelligent. A deterministic program may become a valuable per-node capability when embedded in an intelligent problem-solving workflow. Nor does SIF claim a demonstrated universal advantage over other architectures; such benefits are hypotheses to be tested under matched workloads and budgets.

## 2. The Four-Domain Architecture

| Domain | Primary question | Core responsibility | Typical outputs |
|---|---|---|---|
| I. Localization | Where should intelligence be applied? | Identify relevant problem regions, context, structures, and execution destinations | Candidate nodes, context bindings, routes, uncertainty |
| II. Per-Node Intelligence | What capability should operate here? | Reason, calculate, predict, search, simulate, or transform | Results, candidate actions, explanations, artifacts |
| III. Control Planes and Scoring/Folding | Which outcomes and actions are acceptable? | Apply policies, compare alternatives, manage authority and audit | Rankings, constraints, approvals, denials, traces |
| IV. Residual-Based Structural Growth | What is missing or inadequate? | Detect gaps, propose changes, test and register validated structures | Counter-evidence, new candidates, revisions, retirement decisions |

These domains describe **roles**, not exclusive containers. For example, an LLM may classify a problem in Localization, generate an answer within Per-Node Intelligence, assist with scoring under controlled evaluation, or suggest a new structure in Growth. Each role should be declared and evaluated separately.

**Figure placement:** `../../figures/Fig-002-Four-Functional-Domains.png` may be inserted here when available.

## 3. Domain I — Localization of Intelligence Problems

### 3.1 Purpose

Localization extends beyond information retrieval. It determines *which representation, context, capability, or delegated destination* is relevant to a problem. The target may be a document, a graph region, a computational node, a world-state hypothesis, or a chain of capabilities.

### 3.2 Representative structures

- **LLM-based localization:** semantic interpretation, decomposition, candidate routing, and flexible handling of incomplete descriptions. Its maturity and broad applicability justify placing it first in the initial SIF registry, without asserting it is universally optimal.
- **Metric-space CCC:** shared structural cores and context-dependent residuals; unlike a simple mean/standard-deviation summary, a CCC may encode conditions, behaviors, and semantic relations.
- **Metric Differential Tree (MDT):** hierarchical differential indexing, progressive narrowing, and structural addressing.
- **Two-phase search:** inexpensive candidate localization followed by deeper evaluation, especially for partial or uncertain targets.
- **Intelligence Relay Network:** discovery and handoff across specialized nodes or organizations.
- **CallingGraph for AI coding:** dependency-aware mapping between task requirements and executable capabilities.
- **Core + Delta:** localize shared structure and problem-specific variation without repeatedly reconstructing the whole representation.
- **Universal names, types, and relay interfaces:** make discovered targets addressable and interpretable across boundaries.
- **World models:** contribute state estimation and predicted consequences, but also operate in Per-Node, Control, and Growth roles; they are not exclusively localization engines.

### 3.3 Localization contract

A localization result should ideally include a target identity, a task-to-capability match rationale, required context, known assumptions, confidence or uncertainty representation where meaningful, and fallback routes. A locator should not silently grant permission to execute the target.

## 4. Domain II — Per-Node Intelligence

### 4.1 Purpose and openness

Per-Node Intelligence is deliberately plural. Nodes may be LLMs, rule engines, Two-Way CCC or principle engines, event-trigger systems, ANN retrieval, linear algebra kernels, optimization solvers, time-series models, simulations, world models, or composite systems. The category is open to future computational methods.

A node's value depends on *fitness to the task*, not parameter count, model family, or novelty. A small constraint checker may be the correct final gate for a safety-sensitive workflow even when a larger generative model supplies candidate solutions.

### 4.2 Multiple classification perspectives

No single taxonomy captures all useful distinctions. A capability may be indexed simultaneously by:

- **Algorithm:** symbolic, statistical, neural, numerical, simulation, optimization, hybrid.
- **Application:** coding, planning, science, logistics, education, operations, etc.
- **Signature and API:** accepted inputs, outputs, state transitions, resource requirements, and relay methods.
- **Execution properties:** deterministic/stochastic, synchronous/asynchronous, local/remote, bounded/unbounded.
- **Evidence and governance:** test coverage, uncertainty, provenance, permissions, and known failure modes.

### 4.3 Per-node contract

A useful node declaration includes identity and version, capabilities, input/output signatures, assumptions, applicable contexts, limitations, resource requirements, evidence, policy constraints, and growth hooks. This is a proposed *Structural Intelligence Contract (SIC)*, not a claim that a universal protocol has already been standardized.

## 5. Domain III — Universal Control Planes and Scoring/Folding

### 5.1 Why control is a distinct function

Producing a candidate answer, evaluating its quality, and authorizing its real-world execution are three different operations. In particular:

> **Evaluation does not imply authorization.**

A top-scoring candidate may still violate a hard constraint, lack required evidence, or fall outside an agent's authority.

### 5.2 Three interacting planes

1. **Policy and authority plane:** ownership, delegated rights, hard constraints, action boundaries, and escalation paths.
2. **Scoring and decision plane:** Scoring Tree/Forest, perspective-dependent comparisons, structural folding/unfolding, multi-objective tradeoffs, and candidate selection.
3. **Evidence and audit plane:** provenance, uncertainty, counter-evidence, evaluator calibration, decision traces, and post-deployment monitoring.

The planes interact but must not collapse into a single opaque scalar score. Hard constraints should remain distinguishable from preferences. A scoring mechanism can exist inside one node or across an entire system; role and authority are context-dependent.

### 5.3 Governance of evaluators

Evaluators can fail, overfit, or be gamed. SIF therefore calls for independent tests, adversarial challenge, alternative perspectives, and versioned evaluation criteria. Recursive evaluation must be bounded by risk, resources, and explicit stopping conditions.

## 6. Domain IV — Residual-Based Structural Growth

### 6.1 Residuals as structural signals

A residual is not necessarily a numerical prediction error. SIF distinguishes, among others:

| Residual | Example |
|---|---|
| Prediction | A forecast systematically misses observed outcomes |
| Structural | The available representation cannot express a relevant relation |
| Localization | No suitable capability or destination can be found |
| Perspective | An important framing or stakeholder view is absent |
| Relay | Two nodes cannot transfer meaning or context reliably |
| Control | Scoring and policy fail to resolve a material conflict |
| World-model | Simulated dynamics diverge from reality |
| Governance | An authority, accountability, or audit gap is exposed |

Residuals can also be noise, data errors, or transient operational faults. **Detection is not automatic justification for growth.**

### 6.2 Candidate lifecycle

1. Detect and characterize residuals, leftovers, and counter-evidence.
2. Distinguish structural inadequacy from noise or implementation defects.
3. Search the precedent registry for reusable or composable solutions.
4. Propose candidate localization, per-node, relay, control, or worldview changes.
5. Evaluate candidates in isolated tests and, where appropriate, multi-intelligence adversarial sandboxes.
6. Accept, restrict, revise, reject, or retain as an open research problem.
7. Version and register accepted changes with evidence, limitations, and rollback paths.

Growth includes replacement and retirement, not merely accumulation. A new structure should demonstrate value relative to simpler alternatives and its added coordination cost.

## 7. Cross-Cutting Infrastructure: Identity, Contracts, Relay, and Evidence

The four domains require common infrastructure but should not be forced into one algorithmic implementation.

### 7.1 Universal Name, Universal Type, Relay API

- **Name** identifies a structure or service across contexts and versions.
- **Type** describes capability semantics, constraints, and compatible representations.
- **Relay API** supports discovery, invocation, context handoff, results, and controlled delegation.

These functions form a candidate **Universal Naming, Typing and Relay (UNT-R)** foundation. Extensible namespaces and adapters are preferable to a closed global enumeration of intelligence types.

### 7.2 Portable intelligence and structural contracts

PIRP can carry relatively informal intelligence pieces; PIRU can provide more formal runtime units and contracts. Neither requires all intelligence to be converted into one rigid format. Contract-based interoperability standardizes the *boundary*, not the internal intelligence.

### 7.3 Evidence, policy, and provenance

All four domains should be able to reference evidence and policy requirements. Passing a syntactically valid payload is not proof of semantic compatibility, correctness, or authorization. Conformance tests and explicit context translations remain necessary.

## 8. Two Maps, One Open Registry

SIF benefits from two complementary maps:

- **Problem-Solving Map (Task CG perspective):** goals, constraints, decomposition, required intelligence, and execution dependencies.
- **Capability Map (Action CG perspective):** available structures, contracts, interfaces, known performance, and composable paths.

A **Structural Precedent Registry** connects them. It stores examples of successful and failed uses, applicability conditions, counter-evidence, and versioned claims.

The mapping is bidirectional. Problems can request capabilities; new capabilities can reveal previously unrecognized tasks. Matching can produce direct reuse, composition, or a documented residual that triggers research. This is a conceptual analogy to Task CG/Action CG, not a claim of identical graph semantics.

**Figure placement:** `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` may be inserted here when available.

## 9. Three System Responsibilities

The functional domains can be deployed across three complementary system responsibilities:

1. **Structural Intelligence Registry:** records what exists, its contracts, applicability, and evidence.
2. **Structural Intelligence Runtime:** localizes, invokes, relays, evaluates, and governs capabilities.
3. **Structural Intelligence Evolution Laboratory:** explores residuals, adversarially tests candidates, and proposes registry changes.

These are architectural responsibilities rather than mandatory physical services. A prototype may combine them; a large deployment may distribute them across organizations and sovereign boundaries.

## 10. Worked Example: Risk-Aware Supply-Chain Planning

Suppose an organization asks for a low-risk response to uncertain delivery disruptions.

**Localization** interprets the incomplete target, identifies relevant network segments, and routes subtasks to graph search, forecasts, and optimization. **Per-Node** capabilities estimate demand, simulate disruption scenarios, and generate candidate plans. **Control and Scoring** apply hard regulatory and safety constraints, compare cost, resilience, and delay, and require authorization before any operational change. **Growth** records systematic blind spots—for example, missing supplier-dependency information—and proposes a new data source, world-model perspective, or relay interface.

The system's effectiveness cannot be inferred from architecture alone. It must be compared against simpler baselines under matched workloads, with recorded latency, cost, failure modes, and downstream outcomes.

## 11. Boundaries and Failure Modes

A four-domain decomposition does not guarantee modularity, scalability, safety, or emergence. Important failure modes include:

- **Overclassification:** an inflexible registry obscures rather than improves discovery.
- **Semantic drift:** apparently compatible contracts encode different meanings.
- **Coordination overhead:** relay and control cost exceed the benefits of specialization.
- **Shared evaluator bias:** adversarial participants agree for the wrong reasons.
- **False growth:** transient errors produce unnecessary new structures.
- **Authority confusion:** a high score is mistaken for deployment permission.
- **Worldview lock-in:** the framework only discovers what its existing perspectives can represent.

These risks motivate open typing, independent evaluation, explicit policy boundaries, and reversibility.

## 12. Testable Research Propositions

The following are hypotheses, not established findings:

- **H1 — Localization efficiency:** structure-aware localization improves quality-adjusted retrieval or routing relative to flat alternatives at comparable compute budgets.
- **H2 — Composition benefit:** contract-based heterogeneous nodes outperform selected monolithic baselines on tasks requiring multiple specialized methods, after accounting for coordination cost.
- **H3 — Governance separation:** separating scoring from authorization reduces unauthorized or policy-inconsistent actions.
- **H4 — Counter-evidence quality:** diverse adversarial evaluators identify more consequential structural failures than a single evaluator, at controlled false-positive rates.
- **H5 — Growth quality:** residual-driven, evidence-gated evolution improves long-run task performance and reliability compared with unfiltered structural accumulation.
- **H6 — Perception expansion:** some validated higher-order compositions increase the set of task distinctions or relationships a system can reliably detect and evaluate.

Tests should use explicit operational definitions, preregistered or held-out cases where feasible, ablations, resource accounting, and independent replication.

## 13. Architectural Principles

1. **Open-ended evolution:** do not presume a closed inventory of possible intelligence structures.
2. **Functional rather than exclusive classification:** one structure may serve multiple domains.
3. **Precedent-first, not precedent-only:** reuse existing structures while preserving discovery pathways.
4. **Multi-perspective representation:** support distinct algorithmic, application, semantic, and governance views.
5. **Contracts over internal uniformity:** standardize interoperable boundaries, not implementation details.
6. **Evaluation separate from authorization:** decision quality and permission are different claims.
7. **Counter-evidence before promotion:** growth requires challenge and evidence, not novelty alone.
8. **Versioned and reversible change:** allow retirement, isolation, rollback, and re-evaluation.
9. **Budget-aware composition:** account for communication, evaluation, and coordination costs.
10. **Epistemic humility:** distinguish proposals, measured results, and unresolved hypotheses.

## 14. Relationship to the SIF Research Series

This paper defines the common domain vocabulary. Subsequent papers elaborate the mechanisms:

- **SIF-003:** Structural Precedents and Open Intelligence Evolution.
- **SIF-004–007:** the four functional domains in detail.
- **SIF-008–011:** dual maps, precedent registry, UNT-R, and Structural Intelligence Contracts.
- **SIF-012–014:** multi-intelligence adversarial validation, counter-evidence, and collective growth.
- **SIF-015–018:** perception horizons, macro-intelligence pieces, scaling axes, and perspective-relative ASI.

The series should cross-reference the authors' existing research on MDT–UTN–CBT, CallingGraph, Core + Delta, PIRP/PIRU, Universal Control Planes, Structural RSI, and Beyond-the-LLM-Boundary, without claiming that these projects already constitute a fully integrated runtime.

## 15. Conclusion

SIF's four functional domains provide a practical way to organize a heterogeneous, growing universe of computational intelligence. **Localization** identifies where intelligence is needed; **Per-Node Intelligence** supplies task-specific capabilities; **Control Planes and Scoring/Folding** distinguish evaluation from authorization; and **Residual-Based Structural Growth** identifies, tests, and incorporates needed change. Names, types, contracts, relay, evidence, and provenance bind these roles without dictating a universal internal model.

The aim is not to freeze intelligence into four boxes. It is to make known structures findable, usable, contestable, and replaceable—while leaving the framework open to structures and perspectives that have yet to be discovered.

---

## Citation and Status Note

**Suggested citation:** Tan, S., & GPT-Obot. (2026). *SIF-002: Four Functional Domains of Structural Intelligence*. Structural Intelligence Framework, v1.0.0. Repository manuscript.

This document presents a proposed research architecture. It does not claim empirical validation of the framework or formal proof of open-ended intelligence growth. Readers should consult the repository's `CITATION.cff` and release DOI, once available, for canonical citation metadata.

**License:** Apache-2.0 (subject to repository LICENSE).
