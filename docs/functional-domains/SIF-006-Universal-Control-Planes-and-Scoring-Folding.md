# SIF-006 — Universal Control Planes and Scoring Folding

**Structural Intelligence Framework (SIF) — Functional Domains Series**  
**Version:** 1.0.0 (Research Framework)  
**Date:** 2026-10-26  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual architecture, candidate contracts, and testable research agenda; not a deployed control standard  
**License:** Apache-2.0

## Abstract

The Structural Intelligence Framework (SIF) proposes an open ecosystem in which heterogeneous intelligence structures can be localized, composed, evaluated, and evolved. Such openness introduces a fundamental control problem: a system may generate a high-scoring proposal without possessing the authority to execute it, and its scoring machinery may itself be incomplete, biased, or vulnerable to optimization pressure. This paper develops the third SIF functional domain, **Universal Control Planes and Scoring/Folding**, as an explicit separation of policy authority, comparative evaluation, evidence, and execution authorization. It proposes hierarchical and federated control-plane patterns; Scoring Trees and Forests for multi-perspective evaluation; structural folding and unfolding for manageable decision depth; a contract-mediated interface to Localization, Per-Node Intelligence, and Residual-Based Growth; and adversarial evaluation procedures that challenge both candidates and evaluators. An illustrative supply-chain decision and a falsifiable validation program show how to investigate the approach. The architecture is a research proposal: no universal evaluator, globally valid score, or general safety guarantee is claimed.

**Keywords:** Structural Intelligence Framework; universal control plane; scoring tree; scoring forest; structural folding; decision governance; action authorization; evidence; counter-evidence; Goodhart; structural growth.

---

## 1. Why SIF Needs an Independent Control Domain

SIF is organized into four interacting **functional domains**, not mutually exclusive software layers:

1. **Localization** identifies relevant problem regions, contexts, evidence, and intelligence destinations.
2. **Per-Node Intelligence** supplies heterogeneous reasoning, computation, planning, prediction, and simulation capabilities.
3. **Universal Control Planes and Scoring/Folding** establishes constraints, evaluates alternatives, determines authority, and supports audit.
4. **Residual-Based Structural Growth** investigates gaps, counter-evidence, and candidate structural revisions.

The third domain must be distinguishable from the other three. A capable model may propose an action; a solver may prove that a plan satisfies its encoded constraints; a scoring engine may rank a plan first. None of those facts, alone, establishes **who is entitled to choose**, **which constraints are binding**, or **whether execution is authorized**.

> **Evaluation does not imply authorization.**

A control plane must be able to deny a highly rated action, require independent evidence, delegate a bounded decision, or return a case for human judgment. The framework's ambition is *controlled interoperability*, not a single all-powerful decision maker.

### 1.1 From isolated decisions to structural governance

In an isolated application, policy checks may be embedded inside one program. In SIF, decisions can cross models, organizations, relay networks, composite nodes, and dynamically introduced intelligence structures. This creates additional questions:

- Can a capability declare a policy that conflicts with the caller's policy?
- Which party owns a choice after delegation?
- How can an evaluator compare results produced under different assumptions?
- When is an apparently superior score an artifact of a defective metric?
- Can a new intelligence structure be tested without silently inheriting production authority?

The control domain supplies explicit places to represent and test answers.

---

![Fig-002-Four-Functional-Domains.png](../../figures/Fig-002-Four-Functional-Domains.png)

---

## 2. Three Distinct Planes

### 2.1 Policy and authority plane

The **Policy Plane** defines binding rules and decision rights: ownership, permissible operations, prohibited actions, budget limits, jurisdictional or organizational restrictions, approval thresholds, and revocation mechanisms. It may include hard constraints that must not be traded away for a higher score.

Policy is contextual. A research sandbox, shadow runtime, and production system may authorize different actions by the same node. Authority should be represented as a bounded, revocable grant, not inferred from model competence or the existence of an API endpoint.

### 2.2 Scoring and decision plane

The **Scoring and Decision Plane** compares permissible candidates using objectives, preferences, tradeoffs, uncertainty, and task-specific evaluation structures. A Scoring Tree decomposes a decision into evaluable criteria; a Scoring Forest allows multiple trees or perspectives to coexist. Structural folding can compress repeated patterns or summarize subproblems, provided that important distinctions and constraints are recoverable or independently checked.

Scores support choice, but do not define the legitimacy of choice.

### 2.3 Evidence and audit plane

