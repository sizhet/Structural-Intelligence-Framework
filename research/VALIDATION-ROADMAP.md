# SIF Validation Roadmap

**Project:** Structural Intelligence Framework (SIF)  
**Document:** `research/VALIDATION-ROADMAP.md`  
**Release:** v1.0.0 research baseline  
**Status:** Proposed research and engineering roadmap; not a report of completed validation  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0

> **Purpose.** Convert SIF's architectural claims into reproducible experiments, interoperable prototypes, adversarial evaluations, and explicitly governed deployment decisions. A successful program must be able to reject SIF components when evidence does not support them.

## 1. Scope and Operating Principles

SIF is an open architecture for locating, composing, governing, and evolving heterogeneous intelligence structures. This roadmap evaluates its four functional domains—**Localization**, **Per-Node Intelligence**, **Universal Control Planes and Scoring/Folding**, and **Residual-Based Structural Growth**—together with their cross-cutting infrastructure: Problem–Capability Dual Maps, Structural Precedent Registry (SPR), Universal Naming/Typing/Relay (UNT-R), Structural Intelligence Contracts (SIC), and the Multi-Intelligence Adversarial Sandbox (MIAS).

This roadmap is a proposal. It does **not** assert that the SIF architecture has already been implemented or empirically validated. Specifications in `specifications/` are candidate contracts, not ratified standards.

Core commitments:

1. **Claims before demonstrations.** Pre-register the task, comparator, metric, resource budget, and rejection condition.
2. **Baselines before integration.** A hybrid system must beat credible simpler alternatives under matched constraints.
3. **Evidence before promotion.** Record both positive and negative findings, including uncertainty and applicability boundaries.
4. **Authorization separate from evaluation.** Passing a benchmark never grants operational authority.
5. **Reproducibility before scale.** Freeze versions, seeds, datasets, hardware assumptions, and execution traces.
6. **Open architecture, bounded experiments.** Discovery can be broad; resource use, data access, and real-world actions remain controlled.

## 2. Traceability: Questions, Hypotheses, and Specifications

The primary traceability chain is:

`OPEN-QUESTIONS.md` → `TESTABLE-HYPOTHESES.md` → experiment protocol → evidence/counter-evidence → qualification decision → updated architecture or new residual.

For continuity, the hypothesis IDs below use the H01–H20 groups introduced in `TESTABLE-HYPOTHESES.md`. Before any formal pre-registration, verify exact statement-to-ID alignment against that file; the mapping here is a planning index, not a replacement for its detailed hypothesis definitions.

| Workstream | Primary hypothesis IDs | Main specification | Primary outcome |
|---|---|---|---|
| Structural localization | H01–H04 | SPEC-001, SPEC-002 | Match quality, retrieval cost, missed capabilities |
| Dual maps and precedents | H05–H06 | SPEC-003 | Applicability-calibrated reuse and adaptation |
| Contracts and relay | H07–H08 | SPEC-001, SPEC-002 | Cross-implementation compatibility and context fidelity |
| Control, scoring, folding | H09–H11 | SPEC-001, SPEC-004 | Decision quality, auditability, safe authority separation |
| Residual diagnosis and MIAS | H12–H14 | SPEC-003, SPEC-004 | Failure detection, false promotion, evaluator robustness |
| Structural/collective growth | H15–H17 | SPEC-001–004 | Durable transfer, composition gains, bounded evolution |
| Scaling and frontiers | H18–H20 | SPEC-001–004 | Resource-adjusted gains, perceptual novelty, perspective robustness |

## 3. Program Architecture

### 3.1 Three independently reviewable systems

- **Structural Intelligence Registry:** catalogues capabilities, structural precedents, applicability envelopes, evidence, counter-evidence, and lineage.
- **Structural Intelligence Runtime:** matches problem requirements to candidate capabilities, composes them through typed relay, and enforces authority boundaries.
- **Structural Intelligence Evolution Laboratory:** discovers residuals, proposes candidates, challenges claims, evaluates results independently, and recommends—not authorizes—promotion.

The systems should be independently testable. A registry may be useful without automated growth; a relay protocol may be useful without a scoring forest. Avoid an all-or-nothing validation design.

### 3.2 Four functional domains as experimental strata

Each benchmark must identify which SIF function it exercises and which functions are intentionally held constant. A successful localization experiment is not automatically evidence for open-ended growth; a successful multi-agent composition is not automatically evidence for a changed worldview.

### 3.3 Required artifact provenance

