# SIF-017 — Scaling Axes and Computational Intelligence Growth

**Structural Intelligence Framework (SIF)**  
**Frontiers Series · Research Architecture · v1.0.0**  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual framework and testable research hypotheses; not an experimentally validated performance claim.  
**License:** Apache-2.0

## Abstract

Scaling intelligence is often framed primarily as increasing model parameters, training data, inference tokens, or computational throughput. These resources matter, but they do not exhaust the design space. The Structural Intelligence Framework (SIF) proposes a complementary perspective: intelligence may scale through the breadth of structures that can be addressed, the depth at which problems can be decomposed, the precision with which computation is directed, and the amount of computation that can be allocated and verified. Additional axes—interoperability, evidence quality, governance, and collective structural learning—determine whether such growth remains useful and trustworthy. This paper develops a multi-axis scaling model, relates it to SIF's four functional domains, and proposes mechanisms for allocating computational effort through Problem–Capability dual maps, structural precedents, contracts, and adversarial evaluation. It distinguishes resource scaling from demonstrated capability gains, and specifies empirical tests for complementarity, diminishing returns, compositional overhead, and possible expansion of the Structural Perception Horizon.

**Keywords:** structural intelligence, scaling laws, computational allocation, hierarchical reasoning, intelligence localization, precision guidance, structural folding, collective learning, adversarial validation, open-ended growth

---

## 1. The Scaling Question Beyond Model Size

The question is not whether larger models and more computation can improve performance; they frequently can under suitable conditions. The question is whether a single scaling variable is an adequate description of a heterogeneous intelligence system.

A structural intelligence system can draw on language models, rule engines, search, optimization, simulation, specialized learned models, and external services. It can also revise the way these capabilities are represented, routed, composed, evaluated, and governed. Its effective performance therefore depends on more than the capacity of any one component.

SIF treats scaling as a **multi-dimensional engineering and scientific problem**:

- Which structures are available and discoverable?
- At what granularity can the system reason and intervene?
- How accurately can it target the right structure and allocate resources?
- How much computation can it use within a defined budget?
- How well can heterogeneous components exchange meaning and evidence?
- How reliably can outcomes and structural claims be challenged?
- How safely can successful structures be reused and shared?

These questions motivate the scaling axes developed below. They are research variables, not an assertion that every axis must improve every task.

---

![Fig-001-SIF-Grand-Architecture.png](../../figures/Fig-001-SIF-Grand-Architecture.png)

---

## 2. Four Primary Scaling Axes

### 2.1 Large Structures — Structural Breadth and Reach

**Large structures** refer to the scope of problems, capabilities, relations, and coordinated subsystems that can be represented and managed. They are not merely large context windows or long prompts.

Examples include an enterprise-wide task graph, a multi-agent scientific workflow, a network of sovereign BrainUnits, or a multi-level Structural Capability Map. Breadth may allow the system to consider dependencies invisible to a narrowly scoped solver.

However, increased breadth also introduces routing complexity, stale information, conflicting assumptions, and coordination overhead. A larger graph is valuable only if relevant relationships can be localized and validated.

**Operational variables:** number of addressable capabilities; coverage of task families; graph connectivity; proportion of cross-domain dependencies represented; retrieval precision at increasing registry size.

### 2.2 Deep Structures — Structural Depth and Granularity

**Deep structures** refer to the ability to descend from a macro problem to its relevant constituent mechanisms, constraints, and evidence, and to return to a coherent higher-level result.

Depth can be implemented through Metric Differential Trees (MDT), CallingGraphs, nested contracts, per-node intelligence, multi-stage decomposition, and structural folding/unfolding. It is distinct from simply extending a chain of verbal reasoning.

Depth may reveal failure causes or controllable subproblems. Yet uncontrolled decomposition can multiply errors, produce unbounded searches, or obscure the original objective. The depth chosen should depend on expected information value and the cost of expansion.

**Operational variables:** maximum useful decomposition depth; depth-adjusted accuracy; error localization; cost per resolved subproblem; recoverability of folded evidence.

### 2.3 Precision Guidance — Targeting and Computational Direction

**Precision guidance** means directing a suitable intelligence capability to the right problem region, with the right context, constraints, evaluation method, and resource budget.

It includes structural localization, two-phase search, Task–Capability matching, policy-aware dispatch, confidence-aware escalation, and the ability to abstain or seek counter-evidence. Precision is not synonymous with a high similarity score. A structurally similar precedent can be inapplicable because of changed assumptions or authorization constraints.

A practical guidance sequence is:

