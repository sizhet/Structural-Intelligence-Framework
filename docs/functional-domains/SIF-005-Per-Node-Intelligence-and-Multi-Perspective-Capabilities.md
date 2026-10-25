# SIF-005 — Per-Node Intelligence and Multi-Perspective Capabilities

**Structural Intelligence Framework (SIF) — Functional Domains Series**  
**Version:** 1.0.0 (Research Framework)  
**Date:** 2026-10-26  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual architecture and proposed research agenda; not an implemented interoperability standard  
**License:** Apache-2.0

## Abstract

The Structural Intelligence Framework (SIF) treats Per-Node Intelligence as an open, extensible domain of computational capabilities. Rather than defining intelligence by one model family, SIF permits language models, symbolic reasoning, constraint solvers, numerical methods, simulations, forecasting systems, and future structures to operate as problem-solving nodes. This paper proposes a multi-perspective capability taxonomy, distinguishes computational capability from autonomous intelligence, introduces a minimal node contract, and explains how localization, relay, control, evidence, and residual-based growth interact with Per-Node execution. It further describes composition patterns, structural precedents, governance boundaries, failure modes, and falsifiable research questions. The proposal is an architectural hypothesis, not evidence that arbitrary nodes can already interoperate without adapters or semantic validation.

**Keywords:** Structural Intelligence Framework; Per-Node Intelligence; capability registry; multi-perspective taxonomy; Structural Intelligence Contract; hybrid intelligence; relay; evaluation; open-ended growth.

---

## 1. The Per-Node Domain in SIF

SIF distinguishes four functional domains:

1. **Localization:** identify the relevant problem region, context, evidence, and execution destination.
2. **Per-Node Intelligence:** perform domain-specific reasoning, computation, prediction, simulation, planning, or action preparation.
3. **Universal Control Planes and Scoring/Folding:** govern permissible actions, compare candidates, and audit evidence.
4. **Residual-Based Structural Growth:** identify capability gaps, generate candidate structures, and validate revisions.

These are **roles, not mutually exclusive layers**. An LLM can localize a task, perform reasoning within a node, and propose a structural revision. A scoring engine can operate within one node or coordinate multiple nodes. The same capability may have multiple registrations and perspectives without duplicating its implementation.

The central principle is:

> **Standardize the contract, not the intelligence.**

SIF should preserve the diversity of internal algorithms while making capabilities discoverable, composable, testable, and governable.

---

![Fig-002-Four-Functional-Domains.png](../../figures/Fig-002-Four-Functional-Domains.png)

---

## 2. What Counts as Per-Node Intelligence?

A conventional program is not necessarily an autonomous intelligent agent. Yet a conventional program can provide an indispensable **intelligence capability** when invoked as part of a larger problem-solving process. A linear-programming solver, for example, need not learn or converse to improve the decisions of a hybrid system.

We therefore use **Per-Node Intelligence Capability** operationally: a bounded computational component that accepts a specified problem representation and produces outputs useful to an intelligence workflow, with declared assumptions and observable behavior. This definition avoids attributing cognition to every algorithm.

A node may be:

- **Atomic:** one function, solver, rule set, or model call.
- **Composite:** a local CallingGraph of cooperating capabilities.
- **Delegating:** a node that routes to another unit under a relay contract.
- **Macro-scale:** a validated, reusable subsystem that appears as a node to a larger system.

A node's granularity is perspective-dependent. What is a complete intelligence system at one level may become a single node at another.

## 3. An Open Capability Registry: LLM First, Not LLM Only

LLMs deserve the first position in the initial registry because of their broad applicability, natural-language interface, and substantial deployment maturity. This ordering is pragmatic, **not a claim that LLMs dominate every domain**. A specialized optimizer or verified rule engine may be more reliable, cheaper, or more appropriate for a particular task.

