# Open Questions — Structural Intelligence Framework (SIF)

**Repository:** Structural Intelligence Framework  
**Document:** `research/OPEN-QUESTIONS.md`  
**Version:** 1.0.0 (research agenda)  
**Status:** Open research questions; not validated claims  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0

## Purpose and scope

The Structural Intelligence Framework (SIF) proposes an open architecture for locating, composing, governing, validating, and growing heterogeneous intelligence structures. Its four functional domains—**Localization**, **Per-Node Intelligence**, **Universal Control Planes and Scoring/Folding**, and **Residual-Based Structural Growth**—are functional viewpoints, not disjoint software layers. This document identifies unresolved questions that should shape subsequent theory, specifications, prototypes, and empirical evaluation.

A question is *open* when the present framework lacks sufficient formalization, evidence, or implementation experience to resolve it. A proposed mechanism is not proof of feasibility; an observed performance gain is not, by itself, proof of structural intelligence growth. Questions below are deliberately falsifiable where possible, and should be revisited as evidence accumulates.

### Research conventions

- **[F] Foundational:** concepts, definitions, formal properties, and limits.
- **[A] Architectural:** interoperability, system composition, and runtime design.
- **[E] Empirical:** test design, measurements, baselines, and reproducibility.
- **[G] Governance:** authority, safety, accountability, and institutional boundaries.
- **[X] Frontier:** exploratory hypotheses with substantial epistemic uncertainty.

**Priority:** P0 = prerequisite to credible implementation; P1 = near-term research; P2 = longer-horizon inquiry. Priorities reflect dependency, not scientific importance.

---

## Q01 — What constitutes an intelligence structure? [F, P0]

A structural definition must distinguish a reusable intelligence structure from an ordinary function, data artifact, prompt, model weight set, or workflow description.

**Questions:**

1. What minimal combination of behavior, interface, applicability conditions, evidence, and lifecycle warrants the label *intelligence structure*?
2. Are algorithms, learned models, tools, CallingGraphs, scoring policies, world models, and composite organizations instances of one formal abstraction, or only interoperable families?
3. How should a structure's identity persist through adaptation, versioning, folding, and replacement?
4. Can structural novelty be measured independently of task performance?

**Resolution path:** propose an operational ontology, annotate diverse examples, and measure inter-rater agreement and downstream utility. **Failure signal:** the definition is so broad that every computation qualifies, or so narrow that useful heterogeneous capabilities cannot be represented.

## Q02 — Can the four functional domains be operationally separated without creating artificial silos? [F/A, P0]

LLMs, CCCs, world models, and scoring structures can serve multiple roles. A rigid classification would misrepresent SIF.

**Questions:** What are the observable functions of each domain? How can a single component occupy several domains simultaneously? Which interfaces genuinely cross domain boundaries? How are domain-specific residuals attributed when failure spans multiple functions?

**Resolution path:** define role-based annotations and multi-label conformance examples. **Failure signal:** classifications depend mainly on arbitrary naming rather than reproducible behavior.

## Q03 — What is a meaningful structural precedent? [F/E, P0]

The legal-precedent analogy suggests reuse under explicit conditions, but analogical similarity does not establish transferability.

**Questions:**

- What distinguishes a capability definition, a precedent case, and an evidence record?
- How should successful, failed, inconclusive, and contested precedents be weighted?
- What is the smallest useful *applicability envelope* (context, assumptions, exclusions, resource constraints, evidence quality)?
- When should adaptation create a new precedent rather than mutate an existing one?
- How do we detect selection bias when only successful cases are registered?

**Resolution path:** compare precedent-guided retrieval against unstructured RAG and ordinary tool selection on held-out tasks with distribution shift. **Failure signal:** precedent retrieval increases confidence but not transfer accuracy, or suppresses discovery of better new structures.

## Q04 — How should the Problem–Capability Dual Maps be represented and maintained? [F/A, P0]

The **Problem-Solving Map (PSM)** describes requirements, dependencies, constraints, and success criteria; the **Capability Map (SCM)** describes available structures, contracts, evidence, and composition relationships. **Bidirectional Structural Intelligence Mapping (BSIM)** connects them.

**Questions:**