Every experimental run should produce a **run manifest** with: experiment ID, research question, hypothesis ID, dataset/task version, split policy, baseline identifiers, model/tool versions, SIC/UNT-R profile, configuration, random seeds, compute budget, evaluator identity, authorization profile, result hashes, and deviations from the preregistered protocol. Store sensitive raw data in appropriately access-controlled systems and publish only permitted derivatives.

## 4. Stage-Gated Validation Program

Progress is gated by evidence quality, not by calendar date. Stages may overlap, but a later stage must not be treated as validated merely because its prototype exists.

| Stage | Focus | Minimum deliverable | Gate to advance |
|---|---|---|---|
| **V0** | Definitions and measurement | Claim register, task taxonomy, baseline suite, threat model | Unambiguous metrics, failure criteria, independent review |
| **V1** | Isolated mechanisms | Localization, registry, contract, and relay experiments | Reproducible gains or documented null results |
| **V2** | Composition and control | Dual-map routing, per-node composition, scoring/policy separation | End-to-end quality with bounded cost and no authority bypass |
| **V3** | Adversarial evidence | MIAS, counter-evidence, evaluator challenge, sandbox controls | Measurable failure detection and calibrated promotion |
| **V4** | Growth and transfer | Residual-driven proposals, PIRP→PIRU, collective learning | Held-out transfer and sustained benefit versus simpler alternatives |
| **V5** | Frontiers and external replication | Macro-units, scaling, perception/worldview studies | Independent replication and strict interpretation of claims |

### V0 — Definitions, task suites, and preregistration

**Questions.** What counts as an intelligence structure, an applicable precedent, a residual, a successful relay, and a genuine new capability?

**Actions.**

- Define canonical task records: objectives, constraints, context, admissible actions, evaluation targets, and expected uncertainty.
- Select benchmark families: constrained planning, code maintenance, knowledge retrieval, simulation-based decision support, and heterogeneous service orchestration.
- Separate synthetic tests (controllable ground truth) from real-world-derived tests (ecological validity).
- Pre-register primary endpoints, uncertainty intervals, exclusion rules, multiple-testing treatment, and stopping criteria.
- Establish simple comparators: direct LLM, fixed workflow, flat retrieval, non-typed API routing, and ordinary ensemble methods.
- Threat-model prompt injection, provenance tampering, unsafe delegation, evaluator leakage, reward hacking, and data exfiltration.

**Exit criteria.** At least one complete, independently executable protocol per initial workstream; a stable task/evidence schema; and a published negative-result policy.

### V1 — Isolated structural mechanisms

**A. Localization and intelligence addressing.** Compare flat semantic retrieval, LLM-only tool selection, hierarchical MDT/CCC retrieval, and Two-Phase Search under matched latency/token/compute budgets. Measure top-k candidate recall, applicability precision, calibration, latency, total compute, and out-of-distribution failure.

**B. Structural precedents.** Compare plain example retrieval against applicability-aware precedent retrieval. Use matched positive cases, near-miss cases, obsolete cases, and counter-evidence-rich cases. Measure inappropriate reuse, adaptation success, and the ability to abstain.

**C. SIC and UNT-R.** Run interoperability matrices across at least two independent adapters and multiple capability types. Test identity resolution, schema/semantic incompatibility, context preservation, cancellation, version pinning, error propagation, and authorization rejection.

**Exit criteria.** Report effect sizes and confidence/uncertainty estimates, not only pass rates. Publish failures and compatibility limitations. Do not promote a contract profile solely because happy-path calls work.

### V2 — Composition, scoring, and control

**A. Dual-map matching.** Compare a single-route planner, flat capability catalog, PSM→SCM matching, and bidirectional mapping. Evaluate task completion, avoidable calls, unmatched requirements, candidate discovery, and false confidence.

**B. Per-node intelligence.** Use a heterogeneous set (e.g., LLM, deterministic rules, optimization solver, simulator, retrieval engine). Compare single-model, fixed pipeline, and contract-guided composition. Require matched access to tools and data.

**C. Control planes.** Test Policy & Authority, Scoring & Decision, and Evidence & Audit independently. Deliberately create cases with high score but insufficient permission; valid permission but insufficient evidence; and conflicting objectives. Verify that evaluation cannot silently authorize action.

**D. Structural folding.** Compare full-structure execution, folded summaries, and adaptive unfolding. Measure computation saved, error introduced, audit recovery, and counter-evidence preservation.

**Exit criteria.** No observed policy-bypass path in the preregistered test suite, plus reproducible task or efficiency gains against matched baselines. Absence of detected bypass is not proof of safety.

### V3 — Adversarial validation and evaluator governance

