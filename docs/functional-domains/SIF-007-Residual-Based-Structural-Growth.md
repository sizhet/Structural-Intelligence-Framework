# SIF-007 — Residual-Based Structural Growth

**Structural Intelligence Framework (SIF) — Functional Domain IV**  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0 (research architecture)  
**Status:** Conceptual framework and testable research agenda  
**License:** Apache-2.0

> **Core proposition.** A structural intelligence system should treat the portion of a problem that its current structures cannot adequately represent, localize, solve, justify, or govern not merely as failure, but as a *candidate signal for structural growth*. Residuals are evidence to investigate—not automatic proof that a new intelligence structure is needed.

## Abstract

Many AI systems optimize a fixed model or workflow against a specified task distribution. The Structural Intelligence Framework (SIF) proposes a complementary path: preserve the ability to recognize when existing intelligence structures are inadequate, then discover, test, integrate, revise, or retire structural capabilities. This paper develops **Residual-Based Structural Growth (RBSG)**, the fourth functional domain of SIF. It distinguishes residuals arising from localization, representation, computation, composition, evidence, governance, and shifting environments; presents a bounded growth lifecycle from residual detection through adversarial validation and controlled deployment; and explains how the Structural Precedent Registry, Problem–Capability Dual Maps, Universal Naming–Typing–Relay (UNT-R), Structural Intelligence Contracts (SIC), and Multi-Intelligence Adversarial Sandbox (MIAS) participate. We discuss the role of LLMs and other intelligence mechanisms as candidate generators rather than privileged arbiters, address false growth signals and Goodhart effects, and propose measurable experiments. RBSG is a research architecture, not a claim that open-ended intelligence evolution has already been demonstrated.

**Keywords:** structural intelligence; residual learning; open-ended evolution; structural discovery; counter-evidence; capability registry; hybrid AI; recursive self-improvement; governance; adversarial evaluation.

---

## 1. Introduction: From Task Error to Structural Opportunity

A conventional improvement loop often keeps the architecture fixed while adjusting parameters, prompts, data, thresholds, or tools. Those interventions are useful and frequently sufficient. But some recurring failures expose a mismatch between the problem and the *structure of available intelligence*: a missing representation, an unavailable specialist, a poorly chosen decomposition, an invalid transfer boundary, or an evaluator that cannot distinguish genuine improvement from metric gaming.

SIF makes this mismatch a first-class research object. Its four functional domains are:

1. **Localization and Intelligence Addressing:** find the relevant problem region and available intelligence structures.
2. **Per-Node Intelligence:** execute heterogeneous reasoning, computation, simulation, and specialized methods.
3. **Universal Control Planes and Scoring/Folding:** evaluate, constrain, authorize, and audit decisions and resource use.
4. **Residual-Based Structural Growth:** investigate inadequacy and propose validated changes to the intelligence architecture.

These are functional roles, not mutually exclusive layers. A language model, a world model, a scoring tree, or a structural index can participate in several domains.

The central transition is:

**Solve with known structures → characterize the unresolved residual → determine whether the residual is structural → propose and challenge candidate changes → integrate only if justified.**

A residual is not a guarantee of novelty. The same signal may be caused by noisy data, implementation defects, distribution shift, unrealistic objectives, or inadequate compute. The growth system must discriminate among them.

---

![Fig-002-Four-Functional-Domains.png](../../figures/Fig-002-Four-Functional-Domains.png)

---

## 2. What Is a Structural Residual?

Let a task instance be represented by a problem specification \(P\), context \(C\), and admissible policy \(\Pi\). Let \(\mathcal{K}_t\) denote the available capability and precedent structures at time \(t\), and \(\mathcal{R}_t\) the available runtime and resource envelope. A SIF execution produces an outcome \(Y_t\) and an evidence record \(E_t\):

\[
(Y_t,E_t) = \operatorname{Execute}(P,C,\mathcal{K}_t,\mathcal{R}_t,\Pi).
\]

Define a **residual record** as a structured diagnostic rather than a single scalar:

\[
\rho_t = \operatorname{Diagnose}(P,C,Y_t,E_t,\mathcal{K}_t,\Pi).
\]

A residual record may contain observed discrepancies, confidence intervals, failed assumptions, missing capability signatures, provenance, counterexamples, and uncertainty about the cause. The objective is to avoid conflating *unexplained* with *unexplainable*.

### 2.1 Residual taxonomy

