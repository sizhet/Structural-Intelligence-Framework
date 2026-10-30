# SIF-018 — Perspective ASI and the Open Future of Intelligence

**Structural Intelligence Framework (SIF) — Frontiers Series**  
**Version:** 1.0.0 (research position paper)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual framework and testable research agenda; not a demonstration of ASI  
**License:** Apache-2.0

> **Central thesis.** No finite intelligence architecture should be presumed to exhaust all possible future intelligence structures and perspectives. A system may exhibit extraordinary intelligence within a specified perspective while remaining limited by the problems it can formulate, the evidence it can evaluate, and the actions it is authorized to take.

## Abstract

Artificial superintelligence (ASI) is often discussed as though it were a single, globally ordered destination. This paper proposes **Perspective ASI** as a more operational research lens: exceptional performance must be indexed to a domain, task distribution, evaluation protocol, resource envelope, time horizon, and governance boundary. Such indexing does not resolve the philosophical definition of general intelligence or establish the existence of ASI. It does, however, make capability claims more precise and falsifiable.

Within the Structural Intelligence Framework (SIF), intelligence is an open ecosystem of heterogeneous and revisable structures rather than a closed inventory of models. Four functional domains—localization, per-node intelligence, control planes and scoring/folding, and residual-based structural growth—enable systems to locate, compose, evaluate, and revise capabilities. Structural Problem-Solving and Capability Maps, a Structural Precedent Registry, Universal Naming/Typing/Relay, Structural Intelligence Contracts, and a Multi-Intelligence Adversarial Sandbox provide proposed mechanisms for interoperability and accountable evolution.

We distinguish **performance growth**, **capability growth**, **structural growth**, and **perception/worldview growth**. The last is a hypothesis requiring stronger evidence than benchmark improvements. We examine the limits of perspective-relative superiority, the possibility of higher-order intelligence structures, and the non-finality of architectural choices. The paper closes with falsifiable hypotheses, adversarial evaluation designs, governance principles, and open questions.

**Keywords:** structural intelligence; perspective-relative ASI; open-ended intelligence; structural perception horizon; intelligence governance; structural precedents; counter-evidence; collective learning; higher-order intelligence.

---

## 1. Why Revisit the Meaning of ASI?

The phrase *artificial superintelligence* is frequently used to denote an intelligence surpassing human abilities across a very broad range of cognitive activities. That aspiration is important, but a claim of superiority is incomplete unless it identifies **superiority at what, under which conditions, relative to whom, and according to which evidence**.

A system might outperform expert humans at molecular search while failing at physical intervention, social negotiation, or the recognition of a previously unmodeled hazard. Another might coordinate many specialized systems yet lack the authority to perform consequential actions. These examples demonstrate why ability, understanding, generalization, and authorization must not be collapsed into one scalar.

SIF adopts a deliberately open posture:

1. A currently successful intelligence structure is a **precedent**, not a final ontology of intelligence.
2. New structures may complement, displace, or reframe old ones.
3. A capability claim remains conditional on its evidence and applicability boundaries.
4. Greater capability does not confer legitimate authority.
5. The set of meaningful perspectives may itself change as structural intelligence evolves.

The term **Perspective ASI** is used here as a *research construct*, not as a new certified intelligence level.

## 2. A Working Definition of Perspective ASI

Let a perspective be a specification

$$
P=(D,T,M,E,R,H,G),
$$

where:

- $D$: domain and environment;
- $T$: tasks and their sampling distribution;
- $M$: metrics and success criteria;
- $E$: admissible evidence and evaluation procedures;
- $R$: available resources and tools;
- $H$: relevant time horizon;
- $G$: governance and action boundaries.

A candidate system $S$ can be evaluated relative to a comparator population $B$ through a performance distribution, rather than a single unqualified score:

$$
\Delta_P(S,B)=\mathbb{E}_{t\sim T}[U_P(S,t)-U_P(B,t)].
$$

