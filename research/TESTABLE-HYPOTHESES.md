# Testable Hypotheses for the Structural Intelligence Framework

**Project:** Structural Intelligence Framework (SIF)  
**Document:** `research/TESTABLE-HYPOTHESES.md`  
**Version:** 1.0.0 (research agenda; not an empirical results report)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed hypotheses and evaluation protocols  
**License:** Apache-2.0

> **Research principle:** A structural intelligence claim becomes scientifically useful when it specifies a comparator, an observable outcome, a failure criterion, and the conditions under which the result may generalize.

## 1. Purpose and Scope

This document converts SIF's architectural proposals into falsifiable research hypotheses. It does **not** claim that the proposed mechanisms have been implemented, benchmarked, or validated. SIF treats the following as separable research objects:

- **Problem representation and localization:** How a problem is represented and routed to applicable intelligence.
- **Per-node capability and composition:** Which algorithms or intelligence units execute subtasks, and how they interact.
- **Control, scoring, and authorization:** How alternatives are evaluated, audited, and permitted to act.
- **Residual-driven growth:** How failures and uncovered needs lead to proposed, tested, and potentially reusable new structures.

These domains are functional roles, not mutually exclusive software layers. An LLM, world model, structural precedent, or scoring forest may participate in multiple roles. The hypotheses below also cover the cross-cutting mechanisms of Structural Intelligence Contracts (SIC), Universal Naming, Typing, and Relay (UNT-R), Structural Precedent Registry (SPR), Multi-Intelligence Adversarial Sandbox (MIAS), and Collective Structural Learning (CSL).

## 2. Evaluation Conventions

### 2.1 Units of analysis

An experimental unit may be a task instance, a task family, a composed workflow, a registered precedent, a relay session, or an evolving system evaluated at a specified checkpoint. **Do not** treat correlated attempts on the same task as independent samples. Group by task family, environment, organization, or time period as appropriate.

### 2.2 Baselines and ablations

For every hypothesis, use the strongest feasible baselines rather than only an intentionally weak reference:

1. A capable single-model or single-method baseline with comparable access to tools and data.
2. A nonstructural multi-tool/agent orchestration baseline where relevant.
3. A fixed SIF-like architecture with structural growth disabled.
4. A full proposed configuration.
5. Mechanism-specific ablations (for example, remove the registry, contract checks, counter-evidence, or bidirectional matching).

Control for total token usage, wall-clock time, compute, human review effort, retrieval corpus size, and external tool access. Report both **equal-budget** and **best-achievable-under-cap** comparisons when possible.

### 2.3 Outcome and evidence rules

- Pre-register primary outcomes, task splits, exclusion rules, and stopping criteria before final evaluation.
- Report uncertainty intervals, per-task-family results, effect sizes, and negative outcomes, not just aggregate averages.
- Evaluate out-of-distribution (OOD) transfer separately from in-distribution performance.
- Track safety and governance violations independently of task quality.
- Preserve provenance: data versions, model versions, prompts, policies, registry snapshots, and evaluator versions.
- Distinguish a **failed implementation** from a **disconfirmed hypothesis**. Repeated, well-powered failures across competent implementations provide stronger evidence against a broad architectural claim.
- Where quantitative thresholds appear below, treat them as *illustrative preregistration choices*, not established empirical benchmarks.

### 2.4 Primary metrics catalog

| Metric | Operational meaning | Typical direction |
|---|---|---|
| Task success | Independently adjudicated completion against explicit criteria | Higher |
| Correct routing@k | Ground-truth applicable capability appears in top-k | Higher |
| Applicability precision | Fraction of selected capabilities valid in target context | Higher |
| Calibration | Agreement between predicted confidence and observed correctness | Better calibrated |
| End-to-end cost | Compute, tokens, latency, tools, and human labor | Lower at equal quality |
| Contract violation rate | Type, context, evidence, or authorization failures per relay | Lower |
| Counter-evidence yield | Distinct reproducible defects discovered per test budget | Higher, conditional on severity |
| False qualification rate | Invalid candidate admitted as qualified | Lower |
| Transfer success | Valid reuse across unseen environments or task families | Higher |
| Net structural value | Validated gain minus maintenance, coordination, and evaluation costs | Higher |
| Horizon expansion | Independently verified new representational distinctions or task classes | Higher, when valid |

## 3. Hypothesis Register

The register uses stable IDs (`H-SIF-01` onward). Each entry specifies its claim, design, measurement, and falsification pressure. These are hypotheses, **not findings**.

