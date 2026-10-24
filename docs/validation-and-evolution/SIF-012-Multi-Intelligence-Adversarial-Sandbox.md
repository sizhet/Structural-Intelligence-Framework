# SIF-012 — Multi-Intelligence Adversarial Sandbox

**Subtitle:** Evidence-Governed Structural Discovery, Falsification, and Controlled Promotion in Open Intelligence Systems  
**Project:** Structural Intelligence Framework (SIF)  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0 — Research Architecture  
**Status:** Conceptual proposal; interfaces and experiments require implementation and validation  
**License:** Apache-2.0

---

## Abstract

Open structural intelligence cannot grow safely or scientifically through generation alone. New intelligence pieces, compositions, scoring systems, relay paths, and world-model assumptions must be tested against competing explanations, adversarial cases, boundary conditions, and independently reproducible evidence. This paper proposes the **Multi-Intelligence Adversarial Sandbox (MIAS)** as the experimental subsystem of the Structural Intelligence Framework (SIF). MIAS organizes heterogeneous builders, challengers, evaluators, simulation environments, formal checkers, and governance authorities around versioned structural hypotheses. It turns failures and unexplained residuals into explicit research objects without confusing novelty with validity or experimental success with deployment authorization. The proposed lifecycle spans structural candidate generation, threat and applicability modeling, controlled trials, counter-evidence discovery, evaluator challenge, independent replication, and staged promotion. We distinguish what MIAS can automate from what remains epistemically uncertain, and specify testable hypotheses and an incremental validation program.

**Keywords:** structural intelligence; adversarial evaluation; structural counter-evidence; heterogeneous AI; sandbox; open-ended growth; evaluator governance; Anti-Goodhart; capability contracts; structural precedent

---

## 1. Introduction: Discovery Needs an Opponent

A system that can propose increasingly complex intelligence structures but cannot challenge them may accumulate impressive demonstrations without accumulating reliable knowledge. This risk grows when structural intelligence expands beyond a single model to include LLMs, rule systems, optimization solvers, learned policies, simulation engines, scoring forests, calling graphs, and portable intelligence units.

SIF distinguishes four functional domains:

1. **Localization and intelligence addressing:** determine where relevant information, capabilities, and structural precedents may be found.
2. **Per-node intelligence:** execute or reason with heterogeneous computational capabilities.
3. **Universal control planes and scoring/folding:** evaluate alternatives, manage authority, and regulate action.
4. **Residual-based structural growth:** diagnose unresolved gaps and propose revisions or new structures.

MIAS is a cross-domain validation facility, not a fifth domain that replaces the other four. It is the place where their claims can be subjected to structured contestation.

The central thesis is:

> **Structural intelligence grows credibly only when its proposed improvements remain open to independent counter-evidence, boundary testing, and governed revision.**

A sandbox is necessary but not sufficient. Isolation reduces operational risk; it does not prove the correctness, completeness, or generalizability of an intelligence structure.

---

![Fig-001-SIF-Grand-Architecture.png](../../figures/Fig-001-SIF-Grand-Architecture.png)

---

## 2. The Unit of Experiment: A Structural Claim

MIAS evaluates a **structural claim**, rather than only an answer or a benchmark score. A claim identifies what a candidate structure is expected to do, under which conditions, relative to what baseline, and with what consequences if wrong.

A minimal claim can be represented as:

\[
H = (S, C, T, B, M, E, R)
\]

where:

- \(S\): proposed structure, composition, or structural modification;
- \(C\): context and applicability conditions;
- \(T\): task family and success criteria;
- \(B\): baseline and alternative explanations;
- \(M\): measurement protocol;
- \(E\): existing supporting and opposing evidence;
- \(R\): risks, resource limits, and authorization constraints.

This is a proposed research notation, not a standardized SIF data model. A practical implementation should map these fields to the Structural Intelligence Contract (SIC), Structural Precedent Registry (SPR), and evidence records.

### 2.1 Examples of claims