Here $U_P$ is a perspective-specific utility or evaluation function, and uncertainty estimates must accompany empirical estimates of $\Delta_P$. This expression is an **illustrative formalization**, not a universally accepted intelligence metric.

We use **perspective-relative superhuman performance** when a system demonstrably exceeds a defined human comparator under rigorous evaluation. The stronger label **Perspective ASI** is reserved, provisionally, for claims of exceptional, robust superiority across a *substantial family of tasks within a declared perspective*, including tests of adaptation, uncertainty, and adversarial stress. No universal numerical threshold is proposed.

### 2.1 What the definition does not imply

- Superior performance in one perspective does **not** imply general ASI.
- A composite system's success does **not** prove that every constituent is superior.
- High benchmark scores do **not** establish causal understanding or a transformed worldview.
- A broader set of capabilities does **not** entail safety, alignment, or authorization.
- The absence of a discovered counterexample does **not** establish that none exists.

### 2.2 The perspective boundary is part of the claim

A perspective must record what is excluded: missing sensors, untested populations, unavailable actuators, assumptions about the environment, or prohibited actions. An honest capability statement identifies these boundaries as carefully as it identifies successes.

## 3. From Isolated Models to Open Structural Intelligence

SIF does not begin with the premise that a single model family must embody all intelligence. Large language models are important general-purpose components and often the most practical starting point for reasoning and interface tasks. Yet different problem classes can also benefit from symbolic constraints, optimization, simulation, statistical inference, formal verification, world models, and specialized domain engines.

The framework distinguishes four interacting **functional domains**, not four mutually exclusive software layers:

| Functional domain | Central question | Illustrative structures |
|---|---|---|
| Localization and intelligence addressing | Where is the relevant problem, knowledge, or capability? | LLMs, CCC, MDT, two-phase search, CallingGraphs, relay networks, world models |
| Per-node intelligence | What computation or judgment can a node provide? | LLMs, rules, optimization, ANN, simulation, formal checkers, domain tools |
| Universal control planes and scoring/folding | Which alternatives should be evaluated, selected, or authorized? | Policy, scoring trees/forests, evidence audit, structural folding |
| Residual-based structural growth | What remains unresolved, and what should change? | Residual diagnosis, structural proposals, adversarial validation, collective learning |

The same component may participate in several domains. A world model, for example, may help localize states, simulate consequences, evaluate decisions, and reveal representational gaps.

**Figure placement:** `../../figures/Fig-001-SIF-Grand-Architecture.png` may be inserted after this section. `../../figures/Fig-002-Four-Functional-Domains.png` may accompany the table.

## 4. Two Maps, One Evolving Relationship

SIF separates two complementary representations:

**Structural Problem-Solving Map (PSM).** What must be accomplished? It records goals, constraints, subproblems, dependencies, context, uncertainties, and success conditions, resembling a task-oriented CallingGraph.

**Structural Capability Map (SCM).** What can currently be done? It records capabilities, interfaces, prerequisites, evidence, costs, restrictions, and composition paths, resembling an action-oriented CallingGraph.

**Bidirectional Structural Intelligence Mapping (BSIM)** relates the two:

$$
\mathrm{PSM}\;\rightleftarrows\;\mathrm{SCM}.
$$

The forward direction locates candidate capabilities for a problem. The reverse direction examines whether a newly discovered capability makes previously impractical tasks feasible or exposes new classes of questions. Neither direction guarantees a valid match.

A **Structural Precedent Registry (SPR)** mediates this relationship by preserving conditional, versioned cases: what worked, what failed, where it applied, what evidence supported it, and what counter-evidence limited it. The analogy is to legal precedent, with an essential difference: SIF precedents are engineering claims subject to empirical challenge, not binding judicial authority.

**Figure placement:** `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` and `../../figures/Fig-005-Structural-Precedent-Intelligence.png`.

## 5. Interoperability Without Architectural Uniformity

An open ecosystem cannot require every intelligence unit to share one internal algorithm. Instead, it needs explicit boundary agreements.

**Universal Naming, Typing, and Relay (UNT-R)** proposes three complementary functions:

- **Naming:** stable, versioned identity for capabilities, contracts, precedents, evidence, and sessions.
- **Typing:** machine- and human-interpretable declarations of semantics, inputs, outputs, contexts, and behavioral expectations.
- **Relay:** controlled discovery, invocation, handoff, status, result, and cancellation across heterogeneous units.

A **Structural Intelligence Contract (SIC)** declares identity, capabilities, input/output signatures, context assumptions, evidence, counter-evidence, policy, resource limits, and evolution hooks. Flexible **Portable Intelligence Runtime Pieces (PIRP)** can be explored before stricter **Portable Intelligence Runtime Units (PIRU)** are formalized and validated.

These are **candidate specifications** for future testing, not claims of deployed universal standards.

> **Standardize the contract, not the intelligence.**

This approach makes architectural diversity compatible with composability, while acknowledging that semantic interoperability is much harder than merely agreeing on a data format.

## 6. Four Distinct Kinds of Intelligence Growth

The term *growth* can conceal importantly different phenomena.

### 6.1 Performance growth

An existing system becomes faster, cheaper, or more accurate on a defined task distribution without materially changing the set of tasks it can perform.

### 6.2 Capability growth

The system gains a new ability or expands the set of tasks it can solve—for example, by integrating a solver or a validated simulation component.

### 6.3 Structural growth

The system revises how capabilities are represented, localized, composed, governed, or evaluated. A new routing graph, an improved structural precedent schema, or a better evaluator can qualify if it creates reproducible functional change.

### 6.4 Perception and worldview growth

The system begins to recognize or model previously unavailable entities, relations, scales, or causal distinctions. This is the strongest and most difficult claim. Better performance or richer text alone does not demonstrate it.

A useful conceptual sequence is:

$$
\text{Structural Change}
\longrightarrow
\text{New Detectable Distinctions}
\longrightarrow
\text{Revised Problem Formulation}
\longrightarrow
\text{New Evaluation and Action Possibilities}.
$$

Each arrow is a **hypothesis to be tested**, not a guaranteed implication.

## 7. Structural Perception Horizon and Worldview Reconstruction

A **Structural Perception Horizon (SPH)** denotes the effective boundary of distinctions a system can presently detect, represent, relate, and test under its available resources and interfaces.

A **world model** represents states, transitions, dynamics, or consequences in some domain. A **worldview**, in this paper's technical sense, governs which distinctions, entities, causal hypotheses, granularities, and perspectives are considered meaningful. The latter is not a claim that an AI possesses a human-like philosophy or subjective experience.

A system can improve its world model within an unchanged worldview. More ambitiously, new instruments, representations, or collaborations might reveal that the old worldview omitted a critical variable or misidentified a causal boundary.

For example, a logistics planner may first optimize routes and inventories. Later, a structural challenge may reveal that organizational trust, supplier incentives, or correlated disruptions must be modeled explicitly. The improvement is not merely another optimization iteration: the **problem representation** has changed. Whether this constitutes SPH expansion requires evidence that the new distinctions are reliable, causally useful, and transferable beyond the motivating case.

### 7.1 A candidate feedback loop

1. Existing structures expose unresolved residuals or systematic counterexamples.
2. Alternative perspectives and representations are proposed.
3. Independent tests identify genuinely new, useful distinctions.
4. The PSM and SCM are revised to accommodate them.
5. New problems and capabilities become discoverable.
6. Further residuals arise, restarting the cycle.

This is a possible mechanism for open-ended inquiry, not proof of unbounded growth.

**Figure placement:** `../../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png`.

## 8. Macro-Intelligence Pieces and Higher-Order Structures

An entire intelligence workflow can become a component of a larger workflow. We call a sufficiently encapsulated and reusable composite a **Macro-Intelligence Piece (MIP)**.

Examples may include a validated research workflow, a supply-chain planning ensemble, or a multi-agent scientific hypothesis-testing system. A macro-piece must expose more than a convenient name: it needs a contract, provenance, evidence, boundary conditions, cost profile, and cancellation/oversight mechanisms.