1. Express the task and its acceptance conditions in the Structural Problem-Solving Map (PSM).
2. Retrieve candidate capabilities and precedents from the Structural Capability Map (SCM) and registry.
3. Check type, context, evidence, policy, and resource compatibility.
4. Allocate a bounded exploratory budget to ambiguous candidates.
5. Select, compose, or reject candidates; preserve unresolved residuals.
6. Escalate to independent evaluation when the stakes or uncertainty warrant it.

**Operational variables:** correct-route rate; calibration; false-positive capability matches; avoidable compute expenditure; rate of appropriate abstention; policy-compliant dispatch.

### 2.4 Major Computational Investment — Resource Scale

**Major computational investment** encompasses training, inference, search, simulation, optimization, verification, and adversarial evaluation. SIF does not presume that these workloads should receive equal shares.

The central research problem is **allocation**, not merely expenditure. A unit of compute used to expand a promising structural branch may outperform a unit spent repeating an unproductive general-purpose search. Conversely, expensive structural orchestration can be wasteful on tasks that a single model already solves well.

Resources may include latency, energy, memory, monetary cost, human review time, simulation budget, and risk exposure. A good allocation policy must optimize against a task-specific utility function subject to hard constraints.

**Operational variables:** success per unit cost; latency-to-quality frontier; energy use; validation cost; resource overruns; marginal gain from additional compute.

## 3. Complementary Scaling Axes

The four primary axes become more useful when accompanied by at least four complementary dimensions.

### 3.1 Interoperability and Relay Fidelity

Universal Naming, Typing and Relay (UNT-R), Structural Intelligence Contracts (SIC), and PIRP/PIRU units enable structural breadth to become executable composition. Relay fidelity measures whether semantics, context, evidence, constraints, and responsibility survive handoffs.

Without interoperability, the system may possess many capabilities but be unable to combine them reliably.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

### 3.2 Evidence and Evaluation Quality

Structural Precedent Intelligence records applicability conditions, outcomes, counter-evidence, and versions. Multi-Intelligence Adversarial Sandbox (MIAS) challenges structural claims and evaluators. A larger system without stronger evidence may scale error propagation rather than intelligence.

### 3.3 Governance and Authorized Action

The Universal Control Plane distinguishes policy and authority from scoring and evidence. Higher computational capacity does not confer broader authority. Exploratory discovery, validated shadow operation, and production deployment remain separate states.

### 3.4 Collective Learning and Reuse

Portable intelligence units, precedent exchange, and federated structural learning can allow validated improvements to benefit multiple systems. Transfer requires context compatibility and provenance; reuse cannot be equated with universal validity.

## 4. A Multi-Axis Model

Let a system configuration be represented by

$$
\mathbf{s} = (B, D, P, C, I, E, G, L),
$$

where:

- $B$: structural breadth;
- $D$: useful structural depth;
- $P$: guidance precision;
- $C$: available computational resources;
- $I$: interoperability fidelity;
- $E$: evidence and evaluation quality;
- $G$: governance adequacy;
- $L$: collective learning and reuse effectiveness.

For task distribution $\mathcal{T}$, define measured utility:

$$
U(\mathbf{s};\mathcal{T}) = \mathbb{E}_{t\sim\mathcal{T}}
\left[Q_t - \lambda_c K_t - \lambda_r R_t\right],
$$

where $Q_t$ is task-specific validated quality, $K_t$ is total resource cost, and $R_t$ is a risk penalty. The coefficients are chosen by an authorized evaluation process and must not be silently optimized by the candidate under test.

This is an **evaluation template**, not a universal intelligence equation. Each axis requires a domain-specific measurement protocol. The model does not imply linearity, independence, or monotonicity.

A more useful experimental question is whether axes interact:

$$
\Delta_{ij} U = U(s_i^+,s_j^+) - U(s_i^+,s_j^0) - U(s_i^0,s_j^+) + U(s_i^0,s_j^0).
$$

Positive interaction suggests complementarity; negative interaction suggests interference or overhead. Results must be interpreted with confidence intervals and controlled task distributions.

## 5. How the Four Functional Domains Contribute

| SIF functional domain | Scaling contribution | Principal failure risk |
| --- | --- | --- |
| Localization and intelligence addressing | Finds relevant structures at greater breadth and depth | Wrong address, missing context, false analogy |
| Per-node intelligence | Supplies specialized reasoning and computation | Capability mismatch, inconsistent semantics |
| Universal control planes and scoring/folding | Directs resources, evaluates alternatives, constrains action | Goodhart effects, hidden scoring assumptions, authority leakage |
| Residual-based structural growth | Discovers and validates missing or improved structures | Mistaking novelty for progress, unsafe promotion |