The **Evidence and Audit Plane** records the provenance of inputs, evaluator versions, uncertainty, counter-evidence, policy decisions, and resulting outcomes. It also challenges whether the criteria used by the scoring plane actually track the desired real-world properties.

These planes interact without collapsing into one another:

| Plane | Primary question | Representative output |
|---|---|---|
| Policy / Authority | May this action be considered or executed, and by whom? | Constraint decision, authorization token, approval requirement |
| Scoring / Decision | Which eligible candidate is preferable under stated objectives? | Ranked alternatives, tradeoff record, sensitivity analysis |
| Evidence / Audit | What supports the decision, and what might refute it? | Evidence bundle, counter-evidence, trace, evaluation status |

A fourth operational element, the **Execution Gate**, enforces the resulting authorization at the boundary where side effects occur. It is not interchangeable with an evaluator.

## 3. Universal Does Not Mean Centralized or Omniscient

“Universal” in Universal Control Planes means **widely applicable control interfaces and compositional principles**, not one central controller that understands every domain or a universally correct scoring function.

Three deployment patterns are useful:

1. **Local control:** a node validates inputs, constraints, and its own outputs.
2. **Hierarchical control:** parent and child nodes carry bounded, inherited, or narrowed permissions.
3. **Federated control:** independent organizations exchange requests under negotiated contracts and mutually enforced boundaries.

A local control plane may be embedded inside a Per-Node engine, while a broader plane governs its invocation. This intentional overlap is consistent with SIF's multi-role functional domains.

### 3.1 Authority composition

A proposed policy-composition rule is **deny by default for undeclared side effects** and **least authority for delegated tasks**. A child capability should not acquire more execution authority merely because it was called by a powerful parent. Exceptions, if allowed, must be explicit, logged, and independently authorized.

Policy conflicts require declared precedence or escalation. A scoring tree must never resolve a non-negotiable policy conflict simply by assigning it a small negative weight.

## 4. Scoring Trees: Decomposing Evaluation

A Scoring Tree represents an evaluation question as a hierarchy of criteria, evidence requirements, and aggregation operators. For example, a logistics proposal may be assessed on feasibility, delivery reliability, cost, environmental impact, and resilience. Each branch may use a different computational evaluator.

A generic conceptual representation is:

$$
S(c\mid p, x, e)=A_p\bigl(s_1(c,x,e),\ldots,s_n(c,x,e)\bigr),
$$

where $c$ is a candidate, $p$ a policy/evaluation perspective, $x$ context, $e$ available evidence, $s_i$ local evaluation functions, and $A_p$ a declared aggregation rule. This expression is **not** a claim that every criterion is commensurable or reducible to one scalar.

### 4.1 Hard constraints before soft preferences

An operationally safer sequence is:

1. Check identity, context, and applicability.
2. Apply non-negotiable eligibility constraints.
3. Evaluate eligible candidates using declared criteria.
4. Analyze sensitivity, uncertainty, and competing perspectives.
5. Seek required approval before any external side effect.

This avoids a common failure mode in which an attractive weighted score masks an unacceptable violation.

### 4.2 Calibration and score normalization

Scores produced by distinct evaluators may have incompatible scales or meanings. A probability, a utility estimate, a heuristic rank, and a compliance Boolean cannot be averaged naively. Every aggregation contract should declare score semantics, calibration data, normalization assumptions, missing-value behavior, and uncertainty handling.

Short or sparse evidence can also distort ranking. Normalization should be evaluated for its failure modes rather than treated as a universal correction.

## 5. Scoring Forests: Preserving Competing Perspectives

A **Scoring Forest** comprises multiple evaluation trees representing different objectives, stakeholders, contexts, granularities, or time horizons. The forest preserves disagreement rather than hiding it inside an opaque scalar.

Examples include:

- short-term cost versus long-term robustness;
- technical feasibility versus institutional acceptability;
- customer benefit versus third-party externalities;
- optimistic world-model assumptions versus adversarial stress scenarios.

Forest-level decisions may use Pareto frontiers, lexicographic priorities, veto rules, explicit stakeholder weights, or escalation. The choice of method is itself a policy decision and must be documented.

### 5.1 Why disagreements are informative

Large disagreement between trees may reveal a missing perspective, poorly calibrated evaluator, ambiguous objective, or genuine social tradeoff. Such disagreement should become a **Structural Residual** eligible for further investigation—not merely a nuisance to be averaged away.

### 5.2 No universal score