- A Metric Differential Tree improves capability localization over a flat retrieval baseline at a specified recall and compute budget.
- A Two-Phase Search pipeline reduces expensive specialist calls while maintaining acceptable failure rates.
- A PIRU relay preserves required context across a heterogeneous solver boundary.
- A new scoring forest improves decisions without concealing minority risk or violating policy constraints.
- A world-model revision improves predictions under distribution shift rather than merely fitting historical examples.

Each claim requires an explicit **failure condition**. A claim that cannot be contradicted by any conceivable observation is not ready for MIAS evaluation.

## 3. Architectural Roles

MIAS defines **roles**, not mandatory separate AI models. A role may be implemented by a human, an LLM, a deterministic program, a simulation engine, or a combination. Role separation is essential where independence is needed; different prompts to the same model are not automatically independent evaluators.

| Role | Primary responsibility | Typical outputs |
| --- | --- | --- |
| **Builder** | Propose or revise a structural candidate | Candidate SIC, rationale, expected gains |
| **Challenger** | Search for counterexamples, boundary failures, and competing explanations | Attack cases, structural counter-evidence |
| **Independent Evaluator** | Apply preregistered criteria and compare baselines | Metrics, confidence intervals, decision record |
| **World / Simulation Engine** | Generate controlled states, interventions, and trajectories | Scenarios, traces, counterfactual outcomes |
| **Formal / Deterministic Checker** | Check invariants, types, constraints, or proofs where applicable | Pass/fail reports, witness traces |
| **Evidence Curator** | Preserve provenance, splits, artifacts, and reproducibility | Evidence records and audit lineage |
| **Governance Authority** | Determine allowable experiments and deployment scope | Permissions, constraints, promotion decisions |
| **Registry Steward** | Version and relate structural precedents | Candidate, validated, deprecated, or retired records |

No role should be treated as universally infallible. Independent evaluation may require diverse methodologies, blinded trials, third-party replication, or human adjudication for contested cases.

### 3.1 Role conflicts

A builder evaluating its own proposal introduces selection and confirmation risks. A challenger rewarded only for producing failures may manufacture irrelevant attacks. An evaluator optimized on a public benchmark can become a target for gaming. MIAS therefore records role identity, shared dependencies, incentives, access to held-out tests, and potential conflicts.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 4. The MIAS Experimental Boundary

The architecture separates three operational environments:

**Exploratory Sandbox.** Candidates are generated and tested using synthetic or appropriately de-identified data, constrained tools, simulated side effects, and explicit resource budgets. External writes and sensitive access are disabled by default.

**Validated Shadow Runtime.** Promising candidates may process representative workloads without exercising production authority. Shadow results are compared with existing workflows while preserving data handling and access controls.

**Authorized Production Runtime.** A separately governed decision may permit limited deployment, subject to rollback, monitoring, and scoped authority. A passing sandbox score does not automatically trigger promotion.

A practical isolation design should address network egress, filesystem permissions, secrets, tool capabilities, model-supplied code, resource quotas, logging, prompt-injection surfaces, and artifact provenance. Where testing involves real-world systems, additional domain-specific safeguards may be required.

**Design invariant:** *Evaluation does not imply authorization.*

## 5. A Candidate-to-Evidence Lifecycle

MIAS organizes structural research as a traceable sequence.

### Stage 0 — Residual intake

An unresolved residual may arise from a failed task, low-confidence localization, an incompatible relay contract, unexplained scoring behavior, a novel application demand, or a challenge to an existing worldview. The intake record states what is observed and what remains unknown; it does not assume a new structure is required.

### Stage 1 — Structural diagnosis and precedent search

Search the Problem-Solving Map (PSM), Capability Map (SCM), and SPR for relevant prior solutions, failures, and applicable constraints. Distinguish among missing capability, missing representation, missing evidence, incorrect routing, insufficient resources, and an unsuitable perspective.

### Stage 2 — Candidate construction

The Builder proposes one or more candidates, including a null hypothesis, an existing-structure adaptation, and, when justified, a genuinely new structure. Candidate records identify dependencies, signatures, context assumptions, resource requirements, and predicted improvements.

### Stage 3 — Test design and preregistration