1. What graph semantics allow partial matches, conditional dependencies, alternatives, cycles, and uncertain edges?
2. How can the system distinguish *missing capability* from *failed discovery of an existing capability*?
3. Can capability-led exploration generate useful new tasks without rewarding spurious novelty?
4. How should map revisions propagate through cached plans and deployed composites?
5. Which provenance must survive map folding/unfolding?

**Resolution path:** create typed graph benchmarks with known ground truth, hidden capabilities, and deliberately misleading matches. **Failure signal:** graph overhead exceeds improvements over simpler planners and registries.

## Q05 — What does localization quality mean beyond retrieval accuracy? [F/E, P0]

SIF localization may use LLMs, metric-space CCC, MDT, two-phase search, intelligence relay, CallingGraphs, Core+Delta, UTN, and world models. Their outputs are not directly comparable.

**Questions:** How should localization be evaluated for recall, calibration, routing cost, context fidelity, and downstream task utility? When does two-phase localization outperform direct computation? How can localization uncertainty be carried into later scoring and authorization?

**Resolution path:** report precision/recall, task completion, resource cost, uncertainty calibration, and error propagation under controlled budgets. **Failure signal:** better retrieval scores fail to improve end-to-end decisions.

## Q06 — Can a universal contract be precise without standardizing intelligence internals? [A, P0]

The **Structural Intelligence Contract (SIC)** proposes identity, type, capability, signature, context, relay, evidence, policy, lifecycle, and growth fields. **UNT-R** supplies naming, typing, and relay semantics.

**Questions:**

- Which fields are mandatory for discovery, invocation, and governed deployment respectively?
- How are semantic types validated when two systems use incompatible ontologies?
- How should unknown, probabilistic, and context-dependent guarantees be expressed?
- Can contracts be safely composed when individual contracts are valid but their assumptions conflict?
- What migration rules prevent version drift and broken references?

**Resolution path:** publish machine-checkable candidate schemas, negative conformance tests, and independent adapters. **Failure signal:** passing conformance tests predicts neither interoperability nor safe composition.

## Q07 — What must an intelligence relay preserve? [A/E, P0]

Relay is more than passing a payload between APIs. A handoff may change context, identity, trust, and the meaning of evidence.

**Questions:** Which semantic invariants must survive `describe`, `match`, `invoke`, `status`, `result`, and `cancel`? What must be carried for delegation, handoff, counter-evidence, and growth proposals? How should loss of context, partial execution, retries, cancellation, and replay be handled?

**Resolution path:** adversarial interoperability tests for context truncation, semantic mismatch, replay, privilege escalation, and partial failure. **Failure signal:** a relay appears syntactically successful while silently changing task constraints or authority.

## Q08 — How can per-node intelligence remain open and heterogeneous? [A/E, P1]

Per-node capability may be an LLM, rule engine, optimizer, ANN, simulation, statistical estimator, formal solver, world model, or composite intelligence piece.

**Questions:** How can nodes be indexed by algorithm, application, signature, evidence, and resource needs without a brittle taxonomy? How do nodes advertise nondeterminism and failure modes? When should a general model route to a specialist versus execute directly? How can specialized models be replaced without invalidating system-level claims?

**Resolution path:** evaluate heterogeneous nodes under identical tasks and budgets, including replacement and rollback experiments.

## Q09 — How should scoring, evidence, and action authority be separated? [G/A, P0]

SIF distinguishes **Policy & Authority**, **Scoring & Decision**, and **Evidence & Audit**. A high score is not permission to act.

**Questions:**

1. Which decisions can be delegated and which require external approval?
2. How are policy conflicts resolved across owners, BrainUnits, and jurisdictions?
3. How can scoring trees/forests preserve minority evidence and avoid proxy optimization?
4. How can authorization be revoked when evidence or context changes?
5. What audit trail is sufficient to reconstruct why an action was permitted?

**Resolution path:** threat-model privilege escalation, policy ambiguity, evaluator capture, and stale authorization. **Failure signal:** evaluation outcomes silently alter execution privileges.

## Q10 — When is structural folding valid, and what must be recoverable? [F/A/E, P1]