SIF should not assume the existence of a context-independent “intelligence score” or universally valid preference ordering. A forest makes evaluation plural, inspectable, and revisable. Its practical success remains subject to empirical comparison with simpler methods.

## 6. Structural Folding and Unfolding in Control

Scoring depth and candidate count can grow beyond what a human or a single evaluator can inspect directly. **Structural Folding** groups repeated patterns, compresses lower-level distinctions, or constructs higher-level decision summaries. **Unfolding** restores selected detail for inspection, alternative analysis, or counter-evidence.

Folding can reduce search and evaluation cost, but it can also suppress minority cases, rare hazards, or policy exceptions. Consequently, control-relevant folding should declare:

- what information was retained and discarded;
- which constraints remain invariant;
- how exceptions are surfaced;
- when a summary must be unfolded;
- whether confidence is preserved, estimated later, or unavailable.

SIF does **not** require every fold to preserve full uncertainty exactly. A two-phase approach may use coarse folding for candidate discovery and detailed, independent evaluation for shortlisted candidates. The cost and residual risks of this approximation must be measured.

> **Compress for tractability; unfold where evidence, disagreement, or authority requires detail.**

## 7. Control in the Problem–Capability Dual Maps

SIF's **Problem-Solving Map** describes goals, task decomposition, constraints, and required intelligence. Its **Capability Map** describes available structures, signatures, evidence, and relay interfaces. The analogy to Task CallingGraph and Action CallingGraph is useful but not exact.

The control domain operates on the bridge between these maps:

1. The Problem Map declares goals, owners, and constraints.
2. Localization retrieves plausible capabilities and structural precedents.
3. Contracts expose each candidate's assumptions and permissible operations.
4. The Scoring Forest compares viable compositions and routes.
5. The Policy Plane determines which composition may proceed.
6. Evidence and outcome traces feed the Registry and Growth domain.

**Capability matching is not permission matching.** A node may be technically suitable but unauthorized for the proposed context.

---

