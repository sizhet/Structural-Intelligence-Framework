# SIF-013 — Structural Counter-Evidence and Evaluator Governance

**Structural Intelligence Framework (SIF)**  
**Series:** Validation and Evolution · Paper 013  
**Version:** 1.0.0 · Research architecture and testable proposals  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0

> **Central proposition:** An intelligence system cannot responsibly grow by optimizing only what its current evaluator rewards. It must also preserve the means to challenge its structural assumptions, its evidence, and the evaluator itself.

## Abstract

Open structural intelligence depends on the discovery, adaptation, composition, and retirement of heterogeneous intelligence structures. This creates a distinctive validation problem: a candidate may produce an apparently correct answer while relying on an invalid decomposition, an inapplicable precedent, an unstable relay, or a scoring mechanism that rewards a proxy rather than the intended objective. Conventional outcome tests remain necessary, but they are not sufficient for evaluating reusable and evolving intelligence architectures.

This paper proposes **Structural Counter-Evidence (SCE)** as a first-class research object and **Evaluator Governance** as a distinct control function in the Structural Intelligence Framework (SIF). SCE records falsifying observations and boundary violations against explicit structural claims. Evaluator governance examines who defines success, which evidence counts, how scoring can be manipulated, when evaluators must be challenged, and who may authorize changes. We present a taxonomy of structural counter-evidence, a claim–evidence–challenge protocol, bounded recursive evaluator challenge, independent validation patterns, anti-Goodhart controls, registry and contract integration, and a staged empirical research program. The proposal is architectural, not a claim that complete automated falsification or safe recursive self-improvement has been achieved.

**Keywords:** Structural Intelligence Framework; structural counter-evidence; evaluator governance; Goodhart's law; adversarial validation; structural precedent; policy control plane; recursive self-improvement; evidence provenance.

---

## 1. The Evaluation Problem in Open Structural Intelligence

SIF treats intelligence as an evolving collection of capabilities, localization structures, control mechanisms, and growth processes. Its four functional domains are:

1. **Localization and Intelligence Addressing:** identify relevant problems, structures, precedents, and execution paths.
2. **Per-Node Intelligence:** invoke heterogeneous reasoning and computational capabilities.
3. **Universal Control Planes and Scoring/Folding:** score alternatives, manage evidence, and govern permitted actions.
4. **Residual-Based Structural Growth:** discover and validate improved or new structures when existing ones prove insufficient.

A candidate structure may improve a benchmark while degrading reliability outside the benchmark, or may appear effective only because its evaluator shares the same mistaken assumptions. Thus, an evaluation process must address at least three questions:

- **Outcome:** Did the system produce an acceptable result in the tested setting?
- **Structure:** Are the representation, decomposition, composition, and applicability claims supported?
- **Governance:** Was the evaluation sufficiently independent, and is the proposed action authorized?

These questions should not be collapsed into one numerical score.

### 1.1 The failure of outcome-only evaluation

Consider a planner that succeeds on a supply-chain benchmark by exploiting a fixed demand pattern. The reported outcome may be favorable, yet the planner may fail under a distribution shift, silently discard a safety constraint, or depend on an unrecorded upstream assumption. The score describes a tested outcome; it does not establish general applicability.

### 1.2 The failure of evaluator-only trust

An evaluator may be biased by its training data, incomplete simulation, inadequate adversarial coverage, or a metric that is easy to game. Even a nominally independent evaluator may share data, tools, or assumptions with the builder. Independence is therefore a property to investigate, not a label to accept.

## 2. Structural Claims as the Unit of Challenge

A **Structural Claim** is an explicit, bounded assertion about how and where an intelligence structure works.

A candidate claim may be represented conceptually as:

$$
C = (S, P, K, I, O, A, E, G, V)
$$

where:

- \(S\): identified structure and version;
- \(P\): problem class and perspective;
- \(K\): context and applicability conditions;
- \(I, O\): input and output signatures;
- \(A\): asserted behavior, mechanism, or performance;
- \(E\): supporting evidence and known limitations;
- \(G\): policy, authority, and resource constraints;
- \(V\): validation protocol and evaluator version.

A structural claim must be falsifiable at a stated scope. Broad statements such as “this planner is intelligent” or “this evaluator is reliable” should be decomposed into narrower propositions with observable failure criteria.