A Macro-Intelligence Piece may hide internal complexity behind a contract, but hiding detail can erase essential uncertainty, provenance, and failure paths.

**Questions:** What information must remain available for selective unfolding? How can a folded structure's claimed behavior be validated compositionally? How do we detect when a new context invalidates a folded abstraction? What are the latency, auditability, and robustness tradeoffs?

**Resolution path:** compare folded and unfolded execution on counterfactual tasks and incident reconstruction. **Failure signal:** folding produces unobservable errors or systematically masks counter-evidence.

## Q11 — How should residuals be detected, classified, and prioritized? [F/E, P0]

Residuals may concern localization, representation, capability, composition, evidence, control, resources, environment, or perspective. Not every failure is a missing intelligence structure.

**Questions:**

- Can a diagnostic process distinguish data error, bad routing, inadequate compute, policy denial, and genuinely missing capability?
- How should unresolved residuals be represented without premature explanation?
- What is the value of investigating a residual relative to its cost and risk?
- Can residual taxonomies evolve without making historical comparisons meaningless?

**Resolution path:** create labeled fault-injection datasets and measure diagnostic accuracy, cost, and unnecessary growth proposals. **Failure signal:** residual handling becomes a mechanism for relabeling ordinary bugs as architectural innovation.

## Q12 — How can structural growth be distinguished from accumulation? [F/E, P1]

Adding more tools, prompts, or nodes can increase inventory without improving intelligence.

**Questions:** What evidence shows that a new structure improves transfer, composability, robustness, cost, or perceptual reach? When should old structures be consolidated, replaced, or retired? Can growth reduce complexity rather than increase it? How should negative results shape future search?

**Resolution path:** use ablation, out-of-distribution tests, lifecycle cost, and net capability-per-resource measures. **Failure signal:** registry size grows while performance, reliability, or maintainability stagnates.

## Q13 — Can Multi-Intelligence Adversarial Sandbox (MIAS) reliably challenge structural claims? [E/G, P0]

MIAS proposes Builder, Challenger, Independent Evaluator, Formal Checker, and World/Simulation roles, with isolated exploratory and shadow environments.

**Questions:**

1. What constitutes meaningful independence among challenger and evaluator models?
2. How can correlated model errors and shared training data be detected?
3. What balance of formal checks, simulations, empirical tests, and human review is appropriate?
4. How should a sandbox avoid contaminating production state or exposing privileged resources?
5. When is shadow evidence sufficient to justify a separate authorization review?

**Resolution path:** benchmark known defective structures, red-team hidden failure cases, and measure detection sensitivity and false alarms. **Failure signal:** multi-agent agreement is mistaken for independent verification.

## Q14 — Who challenges the evaluator, and when does recursion stop? [F/G/E, P0]

Evaluator governance is a central unresolved problem in recursive self-improvement and Goodhart-resistant scoring.

**Questions:** What triggers an evaluator audit? How are audit budgets, recursion depth, and escalation rules set? Who may change metrics or thresholds? How should disagreements between evaluators be adjudicated? What evidence would demonstrate evaluator capture or reward hacking?

**Resolution path:** staged evaluator-corruption experiments with explicit stop conditions, external holdouts, and pre-registered metrics. **Failure signal:** recursive review adds cost without increasing defect detection or merely moves bias one level upward.

## Q15 — What qualifies as structural counter-evidence? [F/E, P0]

Counter-evidence can undermine applicability, representation, localization, composition, governance, evaluation, or an assumed perspective—not only a final answer.

**Questions:** How should severity, reproducibility, independence, and scope be encoded? When does a single counterexample invalidate a broad claim versus narrow its envelope? Can contradictory evidence be preserved without collapsing into a single misleading score? How should counter-evidence propagate to dependent composites?

**Resolution path:** develop typed counter-evidence records and replayable tests; measure how quickly invalidated claims are detected and quarantined.

## Q16 — Can PIRP/PIRU portability support collective learning without erasing ownership? [A/G/E, P1]

Flexible PIRPs and more formal PIRUs may be exchanged among sovereign BrainUnits, but sharing creates semantic, governance, provenance, and incentive problems.