### H-SIF-01 — Structural localization improves capability selection

**Claim.** Given a heterogeneous capability inventory, contextual localization using task structure, capability signatures, and applicability envelopes yields better selection than semantic similarity alone.

**Experiment.** Construct tasks with deliberately confusable tools, context restrictions, and hidden applicability conditions. Compare embedding/LLM retrieval, a rule-based router, and an SIF-style two-phase localization pipeline. Hold inventory and inference budget constant.

**Primary metrics.** Applicability precision and correct routing@k; secondary: latency, cost, and unsafe invocation rate.

**Falsification pressure.** If the structural approach provides no reliable advantage over tuned baselines under matched budgets, the extra structural machinery is not justified for these task classes.

### H-SIF-02 — Metric differential representations support efficient localization

**Claim.** Metric Differential Trees (MDT) and CCC-plus-residual representations can improve retrieval efficiency or transfer on suitable hierarchical, difference-rich tasks.

**Experiment.** Benchmark hierarchical retrieval, anomaly localization, and compositional queries using flat vector search, graph retrieval, and MDT-based indexing; vary branching factor, update frequency, and noise.

**Primary metrics.** Recall at fixed latency, memory footprint, incremental update cost, and robustness to distribution shifts.

**Falsification pressure.** No favorable quality–cost frontier relative to well-tuned alternatives; degradation under realistic updates.

### H-SIF-03 — Two-phase search improves partial-target resolution

**Claim.** Separating broad candidate localization from expensive verification improves task success per compute unit when user targets are incomplete or ambiguous.

**Experiment.** Vary target completeness, candidate-set size, and verification expense. Compare one-shot exhaustive selection, standard retrieve-then-rerank, and structurally constrained two-phase search.

**Primary metrics.** Verified target resolution at fixed cost; error propagation from phase one; abstention calibration.

**Falsification pressure.** Candidate pruning repeatedly removes valid solutions or gains vanish against strong retrieve-then-rerank systems.

### H-SIF-04 — Multi-perspective per-node capability descriptions improve composition

**Claim.** Classifying capabilities by algorithm, application, signature, context, evidence, and governance produces more reliable compositions than a single taxonomy.

**Experiment.** Use the same capability set and planner with single-axis tags, free-text descriptions, and multi-perspective descriptors. Include semantic near-matches with incompatible context assumptions.

**Primary metrics.** Composition success, invalid dependency rate, description maintenance burden.

**Falsification pressure.** Added metadata increases complexity without measurable compatibility or reliability gains.

### H-SIF-05 — Dual maps outperform one-way capability lookup

**Claim.** Bidirectional Structural Intelligence Mapping (BSIM), linking a Problem-Solving Map to a Capability Map, improves both solution construction and identification of overlooked applications.

**Experiment.** Compare task-to-tool routing alone against bidirectional mapping on a preregistered set of tasks and a separate blinded panel assessing newly suggested application opportunities.

**Primary metrics.** Task success; independently verified novel-use precision; discovery cost.

**Falsification pressure.** Apparent new applications are trivial reformulations, unsupported claims, or too expensive to validate.

### H-SIF-06 — Structural precedents transfer better with explicit applicability boundaries

**Claim.** Registry entries that preserve context, applicability envelopes, failures, and counter-evidence transfer more reliably than success-only examples or unqualified reusable templates.

**Experiment.** Populate equal-sized registries with (A) successes only, (B) successes plus metadata, and (C) full precedent/evidence/counter-evidence records. Evaluate unseen contexts, including near-miss conditions.

**Primary metrics.** Correct transfer, false transfer, justified abstention, retrieval overhead.

**Falsification pressure.** Full records offer no improved discrimination or incur costs larger than avoided errors.

### H-SIF-07 — SIC checks reduce cross-node failures

**Claim.** Structural Intelligence Contracts that cover semantics, context, evidence, and policy reduce relay and composition failures relative to schema-only API contracts.

**Experiment.** Replay heterogeneous workflows with identical nodes under (A) syntactic schema checks, (B) semantic/context checks, and (C) full SIC gates.

**Primary metrics.** Undetected incompatibility, false rejection, latency, developer effort.

**Falsification pressure.** Semantic contract checks are unreliable, nonportable, or dominated by simpler validation approaches.

### H-SIF-08 — UNT-R enables portability without internal algorithm standardization

**Claim.** Standardizing names, types, and relay boundaries improves cross-runtime interoperability while preserving heterogeneous internal implementations.