Define primary metrics, safety constraints, baseline comparisons, task splits, stopping rules, statistical methods, and a budget for adversarial exploration. Reserve genuinely held-out cases where feasible. Document which measures are proxies and which outcomes matter operationally.

### Stage 4 — Adversarial challenge

Challengers probe the candidate with distribution shifts, adversarial inputs, composition failures, missing context, incorrect types, resource stress, contradictory evidence, and alternate causal explanations. Challenge both the claimed capability and its applicability boundary.

### Stage 5 — Independent evaluation

Evaluators compare candidates against baselines using repeatable protocols. Formal checks can establish specified invariants; empirical trials estimate performance within sampled conditions. Neither establishes universal validity.

### Stage 6 — Evaluator challenge

Investigate whether the measurement itself can be gamed, whether benchmark selection favored the candidate, whether subgroup harms are hidden by aggregates, and whether evaluators share correlated blind spots.

### Stage 7 — Evidence synthesis

Store supportive results, counter-evidence, uncertainty, costs, reproducibility status, and unresolved disputes. The evidence record must not collapse into a single opaque score.

### Stage 8 — Governed disposition

Possible outcomes include **reject**, **revise**, **retain as exploratory**, **validate for specified contexts**, **shadow-test**, **authorize limited deployment**, or **retire/supersede**. Each outcome has an explicit decision owner and review trigger.

### Stage 9 — Monitoring and reopening

Real-world drift, new counter-evidence, changed policy, or new alternatives can reopen a precedent. A validated structural claim is always versioned and bounded.

---