| Residual class | Diagnostic question | Possible intervention |
|---|---|---|
| Localization | Did the system address the wrong node, context, precedent, or granularity? | Improve MDT routing, CCC matching, two-phase search, or relay |
| Representation | Can the current structures express the relevant distinctions or causal relationships? | New feature space, ontology, world-model state, or structural decomposition |
| Capability | Is a required algorithm, model, solver, or tool absent or inadequate? | Reuse, adapt, or introduce a per-node capability |
| Composition | Are individually competent nodes failing together? | Revise CallingGraph, contracts, handoffs, or orchestration |
| Evidence | Is success uncertain, poorly calibrated, or unsupported? | Add independent evaluation, instrumentation, or counter-evidence |
| Control | Are scoring objectives, permissions, or policies incomplete or inconsistent? | Repair control planes; do not bypass authorization |
| Resource | Is the solution feasible but too costly, slow, or brittle? | Folding, caching, approximation, delegation, or compute allocation |
| Environmental | Has the world or task distribution changed? | Revalidate precedents and update contextual assumptions |
| Perspective | Does the current framing omit a meaningful dimension of the problem? | Introduce or compare alternative perspectives and worldviews |

A single incident can produce several residual classes. Causal diagnosis matters more than assigning a convenient label.

### 2.2 Residual versus ordinary error

A prediction error, test failure, or low score is an *observation*. It becomes a candidate structural residual only when the diagnostic process identifies a plausible inadequacy of representation, addressing, composition, control, or available capability. Conversely, a seemingly successful output may conceal a structural residual if its evidence is weak, its authorization invalid, or its robustness poor.

## 3. A Residual-First Diagnostic Protocol

Before proposing a new structure, the system should attempt less costly explanations and repairs.

**Stage A — Verify the observation.** Reproduce the failure; inspect inputs, measurement quality, ground truth, and execution traces.

**Stage B — Challenge the framing.** Ask whether the objective, constraints, context, and success criteria were correctly specified.

**Stage C — Search existing structural precedents.** Query the Structural Precedent Registry for exact, analogous, composable, and historically failed approaches. Preserve applicability conditions and counterexamples.

**Stage D — Attempt bounded adaptation.** Test routing changes, parameter tuning, prompt or data repair, alternative granularity, or different capability composition before assuming invention is necessary.

**Stage E — Form a structural growth hypothesis.** State what is missing, why existing alternatives are inadequate, and what observable result would falsify the proposed change.

**Stage F — Decide whether investigation is worth its cost.** Allocate sandbox budget based on expected value, severity, uncertainty, reversibility, and risk.

This protocol discourages uncontrolled architectural proliferation. **Not every failure deserves a new node.**

## 4. The Structural Growth Lifecycle

The proposed lifecycle is:

```text
Observed task / environment / evaluator discrepancy
                      |
                      v
          Residual characterization
                      |
                      v
     Diagnosis + precedent retrieval
                      |
           +----------+----------+
           |                     |
           v                     v
   Existing repair works    Structural gap persists
           |                     |
           v                     v
   Update precedent        Candidate generation
           |                     |
           |                     v
           |             Contract + hypothesis
           |                     |
           |                     v
           |            Adversarial sandbox
           |                     |
           |              +------+------+ 
           |              |             |
           |              v             v
           |           Reject /      Supported
           |           revise        candidate
           |              |             |
           |              v             v
           |          Record SCE    Shadow validation
           |                            |
           |                            v
           |                   Policy authorization
           |                            |
           +----------------------------+
                                        v
                            Registry + runtime update
                                        |
                                        v
                              Monitor / revalidate
                                        |
                                        +----> New residuals
```

### 4.1 Candidate generation

A candidate may be a new capability, an adapter, a changed contract, a different localization path, a replacement evaluator, a novel decomposition, a new perspective, or the retirement of a misleading precedent. Growth is therefore not synonymous with adding components.

Potential generators include LLMs, symbolic synthesis, evolutionary search, program synthesis, mathematical optimization, human proposals, and combinations thereof. Their outputs remain *proposals* until validated.

### 4.2 Candidate structural delta

Represent a proposal as a change set:

\[
\Delta\mathcal{K} = (\text{add},\text{modify},\text{compose},\text{replace},\text{retire}).
\]