**Questions:** Which portions of a portable unit may be shared, adapted, or withheld? How do local contexts and policies alter a unit's meaning? How are lineage, licenses, attribution, and revocation represented? Can collective learning remain useful under partial disclosure and heterogeneous trust?

**Resolution path:** multi-organization relay trials with explicit ownership boundaries and provenance checks. **Failure signal:** portability requires hidden centralization or unacceptable disclosure.

## Q17 — When does composition yield a genuine Macro-Intelligence Piece? [F/E, P1]

A large composite is not automatically a higher-order intelligence structure.

**Questions:** Which novel behaviors, transfer properties, or abstractions justify promotion to a macro-node? Can a composite be independently contracted and tested? How do hidden inter-component dependencies affect reuse? What constitutes compositional evidence rather than mere aggregate success?

**Resolution path:** compare composites with their strongest individual components, simple ensembles, and equal-compute baselines. **Failure signal:** claimed emergence disappears after accounting for compute or task decomposition.

## Q18 — What is the Structural Perception Horizon, operationally? [F/X/E, P1]

The **Structural Perception Horizon (SPH)** is proposed as the boundary of distinctions and relations a system can currently represent, detect, and evaluate. It is not directly observable as a single scalar.

**Questions:** Can SPH be approximated through representational probes, discovery tasks, and causal interventions? How do we distinguish new perception from better recall or more compute? How can blind spots be tested without assuming the evaluator already knows all relevant distinctions?

**Resolution path:** synthetic worlds with concealed latent structure, controlled interventions, and blinded external evaluation. **Failure signal:** SPH measures merely reproduce ordinary benchmark accuracy.

## Q19 — What would count as Worldview Reconstruction? [F/X/E, P2]

A **world model** represents states and dynamics; a **worldview** organizes what entities, scales, causal relationships, and perspectives are treated as meaningful.

**Questions:** When does a system revise its ontology rather than extend an existing model? How can a worldview change be compared when old and new concepts are not directly commensurable? Can structural growth produce useful novel scientific questions? How do we detect attractive but false reframings?

**Resolution path:** controlled discovery environments where successful solutions require new latent variables or relational abstractions; test transfer to independent tasks. **Failure signal:** claimed worldview growth is only vocabulary change or post hoc narrative.

## Q20 — How should multi-axis intelligence scaling be measured? [F/E, P1]

Proposed axes include **large structures**, **deep structural granularity**, **precision guidance**, and **major compute investment**, complemented by interoperability, evidence, governance, and collective learning.

**Questions:** Which axes are causally distinct? Where are complementarities, diminishing returns, or negative interactions? Can better localization reduce the compute required for a fixed reliability target? Does deeper structure improve accuracy at the expense of fragility?

**Resolution path:** factorial experiments varying structure size, depth, routing precision, and compute under matched workloads. **Failure signal:** gains attributed to structure are explained entirely by additional resources or data leakage.

## Q21 — What is the value and limit of AI Structural Discovery and Growth? [A/E/G, P2]

SIF suggests a possible **AI Structural Discovery and Growth Stream (AI-SDGS)** alongside AI coding and AI-assisted research/writing.

**Questions:** Which stages of structure discovery can be automated safely? What should remain under human or institutional control? How can search avoid generating plausible but redundant architectures? How can discoveries be reproduced and independently audited?

**Resolution path:** constrained discovery challenges with blinded evaluation and explicit compute budgets. **Failure signal:** automation yields many proposals but few reproducible improvements.

## Q22 — How should Perspective-relative ASI be framed and evaluated? [F/X/G, P2]

A system may be superior within a domain, task distribution, metric, resource budget, time horizon, and governance regime without being universally superior.

**Questions:** Can superiority claims be represented as bounded, revisable tuples rather than a global ranking? How should incomparable objectives and differing human values be handled? What evidence could justify a broader claim, and what would falsify it? How can the framework avoid treating an open future as a guarantee of unlimited progress?

**Resolution path:** publish explicit evaluation envelopes, adversarial counterexamples, and claim revision histories. **Failure signal:** a perspective-qualified label is used to imply unrestricted capability or authority.

---

## Cross-cutting methodological questions

### M01 — Baselines and ablations