### 2.1 Five distinctions

**Claim versus implementation:** one implementation can support multiple claims, and a claim may survive an implementation replacement.  
**Claim versus score:** a score is an observation under a protocol, not the claim itself.  
**Claim versus evidence:** evidence supports or contests a claim; it does not define it retroactively.  
**Claim versus authority:** verified capability does not grant permission to act.  
**Claim versus precedent:** a precedent is a contextualized application of a claim, with outcomes and counter-evidence attached.

## 3. Structural Counter-Evidence: Definition and Taxonomy

**Structural Counter-Evidence (SCE)** is a traceable observation, test result, argument, or independently reproduced failure that weakens, qualifies, or falsifies a specified structural claim. An SCE record must identify the challenged claim and the conditions under which the challenge applies.

Not every disagreement is valid counter-evidence. A challenge must carry provenance, test conditions, and an explicit relevance argument. Conversely, an unresolved challenge must not be silently discarded merely because it is inconvenient.

| SCE class | Challenged assumption | Illustrative failure |
|---|---|---|
| Representation | Relevant distinctions are preserved | A folded state omits a critical constraint |
| Localization | The right structure or precedent was selected | Semantic similarity masks incompatible operating conditions |
| Applicability | A precedent transfers to the new context | A routing rule fails under a new demand regime |
| Composition | Component contracts compose safely | Individually valid nodes violate an end-to-end invariant |
| Causality / World Model | Modeled mechanisms match the environment | Simulation excludes feedback effects |
| Temporal / Distributional | Performance persists over time or shift | Accuracy collapses after a policy change |
| Evidence / Provenance | Observations are authentic and relevant | Training leakage contaminates the benchmark |
| Evaluator | The test measures the intended objective | A proxy score rewards unsafe shortcuts |
| Governance / Authority | Actions respect policy boundaries | An unapproved candidate executes in production |
| Resource / Scaling | Benefits survive realistic cost constraints | Validation costs exceed the claimed savings |
| Perspective | The framing captures the important problem | A newly relevant stakeholder objective is omitted |

A single observation may challenge multiple classes. The registry should retain the primary challenged claim and any linked secondary claims, rather than forcing artificial exclusivity.

### 3.1 Severity is not certainty

Severity measures the consequence if the challenge is valid. Confidence measures how well the challenge is supported. A potentially catastrophic but low-confidence finding can justify containment and further testing without being mislabeled a confirmed failure.

### 3.2 Negative results are reusable assets

Failed transfer, failed composition, and invalid evaluator assumptions are valuable structural precedents. Preserving them helps avoid repeating expensive mistakes and improves future localization.

---