The proposal should identify the baseline architecture, affected dependencies, expected benefits, risks, resource requirements, rollback procedure, and explicit falsification tests. Comparing \(\mathcal{K}_t\) with \(\mathcal{K}_t \oplus \Delta\mathcal{K}\) under matched conditions helps separate genuine improvement from changes in workload or evaluation.

### 4.3 Acceptance is conditional

A candidate should not be promoted solely because it wins one benchmark. Acceptance may require demonstrated benefit across relevant contexts, acceptable tail risk, robust calibration, independent challenge, and policy approval. Promotion can be scoped to a task family or context rather than made global.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 5. Growth Across the Four Functional Domains

### 5.1 Localization growth

A recurring retrieval miss may indicate an inadequate Metric Differential Tree partition, an overly coarse CCC, or a failed relay. Growth can add new indexing axes, differential branches, structural addresses, or context-sensitive matching rules. A newly discovered location should be compared against simpler query reformulations and improved embeddings.

### 5.2 Per-node growth

When the relevant problem is correctly addressed but available solvers are inadequate, the system may propose a new per-node intelligence mechanism: for example, a constraint solver, causal simulator, time-series specialist, formal checker, or hybrid LLM–optimization unit. SIF does not presume that LLMs alone can or should implement every node.

### 5.3 Control-plane growth

Persistent disagreement between utility scores and observed harm may reveal a flawed scoring objective or evaluator. The appropriate change may be a new counter-metric, an uncertainty gate, or an authority rule—not a more aggressive optimizer. **Better scores do not automatically grant greater action authority.**

### 5.4 Structural growth of growth itself

A growth process can discover limitations in its own candidate generator, sandbox, or evaluator. Such meta-residuals warrant controlled revision of the growth machinery, subject to independent evaluation and explicit governance. Recursive improvement without bounded challenge invites self-confirmation and Goodhart failures.

## 6. The Problem–Capability Dual Maps

SIF maintains two complementary views:

- The **Structural Problem-Solving Map** records tasks, subtasks, constraints, desired outcomes, and unresolved demand.
- The **Structural Capability Map** records existing methods, structural precedents, interfaces, applicability, evidence, and resource profiles.

**Bidirectional Structural Intelligence Mapping (BSIM)** connects the maps. Problem-driven growth begins when a demand cannot be satisfied with available capabilities. Capability-driven growth begins when a new method suggests previously unrecognized tasks, compositions, or perspectives.

This second direction matters: discovery need not be restricted to known benchmark failures. However, novel capability claims still require externally meaningful tasks and evidence; otherwise, the system risks optimizing novelty for its own sake.

## 7. Structural Precedent Intelligence and the Registry

The legal-precedent analogy suggests that intelligent systems should remember not only *what worked*, but *under which conditions*, *why*, *what failed*, and *which later evidence changed the conclusion*.

A registry entry for growth should minimally include:

| Field | Purpose |
|---|---|
| Structural identity and version | Distinguish the candidate and its lineage |
| Problem signature and context | Define intended applicability |
| Baseline and structural delta | Make the claimed change auditable |
| Capability / relay contract | Specify interoperable invocation |
| Positive evidence | Record supported benefits and uncertainty |
| Structural counter-evidence | Preserve failures, adversarial tests, and scope limits |
| Policy and resource envelope | State authorization and compute constraints |
| Lifecycle state | Proposed, sandboxed, shadow-validated, authorized, deprecated, or retired |
| Provenance and dependencies | Support reproduction, attribution, and rollback |

A failed experiment is a useful precedent when its conditions and failure mechanism are preserved. The registry should support distinguishing a new problem from a superficially similar but inapplicable precedent.

---