These are **functional domains**, not mutually exclusive software layers. An LLM, world model, or scoring forest may participate in several domains. Their roles should be identified through contracts and evidence rather than fixed taxonomy.

---

![Fig-002-Four-Functional-Domains.png](../../figures/Fig-002-Four-Functional-Domains.png)

---

## 6. Compute Allocation Through Structural Guidance

### 6.1 From Uniform Spending to Conditional Spending

Consider three strategies for a task portfolio:

- **Uniform:** apply the same large model and fixed compute budget to every task.
- **Routed:** select specialized capabilities based on a task signature.
- **Evidence-guided structural:** route, inspect precedent applicability, estimate uncertainty, selectively decompose, challenge high-impact claims, and preserve residuals.

The third strategy can be more efficient when task heterogeneity is high and routing overhead is controlled. It may be less efficient for simple or highly uniform workloads.

---

![Fig-003-Problem-Capability-Dual-Maps.png](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

### 6.2 A Budgeted Dispatch Objective

For candidate plan $\pi$, the runtime may seek:

$$
\pi^* \in \arg\max_{\pi\in\Pi_{\mathrm{authorized}}}
\widehat{V}(\pi\mid t,e) - \lambda\widehat{K}(\pi),
$$

subject to resource, policy, and verification constraints. Here $e$ denotes available evidence. Estimates should include uncertainty and must not be treated as proof of correctness.

An illustrative decision policy:

```text
INPUT: task, policy boundary, compute budget

construct problem signature and acceptance criteria
retrieve capabilities and precedents
filter by type, context, authority, and minimum evidence
estimate benefit, uncertainty, and cost of candidate plans

IF a low-cost validated plan satisfies requirements:
    execute only if authorized
ELSE IF uncertainty can be reduced within budget:
    run targeted decomposition, simulation, or counter-evidence tests
    update estimates and re-evaluate
ELSE:
    abstain, escalate, or record a structural residual

preserve trace, evidence, costs, and unresolved assumptions
```

This pseudocode describes a candidate architecture; it is not a verified dispatch algorithm.

### 6.3 Structural Folding as a Resource Control

A macro-intelligence piece can hide internal detail for efficient selection while exposing enough contract and evidence for safe composition. When a failure or counterexample arises, the runtime should support controlled unfolding to inspect the responsible substructure.

Folding therefore has two requirements: **compression of operational complexity** and **recoverability of decision-relevant evidence**. A fold that conceals important limitations may reduce visible cost while increasing systemic risk.

## 7. Scaling the Intelligence Structure Itself

Scaling can change not only how much work is performed, but also what counts as a reusable unit of work.

A validated multi-step workflow may become a PIRU. A collection of PIRUs may become a Macro-Intelligence Piece. A higher-order piece may then be indexed as a node in the SCM and matched to future problems. This process can repeat, provided that contracts, composition tests, evidence, and policy remain meaningful at each level.

**Higher-order composition is not automatically emergent intelligence.** Evidence of a new capability requires comparison against appropriately resourced baselines, including the uncomposed components, straightforward ensembles, and conventional orchestration.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 8. The Third AI Stream: Structural Discovery and Growth

SIF distinguishes a prospective research and engineering stream alongside AI coding and AI-assisted writing/research: **AI Structural Discovery and Growth (AI-SDGS)**.

Its work products are not just code or prose. They include:

- candidate problem decompositions and capability maps;
- new or revised structural precedents;
- PIRP candidates and PIRU contracts;
- improved routing and scoring structures;
- adversarial tests and structural counter-evidence;
- validated macro-intelligence pieces;
- documented residuals and proposed research experiments.

AI-SDGS should be judged by **independently verified structural improvement**, not the number of generated designs. Human oversight may focus on evaluation criteria, resource and action boundaries, and consequential promotion decisions rather than manually inspecting every exploratory candidate.

This is a proposed stream, not an established industry classification.

## 9. Scaling and the Structural Perception Horizon

A larger and better organized structural system may notice relationships that a narrower architecture cannot represent or test. Yet greater compute and larger graphs do not prove expanded perception.

SIF distinguishes:

1. **Within-horizon improvement:** better performance on already representable problems.
2. **Capability extension:** new methods for previously identified tasks.
3. **Perceptual extension:** reproducible detection of previously unrepresented, decision-relevant structures.
4. **Worldview reconstruction:** revision of the entities, relations, scales, or perspectives through which tasks are framed.

A claimed expansion of the Structural Perception Horizon requires prospective tasks, independent evaluators, evidence of novel representations, and ablation tests ruling out simpler explanations such as added context or brute-force search.

See [SIF-015 — Structural Perception Horizon and Worldview Growth](SIF-015-Structural-Perception-Horizon-and-Worldview-Growth.md).

---

![Fig-008-Perception-Horizon-and-Worldview-Growth.png](../../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png)

---

## 10. Conceptual Case Study: Supply-Chain Resilience

Suppose a multinational manufacturer must assess disruption risk across suppliers, transport routes, regulatory constraints, and inventory policies.

**Breadth:** a structural map connects suppliers, facilities, regulations, and contingency capabilities.  
**Depth:** high-risk paths unfold into supplier-specific, route-specific, and contract-specific subproblems.  
**Precision:** dispatch chooses forecasting, optimization, simulation, or legal-rule checking according to the subproblem and its evidence.  
**Compute:** intensive simulation is reserved for uncertain high-impact scenarios rather than every routine order.  
**Interoperability:** typed contracts preserve units, time horizons, assumptions, and provenance across models.  
**Evaluation:** independent stress tests challenge optimistic scenarios and inspect evaluator blind spots.  
**Governance:** the system can propose rerouting or purchasing actions but cannot execute them without the relevant authority.  
**Learning:** validated strategies become precedents; failures become residuals for future investigation.

This is an illustrative design, not an implemented system or reported experiment.

## 11. Testable Hypotheses

**H1 — Structural breadth under fixed budget.** For heterogeneous task portfolios, increasing accessible, well-indexed capability coverage improves verified task success until retrieval and coordination costs dominate.

**H2 — Useful depth versus raw depth.** Adaptive decomposition yields better cost-adjusted accuracy than uniformly deep decomposition on tasks with localized complexity.

**H3 — Precision–compute interaction.** Improved routing precision increases the marginal value of additional inference or simulation compute relative to non-routed baselines.

**H4 — Contract fidelity.** Typed, evidence-preserving relays reduce cross-component semantic failures compared with untyped payload transfer.

**H5 — Evaluation scaling.** Independent adversarial testing reduces the rate of invalid structural promotions compared with self-evaluation alone, at measurable additional cost.

**H6 — Folding recoverability.** Evidence-recoverable structural folding achieves a better auditability–latency tradeoff than opaque macro-node abstraction.

**H7 — Collective reuse.** Context-matched precedent sharing improves cross-system transfer compared with sharing raw outputs without applicability conditions.

**H8 — Scaling saturation.** Each axis exhibits task-dependent diminishing returns or interference; no single axis dominates all workloads.

**H9 — Perception expansion.** Some multi-axis configurations yield independently validated novel problem representations not reproduced by equal-compute single-axis baselines.

These hypotheses may be rejected; rejection should update the SIF research program rather than be treated as a failure of the evaluation.

## 12. Experimental Design and Validation Roadmap

### Phase 1 — Define Tasks, Baselines, and Metrics

Construct task families with known heterogeneity, decomposition requirements, and cross-domain dependencies. Compare a strong single-model baseline, a conventional tool-routing baseline, and SIF-inspired variants. Pre-register success metrics and resource accounting.

### Phase 2 — Isolate Each Axis

Vary registry breadth, maximum decomposition depth, routing precision, and compute budget separately. Hold other variables as constant as practicable. Report both quality and overhead.

### Phase 3 — Measure Interactions

Run factorial or fractional-factorial experiments to estimate cross-axis complementarity. Include tests for failure propagation, stale precedents, misleading similarity, and distribution shift.

### Phase 4 — Validate Contracts and Governance

Inject incompatible types, missing context, false evidence, and unauthorized actions. Test whether the system detects, blocks, or escalates them. Verify that a high score never bypasses authorization.

### Phase 5 — Test Growth and Transfer

Permit sandboxed structural proposals, then require independent evaluation before promotion. Measure transfer to unseen tasks and different BrainUnits. Keep exploratory, shadow, and production environments separated.

### Phase 6 — Investigate Perception Claims

Use blinded assessments of newly proposed relations or problem decompositions. Require explanatory and predictive value, not merely persuasive narratives. Record negative results and alternative explanations.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 13. Failure Modes and Limits

| Failure mode | Consequence | Mitigation or test |
| --- | --- | --- |
| Breadth without localization | Search and coordination explosion | Retrieval ablations; precision@k; bounded candidate sets |
| Depth without stopping rules | Cost overruns and compounded error | Adaptive budgets; early stopping; decomposition audits |
| High-confidence wrong routing | Systematic misapplication | Applicability checks; abstention; counterexamples |
| Compute without allocation discipline | Expensive marginal gains | Cost-quality frontiers; strong equal-budget baselines |
| Untyped relay | Silent semantic corruption | SIC conformance; unit and context tests |
| Opaque folding | Lost evidence and accountability | Controlled unfolding; provenance requirements |
| Self-judging improvements | Reward hacking and Goodhart effects | Independent evaluators; held-out tests |
| Uncontrolled composition | Emergent failure pathways | Integration tests; sandbox isolation; authorization gates |
| Uncritical precedent reuse | Propagation of stale failures | Versioning; counter-evidence; expiry/revalidation |
| Mistaking complexity for perception | Unsupported worldview claims | Prospective novelty tests and causal ablations |

A further limitation is that the proposed axes are not guaranteed to be statistically independent or measurable on common scales. Their definitions may need revision after empirical work.

## 14. Relationship to the SIF Research Program

This paper builds on:

- [SIF-002 — Four Functional Domains of Structural Intelligence](../foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md)
- [SIF-004 — Localization and Intelligence Addressing](../functional-domains/SIF-004-Localization-and-Intelligence-Addressing.md)
- [SIF-005 — Per-Node Intelligence and Multi-Perspective Capabilities](../functional-domains/SIF-005-Per-Node-Intelligence-and-Multi-Perspective-Capabilities.md)
- [SIF-006 — Universal Control Planes and Scoring Folding](../functional-domains/SIF-006-Universal-Control-Planes-and-Scoring-Folding.md)
- [SIF-007 — Residual-Based Structural Growth](../functional-domains/SIF-007-Residual-Based-Structural-Growth.md)
- [SIF-008 — Dual Maps and Bidirectional Structural Mapping](../interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md)
- [SIF-010 — Universal Naming, Typing and Relay](../interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md)
- [SIF-011 — Structural Intelligence Contracts and Portable Units](../interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md)
- [SIF-012 — Multi-Intelligence Adversarial Sandbox](../validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
- [SIF-013 — Structural Counter-Evidence and Evaluator Governance](../validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md)
- [SIF-014 — Open-Ended Structural Growth and Collective Learning](../validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md)
- [SIF-015 — Structural Perception Horizon and Worldview Growth](SIF-015-Structural-Perception-Horizon-and-Worldview-Growth.md)
- [SIF-016 — Macro-Intelligence Pieces and Higher-Order Structures](SIF-016-Macro-Intelligence-Pieces-and-Higher-Order-Structures.md)

The next paper, **SIF-018 — Perspective ASI and the Open Future of Intelligence**, considers the epistemic and architectural implications of non-final intelligence frontiers.

## 15. Open Research Questions

1. Can structural breadth and depth be measured in ways that generalize across domains?
2. Under which workload conditions does routing overhead erase the benefit of specialized intelligence?
3. How should a system allocate compute between solving a task and challenging its own proposed solution?
4. Can evidence quality be calibrated across heterogeneous evaluators and simulations?
5. What minimal contracts permit useful cross-organization intelligence relay without centralizing ownership?
6. How should structural growth be throttled when validation cost rises faster than candidate generation?
7. Can a macro-intelligence piece preserve enough evidence to remain independently auditable after multiple folding levels?
8. What observations would distinguish a genuine perception-horizon expansion from an increase in retrieval coverage or raw compute?
9. How can a governance process revise scoring objectives without allowing candidates to manipulate their own evaluators?
10. What is the smallest empirical demonstration that would justify treating AI-SDGS as a distinct engineering workflow?

## 16. Conclusion

The proposed scaling picture has four primary dimensions: **large structures, deep structures, precision guidance, and major computational investment**. Their effectiveness depends on complementary capabilities for interoperability, evidence, governance, and collective learning.

The central claim is modest but consequential: scaling an intelligence system should not be reduced to scaling one model or one resource. A well-governed architecture may improve by changing **what it can address, how far it can decompose, where it directs computation, and how rigorously it validates structural change**.

Whether such scaling can eventually extend a system's Structural Perception Horizon remains an open empirical question. SIF provides a vocabulary and an experimental agenda for asking it without confusing architectural ambition with established fact.

> **Scale the structure, deepen the inquiry, guide the computation, and challenge the evidence.**

---

**Repository path:** `docs/frontiers/SIF-017-Scaling-Axes-and-Computational-Intelligence-Growth.md`  
**Citation:** Sizhe Tan and GPT-Obot, *Structural Intelligence Framework*, SIF-017, v1.0.0 (2026).  
**Research status:** Hypotheses and candidate architecture; independent empirical validation required.