For every proposed SIF mechanism, compare against simpler alternatives: direct LLM, standard RAG, conventional tool routing, workflow orchestration, ordinary registries, and equal-budget ensembles. Remove one component at a time. A complex architecture should earn its complexity.

### M02 — Evidence quality and reproducibility

Record datasets, task distributions, model versions, random seeds where applicable, hardware, cost, policies, failure cases, evaluator independence, and confidence intervals. Separate conceptual examples from measured experiments.

### M03 — Distribution shift and adversarial pressure

Test unseen contexts, conflicting contracts, unreliable tools, malicious claims, stale precedents, evaluator drift, and constrained resources. Evaluate whether the system abstains, narrows applicability, or escalates appropriately.

### M04 — Efficiency and net value

Report end-to-end utility, latency, compute, energy where measurable, human review time, registry maintenance, incident cost, and the expense of failed growth attempts. Structural sophistication is not itself an outcome metric.

### M05 — Accountability and human oversight

Define responsibility for registration, evaluation, authorization, revocation, incident response, and external review. Make governance boundaries explicit for federated or sovereign deployments.

### M06 — Open-world uncertainty

Allow the system to say *unknown*, *not yet evaluated*, or *outside the applicability envelope*. Never equate absence of recorded counter-evidence with proof of safety or generality.

---

## Dependency-oriented research roadmap

| Stage | Primary questions | Required deliverable | Exit criterion |
|---|---|---|---|
| **R0 — Definitions** | Q01–Q04, Q11 | Ontology, typed dual-map examples, residual taxonomy | Independent reviewers can apply definitions consistently |
| **R1 — Interoperability** | Q05–Q08, Q16 | Candidate SIC/UNT-R schemas, adapters, negative tests | Cross-implementation tests expose and reject incompatible contracts |
| **R2 — Evidence and governance** | Q09, Q13–Q15 | MIAS harness, evidence schema, authorization boundaries | Known defects are detected and unqualified actions are blocked |
| **R3 — Growth and composition** | Q10, Q12, Q17, Q20 | Precedent-driven growth experiments, macro-node ablations | Reproducible benefit over equal-budget baselines |
| **R4 — Frontiers** | Q18, Q19, Q21, Q22 | Perception/worldview probes and perspective-qualified claims | Novel claims survive blinded, independent evaluation |

The stages are dependency guides, not promises of feasibility or a release schedule. Research may loop backward when counter-evidence invalidates an assumption.

## Minimum evidence package for closing a question

A question should not be marked *resolved* solely because a plausible design exists. Its closure record should include:

1. **Claim and scope:** a precise statement and applicability envelope.
2. **Method:** formal proof, implementation, empirical study, or clearly labeled argument.
3. **Baselines:** appropriate simpler alternatives and ablations.
4. **Counter-evidence:** strongest known failures and unresolved objections.
5. **Independent review:** reproducibility details and evaluator independence where possible.
6. **Decision:** resolved, provisionally supported, narrowed, refuted, or still open.
7. **Lineage:** affected SIF documents, contracts, precedents, and versions.

A provisional answer may generate new questions. Reopening a question in light of better evidence is a feature of the research process, not a defect.

## Connections to the SIF corpus

**Foundations:** `docs/foundations/SIF-001` through `SIF-003`.  
**Functional domains:** `docs/functional-domains/SIF-004` through `SIF-007`.  
**Interoperability:** `docs/interoperability/SIF-008` through `SIF-011`.  
**Validation and evolution:** `docs/validation-and-evolution/SIF-012` through `SIF-014`.  
**Frontiers:** `docs/frontiers/SIF-015` through `SIF-018`.  
**Candidate specifications:** `specifications/SPEC-001` through `SPEC-004`.

Companion research files: `research/TESTABLE-HYPOTHESES.md` and `research/VALIDATION-ROADMAP.md`. These should convert selected open questions into pre-registered experimental claims and staged validation work.

## Closing principle

> An open intelligence framework must preserve the ability to discover not only new answers and new capabilities, but also new reasons why its existing structures, evaluators, and perspectives may be inadequate.

**SIF is an evolving research proposal, not an established universal theory or a certified runtime standard.** Its credibility depends on explicit limits, counter-evidence, and reproducible improvements.