![Fig-005-Structural-Precedent-Intelligence.png](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 8. UNT-R and Structural Intelligence Contracts

Growth requires a stable interface without freezing the space of possible intelligence mechanisms. **Universal Naming, Typing and Relay (UNT-R)** supplies identity, semantic typing, and interoperable handoff. The **Structural Intelligence Contract (SIC)** specifies what a unit claims it can do and the conditions under which those claims are valid.

A candidate SIC may specify:

```yaml
# Illustrative research sketch, not a ratified schema
identity: sif.example.forecast-risk-adapter
version: 0.1.0
capability_type: risk_forecast
input_signature: demand_series + context + policy
output_signature: forecast + uncertainty + provenance
applicability:
  contexts: [regional_inventory]
  exclusions: [unvalidated_extreme_disruptions]
relay:
  describe: supported
  invoke: sandbox_only
  cancel: supported
evidence:
  baseline: sif.example.baseline-forecast@1.0
  positive_tests: pending
  counter_evidence: pending
policy:
  action_authority: none
  resource_budget: bounded
lifecycle: candidate
```

The contract should not force all mechanisms into a single algorithmic representation. PIRP-like flexible pieces and PIRU-like formal units may both participate through adapters, with differences in guarantees made explicit.

## 9. Multi-Intelligence Adversarial Sandbox (MIAS)

SIF proposes a heterogeneous, isolated test environment with separable roles:

1. **Builder:** constructs the candidate or structural delta.
2. **Challenger:** searches for failures, counterexamples, leakage, and invalid assumptions.
3. **Independent evaluator:** applies predeclared criteria and compares against baselines.
4. **World/simulation engine:** supplies controlled scenarios, perturbations, and delayed consequences where feasible.
5. **Governance gate:** determines whether evidence permits shadow testing or deployment.

These roles should not be presumed independent merely because they are labeled differently. Diversity of models, data, evaluation procedures, and ownership can reduce correlated failure, but independence must be assessed.

### 9.1 Structural counter-evidence

Structural Counter-Evidence (SCE) targets the architecture and its assumptions, not just a final answer. Examples include a hidden context dependency, a missing branch of a differential tree, a relay contract violation, benchmark contamination, evaluator capture, unbounded compute, or an invalid transfer from one perspective to another.

### 9.2 Evaluator governance

An evaluator can itself become the object of challenge. Use held-out cases, independent measurement, adversarial metric probes, calibration checks, and bounded recursive review. Where uncertainty cannot be resolved, the correct decision may be *do not promote*.

### 9.3 Deployment separation

Maintain three distinct environments:

**Exploratory sandbox → validated shadow runtime → explicitly authorized production runtime.**

A candidate may be free to explore inside a safe sandbox without receiving real-world action permissions. No autonomous growth loop should silently expand its own authority.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 10. Growth, Folding, and Macro-Intelligence Pieces

Structural growth can increase capability but also complexity. Without compression, dependency management, and evidence preservation, a growing architecture may become harder to understand and govern.

SIF therefore considers **structural folding**: validated compositions may become reusable macro-intelligence pieces, with their internal structure available for inspection or unfolding when needed. A former multi-step workflow can become a single callable unit in a higher-level CallingGraph.

Folding must not erase applicability boundaries, uncertainty, provenance, or rollback paths. A compact interface is not evidence that the underlying composition is universally safe or correct.

This leads to a possible hierarchy:

\[
\text{Methods} \rightarrow \text{Nodes} \rightarrow \text{Compositions} \rightarrow \text{Macro-Units} \rightarrow \text{Higher-Order Systems}.
\]

The arrows indicate possible engineering transformations, not a proven universal evolutionary law.

## 11. Structural Perception Horizon and Worldview Growth

Some residuals are invisible because the current system lacks the representation needed to notice them. SIF calls the boundary of detectable and evaluable distinctions a **Structural Perception Horizon**.

A **world model** describes states, dynamics, and predictions within some representation. A **worldview** concerns which distinctions, perspectives, scales, and causal relationships are considered relevant. Growth in structural capabilities may expand the perception horizon and, in turn, motivate worldview revision.

A hypothesized feedback loop is:

\[
\text{Structural Growth} \rightarrow \text{New Perceptual Distinctions}
\rightarrow \text{Reframed Problems} \rightarrow \text{New Residuals}
\rightarrow \text{Further Structural Growth}.
\]

This is an important research hypothesis, not a demonstrated inevitability. Measuring genuine worldview expansion requires more than observing that a system produces novel descriptions; it requires better grounded distinctions, predictions, interventions, or decisions on independent tasks.

---

![Fig-008-Perception-Horizon-and-Worldview-Growth.png](../../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png)

---

## 12. Scaling Axes and Resource Discipline

Four recurring scaling directions are especially relevant:

- **Large structures:** broader graphs, registries, and interacting intelligence units.
- **Deep structural granularity:** finer localization and multi-level decomposition.
- **Precision guidance:** better addressing, routing, scoring, uncertainty control, and authorization.
- **Major computational investment:** increased simulation, search, adversarial testing, and optimization budgets.

Interoperability and evidence-governed validation cut across these axes. Scaling compute without improving problem localization or evaluation may simply produce more expensive errors.

A practical allocation rule is to fund growth experiments when the expected value of information and potential capability gain justify the experiment's cost and risk. This criterion is necessarily approximate and should be monitored for systematic bias against unconventional but valuable candidates.

## 13. Conceptual Case Study: Supply-Chain Disruption Planning

Consider a planning system that uses demand forecasts, inventory optimization, supplier constraints, and a scoring forest. It performs well on routine disruptions but repeatedly fails when a supplier outage coincides with an unexpected transport restriction.

**Observation.** Late deliveries increase despite apparently acceptable forecast scores.

**Diagnosis.** The localization engine retrieves routine supplier-outage precedents but misses the joint transport-policy context. The scoring model also undervalues tail risk.

**Existing-structure repair.** Improve context typing and retrieve multi-factor disruption precedents. Test whether an existing robust optimization node can handle the problem.

**Growth hypothesis.** Introduce a joint disruption scenario generator and a new context-sensitive relay branch; add a tail-risk counter-metric to the evaluator.

**Sandbox challenge.** Compare against the baseline on held-out disruptions, synthetic perturbations, and stress cases. Examine whether benefits disappear under different cost assumptions or whether the new simulator creates spurious confidence.

**Controlled outcome.** If the evidence supports the candidate, authorize only a limited shadow deployment, preserve rollback, and record contexts where the original system remains preferable.

This case illustrates a *possible method*, not an empirical result or verified implementation.

## 14. Failure Modes and Defensive Design

| Failure mode | Why it matters | Defensive measure |
|---|---|---|
| False novelty | Existing methods are rediscovered under new names | Precedent search and baseline comparison |
| Structural bloat | Complexity grows faster than value | Pruning, folding, maintenance-cost accounting |
| Benchmark overfitting | Candidate improves a proxy but not real tasks | Held-out tests, independent outcomes, distribution shifts |
| Evaluator capture | Generator exploits or influences its judge | Role separation, evaluator challenges, external tests |
| Unsafe self-modification | Candidate acquires unauthorized action power | Sandbox isolation and independent policy gate |
| Lost counter-evidence | Failed contexts disappear from institutional memory | Versioned registry with negative precedents |
| Context drift | Previously valid contracts become misleading | Applicability monitoring and revalidation |
| Relay mismatch | Components agree syntactically but not semantically | Semantic typing and conformance tests |
| Compute escalation | Search consumes resources without reliable gain | Budgets, stopping rules, value-of-information review |
| Perspective lock-in | System cannot detect failures outside its framing | Heterogeneous challenges and new-perspective tests |

The purpose of governance is not to forbid exploration; it is to separate exploration from authority and to preserve accountable selection.

## 15. Testable Hypotheses

The following hypotheses require controlled experiments and may fail.

**H1 — Residual typing improves repair efficiency.** Systems using the residual taxonomy will resolve a larger share of failures per unit of engineering effort than systems using undifferentiated error signals.

**H2 — Precedent-first growth reduces unnecessary invention.** Registry-based retrieval and applicability checks will lower redundant candidate creation without reducing performance on novel tasks.

**H3 — Dual-map matching improves capability discovery.** BSIM will improve successful task-to-capability matching and reveal useful capability-driven task opportunities compared with one-way routing.

**H4 — Heterogeneous adversarial challenge improves robustness.** Builder–challenger–evaluator separation with diverse mechanisms will expose more consequential structural failures than self-evaluation alone, under matched compute budgets.

**H5 — Contract-based relay improves safe composition.** SIC/UNT-R conformance checks will reduce semantic handoff failures and ease replacement of per-node mechanisms.

**H6 — Bounded growth can outperform fixed architecture.** On nonstationary task families, a governed structural-growth system will achieve higher risk-adjusted performance than a fixed architecture with comparable tuning and compute resources.

**H7 — Folding improves scaling only when evidence survives compression.** Macro-unit reuse will reduce execution overhead without unacceptable loss of interpretability or robustness when provenance and counter-evidence remain accessible.

**H8 — Perspective expansion can be operationalized.** Some structural changes will enable detection and successful handling of independently specified problem distinctions previously missed by the baseline.

## 16. Experimental Roadmap

### Phase I — Diagnostic benchmark

Construct a suite with deliberately separated localization, capability, composition, control, and representation failures. Evaluate whether the system correctly identifies root causes rather than merely labeling symptoms. Report confusion matrices and human adjudication uncertainty.

### Phase II — Precedent and contract tests

Build a small versioned registry and heterogeneous capability set. Compare exact matching, analogy-based matching, and bidirectional mapping. Measure retrieval precision, applicability errors, relay conformance, and adaptation cost.

### Phase III — Adversarial growth trials

Generate candidate structural deltas with multiple methods. Use held-out tasks, counterexample search, ablation, and matched-budget baselines. Record both promoted and rejected candidates, including reasons.

### Phase IV — Controlled nonstationarity

Introduce distribution shifts and new task types over time. Measure adaptation latency, cumulative performance, resource cost, regressions, safety violations, and rollback success.

### Phase V — Perspective and higher-order composition

Test whether newly composed or folded units enable externally verifiable distinctions or tasks that the original capability map could not support. Distinguish task discovery from task invention with no independent utility.

### Suggested metrics

- **Diagnostic accuracy:** correctly attributed residual causes, including multi-cause cases.
- **Growth yield:** validated, useful structural changes per candidate and per compute budget.
- **Net value:** performance gain minus maintenance, inference, validation, and governance costs.
- **Robustness:** performance under perturbations, shifts, and adversarial tests.
- **Safety:** unauthorized actions, policy violations, and rollback failures.
- **Evidence quality:** calibration, replication, provenance completeness, counter-evidence coverage.
- **Open-endedness indicators:** sustained improvement across changing task families and genuinely new, independently useful capabilities.

No single metric should be allowed to stand in for the full growth objective.

## 17. Open Research Questions

1. How can a system distinguish a missing structure from inadequate data or insufficient computation with reliable uncertainty estimates?
2. What minimal evidence makes a structural precedent transferable to a new context?
3. How should structural growth be priced when its future reuse value is unknown?
4. Can evaluator independence be quantified rather than merely asserted?
5. How can new perspectives be proposed without rewarding arbitrary novelty?
6. What are the right retirement rules for obsolete, harmful, or redundant capabilities?
7. How should ownership and authorization propagate across nested macro-intelligence pieces?
8. Under what conditions does recursive improvement converge, oscillate, or degrade?
9. How can human and machine contributions be represented in a collective structural learning registry?
10. Which experiments can falsify claims of expanded structural perception or worldview reconstruction?

## 18. Relationship to the SIF Research Series

This paper completes the initial four-domain description introduced in **SIF-002**. It relies on **SIF-004** for intelligence addressing, **SIF-005** for heterogeneous per-node capabilities, and **SIF-006** for control, scoring, and folding. It also extends the structural precedent approach of **SIF-003** and the open architecture principles of **SIF-001**.

Subsequent manuscripts develop the enabling systems in more detail:

- **SIF-008:** Dual Maps and Bidirectional Structural Mapping.
- **SIF-009:** Structural Precedent Registry.
- **SIF-010:** Universal Naming, Typing and Relay.
- **SIF-011:** Structural Intelligence Contracts and Portable Units.
- **SIF-012–014:** Adversarial validation, evaluator governance, and collective structural growth.
- **SIF-015–018:** Perception horizon, macro-intelligence pieces, scaling, and perspective-relative ASI.

These connections describe a proposed research program. They do not imply that the mechanisms have already been integrated or empirically validated.

## 19. Conclusion

Residual-Based Structural Growth turns architectural inadequacy into an explicit, testable object of intelligence engineering. The key contribution is not the claim that every error calls for invention, but a disciplined procedure for determining when a structural change is warranted: diagnose the residual, search precedents, propose a bounded delta, challenge it with heterogeneous evidence, and integrate it only within an authorized scope.

A growing intelligence system should be capable of **adding, composing, revising, replacing, and retiring** its structures. It should also preserve the history of where each structure works, where it fails, and who may authorize its use. Under those constraints, structural growth may support more capable problem solving and, potentially, new ways of perceiving and framing problems.

> **The unresolved residual is not automatically a new intelligence. It is an invitation to discover what the current intelligence architecture cannot yet justify—and to test whether a better structure exists.**

---

## Citation

Tan, S., & GPT-Obot. (2026). *SIF-007: Residual-Based Structural Growth*. In *Structural Intelligence Framework (SIF)*, version 1.0.0. Research architecture manuscript. Repository: https://github.com/sizhet/Structural-Intelligence-Framework

**Note:** This document contains architectural proposals, conceptual examples, and falsifiable hypotheses. It reports no original empirical validation and makes no claim of a generally autonomous, self-improving implementation.