Build MIAS with separable roles: Builder, Challenger, Independent Evaluator, Formal Checker where applicable, World/Simulation Engine, and Policy Authority. A role label is insufficient; enforce separation through data access, model independence where feasible, and independent review.

Experiments should include:

- **Adversarial counterexamples:** invalid assumptions, adversarial inputs, distribution shift, misleading precedents, and incompatible compositions.
- **Evaluator challenge:** contaminated benchmarks, proxy-metric gaming, correlated judges, inconsistent rubrics, and disagreement escalation.
- **Evidence lineage:** missing or conflicting evidence, unverifiable source claims, and attempted alteration of prior outcomes.
- **Promotion controls:** blocked transitions when evidence is weak, applicability is unknown, or permission is absent.
- **Sandbox isolation:** denial of unapproved network, file, credential, and real-world action access in test environments.

Measure counterexample discovery rate, false positive rate, false qualification rate, time-to-detection, evaluator agreement/calibration, and cost per verified finding. Include deliberately seeded failures whose ground truth is known, plus unseeded challenge sets.

**Exit criteria.** Demonstrated improvement in detecting relevant structural failures without intolerable false rejection or cost; documented blind spots; an explicit human-controlled authorization boundary.

### V4 — Structural growth and collective transfer

Test whether residual-driven discovery creates durable, generalizable improvements rather than merely expanding a catalog.

**Protocol.** Hold out task families, organizations, or environments. Capture a residual; generate candidate PIRPs; evaluate in MIAS; formalize qualifying candidates as PIRUs; register versioned precedents; test transfer to unseen contexts; then re-evaluate after a changed environment.

**Comparators.** Manual expert extension, simple prompt or retrieval updates, fixed-library expansion, and non-adversarial self-improvement. Match development and inference budgets as far as practicable.

**Measures.** Novel held-out tasks solved, negative transfer, time to adaptation, accumulated maintenance burden, regression rate, evidence retention, unauthorized action attempts, and performance after candidate retirement.

**Collective learning.** Use multiple independently administered BrainUnits with distinct contexts and authority boundaries. Test whether portable units and counter-evidence improve cross-unit transfer relative to raw transcript sharing and non-portable artifacts. Do not infer privacy or security merely from a successful relay.

**Exit criteria.** Repeated improvements on held-out tasks, credible attribution to structural changes, bounded regression, and preserved governance. Failed candidates remain in the registry as negative precedents when permissible.

### V5 — Higher-order structures, scaling, and perception

**Macro-Intelligence Pieces.** Compare explicit multi-component orchestration against a contracted macro-unit under equal component access. Measure reusability, integration overhead, failure propagation, auditability, and novel task performance. Aggregation alone is not emergence.

**Scaling axes.** Factorially vary structure breadth, depth, computation guidance, compute budget, interoperability quality, evidence intensity, governance constraints, and collective transfer. Estimate interactions and marginal returns rather than reporting a single aggregate scale score.

**Structural Perception Horizon.** Construct environments with hidden but discoverable relational variables. Predefine what constitutes a newly represented and independently validated distinction. Compare within-horizon optimization against systems allowed to revise their representations and task ontology. Require external validation of claimed new variables and causal relevance.

**Perspective-relative ASI.** If studied, state task distribution, metric family, resource constraints, temporal horizon, and authority envelope. Do not extrapolate narrow superhuman performance into universal intelligence or a guaranteed trajectory toward ASI.

**Exit criteria.** Independent replication of at least one frontier result, transparent null findings, and a documented separation between observed performance and speculative interpretation.

## 5. Common Experimental Design

### 5.1 Baseline ladder

Use a consistent ladder when applicable:

| Level | Comparator | Purpose |
|---|---|---|
| B0 | Direct single-model or deterministic baseline | Minimum credible performance |
| B1 | Existing retrieval/tool-use pipeline | Control for ordinary engineering improvements |
| B2 | Fixed heterogeneous composition | Control for adding more tools |
| B3 | SIF mechanisms without adversarial growth | Isolate structural routing/contract effects |
| B4 | SIF with evidence-gated growth | Test incremental growth contribution |

All comparisons must disclose differences in data, tool access, compute, human labor, and tuning. Where parity is impossible, present a Pareto frontier rather than an unqualified win/loss claim.

### 5.2 Evaluation dimensions

- **Task performance:** correctness, constraint satisfaction, reliability, and calibration.
- **Efficiency:** wall-clock latency, tokens, energy or hardware-normalized compute, monetary cost, and human review effort.
- **Interoperability:** semantic compatibility, context preservation, trace completeness, and version stability.
- **Governance:** authorization violations, escalation accuracy, reversibility, and audit coverage.
- **Evidence quality:** provenance completeness, counterexample sensitivity, reproducibility, and evaluator independence.
- **Growth quality:** held-out transfer, negative transfer, maintenance burden, retirement correctness, and stability over time.
- **Perceptual novelty:** independently confirmed new distinctions, predictive utility, and resistance to post hoc storytelling.