| ID | Capability family | Representative operations | Typical evidence or limits |
|---|---|---|---|
| 2.1 | **LLMs and foundation models** | interpretation, synthesis, reasoning proposals, code generation | task evaluation, hallucination checks, context sensitivity |
| 2.2 | Rules and symbolic engines | inference, policy checks, theorem/rule application | traceability, completeness of rules, conflict handling |
| 2.3 | Two-Way CCC and principle engines | concept-core matching, counter-evidence, principle retrieval | coverage, structural residuals, validity conditions |
| 2.4 | Event, trigger, and CallingGraph engines | dispatch, workflow progression, conditional invocation | execution traces, trigger coverage, deadlock prevention |
| 2.5 | Scoring, ranking, and decision engines | multi-criteria scoring, comparison, selection | calibration, sensitivity, Goodhart risks |
| 2.6 | ANN, retrieval, and metric engines | similarity search, candidate retrieval, localization | recall, ranking quality, embedding drift |
| 2.7 | Linear algebra and numerical computing | matrix operations, estimation, transforms | numerical error, stability, precision |
| 2.8 | Mathematical programming and optimization | constrained search, scheduling, allocation | feasibility, optimality gap, computational cost |
| 2.9 | Simulation and world-model engines | dynamics, scenarios, consequences | fidelity, domain shift, state uncertainty |
| 2.10 | Time-series and statistical engines | forecasting, anomaly detection, inference | uncertainty calibration, regime change |
| 2.11 | Planning, search, and trajectory engines | path planning, search trees, sequential decisions | horizon effects, branching cost, robustness |
| 2.12 | Hybrid and composite intelligence | orchestrated heterogeneous methods | interface semantics, coordination overhead |

This table is a **seed registry**, not an exhaustive ontology. New capabilities may be added, merged, split, or superseded as evidence accumulates.

## 4. Multi-Perspective Classification

A single hierarchical catalog becomes brittle when one capability belongs to multiple domains. SIF instead proposes **multi-perspective indexing**.

### 4.1 Classification axes

1. **By algorithm:** symbolic, neural, statistical, optimization, simulation, search, numerical, hybrid.
2. **By application:** software engineering, logistics, science, medicine, robotics, finance, governance, and others.
3. **By signature and API:** input/output types, supported operations, state transitions, synchronous/asynchronous behavior.
4. **By granularity:** function, node, composite unit, multi-unit network.
5. **By temporal scope:** stateless, episodic, streaming, long-horizon.
6. **By evidence:** formal proof, deterministic checks, benchmarks, empirical trials, simulation, expert review.
7. **By risk and authority:** advisory-only, sandboxed, shadow, authorized execution.
8. **By resource profile:** latency, throughput, memory, compute budget, energy, dependency constraints.

These axes are not independent in practice; a registry must record their interactions rather than assume every combination is valid.

### 4.2 Example: optimization capability

A mixed-integer optimization solver could be indexed simultaneously as:

| Perspective | Entry |
|---|---|
| Algorithm | mathematical programming / mixed-integer optimization |
| Application | production scheduling |
| Signature | objective + constraints + variable domains -> solution / status |
| Evidence | feasibility checks, optimality bound, solver logs |
| Resource | memory and time limits; potentially expensive worst case |
| Governance | proposes a schedule; cannot independently authorize execution |

The multi-perspective index supports both **capability-first discovery** and **problem-first matching**.

## 5. The Per-Node Structural Intelligence Contract

A node should publish a minimal **Structural Intelligence Contract (SIC)**. The following is an *illustrative schema sketch*, not a ratified protocol:

```yaml
sif_contract:
  identity:
    universal_name: "example.optimization.production-scheduler"
    version: "0.1.0"
    publisher: "example"
  type:
    capability_family: "mathematical-optimization"
    perspectives: ["scheduling", "constrained-decision"]
  capability:
    operations: ["solve", "validate"]
    input_signature: "SchedulingProblem/v1"
    output_signature: "SchedulingProposal/v1"
  context:
    assumptions: ["resource capacities supplied", "time horizon fixed"]
    known_limits: ["uncertain demand modeled externally"]
    required_state: "none"
  relay:
    transport_binding: "adapter-defined"
    supports_cancellation: true
  evidence:
    expected_artifacts: ["feasibility-report", "solver-status"]
    evaluation_profile: "scheduling-eval/v1"
  policy:
    maximum_authority: "proposal-only"
    external_side_effects: false
  provenance:
    implementation_digest: "supplied-at-registration"
  growth:
    feedback_channels: ["counterexample", "unmatched-requirement"]
```