**Experiment.** Port equivalent PIRP/PIRU capabilities across distinct runtimes and organizations using bespoke adapters versus common UNT-R profiles.

**Primary metrics.** Integration time, adapter count, semantic drift, runtime failure rate, maintenance cost.

**Falsification pressure.** The proposed abstraction fails to cover common real-world semantics or shifts complexity into fragile adapters.

### H-SIF-09 — Explicit control-plane separation reduces unauthorized actions

**Claim.** Separating scoring/decision, evidence/audit, and policy/authority lowers unauthorized execution without materially degrading authorized task completion.

**Experiment.** Use an isolated simulation with adversarial tasks that induce score–authority confusion. Compare fused orchestration against separated control planes with identical policy definitions.

**Primary metrics.** Unauthorized-action rate, false denial rate, audit completeness, task success.

**Falsification pressure.** Separation fails to reduce unauthorized actions or causes unacceptable operational friction.

### H-SIF-10 — Scoring forests outperform single scalar scoring on conflicting objectives

**Claim.** Explicit multi-perspective scoring forests improve robustness and explainability for decisions with competing constraints, relative to a single opaque aggregate score.

**Experiment.** Evaluate constrained planning and resource allocation with known Pareto fronts, adversarial metric shifts, and hidden disqualifying conditions.

**Primary metrics.** Constraint violations, Pareto regret, sensitivity, auditability, compute cost.

**Falsification pressure.** Scalar methods with adequate constraints match or exceed forest performance and transparency.

### H-SIF-11 — Structural folding preserves value when reversible at decision-critical boundaries

**Claim.** Evidence-aware folding of large workflows reduces computational and coordination costs without losing decision-critical information, when selective unfolding is available.

**Experiment.** Compare full-detail execution, lossy summaries, and fold/unfold with explicit provenance triggers across growing workflow depths.

**Primary metrics.** Cost, decision accuracy, missed exceptions, provenance recovery fidelity.

**Falsification pressure.** Folding conceals critical exceptions or recovery costs erase savings.

### H-SIF-12 — Residual taxonomy improves growth diagnosis

**Claim.** Categorizing failures by localization, representation, capability, composition, evidence, control, resource, environment, and perspective leads to more effective corrective interventions than generic error logs.

**Experiment.** Give blinded engineering teams or agents identical failure traces with generic labels versus structured residual diagnoses; randomize assignment.

**Primary metrics.** Time to correct root cause, recurrence, inappropriate intervention rate.

**Falsification pressure.** Categories are too ambiguous or fail to improve diagnosis under blinded evaluation.

### H-SIF-13 — MIAS detects more consequential structural defects per budget

**Claim.** Heterogeneous Builder–Challenger–Evaluator testing discovers more reproducible high-severity structural defects than self-review or homogeneous model debate.

**Experiment.** Seed independently verified defects in candidate workflows. Compare self-evaluation, homogeneous debate, heterogeneous MIAS, and formal-only checking under equal budgets.

**Primary metrics.** Severity-weighted defect recall, false positives, discovery cost, reproducibility.

**Falsification pressure.** Independent challenges are correlated, superficial, or inferior to conventional tests.

### H-SIF-14 — Evaluator challenge reduces metric gaming

**Claim.** Periodic independent evaluator challenge and held-out counter-evidence reduce Goodhart-style metric exploitation during iterative improvement.

**Experiment.** Optimize candidate agents repeatedly against fixed versus audited/rotated evaluators; reserve untouched external test suites and adversarial distribution shifts.

**Primary metrics.** Generalization gap, metric-gaming incidence, false qualification, evaluation overhead.

**Falsification pressure.** Evaluator challenge fails to improve held-out outcomes or creates uncontrolled evaluator drift.

### H-SIF-15 — Evidence-gated growth outperforms unconstrained accumulation

**Claim.** Requiring candidate structures to pass explicit validation and governance gates yields higher long-run net value than accepting every apparent improvement.

**Experiment.** Simulate repeated capability proposals with varying noise and distribution shift; compare unrestricted adoption, static review, and evidence-gated lifecycle management.

**Primary metrics.** Cumulative task utility, rollback frequency, safety violations, maintenance burden.

**Falsification pressure.** Gate costs consistently exceed benefits in the intended risk class; the hypothesis may hold only in high-consequence settings.

### H-SIF-16 — Collective structural learning yields transferable improvements

**Claim.** Exchanging portable, evidence-qualified structural precedents among independent BrainUnits improves cross-site performance beyond sharing raw outputs or model prompts alone.