Higher-order composition may yield:

- **Aggregation:** more tools without new coordination logic.
- **Coordination:** useful orchestration among components.
- **Abstraction:** a complex workflow becomes reusable through a stable interface.
- **Emergent system-level capability:** the composite demonstrably performs tasks not achievable by its components under comparable conditions.

Only the final category supports a strong claim of genuinely new system-level capability, and even then the comparison must control for resources, information access, and evaluation design. Size alone is not intelligence.

Structural **folding** can hide validated internal detail for efficiency; **unfolding** must recover enough assumptions, provenance, and counter-evidence for appropriate review. A folded macro-piece should not become an uninspectable authority.

## 9. Scaling Intelligence Along Multiple Axes

SIF proposes four prominent growth axes:

1. **Large structures:** richer capability networks and higher-order compositions.
2. **Deep structural granularity:** finer analysis, multi-scale decomposition, and longer chains of justified reasoning.
3. **Precision guidance:** better localization, routing, evidence selection, and resource allocation.
4. **Major computational investment:** more compute for exploration, simulation, verification, and evaluation.

These are complemented by interoperability, evidence quality, governance, and collective learning. Their interactions matter: better guidance may increase the marginal value of computation; greater computation may also amplify flawed objectives if evaluation is weak.

A prospective third major AI workflow—alongside AI coding and AI writing/research—is **AI Structural Discovery and Growth (AI-SDGS)**: systems proposing, challenging, validating, and refining reusable intelligence structures. This is a research direction, not a prediction that such a workflow is already mature.

## 10. Why Open Growth Requires Adversarial Evaluation

An architecture that can change its own structure also changes the objects, assumptions, and metrics by which it is judged. This creates a particularly acute form of evaluation risk.

The proposed **Multi-Intelligence Adversarial Sandbox (MIAS)** separates roles:

| Role | Responsibility | Principal failure to guard against |
|---|---|---|
| Builder | Propose candidate structures and improvements | Self-serving success criteria |
| Challenger | Generate difficult counterexamples and alternative perspectives | Shallow or repetitive attacks |
| Independent evaluator | Test claims on held-out and adversarial cases | Metric gaming and evaluator contamination |
| World/simulation engine | Test consequences under explicit assumptions | Simulation-to-reality gaps |
| Formal or deterministic checker | Verify selected invariants and constraints | False confidence outside checked scope |
| Policy authority | Determine permitted deployment and escalation | Unauthorized or irreversible action |

A **Structural Counter-Evidence (SCE)** record should capture the challenged claim, test context, failure mode, reproducibility, severity, and the resulting boundary revision. Negative results are assets in the precedent registry, not noise to be erased.

The evaluator itself may need challenge: benchmark leakage, proxy-target divergence, distribution shift, and reward hacking can make apparent progress misleading. Recursive evaluator review must be bounded by cost, risk, and explicit stopping criteria; no finite evaluation program can guarantee complete safety or correctness.

**Figure placement:** `../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` and `../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png`.

## 11. Intelligence, Authority, and Human Sovereignty

SIF distinguishes three questions:

- **Can the system do it?** Capability.
- **Does the evidence justify relying on it here?** Validation.
- **May the system do it?** Authorization.

A high-performing or even perspective-superhuman system must not infer deployment rights from its scores. Policy and authority, scoring and decision support, and evidence and audit are distinct control functions. Authorization should be scoped, revocable, and sensitive to impact, with stronger oversight for consequential or irreversible actions.

The exploratory sandbox, validated shadow runtime, and authorized production runtime must be separated. A proposed structural self-improvement can be investigated without granting it the power to rewrite production policy or to deploy itself.

Sovereign BrainUnits and collective learning introduce further boundary questions: who owns a capability, who may inspect evidence, who can relay context, and who accepts liability for cross-boundary actions? These questions cannot be solved by a universal interface alone.

> **Evaluation does not imply authorization. Discovery does not imply deployment.**

## 12. Perspective ASI Is Not a Terminal Architecture