Do not compress these into one opaque score without also publishing the disaggregated measures and tradeoffs.

### 5.3 Statistical and causal discipline

Predefine unit of analysis, sample size rationale, randomization, paired-task comparisons, and uncertainty reporting. Use ablations for MDT, CCC, relay typing, precedent applicability, MIAS challenge, and policy gating. Avoid data leakage from task generation into evaluation. Include sensitivity analyses across model families, task difficulty, resource budgets, and evaluator choice. Use independent replication where possible.

## 6. Evidence and Promotion Policy

The research evidence ladder below is a proposed project convention; it is not an industry standard.

| Level | Evidence state | Permitted conclusion |
|---|---|---|
| **E0** | Conceptual claim | Hypothesis only |
| **E1** | Executable demonstration | Feasibility in a narrow setting |
| **E2** | Controlled comparison | Measured local effect under stated conditions |
| **E3** | Replicated, adversarially challenged result | Stronger context-bounded support |
| **E4** | Independent, longitudinal, multi-context validation | Qualified generalization within an explicit envelope |

Evidence level does not equal deployment permission. Operational authority must be separately granted and may be revoked. The following states must remain distinct:

`DISCOVERED → PROPOSED → SANDBOXED → EVIDENCE_REVIEWED → QUALIFIED → SHADOW_TESTED → AUTHORIZED → DEPLOYED → MONITORED / SUSPENDED / RETIRED`

These are conceptual states; exact lifecycle transitions should be reconciled with `SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md` before implementation. In particular, **qualification is not authorization** and **shadow execution is not production deployment**.

## 7. Required Deliverables and Directory Conventions

Suggested future experimental layout (not part of the initial code-free DOI release):

```text
experiments/
  protocols/            # preregistered questions, metrics, rejection rules
  datasets/README.md    # dataset sources, licenses, access restrictions
  baselines/            # pinned configurations and comparator definitions
  runs/                 # manifests, non-sensitive outputs, checksums
  evaluations/          # evaluator rubrics, disagreements, audit results
  counter-evidence/     # negative cases and structural failures
  replications/         # independent reruns and deviations
  reports/              # effect sizes, limitations, decisions
```

Initial v1.0.0 can remain **research-documentation only**, with no demos or code. Adding this directory later should follow actual experimental work rather than creating empty claims of validation.

For each completed experiment, publish:

1. A dated protocol with an immutable revision or hash.
2. A reproducibility manifest and permissible dataset access instructions.
3. Baseline and candidate results with uncertainty and resource accounting.
4. Counter-evidence, evaluator disagreements, and known failure conditions.
5. A decision record: supported, unsupported, inconclusive, or unsafe under the tested envelope.
6. Follow-up residuals and changes to relevant registry entries or contracts.

## 8. Program Governance and Roles

| Role | Responsibility | Must not unilaterally do |
|---|---|---|
| Research lead | Hypotheses, protocol integrity, interpretation | Rewrite rejection rules after seeing outcomes without disclosure |
| Builder | Implement candidate intelligence structures | Self-certify safety or applicability |
| Challenger | Generate adversarial cases and counter-evidence | Alter independent evaluation records |
| Independent evaluator | Score outcomes and audit evidence | Grant production authority |
| Registry steward | Maintain versions, provenance, lineage | Erase inconvenient negative evidence |
| Policy authority | Approve bounded actions and deployment | Treat high score as sufficient proof of safety |
| External replicator | Reproduce claims under documented conditions | Claim independence without disclosing shared dependencies |

Where staffing is limited, role separation can be procedural, but conflicts of interest and shared-model dependencies must be recorded.

## 9. Major Risks and Stop Conditions

| Risk | Observable warning | Response |
|---|---|---|
| Benchmark overfitting | Gains disappear on fresh tasks | Freeze training/evaluation boundaries; retest |
| Registry confirmation bias | Failed cases underrepresented | Mandatory negative-case capture and audits |
| Semantic relay drift | Inputs/outputs remain syntactically valid but change meaning | Typed context checks and semantic conformance tests |
| Evaluator capture / Goodhart | Score rises while independent outcomes deteriorate | Rotate independent evaluators and challenge metrics |
| Unauthorized action | A candidate executes outside its permission envelope | Stop execution, isolate, preserve evidence, review authority |
| Unbounded growth | Cost and maintenance grow faster than utility | Apply budget ceilings, retirement and ablation gates |
| False emergence claims | Apparent novelty vanishes under matched baselines | Narrow claims to observed results |
| Privacy / provenance leakage | Relay exposes restricted context or source data | Revoke access, contain, investigate, redesign contracts |
| Recursive validation explosion | Evaluator-of-evaluator loops exhaust budget | Bounded challenge depth and risk-triggered escalation |