### 5.1 Essential contract semantics

**Identity is not capability.** A stable name locates a unit; a type describes semantics; a relay binding specifies how interaction occurs. They must not be collapsed into a single untyped string.

**Transport compatibility is not semantic compatibility.** Two services exchanging JSON can still disagree about units, confidence, temporal meaning, or authorization. Adapters and conformance tests are necessary.

**Evaluation is not authorization.** A high score or valid solution does not itself grant permission to act.

**Optional capabilities stay optional.** Simple nodes need not implement elaborate learning or delegation APIs to participate.

The related specifications are planned as `SPEC-001-SIF-Structural-Intelligence-Contract.md` and `SPEC-002-Universal-Name-Type-and-Relay-API.md`.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 6. Problem–Capability Dual Maps

SIF proposes two complementary maps:

- **Problem-Solving Map (Task CG perspective):** goals, constraints, subtasks, evidence requirements, and dependencies.
- **Structural Capability Map (Action CG perspective):** available units, contracts, interfaces, compositional patterns, and validated operating envelopes.

A **Structural Precedent Registry** connects them. A precedent records a problem signature, an applicable capability or composition, conditions of validity, supporting evidence, counter-evidence, and version history.

### 6.1 Demand-to-capability flow

1. Express the problem and its relevant perspectives.
2. Localize candidate precedents and capabilities.
3. Check semantic, contextual, resource, and policy compatibility.
4. Select or compose nodes under an explicit execution plan.
5. Evaluate results and record residuals.

### 6.2 Capability-to-demand flow

A newly registered node can trigger a search for previously unsolved tasks that match its signature. Thus new capabilities can reveal **new applications and new problem formulations**, not merely serve existing requests.

The dual maps are related to Task CG and Action CG, but are not asserted to be mathematically identical to those earlier constructs.

---