If exceptional intelligence is indexed to a perspective, then a new perspective can expose an old system's limitations. A system that appears comprehensive under a current benchmark suite may be incomplete under newly discovered tasks, new causal variables, or revised social and physical constraints.

This does **not** prove that intelligence must grow forever. Physical constraints, undecidability, limited observations, computational complexity, economics, and governance may create hard or practical ceilings. It does suggest that a finite inventory of today's architectures is a poor basis for asserting that the future space of intelligence has been exhausted.

Three claims should remain separate:

1. **Epistemic openness:** we do not currently know all future useful structures or perspectives.
2. **Architectural openness:** we can design systems that accept and evaluate new structures.
3. **Empirical open-endedness:** a particular implementation repeatedly discovers validated, nontrivial structures over time.

The first is a stance of humility; the second is an engineering goal; the third is an empirical claim requiring longitudinal evidence.

The framework's guiding proposition is therefore:

> **No finite intelligence architecture should be presumed to exhaust all possible future intelligence structures and perspectives.**

This is a methodological caution, not a theorem of unlimited intelligence.

## 13. A Worked Research Scenario: Resilient Infrastructure Planning

Consider a hypothetical system coordinating energy, transportation, and emergency logistics.

**Stage A — Existing perspective.** The PSM contains demand forecasts, routes, capacity, and cost. The SCM contains forecasting models, optimizers, simulators, and policy checks. The system performs well on standard disruptions.

**Stage B — Structural residual.** A correlated infrastructure failure reveals that the planner's independence assumptions are false. A conventional response merely increases model capacity; a structural response records the failure as counter-evidence against the existing representation.

**Stage C — Precedent and discovery.** The registry retrieves related cases, but their applicability is limited. The Builder proposes a new dependency graph linking infrastructure, supplier incentives, and communication reliability.

**Stage D — Adversarial validation.** Challengers introduce unseen disruption combinations. Independent evaluators compare the revised system with resource-matched baselines, test ablations, and check for metric gaming. Formal checks verify selected safety constraints.

**Stage E — Conditional growth.** If the revised representation yields reproducible improvements and identifies new transferable causal distinctions, the system may claim a *bounded* expansion of its structural perception horizon. It may not claim general ASI.

**Stage F — Governed deployment.** Only an authorized operator can promote the candidate from shadow testing to production, with monitoring and rollback provisions.

This scenario illustrates a research protocol. It is not evidence that the proposed architecture has already been implemented or validated.

## 14. Testable Hypotheses

The following hypotheses are designed to be refutable rather than celebratory.

| ID | Hypothesis | Suggested test | What would count against it |
|---|---|---|---|
| H1 | Perspective-indexed claims predict out-of-distribution limits better than aggregate rankings | Compare calibrated claim cards with scalar leaderboards on unseen task families | No improvement in calibration or boundary prediction |
| H2 | Dual maps improve heterogeneous capability discovery | Resource-matched PSM–SCM routing vs. flat tool retrieval | Equal or worse valid-task completion and cost |
| H3 | Precedent records improve transfer while reducing invalid reuse | Compare evidence-rich cases with unqualified examples | No reduction in applicability errors |
| H4 | SIC/UNT-R reduces cross-system integration failures | Controlled integration studies across diverse units | Higher overhead without reliability benefit |
| H5 | Adversarial structural testing finds failures missed by answer-only testing | Blind challenge suites and held-out incidents | No additional meaningful failures detected |
| H6 | Evaluator challenge reduces Goodhart-type regressions | Induced proxy-metric mismatch experiments | No improvement in true-objective performance |
| H7 | Macro-pieces provide useful abstraction without unacceptable audit loss | Compare folded vs. unfolded workflows | Unrecoverable provenance or worse safety/cost |
| H8 | Structural growth can expand the perception horizon | Tests requiring discovery of previously unrepresented variables | Gains explained solely by memorization, added data, or compute |
| H9 | Capability-to-problem mapping identifies useful new applications | Prospective blinded application discovery | Suggestions fail independent utility tests |
| H10 | Governance separation reduces unauthorized consequential actions | Simulated escalation and permission-boundary trials | No reduction or new bypass paths |