![Fig-005-Structural-Precedent-Intelligence.png](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 6. Structural Counter-Evidence: Beyond Wrong Answers

Ordinary error checking asks whether an output is correct. **Structural Counter-Evidence (SCE)** asks whether the architecture, applicability claim, composition, or evaluation premise is wrong or incomplete.

| Counter-evidence class | Question | Example |
| --- | --- | --- |
| **Applicability** | Does the precedent work outside its narrow source context? | Solver fails under a changed demand distribution |
| **Representation** | Did the structure omit a decisive variable? | Differential tree hides a rare safety-critical branch |
| **Localization** | Was the relevant capability reachable? | Retrieval routes to a plausible but unsuitable unit |
| **Composition** | Are individual units sound but their relay unsound? | Unit conversion or context lost at handoff |
| **Causal** | Is improvement due to the proposed mechanism? | Gains disappear under ablation |
| **Evaluator** | Is the score aligned with the actual objective? | Proxy optimization worsens downstream outcomes |
| **Governance** | Is an effective action nevertheless unauthorized? | Candidate invokes an out-of-scope tool |
| **Resource** | Is improvement robust under realistic budgets? | Latency or energy cost dominates benefit |
| **Perspective** | Are the problem categories themselves incomplete? | Novel event cannot be expressed in current task schema |

Counter-evidence should include a minimal reproducing case when possible, affected claim versions, confidence or uncertainty, and the conditions under which the failure appears.

## 7. Heterogeneous Intelligence as an Experimental Advantage

A multi-intelligence sandbox is valuable because different computational paradigms fail differently. An LLM may generate hypotheses and test cases; a rule engine can enforce explicit constraints; a mathematical optimizer can provide bounded solutions; a simulation engine can probe trajectories; a theorem prover can verify formal properties within its assumptions; and humans can challenge framing, social implications, and unmodeled objectives.

Diversity is useful only when it creates **meaningful epistemic independence**. Multiple agents using the same model, same retrieved sources, and same reward proxy may merely reproduce one blind spot at scale.

A candidate architecture should therefore document evaluator diversity across model families, data sources, methods, objectives, and failure modes. Where independence is weak, MIAS must say so.

## 8. Experimental Protocol Families

### 8.1 A/B comparisons

Compare a candidate against a credible baseline on matched task distributions. Report both central performance and tail-risk behavior. Randomize allocation where appropriate and prevent leakage between tuning and evaluation.

### 8.2 Ablation and mechanism tests

Remove one proposed structural feature at a time. If performance remains unchanged, the feature's claimed causal role is unsupported, even if the full system performs well.

### 8.3 Metamorphic and invariant testing

Check whether outputs respect transformations that should preserve meaning, policy constraints, or type invariants. These tests are useful when exact answers are unavailable, but their assumed invariants must themselves be justified.

### 8.4 Stress and distribution-shift testing

Vary scale, noise, missing information, task depth, novelty, context length, adversarial behavior, and compute limits. Report failure surfaces rather than only an average benchmark score.

### 8.5 Relay and contract conformance

Verify input/output schemas, semantic assumptions, identity resolution, authorization scopes, cancellation behavior, evidence lineage, and partial-failure handling across PIRP/PIRU boundaries.

### 8.6 World-model and trajectory evaluation

When a candidate asserts predictive or planning capability, test temporal consistency, intervention sensitivity, state-estimation error, uncertainty calibration, and out-of-distribution behavior. Simulation results require explicit discussion of simulation-to-reality gaps.

### 8.7 Open-ended discovery assessment

Measure not just how many candidates are produced, but how many survive independent testing, how many introduce genuinely new useful structure, how much they improve downstream capability, and whether discoveries remain reproducible over time.

## 9. Evaluator Governance and Anti-Goodhart Controls

Any stable score can become a target. MIAS therefore distinguishes **measurement**, **decision support**, and **authority**.

A proposed evaluation policy should include:

- multiple non-redundant metrics, including constraints and tail outcomes;
- protected holdout sets and controlled benchmark access;
- independent or blinded evaluation for consequential claims;
- challenger access to alternative hypotheses and negative cases;
- preregistered promotion thresholds, with documented exceptions;
- explicit treatment of uncertainty and missing evidence;
- bounded recursive challenges to evaluators;
- separate authority to approve runtime action.

Recursive evaluator challenge must be **budgeted and risk-tiered**. Infinite meta-evaluation is neither computable nor desirable. The stopping condition should state which risks remain untested, not claim all evaluator flaws have been eliminated.

### 9.1 A bounded evidence decision

For candidate \(s\), a conceptual disposition function is:

\[
D(s) = \operatorname{GovernedReview}(Q_s, F_s, U_s, K_s, A_s)
\]

where \(Q_s\) denotes measured quality, \(F_s\) observed failure evidence, \(U_s\) uncertainty, \(K_s\) costs, and \(A_s\) authorization constraints. This is a bookkeeping abstraction, **not** an automatic weighted score or deployment algorithm. In particular, authorization constraints cannot be overridden by a favorable aggregate metric.

## 10. Integration with the SIF Architecture

MIAS operates through the same structural interfaces as the rest of SIF.

**Problem–Capability Dual Maps.** The PSM supplies task demands and failure cases; the SCM supplies candidate capabilities and dependencies. Bidirectional Structural Intelligence Mapping (BSIM) generates both matches and residuals.

**Structural Precedent Registry.** The SPR stores candidate claims, validation outcomes, negative precedents, and context-specific applicability boundaries. An invalidated precedent remains valuable as evidence of what not to assume.

**Universal Naming, Typing, and Relay (UNT-R).** Stable identities, semantic types, and relay protocols permit heterogeneous experiment participants to exchange structured inputs and outputs without forcing common internal algorithms.

**Structural Intelligence Contract (SIC).** Contracts expose capability signatures, assumptions, evidence references, resource limits, permissions, and lifecycle status. Experimental permissions are narrower than production permissions.

**Portable Intelligence Runtime Pieces and Units (PIRP/PIRU).** Exploratory pieces may be investigated before formalization; validated units can acquire stronger interface and conformance guarantees. A PIRP-to-PIRU transition is a validation milestone, not an automatic upgrade.

**Control Planes and Scoring Forests.** Evaluation engines can supply scores, but policy and authority planes retain control over whether, where, and how a candidate may act.

**Residual-Based Growth.** Failure records feed new diagnosis and discovery cycles. MIAS tests growth claims; it does not guarantee that every residual is solvable or that every novel structure is useful.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 11. Illustrative Case: A Supply-Chain Planning Relay

Consider a planning system that composes demand forecasting, inventory optimization, supplier-risk analysis, and a natural-language explanation unit.

**Observed residual:** The system meets average cost targets but repeatedly fails when a low-probability supplier disruption coincides with an abrupt demand change.

**Builder hypothesis:** Introduce a scenario-generation PIRP and a risk-aware scoring forest ahead of the optimizer. The proposed improvement is lower tail-loss at a bounded compute cost.

**Challenger tests:** Construct correlated disruptions, missing supplier data, adversarially optimistic forecasts, and situations in which the new risk scoring suppresses otherwise feasible plans.

**Independent evaluation:** Compare existing and revised pipelines on preregistered historical and simulated scenarios; include tail loss, service level, runtime, constraint violations, and calibration. Use held-out scenarios and ablations of the scenario generator and scoring forest.

**Structural counter-evidence:** The new system may improve simulated tail loss while relying on an unrealistic disruption model. That finding weakens its real-world claim even if sandbox metrics look favorable.

**Governed outcome:** If evidence is promising but incomplete, authorize only a shadow trial. Record the unresolved simulation-to-reality gap in the SPR and revisit the claim after new evidence.

This is a **conceptual example**, not a reported empirical result.

## 12. Evidence Artifacts and Traceability

A minimally useful MIAS experiment should preserve:

| Artifact | Required purpose |
| --- | --- |
| Candidate identifier and version | Make the structural object unambiguous |
| SIC / contract reference | State inputs, outputs, assumptions, and permissions |
| Hypothesis and baseline | Define the comparison being tested |
| Evaluation plan | Fix metrics, splits, thresholds, and stopping rules |
| Test and environment provenance | Support reproducibility and leakage analysis |
| Challenger record | Preserve attacks and negative findings |
| Evaluator and conflict record | Identify dependencies and independence limits |
| Result distribution | Avoid hiding failures in a single average |
| Resource and cost record | Capture compute, latency, and operational overhead |
| Governance decision | Separate evidence from permission |
| Reopen and retirement triggers | Permit revision when conditions change |

A candidate schema and lifecycle are developed further in `../../specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md` (planned companion specification). No claim of existing conformance is implied.

## 13. Threat Model and Failure Modes

MIAS itself introduces risks:

1. **Evaluator collusion or correlation:** multiple nominally independent agents share hidden biases.
2. **Benchmark contamination:** candidate builders obtain or infer protected evaluation cases.
3. **Reward hacking:** candidates optimize proxy scores instead of intended outcomes.
4. **Attack irrelevance:** challengers produce failures outside the legitimate applicability boundary.
5. **Sandbox escape or excessive tool privilege:** experimental code or agents access unauthorized resources.
6. **Evidence laundering:** weak results are promoted through summaries that omit negative cases.
7. **Overfitting to the challenger:** iterative defense hardens only against known attacks.
8. **Simulation mismatch:** convincing synthetic results do not transfer to deployment.
9. **Unbounded evaluation cost:** recursive challenges consume resources without improving decisions.
10. **Authority confusion:** an evaluation verdict is treated as a production deployment permit.
11. **Structural complexity inflation:** candidate compositions become harder to inspect than the failures they address.
12. **Novelty bias:** new architectures are preferred over simpler repairs to localization, data, or contracts.

Mitigations include explicit scope definitions, independent holdouts, role separation, sandbox isolation, resource budgets, signed evidence lineage, staged promotion, and human review at appropriate risk tiers. No mitigation is absolute.

## 14. Testable Research Hypotheses

The following hypotheses are proposals, not established findings.

**H1 — Structural challenge yield.** MIAS detects more materially relevant architecture-level failures than output-only testing under comparable evaluation budgets.

**H2 — Heterogeneous evaluator value.** Methodologically diverse challengers identify more non-overlapping failure classes than same-model prompt ensembles, controlling for cost.

**H3 — Precedent-guided efficiency.** SPR-assisted test design reduces repeated investigation of previously characterized failure modes without reducing detection of new failures.

**H4 — Contract conformance.** SIC/UNT-R boundary tests reduce relay-related production defects relative to schema-only integration tests.

**H5 — Anti-Goodhart robustness.** Protected holdouts, multi-objective measures, and evaluator challenges reduce proxy gaming compared with single public metrics.

**H6 — Growth quality.** Residual-driven candidate generation yields a higher proportion of independently validated improvements than unguided candidate generation at matched compute budgets.

**H7 — Staged promotion.** Shadow testing and scoped deployment detect transfer failures that sandbox-only promotion would miss.

**H8 — Bounded meta-evaluation.** Risk-tiered evaluator challenges provide better marginal defect detection per unit cost than uniform recursive challenge depth.

**H9 — Worldview expansion.** Some validated structural changes enable reliable detection or representation of problem classes absent from the original PSM; this requires operational definitions of novelty and independent confirmation.

## 15. Incremental Validation Roadmap

**Phase A — Protocol baseline.** Implement evidence records and reproducible A/B, ablation, and adversarial test harnesses for a narrow task family. Compare against standard output-only evaluation.

**Phase B — Heterogeneous challengers.** Introduce distinct LLM, rule-based, and formal or simulation evaluators. Measure unique failure discovery, false-positive rates, and cost.

**Phase C — Registry and contract integration.** Link tests to SIC, UNT-R, PSM/SCM, and SPR records. Evaluate precedent reuse and relay conformance.

**Phase D — Controlled growth.** Allow candidate structural modifications within bounded search spaces. Test whether residual-guided generation improves validated gains over baselines.

**Phase E — Shadow and limited runtime.** For appropriately low-risk domains, evaluate drift, rollback, authorization boundaries, and simulation-to-reality transfer.

Each phase should publish negative findings, protocol changes, and external validity limits. Progression depends on evidence, not on a fixed calendar.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 16. Open Research Questions

- How should MIAS quantify meaningful independence among evaluators with partially shared training data and tools?
- Which structural failure categories admit reliable automated or formal verification, and which require domain experts?
- How can challenger incentives reward relevant falsification without encouraging fabricated or trivial counterexamples?
- What is the best evidence representation for comparing incompatible task metrics across different intelligence domains?
- How should SIF decide whether a residual calls for new intelligence, better localization, a repaired contract, or a revised problem formulation?
- Can evidence provenance remain trustworthy across distributed intelligence relays and external registries?
- How can world-model or worldview revisions be tested without circularly assuming the original worldview is complete?
- What promotion criteria are appropriate when failure consequences are asymmetric or difficult to estimate?
- How can structural novelty be measured without rewarding complexity for its own sake?
- How should governance handle disputed evidence and the retirement of widely reused precedents?

## 17. Relationship to Companion SIF Documents

This paper builds on the SIF foundation and functional-domain manuscripts:

- `../foundations/SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md`
- `../foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md`
- `../foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md`
- `../functional-domains/SIF-007-Residual-Based-Structural-Growth.md`
- `../interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md`
- `../interoperability/SIF-009-Structural-Precedent-Registry.md`
- `../interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md`
- `../interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md`

It prepares the ground for:

- `SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md`
- `SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md`
- `../../specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md`

The paper also connects conceptually to the broader SIF research on Structural Recursive Self-Improvement, Two-Way CCC, policy control planes, and portable intelligence. These are research relationships, not claims that their implementations have been integrated.

## 18. Conclusion

The Multi-Intelligence Adversarial Sandbox is proposed as SIF's evidence-producing laboratory for structural change. Its purpose is not to make a single evaluator all-knowing or to turn every failed test into a new intelligence unit. It is to expose structural claims to relevant opposition, retain both positive and negative evidence, and make the boundary between experimentation and authorized action explicit.

**An open intelligence architecture needs an equally open capacity to discover why its own structures may be wrong.** MIAS operationalizes that principle through heterogeneous challenge, bounded evaluator governance, reproducible evidence, and reversible growth decisions. Whether this approach yields better intelligence must be established through the comparative experiments outlined here.

---

**Citation:** Tan, Sizhe, and GPT-Obot. *SIF-012: Multi-Intelligence Adversarial Sandbox*. Structural Intelligence Framework, version 1.0.0, 2026. Research architecture manuscript.