**Immediate stop conditions** for any experiment with real-world effects include unauthorized access/action, uncontrolled propagation, evidence tampering, or inability to contain execution. Sandbox experiments should be designed to make such events observable and containable.

## 10. Prioritization and Resource Allocation

A practical sequence is to validate **low-coupling, falsifiable components first**: SIC/UNT-R conformance; applicability-aware precedents; dual-map routing; control-plane separation; then MIAS and residual-based growth. Frontier studies should not be allowed to displace basic interoperability and safety evidence.

For each proposed experiment, estimate:

- Expected information gain about a disputed architectural claim.
- Cost in compute, engineering, review, and maintenance.
- Severity and reversibility of plausible failures.
- Availability of a credible comparator and independent evaluator.
- Whether the result changes a real design or governance decision.

Prioritize experiments that could materially falsify a foundational SIF assumption. A decisive negative result can be more valuable than an impressive but ambiguous demonstration.

## 11. Cross-Document Consistency Checklist

Before release or experimental implementation, verify:

- [ ] SIF-001–018 claims are labeled as conceptual, empirical, or speculative consistently.
- [ ] `OPEN-QUESTIONS.md` question IDs and `TESTABLE-HYPOTHESES.md` H01–H20 IDs resolve unambiguously.
- [ ] `SPEC-001` SIC fields and profiles agree with `SPEC-002` relay envelopes.
- [ ] `SPEC-003` evidence, precedent, and lineage references can carry `SPEC-004` lifecycle outcomes.
- [ ] `SPEC-004` lifecycle states, gates, and authorization semantics match this roadmap.
- [ ] Evidence levels E0–E4 are consistently defined or explicitly identified as research conventions.
- [ ] Figures do not depict proposed mechanisms as already deployed or validated.
- [ ] Negative evidence, abstentions, and non-transferable results are first-class outputs.
- [ ] Security, privacy, and licensing obligations are reviewed for every data and tool source.
- [ ] Every reported result includes matched baselines, resource costs, and limitations.

## 12. Milestone Decision Records

At each gate, maintain a short decision record:

```yaml
milestone_id: SIF-V2-EXAMPLE
status: proposed  # proposed | in_progress | passed | failed | inconclusive
hypotheses: [H05, H07, H09]
protocol_revision: pending
baseline_set: pending
evidence_level: E0
applicability_envelope: pending
counter_evidence_refs: []
independent_review: pending
authorization_decision: not_requested
next_action: finalize_preregistered_protocol
```

This example is illustrative; it is not a report of an executed milestone.

## 13. Research Success and Scientific Failure

A successful SIF research program need not validate every proposed mechanism. It should yield a **smaller, better-supported, interoperable, auditable architecture**, with explicit knowledge of where the approach works and where it does not.

A scientifically valuable failure might show that a simpler workflow outperforms dual-map routing, that precedent transfer is too brittle in a domain, that a proposed contract imposes unacceptable overhead, or that an apparent perception expansion is merely relabeling. Such results should change the framework, not be hidden.

The long-term objective is not to certify a final intelligence architecture. It is to establish a disciplined process through which intelligence structures can be **located, composed, challenged, revised, transferred, and—when warranted—retired**.

> **Validate the structure. Challenge the evaluator. Preserve the residual. Govern the action. Keep the future open.**

---

## Related SIF Documents

- [`OPEN-QUESTIONS.md`](OPEN-QUESTIONS.md)
- [`TESTABLE-HYPOTHESES.md`](TESTABLE-HYPOTHESES.md)
- [`../specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md`](../specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md)
- [`../specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md`](../specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md)
- [`../specifications/SPEC-003-Structural-Precedent-Registry-Schema.md`](../specifications/SPEC-003-Structural-Precedent-Registry-Schema.md)
- [`../specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md`](../specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md)
- [`../docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md`](../docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
- [`../docs/validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md`](../docs/validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md)
- [`../docs/validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md`](../docs/validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md)

**Citation:** Sizhe Tan & GPT-Obot, *Structural Intelligence Framework (SIF): Validation Roadmap*, proposed research document, v1.0.0 (2026).