All comparisons should specify baseline systems, sample sizes, resource budgets, confidence intervals, and preregistered criteria where feasible. Negative findings should be published alongside positive ones.

## 15. Proposed Validation Program

### Phase 1 — Claim and boundary registry

Create perspective-specific capability cards recording task families, baselines, exclusions, uncertainty, and authorization limits. Test whether independent reviewers can interpret and reproduce claims.

### Phase 2 — Interoperability and precedent retrieval

Implement minimal candidate SIC and UNT-R interfaces, a versioned SPR, and PSM–SCM mappings. Measure integration reliability, applicability errors, and retrieval quality.

### Phase 3 — Adversarial structural evaluation

Deploy builder/challenger/evaluator separation in an isolated environment. Preserve counter-evidence and test evaluator robustness against distribution shift and reward hacking.

### Phase 4 — Macro-structure and growth experiments

Test composition, folding/unfolding, ablations, and controlled resource scaling. Determine whether improvements exceed simple aggregation baselines.

### Phase 5 — Perception-horizon experiments

Design environments with latent variables and discoverable causal structures. Compare whether candidate systems independently identify new distinctions that improve transfer, intervention prediction, and counterfactual reasoning.

### Phase 6 — Longitudinal, governed evolution

Track candidate discovery, validation, rejection, revision, deployment, rollback, and retirement over extended periods. Evaluate whether growth remains useful under changing objectives and constraints.

The program should publish protocols and failure cases, not merely performance summaries.

## 16. Failure Modes and Research Limits

**Perspective shopping.** Selecting an evaluation perspective after seeing results can manufacture apparent superiority. Mitigation: preregistered perspectives and external tests.

**Metric collapse.** Compressing intelligence into a single score hides important tradeoffs. Mitigation: distributions, multi-objective reporting, and explicit exclusions.

**Compositional overclaim.** A larger system may only aggregate existing capabilities. Mitigation: resource-matched ablations and genuinely novel task tests.

**False worldview novelty.** Rewording known facts may look like discovering a new perspective. Mitigation: operational tests of newly represented variables and causal transfer.

**Registry contamination.** Low-quality or circular evidence can spread through collective learning. Mitigation: provenance, independent replication, counter-evidence, and trust boundaries.

**Evaluator capture.** Builders may optimize the evaluator rather than the real objective. Mitigation: separated roles, held-out criteria, adversarial review, and bounded evaluator recursion.

**Governance leakage.** A validated capability may be incorrectly treated as authorized. Mitigation: explicit policy checks at every consequential action boundary.

**Compute-induced illusion.** More resources may mask structural weaknesses. Mitigation: fixed-budget and efficiency-normalized comparisons.

**Open-endedness overclaim.** Repeated changes may be churn rather than progress. Mitigation: longitudinal measures of transfer, robustness, novelty, and cost.

These limits are not peripheral caveats. They define the conditions under which SIF claims can become scientifically meaningful.

## 17. Open Questions

1. Can perspectives be compared without imposing an arbitrary universal utility function?
2. What minimum diversity of tasks and environments would justify the label *Perspective ASI*?
3. How can we distinguish newly discovered causal structure from additional memorized correlations?
4. When does a macro-intelligence piece represent genuine higher-order capability rather than convenient packaging?
5. What evidence is sufficient to promote a flexible PIRP into a dependable PIRU?
6. How should a registry preserve incompatible precedents across contexts and governance regimes?
7. Can an adversarial sandbox reliably expose flaws in its own evaluators without prohibitive cost?
8. Which kinds of structural residual are most predictive of productive innovation?
9. How can multiple sovereign BrainUnits learn collectively without surrendering ownership, privacy, or decision authority?
10. What practical limits arise from compute, energy, latency, observability, and irreversible actions?
11. How should human institutions govern a system whose capabilities and problem representations change over time?
12. What would falsify the proposed perception–growth feedback loop?