**Experiment.** Use multiple simulated organizations with overlapping but nonidentical environments. Compare no sharing, raw-experience sharing, prompt sharing, and portable SIC/precedent sharing.

**Primary metrics.** Cross-site transfer success, adaptation cost, privacy leakage, negative transfer.

**Falsification pressure.** Shared structures fail to adapt, expose sensitive context, or amplify common-mode errors.

### H-SIF-17 — Macro-intelligence pieces can create measurable compositional advantage

**Claim.** Contracted higher-order intelligence pieces can solve selected multi-stage tasks more reliably or efficiently than flat orchestration, after accounting for integration overhead.

**Experiment.** Hold underlying components constant while varying hierarchy depth and macro-unit boundaries. Include exception handling and partial failure scenarios.

**Primary metrics.** End-to-end success, fault isolation, reuse rate, total coordination cost.

**Falsification pressure.** Gains disappear after equalizing engineering effort and computational budget, or hierarchy magnifies error propagation.

### H-SIF-18 — Precision-guided compute improves scaling efficiency

**Claim.** Allocating compute according to structural uncertainty, risk, and expected information gain produces better quality–cost tradeoffs than uniform or heuristic allocation.

**Experiment.** Compare fixed-budget uniform sampling, confidence heuristics, and structural allocation policies on tasks with varying difficulty and consequence.

**Primary metrics.** Quality at fixed compute, compute at fixed quality, worst-case safety, calibration.

**Falsification pressure.** Guidance overhead and miscalibration negate compute savings or worsen tail risk.

### H-SIF-19 — Structural perception expansion can be distinguished from performance gain

**Claim.** Some structural interventions produce verifiable new representational distinctions or causal hypotheses, not merely improved scores on previously defined tasks.

**Experiment.** Design environments with latent variables, previously unmodeled interactions, and genuinely novel task families. Require systems to propose new distinctions that predict held-out interventions; compare against expanded-context LLM and search baselines.

**Primary metrics.** Novel distinction validity, intervention prediction accuracy, explanatory parsimony, OOD transfer.

**Falsification pressure.** Claimed horizon growth collapses to restating known variables, larger retrieval coverage, or benchmark contamination.

### H-SIF-20 — Perspective-relative superiority is more informative than a single ASI label

**Claim.** Reporting superiority as a vector of task domain, metric, evidence, resources, time horizon, and governance constraints predicts deployment suitability better than a single aggregate intelligence ranking.

**Experiment.** Ask independent decision-makers to select systems for held-out deployment scenarios using aggregate rankings versus structured perspective profiles; evaluate choices against observed outcomes.

**Primary metrics.** Selection regret, constraint violation, confidence calibration, decision time.

**Falsification pressure.** Perspective profiles provide no added predictive value or become too complex for reliable use.

## 4. Cross-Hypothesis Experimental Programs

### Program A — Localization and composition benchmark

**Hypotheses:** H-SIF-01 through H-SIF-08. Build a versioned task/capability corpus with semantic distractors, changing contexts, heterogeneous APIs, and blinded transfer tests. Separate routing quality from downstream execution quality. A strong result requires not only improved success but also an acceptable quality–latency–integration frontier.

### Program B — Governance, scoring, and adversarial validation

**Hypotheses:** H-SIF-09 through H-SIF-11 and H-SIF-13 through H-SIF-15. Use sandbox-only workflows with known policy constraints, planted defects, metric-gaming opportunities, and audit trails. Score safety failures as first-class outcomes; no production-side adversarial experimentation without independent approval.

### Program C — Growth and collective learning

**Hypotheses:** H-SIF-12 and H-SIF-15 through H-SIF-17. Run longitudinal experiments over multiple proposal/validation/adoption cycles. Track version histories, negative transfer, maintenance debt, and whether claimed improvements persist after environmental change.

### Program D — Scaling and worldview frontiers

**Hypotheses:** H-SIF-18 through H-SIF-20. Vary compute allocation, structural depth, and representation while holding baseline capabilities constant. Require independent intervention-based evidence for claims of perception-horizon expansion. Avoid inferring generalized superintelligence from narrow-domain success.

## 5. Preregistration Template

Copy this template for each study before examining its final test outcomes.