![Fig-003-Problem-Capability-Dual-Maps.png](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

## 7. Composition Patterns

Per-Node diversity becomes valuable only when composition preserves semantics and controls cost.

### 7.1 Sequential relay

`LLM interpretation -> structured constraints -> optimizer -> verifier -> human decision`

Each boundary requires explicit units, assumptions, and failure handling.

### 7.2 Parallel specialization

Several nodes analyze the same problem from different perspectives; an evaluator reconciles agreements, conflicts, and uncertainty. Agreement among similar models is not automatically independent evidence.

### 7.3 Hierarchical macro-node

A validated composite may expose one contract to an upstream orchestrator while maintaining an internal CallingGraph. Its external claims must be supported by end-to-end tests, not inferred from component tests alone.

### 7.4 Two-phase localization and computation

A low-cost first stage retrieves candidate nodes or plans. A richer second stage performs specialized computation and validation. The expected benefit depends on recall, routing error, and total latency.

### 7.5 Structural folding and unfolding

A recurring composition may be folded into a reusable higher-level unit. When its operating conditions change, the system may need to unfold it for inspection, adaptation, or replacement. Compression must not silently erase relevant uncertainty or provenance.

## 8. Control, Evidence, and Authority

Per-Node capabilities should operate under the applicable **Policy Control Plane**, which may be local, hierarchical, or shared. Control requirements include:

- least-privilege access to tools, data, and external actions;
- explicit separation of proposal, scoring, approval, and execution;
- resource budgets, timeouts, cancellation, and isolation;
- traceable provenance of inputs, outputs, versions, and evaluation criteria;
- context-sensitive escalation for consequential decisions;
- rollback or quarantine when a new node fails after deployment.

A control plane may itself use scoring and optimization, but a scoring engine must not be treated as the sole source of authority.

## 9. Residual-Based Per-Node Growth

Node growth begins when existing capabilities do not adequately satisfy a problem or contract. Candidate residual classes include:

| Residual | Example | Possible response |
|---|---|---|
| Capability | no solver handles the task | new method or external specialist |
| Semantic | incompatible units or types | adapter or contract revision |
| Context | assumptions fail in new setting | context-specific variant |
| Evidence | confidence unsupported | independent validation |
| Coordination | relay loses state | improved handoff protocol |
| Resource | solution too slow or costly | alternate algorithm / routing |
| Governance | unclear action authority | policy redesign |
| Perspective | missing variable or framing | new model / viewpoint |

Not every residual justifies a new node. First distinguish genuine structural gaps from noise, poor data, misconfiguration, or insufficient evaluation.

The proposed growth lifecycle is:

`Detect -> Classify -> Retrieve precedents -> Adapt/Compose/Invent -> Challenge -> Evaluate -> Authorize -> Register -> Monitor`

A rejected candidate remains useful as a **negative precedent** if its failure conditions are recorded.

## 10. Multi-Intelligence Adversarial Validation

SIF proposes a **Multi-Intelligence Adversarial Sandbox (MIAS)** in which different roles evaluate a new node or composition:

- **Builder:** states capability claims and supplies an implementation or design.
- **Challenger:** searches for boundary cases, contradictions, and adversarial inputs.
- **Independent evaluator:** applies declared metrics and verifies evidence.
- **World/simulation engine:** tests state changes, perturbations, and longer trajectories where appropriate.

Heterogeneous evaluators—formal checkers, simulations, statistical tests, and independent models—may reveal failure modes missed by same-family model debates. Independence must be assessed rather than assumed.

Sandbox exploration does not confer production authority. Proposed promotion stages are **isolated experiment -> shadow evaluation -> explicitly authorized deployment**. Risk controls must apply even inside sandboxes, especially when real tools, sensitive data, or external effects are available.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 11. Conceptual Case Study: Supply-Chain Disruption Planning

*This is an illustrative architecture, not a reported benchmark or deployed system.*

**Problem:** a supply-chain operator needs robust contingency plans under uncertain demand and transport disruption.

**Candidate node graph:**

1. An LLM interprets the operator's natural-language objective and drafts a structured task specification.
2. A graph or MDT-based localization unit identifies affected suppliers and routes.
3. A time-series model estimates demand scenarios and communicates uncertainty.
4. A simulation/world-model node estimates disruption consequences under specified assumptions.
5. An optimization solver generates feasible schedules or rerouting proposals.
6. A rule engine checks hard safety, contractual, and policy constraints.
7. A scoring forest compares feasible proposals across cost, resilience, and service perspectives.
8. An independent challenger perturbs demand, lead times, and model assumptions.
9. A human-authorized control plane decides whether any proposal can be deployed.

**Potential structural residuals:** missing supplier-dependency data, unmodeled correlated failures, incompatible temporal granularity, or systematic disagreement between simulation and observed outcomes.

A successful case would require controlled baselines and actual performance measurements. Architectural plausibility alone does not establish effectiveness.

## 12. Failure Modes and Design Safeguards

| Failure mode | Why it matters | Candidate safeguard |
|---|---|---|
| Registry sprawl | duplicates and stale entries obscure capabilities | versioned deduplication and deprecation |
| Semantic mismatch | syntactically valid relay yields wrong meaning | typed contracts and conformance tests |
| Routing errors | useful specialist never invoked | recall-oriented evaluation and fallback |
| Composite brittleness | errors amplify across nodes | end-to-end tests and fault isolation |
| Shared evaluator bias | consensus disguises common failure | heterogeneous checks and external evidence |
| Score optimization | metrics replace true objectives | counter-evidence and policy constraints |
| Cost explosion | coordination exceeds capability benefit | budget-aware routing and ablation |
| Unauthorized execution | capability is mistaken for permission | explicit authority boundaries |
| Premature macro-folding | internal uncertainty becomes hidden | traceability and selective unfolding |

## 13. Testable Hypotheses

The following are proposed experiments, **not established findings**.

**H1 — Capability selection:** Under matched cost budgets, multi-perspective indexing improves relevant-node retrieval compared with a single taxonomy.

**H2 — Hybrid composition:** For tasks requiring both language interpretation and hard constraints, an LLM-plus-solver composition reduces constraint violations relative to an LLM-only baseline.

**H3 — Contract reliability:** Explicit semantic contracts and conformance tests reduce cross-node integration failures compared with untyped payload exchange.

**H4 — Structural precedents:** Retrieval of validated positive and negative precedents reduces repeated design failures on related tasks.

**H5 — Adversarial evaluation:** Heterogeneous challengers discover more distinct, reproducible failure modes per unit of evaluation cost than homogeneous model debate.

**H6 — Macro-node formation:** Validated folding of recurring compositions improves reuse or latency without unacceptable loss of traceability or adaptability.

**H7 — Governance separation:** Explicit authorization gates reduce unintended external actions without disproportionately reducing useful exploratory capability.

For each experiment, report task distributions, baselines, sample sizes, confidence intervals where meaningful, compute costs, and adverse outcomes. Null results should be retained.

## 14. Open Research Questions

1. What is the smallest contract that enables useful interoperability across radically different node types?
2. How should universal types represent uncertainty, temporal scope, and context-dependent meaning?
3. When does a composite deserve promotion to a macro-intelligence node?
4. How can capability discovery avoid overfitting to the registry's existing ontology?
5. How can SIF measure genuine new problem-solving ability rather than merely a larger inventory of nodes?
6. What evidence is sufficient to replace a mature capability with a new candidate?
7. How should relay networks handle competing ownership, privacy, and sovereignty requirements?
8. When does increased structural depth improve performance, and when does it increase fragility?
9. How should capability registries expose failures without leaking sensitive operational information?
10. Can new Per-Node structures measurably expand a system's structural perception horizon?

## 15. Relationship to the SIF Research Series

- **SIF-001:** motivates open structural intelligence beyond isolated models.
- **SIF-002:** defines the four functional domains and their intersections.
- **SIF-003:** develops structural precedents and open intelligence evolution.
- **SIF-004:** details localization and intelligence addressing.
- **SIF-005 (this paper):** defines the open Per-Node capability domain.
- **SIF-006:** will detail universal control planes and scoring/folding.
- **SIF-007:** will detail residual-based structural growth.
- **SIF-008–011:** will elaborate dual maps, registries, universal relay, and contracts.
- **SIF-012–014:** will elaborate adversarial validation and collective evolution.
- **SIF-015–018:** will investigate perception horizons, macro-intelligence, scaling, and perspective-relative ASI.

The SIF architecture also connects conceptually to prior Structural Intelligence work on MDT–UTN–CBT, Two-Way CCC, CallingGraph, PIRP/PIRU, Principle Intelligence, Structural RSI, and Universal Control Planes. These connections are architectural relationships; they do not imply an existing unified implementation.

## 16. Conclusion

Per-Node Intelligence should be the most diverse and extensible functional domain in SIF. Its purpose is not to crown one algorithm as universally intelligent, but to make heterogeneous computational capabilities usable within a coherent, evidence-governed structural system. LLMs are a prominent entry point, yet symbolic methods, optimization, simulation, statistical inference, and future capabilities must remain first-class participants.

The practical challenge is to make diversity interoperable without erasing it. Multi-perspective registries, explicit contracts, bidirectional problem–capability maps, structural precedents, relay protocols, and adversarial validation provide a proposed path. Whether that path produces measurable gains must be established through controlled experiments.

> **An open intelligence framework should enable each useful capability to find its role—and enable the whole system to discover when that role is no longer sufficient.**

---

## Citation Note

For formal citation, use the repository's `CITATION.cff` and the DOI assigned to the relevant archived release once available. No DOI is asserted in this manuscript.