![Fig-005-Structural-Precedent-Intelligence.png](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 4. Claim–Evidence–Challenge Protocol

We propose a traceable protocol for every consequential structural growth candidate.

**Step 1 — Register the claim.** Record the candidate's version, context, intended benefit, assumptions, measurable acceptance criteria, and disqualifying conditions before testing.

**Step 2 — Freeze the initial evaluation plan.** Record datasets, scenarios, metrics, baseline, compute budget, evaluator identity, and holdout rules. Subsequent changes require versioned justification.

**Step 3 — Collect positive evidence.** Run baseline comparisons, reproducibility tests, and targeted capability evaluations.

**Step 4 — Generate counter-evidence.** Challenge assumptions with boundary tests, adversarial cases, perturbations, ablations, competing decompositions, and independent implementations.

**Step 5 — Adjudicate evidence.** Distinguish confirmed falsification, supported limitation, unresolved challenge, and invalid challenge. Preserve minority findings with provenance.

**Step 6 — Decide the disposition.** Candidate outcomes include reject, revise, restrict applicability, approve for shadow evaluation, or request an explicitly authorized deployment review.

**Step 7 — Monitor after disposition.** Record drift, newly observed counter-evidence, contract violations, and reevaluation triggers.

### 4.1 Suggested evidence record

The following is an **illustrative research schema**, not a ratified SIF standard:

```yaml
sce_record:
  id: "sce:example:2026-001"
  claim_ref: "claim:planner-v2:transferability"
  candidate_version: "2.0.0-candidate"
  challenge_type: "applicability"
  context:
    environment: "simulated-distribution-shift"
    scenario_ref: "scenario:peak-demand-04"
  observation:
    result: "constraint_violation"
    artifact_ref: "artifact:trace-04"
  provenance:
    evaluator_ref: "evaluator:independent-b"
    protocol_version: "1.2"
    seed: 417
  assessment:
    confidence: "moderate"
    severity: "high"
    disposition: "open"
  governance:
    production_authorized: false
    review_required: true
```

The record intentionally separates observation from assessment, and assessment from authorization.

## 5. Evaluator Governance as a Distinct Control Function

Evaluator governance concerns the design, independence, calibration, revision, and authority boundaries of evaluation mechanisms. It does not imply that one universal evaluator can judge every intelligence domain.

SIF distinguishes three interacting control functions:

| Function | Governing question | Example artifact |
|---|---|---|
| **Policy and Authority Plane** | What may be done, by whom, and under what conditions? | Deployment authorization and access policy |
| **Scoring and Decision Plane** | Which candidate appears preferable under declared criteria? | Multi-objective scoring tree or forest |
| **Evidence and Audit Plane** | What supports or contests that conclusion? | Evidence ledger, SCE records, audit trail |

A high score is not authorization. An evaluator may recommend a candidate while the policy plane prohibits its deployment. Conversely, an authorized exploratory test does not imply that the candidate has been validated.

### 5.1 Who evaluates the evaluator?

An evaluator is itself a versioned intelligence structure with assumptions, limitations, and evidence requirements. It should be subject to challenge when:

- benchmark performance improves unusually rapidly without independent corroboration;
- optimization pressure is concentrated on a narrow metric;
- the builder and evaluator share substantial training data, tools, or models;
- decisions materially affect safety, rights, resources, or irreversible state;
- a new operating context lies outside the evaluator's validated range;
- credible counter-evidence contradicts the evaluator's ranking.

The response need not always be another general-purpose AI model. A deterministic constraint checker, domain expert, external audit, simulation, or formal verification tool may provide more relevant independence.

### 5.2 Independence is multidimensional

Evaluator independence may be assessed across organizational control, model lineage, training data, benchmark design, instrumentation, financial incentives, and authority to report unfavorable results. No single dimension guarantees independence.

## 6. Bounded Recursive Evaluator Challenge

A naive response to evaluator fallibility is infinite recursion: evaluator \(E_1\) is judged by \(E_2\), which is judged by \(E_3\), and so on. This cannot be an operational requirement.

SIF instead proposes **bounded recursive challenge**. Escalation is driven by risk, uncertainty, and the marginal value of additional evidence.

A conceptual decision rule is:

$$
operatorname{ChallengeNext}(E_i) =
\begin{cases}
1, & \text{if expected reduction in decision risk exceeds review cost and budget remains},\\
0, & \text{otherwise.}
\end{cases}
$$

This is a decision principle, not a validated quantitative formula. It requires explicit estimates or conservative qualitative judgments.

### 6.1 Termination conditions

Recursive challenge must stop or escalate to human governance when the review budget is exhausted, marginal evidence gain is low, an authorized risk threshold is met, or a critical unresolved dispute requires external adjudication. Stopping does **not** certify truth; it records the remaining uncertainty and the decision authority.

### 6.2 Diverse challenge channels

Useful challenge channels include:

1. **Metric challenge:** test whether the score tracks the actual objective.
2. **Data challenge:** inspect leakage, representativeness, and contamination.
3. **Structural challenge:** question decomposition, routing, and composition.
4. **Adversarial challenge:** search for boundary and worst-case failures.
5. **Authority challenge:** verify that evaluation cannot bypass policy.
6. **Perspective challenge:** introduce omitted stakeholders or problem framings.

The goal is complementary error detection, not a performative committee of identical models.

## 7. Anti-Goodhart Design Patterns

When a proxy becomes the optimization target, the relation between proxy and intended objective may degrade. This is particularly dangerous in self-improving systems, where the builder can learn the evaluator's weaknesses.

We propose the following safeguards as **testable design patterns**, not guarantees:

- **Multiple independent measures:** report a vector of outcomes instead of hiding tradeoffs in one aggregate score.
- **Hard constraints before optimization:** enforce non-negotiable safety, policy, and feasibility conditions separately from soft preferences.
- **Private or rotating holdouts:** reduce direct adaptation to a fixed public test, while maintaining reproducible governance.
- **Out-of-distribution testing:** probe where the candidate's applicability claim is weakest.
- **Adversarially generated cases:** permit challengers to search for counterexamples under controlled budgets.
- **Ablation and causal probes:** distinguish real structural improvements from incidental correlations.
- **Evaluator versioning:** revalidate candidates when the metric or test harness changes.
- **Negative evidence retention:** prevent selective reporting and survivorship bias.
- **Post-deployment monitoring:** detect real-world drift without treating deployment as final proof.

### 7.1 Scoring trees and evidence separation

A Scoring Tree or Forest may express multiple objectives, weights, and contextual branches. The tree must expose its inputs, aggregation logic, missing-data treatment, and policy constraints. Its numerical output should link to underlying evidence records and counter-evidence rather than replace them.

Structural folding can reduce evaluation cost by reusing summaries, but folded evidence must preserve traceability to original tests and expose uncertainty introduced by aggregation. Where traceability cannot be preserved, the system should record the loss rather than imply full fidelity.

## 8. Integration with the Multi-Intelligence Adversarial Sandbox

The **Multi-Intelligence Adversarial Sandbox (MIAS)** described in SIF-012 provides an environment for executing the challenge protocol.

| Role | Primary responsibility | Required boundary |
|---|---|---|
| Builder | Propose or adapt candidate structures | Cannot self-authorize deployment |
| Challenger | Search for structural counterexamples | Cannot silently alter registered claims |
| Independent Evaluator | Apply declared and additional tests | Must disclose relevant dependencies |
| World / Simulation Engine | Model scenarios and state transitions | Must disclose model assumptions |
| Formal / Deterministic Checker | Check specified invariants | Cannot certify unmodeled properties |
| Evidence Steward | Maintain traceable records and versions | Cannot suppress unfavorable evidence without audit |
| Policy Authority | Approve permitted transitions and actions | Must not equate score with authorization |

The roles are logical responsibilities, not necessarily separate organizations or models. For high-consequence cases, meaningful separation of duties should be assessed explicitly.

### 8.1 Three execution boundaries

**Exploratory Sandbox:** isolated candidate discovery, adversarial tests, and unrestricted *hypothesis generation* within safety and resource limits.

**Validated Shadow Runtime:** candidate observes or simulates live workflows without controlling production outcomes; comparisons and drift monitoring continue.

**Authorized Production Runtime:** only explicitly approved capabilities may act, under bounded permissions, monitoring, and rollback conditions.

An automated system may generate and evaluate candidates without human review of every intermediate idea. It must not silently promote those candidates across an authority boundary.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

---

## 9. Registry, Contracts, and Bidirectional Mapping

SCE is most useful when attached to reusable structural artifacts.

### 9.1 Structural Intelligence Contract (SIC)

A contract should identify applicability assumptions, invariants, expected inputs/outputs, resource limits, evidence requirements, and authorized actions. Counter-evidence can then target a particular contract clause rather than an ambiguous system label.

### 9.2 Structural Precedent Registry (SPR)

The registry should retain positive and negative precedents, claim lineage, evaluator versions, challenge outcomes, and supersession links. A failed precedent may be retrieved to warn against inappropriate transfer.

### 9.3 Problem–Capability Dual Maps

In **Problem-Solving Map → Capability Map** matching, SCE may reveal why a candidate capability is not suitable for a task. In **Capability Map → Problem-Solving Map** exploration, it may reveal that a newly discovered capability is applicable only to a narrower class of problems than originally proposed.

### 9.4 UNT-R and portability

Universal Naming, Typing, and Relay (UNT-R) provides identity and interface continuity across evaluators, nodes, and organizations. Portable Intelligence Pieces (PIRPs) and Portable Intelligence Units (PIRUs) should carry or reference their claims, constraints, and evidence history. Portability of code or prompts does not automatically imply portability of validity.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 10. Counter-Evidence as a Driver of Structural Growth

Structural counter-evidence should not be treated solely as a rejection signal. It may identify a precise residual that invites improvement.

A candidate lifecycle is:

```text
Registered structural claim
          |
          v
Evidence collection and adversarial challenge
          |
          +---- Supported within bounded context ---> Restricted precedent
          |
          +---- Structural counter-evidence --------> Residual diagnosis
                                                      |
                           +--------------------------+-------------------+
                           |                          |                   |
                           v                          v                   v
                    Revise structure          Narrow applicability   Replace evaluator
                           |                          |                   |
                           +--------------------------+-------------------+
                                                      |
                                                      v
                                            Re-register and retest
```

Growth may occur in localization, per-node computation, control/scoring, or the growth mechanism itself. However, not every residual justifies a new component. Sometimes the correct action is to retire a capability, reduce scope, or improve measurement.

### 10.1 Structural Perception Horizon

A challenge may reveal that the current evaluation system cannot represent an important distinction. Such cases may motivate a new perspective, state variable, causal model, or stakeholder objective. This is a proposed pathway from counter-evidence to expansion of the **Structural Perception Horizon**, not an established law of intelligence evolution.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 11. Conceptual Case: Supply-Chain Planning

Assume an existing planner uses an LLM to interpret requests, a routing model to select optimization tools, and a scoring forest to rank schedules.

**Initial claim:** a new routing policy reduces average planning time while preserving service-level and safety constraints under a declared demand range.

**Positive evidence:** benchmark runtime decreases on the registered scenarios.

**Challenger finding:** under an unusual demand spike, the routing policy sends a fragile constraint class to a fast approximate solver that omits a critical capacity constraint.

**Structural counter-evidence:** the problem is not merely one incorrect answer; it is a **localization-and-composition failure**. The capability selector's applicability condition and the downstream solver's contract do not jointly preserve the end-to-end invariant.

**Evaluator challenge:** the original benchmark's aggregate score underweights rare constraint violations. An independent checker demonstrates that the evaluator's metric is insufficient for the declared safety claim.

**Disposition:** block production promotion; narrow the routing contract; add a deterministic constraint checker; revise the scoring protocol; retest on held-out stress cases.

**Growth outcome:** the registry gains a negative precedent, the contract gains an explicit invariant, and the evaluator gains a new challenge test. No claim of real-world performance is made by this illustrative scenario.

## 12. Failure Modes of the Proposed Governance System

| Failure mode | Why it matters | Proposed mitigation |
|---|---|---|
| Evaluator collusion or shared blind spots | Apparent agreement is not independent evidence | Diverse models, methods, and institutions |
| Challenge theater | Many tests provide little actual coverage | Track unique failure classes and marginal discovery |
| Infinite review recursion | Review consumes all resources | Risk-based budgets and explicit stopping rules |
| Evidence laundering | Unverified claims gain legitimacy through summaries | Provenance chains and auditability |
| Selective counter-evidence retention | Registry becomes promotional | Append-only audit history and documented dispositions |
| Benchmark overfitting | Candidate optimizes a proxy | Holdouts, rotating scenarios, external tests |
| Simulation-to-reality gap | World engine misses relevant mechanisms | Reality checks and applicability bounds |
| Authority confusion | Evaluation becomes unauthorized action | Separate policy plane and runtime gates |
| Excessive conservatism | Every novelty is rejected | Risk-tiered exploratory freedom and reversible trials |
| Perspective lock-in | Important objectives are not represented | Stakeholder and cross-perspective challenges |

A governance design should be evaluated for both **false acceptance** of harmful or invalid structures and **false rejection** of useful innovations.

## 13. Testable Hypotheses

The following are research hypotheses, not reported findings.

**H1 — Structural challenge coverage.** Compared with outcome-only tests under equal compute budgets, structured SCE protocols will detect more distinct failure classes in compositional intelligence pipelines.

**H2 — Negative precedent reuse.** Retrieval augmented with negative precedents will reduce repeated invalid transfers compared with positive-only retrieval.

**H3 — Evaluator diversity.** Heterogeneous evaluator ensembles will identify more independent failure modes than equally sized homogeneous ensembles, after controlling for test budget.

**H4 — Explicit applicability contracts.** Candidates with machine-checkable applicability constraints will exhibit fewer invalid invocations under distribution shift.

**H5 — Bounded recursive challenge.** Risk-triggered evaluator challenges will achieve a better detection-cost tradeoff than either no evaluator review or fixed-depth review.

**H6 — Evidence-preserving folding.** Traceable folded evaluation records will support more accurate audit reconstruction than untraceable aggregate scores at similar retrieval cost.

**H7 — Authority separation.** Explicit evaluation-to-authorization gates will reduce unauthorized production transitions without prohibitive loss of validated candidate throughput.

**H8 — Perspective challenge.** Deliberate alternative-framing tests will identify consequential omitted objectives more often than single-perspective evaluation.

### 13.1 Measurement recommendations

Measure unique confirmed failure classes, false-positive challenge rate, evaluator disagreement, detection latency, validation compute cost, provenance completeness, transfer reliability, unauthorized transition rate, and performance under shift. Pre-register acceptance criteria and report uncertainty intervals where feasible.

## 14. Validation Roadmap

**Phase A — Minimal claims and records.** Define a small claim schema, evidence ledger, and SCE taxonomy for one constrained task family. Establish inter-rater agreement on challenge labels.

**Phase B — Controlled adversarial benchmarks.** Inject known localization, composition, metric, and applicability defects. Compare outcome-only, structural, and mixed evaluation protocols.

**Phase C — Evaluator challenge experiments.** Introduce evaluator contamination, proxy misalignment, and shared-model dependencies. Test heterogeneous challenge channels and bounded escalation policies.

**Phase D — Registry and contract integration.** Connect SCE to the Structural Precedent Registry, SIC, and UNT-R identities. Measure retrieval and transfer effects across repeated tasks.

**Phase E — Shadow-runtime studies.** Evaluate drift, challenge latency, and governance workflows without granting candidate systems production authority.

Advancement between phases should depend on independently reviewed evidence, not on publication milestones or an assumed inevitable progression to autonomous self-improvement.

## 15. Open Research Questions

1. How should structural counter-evidence be represented when the disputed claim is only partially formalizable?
2. Which combinations of evaluator diversity yield genuinely independent error detection?
3. How can an evaluator's hidden optimization incentives be identified without relying on another equally opaque evaluator?
4. How should rare but severe failures be weighted against common, low-impact improvements?
5. Can a precedent registry prevent evidence laundering across repeated summarization and relay?
6. When does recursive evaluator challenge provide sufficient marginal value to justify its cost?
7. How can structural counter-evidence be shared across organizations without disclosing sensitive data or proprietary systems?
8. How should changing world models and stakeholder perspectives trigger retrospective revalidation?
9. What formal guarantees are achievable for narrow contracts, and which claims necessarily remain empirical?
10. How can the governance system itself remain corrigible and open to structural revision?

## 16. Conclusion

Structural intelligence growth creates a second-order responsibility: the system must be able to challenge not only its proposed solutions but also the structural assumptions and evaluation mechanisms through which those solutions are judged. **Structural Counter-Evidence** makes these challenges explicit, traceable, and reusable. **Evaluator Governance** provides a disciplined way to question metrics, independence, and decision authority without demanding impossible infinite verification.

The central architectural separation is simple but consequential:

> **A candidate may be discovered without being validated; validated without being authorized; and authorized only within an explicit, revisable boundary.**

An open intelligence framework should preserve all three distinctions. Its credibility rests not on the absence of failure, but on whether failures and counter-evidence can revise the structures, precedents, evaluators, and perspectives on which future intelligence depends.

---

## Relationship to Other SIF Documents

- **SIF-003:** Structural Precedents and Open Intelligence Evolution — contextualized reuse and negative precedents.
- **SIF-006:** Universal Control Planes and Scoring Folding — authority, scoring, evidence, and traceable aggregation.
- **SIF-007:** Residual-Based Structural Growth — failure-to-growth pathways.
- **SIF-008:** Dual Maps and Bidirectional Structural Mapping — problem–capability applicability.
- **SIF-009:** Structural Precedent Registry — evidence, lineage, and case records.
- **SIF-010:** Universal Naming, Typing, and Relay — identities and cross-boundary evidence continuity.
- **SIF-011:** Structural Intelligence Contracts and Portable Units — explicit applicability and portability constraints.
- **SIF-012:** Multi-Intelligence Adversarial Sandbox — experimental environment and challenger roles.
- **SIF-014 (planned):** Open-Ended Structural Growth and Collective Learning — longer-term evolution mechanisms.
- **SPEC-004 (planned):** Sandbox Evidence and Growth Lifecycle — candidate operational specification.

---

*Research status: Conceptual architecture and falsifiable proposals. No experimental results or formal guarantees are asserted in this paper.*