```yaml
study_id: SIF-STUDY-XXXX
hypothesis_ids: [H-SIF-01]
status: proposed
claim_scope: ""
task_population: ""
unit_of_randomization: ""
primary_outcome: ""
secondary_outcomes: []
baselines: []
ablations: []
compute_budget: ""
human_review_budget: ""
sample_size_rationale: ""
train_validation_test_separation: ""
primary_analysis: ""
uncertainty_method: ""
minimum_practically_important_effect: ""
negative_result_criterion: ""
stopping_rule: ""
exclusion_rules: []
safety_and_authorization_boundary: "sandbox-only unless approved"
artifacts_and_provenance: []
independent_evaluator: ""
registration_timestamp: ""
```

## 6. Evidence Levels and Claim Language

| Level | Evidence state | Permissible description |
|---|---|---|
| E0 | Conceptual proposal only | “We propose” / “We hypothesize” |
| E1 | Reproducible toy demonstration | “Demonstrated in a limited synthetic setting” |
| E2 | Controlled comparative benchmark | “Outperformed named baselines under stated conditions” |
| E3 | Independent replication and OOD evaluation | “Replicated across stated settings” |
| E4 | Monitored field evaluation with governance | “Validated for specified deployment conditions” |

Evidence levels attach to **specific claims and contexts**, not to SIF as a whole. A successful experiment on one mechanism does not validate the full architecture. Negative and inconclusive findings should remain accessible through the Structural Precedent Registry with their methods and boundary conditions.

## 7. Prioritization and Dependencies

A practical first wave should prioritize experiments that can disconfirm expensive architectural commitments early:

| Priority | Hypotheses | Reason |
|---|---|---|
| P0 | 01, 06, 07, 09, 13 | Tests core routing, precedent applicability, contract safety, authorization, and adversarial value |
| P1 | 02, 03, 05, 08, 12, 14 | Tests structural alternatives and their operational costs |
| P2 | 04, 10, 11, 15, 16, 17, 18 | Tests composition, growth, and scaling after foundational interfaces stabilize |
| Exploratory | 19, 20 | Requires unusually careful definitions and independent validation |

Dependencies are methodological, not strict implementation prerequisites. For example, MIAS can be evaluated using mock SIC records before a complete interoperable runtime exists.

## 8. Failure Modes of the Research Program

1. **Benchmark leakage:** The registry, prompts, or models have seen final test tasks.
2. **Baseline neglect:** The proposed architecture is compared only against weak alternatives.
3. **Budget asymmetry:** One system receives more inference, search, or human intervention.
4. **Taxonomy overfitting:** Residual labels are adjusted after observing the desired result.
5. **Evaluator circularity:** The system under study effectively grades its own outputs.
6. **Selection bias:** Only successful precedents, tasks, or runs are published.
7. **Metric laundering:** Complex dashboards hide policy violations or severe tail failures.
8. **Architecture confounding:** Simultaneous changes prevent causal attribution.
9. **Unbounded growth cost:** Registry and evaluation overhead is excluded from total cost.
10. **Worldview overclaim:** New terminology is mistaken for a validated new perception capability.

Mitigate these through frozen protocols, independent audits, matched-budget ablations, explicit negative-result reporting, and full lifecycle cost accounting.

## 9. Mapping to SIF Documents

| Research area | Primary manuscripts | Candidate specifications |
|---|---|---|
| Foundations and four domains | SIF-001–SIF-007 | SPEC-001 |
| Dual maps, precedent, interoperability | SIF-008–SIF-011 | SPEC-001, SPEC-002, SPEC-003 |
| Sandbox, counter-evidence, growth | SIF-012–SIF-014 | SPEC-003, SPEC-004 |
| Perception, macro-structures, scaling, ASI perspectives | SIF-015–SIF-018 | Future experimental extensions |

Related research navigation: [`OPEN-QUESTIONS.md`](OPEN-QUESTIONS.md) and forthcoming [`VALIDATION-ROADMAP.md`](VALIDATION-ROADMAP.md). The present file defines **what to test**; the roadmap should define **when, with which artifacts, and under which gates**.

## 10. Closing Research Position

The value of an open structural intelligence framework is not established by the breadth of its conceptual inventory. It must be earned through reproducible evidence that localization, composition, governance, structural memory, and growth mechanisms produce benefits under clearly defined conditions—and through equally explicit records of where they fail.

**A successful SIF research program should be capable of proving some of its own architectural ideas unnecessary, ineffective, or unsafe.** That is not a weakness of an open framework; it is a requirement for credible structural evolution.

---

**Citation context:** Structural Intelligence Framework (SIF), research hypothesis register, Sizhe Tan & GPT-Obot, v1.0.0. This document is a research agenda, not a peer-reviewed empirical validation.