## 18. Conclusion: An Open Future, Not a Final Intelligence

The central contribution of this paper is not a declaration that ASI has arrived, nor a prediction of an inevitable superintelligent endpoint. It is a proposal to make extraordinary intelligence claims **perspective-specific, evidence-bearing, challengeable, and governed**, while leaving the architecture of future intelligence open to revision.

SIF offers one candidate organizing framework: locate intelligence, compose heterogeneous per-node capabilities, evaluate and authorize actions through distinct control functions, and treat unresolved residuals as opportunities for carefully tested structural growth. Dual maps, structural precedents, universal contracts and relay, adversarial validation, and collective learning may make this openness operational—if their benefits survive empirical comparison.

The most ambitious frontier is not simply to solve more problems within a fixed worldview. It is to determine whether a system can reliably discover that its own way of seeing the problem was incomplete, reconstruct that view, and expose the reconstruction to independent challenge.

> **Structural intelligence does not merely solve problems within a worldview; through open-ended structural growth, it may expand and reconstruct the worldview itself.**

That possibility deserves investigation. It does not deserve exemption from evidence.

---

## 19. Relationship to the SIF Research Series

This article completes the proposed eighteen-paper conceptual core of SIF v1.0.0 and builds particularly on:

- [SIF-001 — From Isolated Intelligence to Open Structural Intelligence](../foundations/SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md)
- [SIF-002 — Four Functional Domains of Structural Intelligence](../foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md)
- [SIF-003 — Structural Precedents and Open Intelligence Evolution](../foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md)
- [SIF-008 — Dual Maps and Bidirectional Structural Mapping](../interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md)
- [SIF-011 — Structural Intelligence Contracts and Portable Units](../interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md)
- [SIF-012 — Multi-Intelligence Adversarial Sandbox](../validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
- [SIF-013 — Structural Counter-Evidence and Evaluator Governance](../validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md)
- [SIF-014 — Open-Ended Structural Growth and Collective Learning](../validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md)
- [SIF-015 — Structural Perception Horizon and Worldview Growth](SIF-015-Structural-Perception-Horizon-and-Worldview-Growth.md)
- [SIF-016 — Macro-Intelligence Pieces and Higher-Order Structures](SIF-016-Macro-Intelligence-Pieces-and-Higher-Order-Structures.md)
- [SIF-017 — Scaling Axes and Computational Intelligence Growth](SIF-017-Scaling-Axes-and-Computational-Intelligence-Growth.md)

The companion candidate specifications (`SPEC-001`–`SPEC-004`) and research documents (`OPEN-QUESTIONS`, `TESTABLE-HYPOTHESES`, `VALIDATION-ROADMAP`) are intended to translate the conceptual claims into reproducible engineering investigations.

## 20. Figure Integration Guide

| Figure | Suggested location | Function |
|---|---|---|
| Fig-001 — SIF Grand Architecture | Section 3 | Situates the open framework and its three engineering systems |
| Fig-002 — Four Functional Domains | Section 3 | Distinguishes four functional roles |
| Fig-003 — Problem–Capability Dual Maps | Section 4 | Shows bidirectional mapping |
| Fig-005 — Structural Precedent Intelligence | Section 4 | Explains evidence-bearing precedents |
| Fig-006 — Multi-Intelligence Adversarial Sandbox | Section 10 | Illustrates adversarial validation and independent authority |
| Fig-007 — Structural Growth and Evolution Loop | Section 10 or 15 | Shows growth lifecycle and feedback |
| Fig-008 — Perception Horizon and Worldview Growth | Section 7 | Illustrates the central frontier hypothesis |

*Figure references are placement guidance; figures are separate planned repository assets.*

---

**Citation guidance:** Cite the SIF repository's release DOI when assigned. Do not substitute an unverified DOI.  
**Research status:** Conceptual and prospective; no implementation, experiment, or ASI capability is claimed by this paper.  
**© Sizhe Tan & GPT-Obot. Licensed under Apache-2.0.**