![Fig-003-Problem-Capability-Dual-Maps.png](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

## 8. Structural Intelligence Contracts and Relay Boundaries

A candidate **Structural Intelligence Contract (SIC)** connects Universal Name, Universal Type, Relay API, Context, Evidence, and Policy. Control-related contract fields should be explicit, typed where feasible, and versioned.

```yaml
# Illustrative research schema, not a finalized standard.
structural_intelligence_contract:
  identity:
    universal_name: "example:route-planner"
    version: "0.1"
  capability:
    type: "planning.optimization"
    input_signature: "RoutePlanningRequest/v1"
    output_signature: "CandidatePlan/v1"
  context:
    required: ["network_snapshot", "delivery_constraints"]
    freshness_requirement: "declared_by_deployment"
  evidence:
    outputs: ["feasibility_report", "cost_breakdown"]
    known_limitations: ["weather_forecast_uncertainty"]
  policy:
    permitted_effects: ["propose_plan"]
    prohibited_effects: ["dispatch_vehicle"]
    escalation_on: ["safety_constraint_conflict"]
  relay:
    supports: ["describe", "match", "invoke", "result"]
    execution_gate: "external_authorization_required"
```

This contract expresses intent, not enforcement by itself. Runtime adapters, identity checks, policy engines, and side-effect isolation are required to enforce declared boundaries. Untrusted output from a delegated node must not be interpreted as a new authorization grant.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 9. Multi-Intelligence Adversarial Validation

The proposed **Multi-Intelligence Adversarial Sandbox (MIAS)** challenges both candidate plans and the control/evaluation machinery used to select them. Suggested roles include:

- **Builder:** constructs a candidate plan, scoring rule, or control structure.
- **Challenger:** seeks counterexamples, hidden assumptions, policy conflicts, and distribution shifts.
- **Independent Evaluator:** applies predeclared tests and reviews evidence quality.
- **World/Simulation Engine:** generates state trajectories, disturbances, and consequences.
- **Governance Gate:** controls movement from isolated exploration to shadow or production execution.

The roles should be separated operationally where feasible. Multiple LLMs with similar training may share correlated blind spots; heterogeneous solvers, formal checks, simulations, and human review are important complements.

### 9.1 Challenge the evaluator, not only the answer

A candidate can be poor because the scoring system is poor. MIAS should test whether the evaluator rewards proxies rather than intended outcomes, ignores rare failure modes, or changes conclusions under harmless rephrasings.

A bounded recursive pattern is:

**Candidate → Challenge → Evaluation → Evaluator Challenge → Governance Decision.**

Recursion needs budgets, stopping rules, and escalation thresholds. More adversarial debate does not itself guarantee truth.

### 9.2 Safe progression of authority

A useful lifecycle separates:

| Stage | Allowed work | Authority boundary |
|---|---|---|
| Exploratory sandbox | Generate and attack candidate structures | No uncontrolled production side effects |
| Validated shadow runtime | Compare against historical or live read-only scenarios | No independent production action |
| Authorized production runtime | Execute bounded approved operations | Explicit authorization, monitoring, revocation, rollback |

The word “sandbox” alone is not a safety guarantee: network access, sensitive data, tool permissions, and executable artifacts require concrete isolation controls.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 10. Structural Counter-Evidence and Anti-Goodhart Controls

A control system must record **counter-evidence** at several levels:

- **Outcome:** a selected plan fails on observed results.
- **Criterion:** a scoring feature is a poor proxy for the real objective.
- **Structure:** the evaluation tree omits an important causal factor.
- **Perspective:** an affected stakeholder or time horizon is missing.
- **Relay:** context was lost or misinterpreted across nodes.
- **Authority:** a decision was evaluated or executed under the wrong permissions.

Possible defenses against Goodhart effects include held-out evaluation, rotating adversarial tasks, independently measured outcomes, explicit constraint gates, sensitivity analysis, and evaluation on distribution shifts. None is sufficient alone.

A newly discovered evaluator failure is a growth input: the system may revise a criterion, add a new tree, introduce an independent checker, or restrict deployment. Revisions require new versions and comparison against the prior baseline.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 11. Worked Conceptual Example: Supply-Chain Disruption

Consider a planning system asked to reroute deliveries after a port closure.

**Problem Map:** minimize delay while respecting safety, contractual, and cost constraints.

**Capability Map:** LLM-based incident interpretation, graph localization, route optimization, weather simulation, contract checker, and human operations review.

**Control sequence:**

1. Localization identifies affected shipments, routes, and candidate nodes.
2. The contract checker rejects legally or operationally infeasible alternatives.
3. Optimization generates feasible route candidates.
4. Scoring Trees evaluate cost, delay, resilience, and environmental impact.
5. A Scoring Forest exposes disagreement between short-term efficiency and long-term resilience.
6. A Challenger introduces a second disruption and checks whether the leading route fails catastrophically.
7. The Evidence Plane records assumptions, uncertainty, rejected alternatives, and test results.
8. The Policy Plane permits a recommendation but requires an authorized dispatcher for execution.
9. Unexplained failure patterns are entered as structural residuals for later research.

The example illustrates an architecture; it is not a reported deployment or performance result.

## 12. Failure Modes and Boundary Conditions

| Failure mode | Consequence | Proposed mitigation |
|---|---|---|
| Policy and score conflated | High score bypasses a hard constraint | Separate eligibility checks and execution gate |
| Evaluator monoculture | Shared blind spots persist | Heterogeneous checks and independent evidence |
| Hidden folding loss | Rare hazards disappear from summaries | Triggered unfolding and exception tests |
| Score incompatibility | Invalid cross-model aggregation | Typed score semantics and calibration |
| Delegation authority leak | Child executes beyond permitted scope | Least privilege, bounded grants, revocation |
| Registry drift | Old precedents used outside context | Versioning, expiry, applicability tests |
| Sandbox escape or unsafe tools | Exploration affects real systems | Isolation, access limits, review of artifacts |
| Excessive control overhead | System becomes impractical | Risk-tiered evaluation and budget-aware routing |
| Metric gaming | Apparent gains fail in deployment | Held-out tests, independent outcomes, shadow trials |
| Endless recursive challenge | Unbounded cost without better evidence | Stopping criteria and escalation |

Control architecture itself introduces complexity. Its benefits must be assessed relative to operational overhead, latency, and the severity of the risks addressed.

## 13. Testable Research Hypotheses

**H1 — Separation of authority and scoring.** Explicit policy gating reduces unauthorized side effects relative to systems in which the highest score automatically triggers execution, under comparable tasks and permissions.

**H2 — Forest versus single score.** Multi-perspective Scoring Forests expose materially important tradeoffs missed by single aggregated scoring functions, at a measurable coordination cost.

**H3 — Evidence-aware folding.** Selective unfolding recovers more decision-relevant exceptions than unconditional coarse folding for a comparable compute budget.

**H4 — Heterogeneous adversarial evaluation.** Mixed evaluator families discover a broader set of independent structural failures than equal-budget same-family model debate.

**H5 — Contract-mediated relay.** Explicit context, policy, and evidence contracts reduce cross-node semantic and authorization failures relative to untyped handoffs.

**H6 — Evaluator challenge.** Bounded adversarial attacks on scoring criteria improve out-of-distribution decision quality compared with candidate-only adversarial tests.

**H7 — Risk-tiered control.** Allocating verification effort by potential harm and uncertainty improves the reliability–latency tradeoff relative to uniformly intensive checks.

These are hypotheses, not established empirical findings. Experiments should pre-register metrics where possible, include simple baselines, and report negative results.

## 14. Suggested Validation Program

### Phase A — Formalize claims and contracts

Specify policy types, score semantics, evidence bundles, and a small set of controlled side effects. Define invariants such as “a recommendation cannot dispatch a vehicle.”

### Phase B — Controlled benchmark

Compare a baseline single-score planner with: (i) hard policy gating; (ii) multi-tree scoring; (iii) forest disagreement handling; and (iv) adversarial evaluator challenge. Measure constraint violations, regret or task-specific utility, latency, cost, and audit completeness.

### Phase C — Relay and folding stress tests

Introduce stale context, incompatible units, missing evidence, novel node versions, and rare exception cases. Measure detection rates and recovery behavior.

### Phase D — Shadow evaluation

Run read-only comparisons on representative historical or live cases, with independent human or domain-expert review of high-stakes outcomes.

### Phase E — Governance review

Only after evidence is sufficient for a bounded deployment should production authority be considered. Preserve rollback, monitoring, and periodic revalidation.

## 15. Interfaces to Other SIF Research

- **SIF-001:** open structural intelligence as the overarching framework.
- **SIF-002:** the four functional domains and their cross-domain roles.
- **SIF-003:** structural precedents, applicability, and failed-case evidence.
- **SIF-004:** intelligence addressing and context-aware localization.
- **SIF-005:** heterogeneous Per-Node capabilities and contracts.
- **SIF-007:** residual-based growth and revision of evaluation structures.
- **SIF-008–011:** dual maps, registry, universal naming/typing/relay, and structural contracts.
- **SIF-012–014:** adversarial sandbox, structural counter-evidence, and collective evolution.
- **SIF-015–018:** perception horizons, macro-intelligence, scaling, and perspective-relative ASI.

This paper also connects to the separately developed **Universal Control Planes and Scoring Folding** research direction. SIF supplies the integrative architecture; the specialized repository can carry deeper algorithms, mathematical formulations, and experimental results. No claim is made that all components are already implemented as one system.

## 16. Open Questions

1. What is the smallest policy contract that works across very different intelligence nodes?
2. Which evaluation semantics can be standardized without erasing domain-specific meaning?
3. How should a Scoring Forest handle irreducible stakeholder conflict?
4. When does folding lose information that cannot be reliably recovered?
5. How can a federated system resolve conflicting policies without inventing a central sovereign?
6. What independent evidence is sufficient to trust an evaluator's claims?
7. How should the framework detect previously unrecognized evaluation perspectives?
8. How should validation compute be allocated between builders, challengers, and evaluators?
9. Can new Macro-Intelligence Pieces inherit control contracts safely, or must they be requalified?
10. How can a system retain human decision authority while AI-generated structural candidates grow faster than human inspection capacity?

## 17. Conclusion

Universal Control Planes and Scoring/Folding provide SIF with a proposed mechanism for **governing an open intelligence ecosystem without demanding a single universal intelligence model**. Policy establishes legitimate boundaries; Scoring Trees and Forests compare eligible possibilities; structural folding manages scale while selective unfolding supports scrutiny; evidence and adversarial challenge test both proposals and their evaluators; and explicit execution gates preserve the distinction between recommending and acting.

The long-term research opportunity is not to automate every choice behind an opaque master score. It is to make increasingly complex intelligence compositions **discoverable, evaluable, contestable, and governable**, while keeping room for future structures and perspectives that the current system cannot yet represent.

> **Intelligence may propose. Scoring may compare. Evidence may challenge. Authority must still be explicitly assigned.**

---

## Citation Note

For formal citation, use the repository's `CITATION.cff` and the DOI assigned to the relevant archived release once available. No DOI is asserted in this manuscript.
