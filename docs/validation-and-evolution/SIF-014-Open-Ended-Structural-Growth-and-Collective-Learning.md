# SIF-014 — Open-Ended Structural Growth and Collective Learning

**Structural Intelligence Framework (SIF)**  
**Series:** Validation and Evolution · Paper 014  
**Version:** 1.0.0 · Research architecture and testable proposals  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0

> **Central proposition:** Open-ended intelligence growth is not the indefinite accumulation of tools. It is the evidence-governed evolution of the structures by which a system represents problems, locates capabilities, composes intelligence, evaluates outcomes, and learns from other intelligence systems.

## Abstract

Intelligent systems can improve by acquiring additional models, tools, examples, or computational resources. Yet accumulation alone does not explain how an architecture discovers a missing problem representation, revises an inadequate decomposition, replaces an unreliable evaluator, or transfers a validated structural improvement across independently governed systems. The Structural Intelligence Framework (SIF) proposes **open-ended structural growth** as a distinct research direction: a process that can modify not only solutions, but also the intelligence structures used to discover, execute, validate, and govern solutions.

This paper develops a conceptual architecture for connecting residual-based growth, structural precedents, portable intelligence pieces and units (PIRP/PIRU), bidirectional problem–capability mapping, multi-intelligence adversarial validation, and **Collective Structural Learning (CSL)**. It distinguishes individual adaptation from cross-system structural learning, describes growth triggers and candidate lifecycles, proposes a federation-oriented exchange model with explicit ownership and policy boundaries, and identifies mechanisms for negative knowledge, versioned replacement, and higher-order structural composition. We also outline a bounded form of structural recursive self-improvement in which the growth mechanism itself may be revised, but only under independent evaluation and authorization.

Open-endedness is treated as a design commitment to admitting unforeseen structures, not a guarantee of unlimited progress. The paper provides falsifiable hypotheses, operational metrics, failure modes, and a staged validation roadmap. It presents research proposals rather than implemented results or claims of achieved autonomous self-improvement.

**Keywords:** Structural Intelligence Framework; open-ended structural growth; collective structural learning; residual intelligence; structural precedent; PIRP; PIRU; recursive self-improvement; structural counter-evidence; intelligence relay; federated governance.

---

## 1. From Accumulation to Structural Evolution

A conventional capability-growth strategy enlarges a model, adds tools, increases retrieval coverage, or expands a library of reusable workflows. These approaches can be valuable, but they may leave the system's *way of organizing intelligence* unchanged.

SIF distinguishes three growth levels:

1. **Parametric or content growth:** improve weights, examples, memory, prompts, or domain knowledge without changing the governing architecture.
2. **Capability and composition growth:** add or adapt specialized components, routing paths, contracts, and multi-node workflows.
3. **Structural and meta-structural growth:** revise the representation of problems, the capability taxonomy, the control/evaluation machinery, or the mechanisms that discover future improvements.

These levels are complementary rather than mutually exclusive. An LLM may generate candidate structures; optimization may test them; a registry may preserve the results; and a policy authority may decide whether a validated candidate may be deployed.

### 1.1 Open-ended does not mean unbounded

An architecture is *open-ended in principle* if it does not assume that its present inventory of structural types, perspectives, or methods is complete. Practical systems still face finite compute, incomplete observations, incompatible interfaces, safety constraints, and human governance. Therefore:

- The **search space** may admit new structural forms.
- The **active runtime** may admit only approved, compatible forms.
- The **evidence base** may remain incomplete or contested.
- The **growth trajectory** may plateau, regress, or require retirement of earlier structures.

Open-endedness is a property of the research and extension interface, not a prediction of monotonic improvement.

### 1.2 Why growth must be structural

A failed task may not require a stronger general model. It may require a different localization strategy, an explicit world-state representation, a new relay adapter, a corrected scoring objective, or an entirely different problem perspective. SIF treats such failures as potential **structural residuals** rather than automatically as requests for more tokens or parameters.

## 2. The Four Functional Domains as Growth Surfaces

SIF identifies four functional domains. Each is both a source of residuals and a target of evolution.

| Functional domain | Typical growth target | Illustrative residual | Candidate response |
|---|---|---|---|
| Localization and Intelligence Addressing | Representation, retrieval, decomposition, addressing | Relevant capability exists but cannot be found | New MDT branch, CCC signature, relay index, or problem decomposition |
| Per-Node Intelligence | Algorithms, models, tools, specialized units | Existing solver fails a recurring constraint class | New PIRP, optimized PIRU, hybrid solver, or world-model component |
| Universal Control Planes and Scoring/Folding | Policies, scoring structures, evaluation and audit | A metric rewards a misleading proxy | New scoring branch, counter-evidence check, or revised evaluator |
| Residual-Based Structural Growth | Candidate generation, challenge, selection, retirement | Growth process repeatedly proposes brittle structures | Revised trigger, challenger ensemble, or selection protocol |

The fourth domain is reflexive: the growth process can itself be a candidate for growth. This is powerful but creates additional evaluation and governance obligations.

**Cross-cutting infrastructure** includes the Structural Intelligence Registry, Structural Intelligence Runtime, Structural Intelligence Evolution Laboratory, Universal Naming, Typing and Relay (UNT-R), and Structural Intelligence Contracts (SIC). These are architectural roles, not mandatory centralized products.

## 3. What Counts as a Structural Growth Event?

A structural growth event is a documented change to a reusable intelligence structure, its applicability boundary, or its composition and evaluation relationships. Merely generating a different answer is not necessarily structural growth.

### 3.1 Growth event classes

| Event | Description | Minimum evidence question |
|---|---|---|
| **Discovery** | Introduce a previously unregistered structural candidate | What capability or representation is genuinely new? |
| **Specialization** | Create a narrower structure for a context or subdomain | Does it improve the specified context without hiding regressions? |
| **Adaptation** | Modify an existing precedent or unit | Which assumptions and interfaces changed? |
| **Composition** | Join existing units into a reusable higher-order unit | Is the composition better than its parts under matched resources? |
| **Replacement** | Substitute an existing unit or routing policy | Does the replacement preserve required contracts and safety properties? |
| **Branching** | Maintain alternatives for distinct perspectives or policies | Are the branch-selection conditions observable and testable? |
| **Retirement** | Withdraw an obsolete or unsafe structure | Can dependent systems migrate or safely fail closed? |
| **Meta-growth** | Revise a growth, evaluation, or governance mechanism | Who independently evaluates the revised evaluator or generator? |

An event should produce a lineage record, not silently overwrite history.

### 3.2 Growth without novelty inflation

Not every new wrapper, prompt, label, or renamed algorithm merits a new intelligence category. A proposed growth event should be tested against simpler explanations: improved parameter tuning, more compute, better data, a corrected implementation, or a previously overlooked existing precedent. Structural novelty is a comparative claim requiring a baseline.

## 4. Residuals as Growth Triggers

The growth loop begins with a mismatch between the task's required properties and the current architecture's demonstrated capabilities.

SIF-007 proposes a residual taxonomy spanning localization, representation, capability, composition, evidence, control, resource, environment, and perspective. The residual should be retained with its context rather than compressed into a generic failure score.

### 4.1 A candidate trigger record

```yaml
trigger_id: "sif:trigger:illustrative-014-001"
source_problem: "sif:problem:supply-chain-disruption"
residual_type: "composition"
observed_failure: "route planner omitted a dependency between ports"
context_signature:
  geography: "multi-region"
  demand_pattern: "disruption scenario"
current_precedent: "sif:precedent:illustrative-routing-v2"
evidence_refs:
  - "sif:evidence:illustrative-failure-17"
severity: "high"
uncertainty: "causal attribution not yet established"
policy_boundary: "sandbox-only"
next_action: "diagnose-before-generating"
```

*Illustrative schema only; not a normative SIF specification.*

### 4.2 Distinguishing growth from repair

A diagnostic stage should ask whether the residual reflects a bug, missing data, weak localization, invalid assumptions, unsuitable evaluation, or a genuine capability gap. The appropriate remedy may be repair or restriction, not architectural expansion.

### 4.3 Growth triggers beyond failure

Open-ended growth also arises from positive discoveries:

- A new algorithm or hardware capability suggests previously infeasible applications.
- A novel interface permits composition across previously isolated intelligence units.
- A newly observed perspective reveals a task that existing maps did not represent.
- A validated precedent suggests a broader reusable principle.

Thus, growth is not restricted to frontier gap-bridging. It can occur through **new interfaces, substitutions, recombinations, and capability-led problem discovery**.

## 5. The Structural Growth Lifecycle

We propose a nine-stage reference lifecycle:

```text
(1) Observe outcome, context, and structural residual
       |
(2) Diagnose the mismatch and competing explanations
       |
(3) Search precedents and existing capability contracts
       |
(4) Generate candidate repair, adaptation, or new structure
       |
(5) Formalize candidate identity, assumptions, and SIC boundary
       |
(6) Challenge in Multi-Intelligence Adversarial Sandbox (MIAS)
       |
(7) Independently evaluate benefit, cost, and counter-evidence
       |
(8) Decide: reject / revise / shadow / authorize limited deployment
       |
(9) Register outcomes, monitor drift, and relay reusable learning
       +-----------------------> future residuals and revisions
```

**Discovery, validation, and authorization are separate decisions.** A candidate can be interesting yet unsupported, supported in a narrow sandbox yet unauthorized in production, or authorized only under a bounded context.

### 5.1 Candidate selection under multiple objectives

For candidate structure $s$, task context $c$, and resource budget $b$, a research evaluation might compare:

$$
V(s,c,b) = \bigl(Q, R, C, T, I, A\bigr),
$$

where $Q$ is task quality, $R$ robustness, $C$ resource cost, $T$ transferability, $I$ interoperability, and $A$ auditability. These are a **vector of measurements**, not automatically a single scalar utility. A policy authority determines constraints and acceptable trade-offs; the evaluator supplies evidence rather than authorization.

A candidate's improvement claim should compare against matched baselines and disclose additional compute, tools, training, and data.

### 5.2 Negative outcomes remain valuable

Rejected candidates can become **negative structural precedents** with explicit reasons, contexts, and counter-evidence. Such records can prevent repeated rediscovery of the same failure, provided they are not overgeneralized beyond their tested boundaries.

---

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

---

## 6. PIRP, PIRU, and the Path from Exploration to Reuse

**Portable Intelligence Runtime Piece (PIRP)** denotes a flexible intelligence artifact that may be incomplete, provisional, or exploratory. **Portable Intelligence Runtime Unit (PIRU)** denotes a more formally specified and interoperable unit with explicit contracts and validation obligations. The transition is not automatic.

A plausible progression is:

```text
Unstructured insight / discovered residual
             -> candidate PIRP
             -> contextual experiment
             -> explicit SIC and UNT-R identity
             -> adversarial and conformance evaluation
             -> candidate PIRU
             -> bounded authorized deployment
             -> monitored precedent / versioned successor
```

A PIRP may remain useful without ever becoming a PIRU. Conversely, a validated PIRU may later be retired when its context or evidence changes. This avoids treating formalization as a one-way certification of universal validity.

### 6.1 Portability requires boundary preservation

A portable unit must not silently discard the assumptions that made it work. Its contract should carry input/output signatures, semantic type, context preconditions, evidence provenance, known counter-evidence, version, resource envelope, and governance requirements.

### 6.2 Adapters are legitimate structural artifacts

Cross-system relay may require translation of types, units, coordinate systems, trust levels, or context. An adapter can itself be a candidate PIRP/PIRU and should be tested for information loss, authority escalation, and semantic drift.

## 7. Collective Structural Learning: Beyond a Single Intelligence System

Individual structural learning occurs when one system discovers, tests, and incorporates improved structures. **Collective Structural Learning (CSL)** occurs when independently situated systems exchange sufficiently meaningful structural knowledge to improve future reasoning, composition, or evaluation.

The exchange need not expose private data, model weights, or proprietary internals. It may instead transmit contracts, abstract structural signatures, reproducible evaluation protocols, permitted evidence summaries, adapters, or negative precedents.

### 7.1 Four levels of collective learning

1. **Outcome exchange:** share a result or observation without a reusable structural account.
2. **Precedent exchange:** share the context, approach, evidence, and failure boundaries of an application.
3. **Portable structural exchange:** share a PIRP/PIRU, adapter, contract, or reproducible composition pattern.
4. **Meta-structural exchange:** share a validated change to discovery, evaluation, governance, or problem-representation processes.

Higher levels may create more reusable intelligence, but also require stronger provenance, compatibility, and governance.

### 7.2 Collective learning is not unrestricted synchronization

Different BrainUnits or organizations may have distinct ownership, policies, contexts, or geopolitical constraints. A structural relay should support **selective publication, selective acceptance, local validation, and local authority**. Global consistency is not assumed.

A recipient can adopt, adapt, reject, or quarantine an incoming precedent. The source's validation result does not automatically transfer across domains or legal boundaries.

### 7.3 A federation-oriented relay pattern

```text
System A                            Shared / mediated relay                     System B
--------                            -----------------------                     --------
Local residual -> Candidate PIRP -> Contract + provenance + evidence summary -> Local discovery
Local MIAS      -> Validated case  -> Context / counter-evidence / limitations -> Local compatibility
Local policy    -> Share decision  -> Versioned signed reference (optional)  -> Local MIAS
                                                                             -> Local policy
                                                                             -> Adopt / adapt / reject
```

A relay can use centralized, federated, or peer-to-peer implementations. SIF does not prescribe a single infrastructure topology.

---

![Fig-004-Universal-Contracts-and-Relay.png](../../figures/Fig-004-Universal-Contracts-and-Relay.png)

---

## 8. Structural Precedent Registry as Collective Memory

The Structural Precedent Registry (SPR) records what was tried, under which conditions, with which evidence, and with what outcomes. In collective learning, a registry is not merely a catalog of successful techniques. It also stores **failed adaptations, disputed evidence, withdrawn claims, incompatible versions, and context-specific exceptions**.

A minimal collective precedent exchange record may contain:

| Field | Purpose |
|---|---|
| Stable identity and version | Avoid ambiguous or overwritten references |
| Structural claim and capability signature | Explain what is proposed for reuse |
| Applicability context | Delimit where the claim was evaluated |
| Contract and relay requirements | Support compatibility checking |
| Evidence and counter-evidence references | Make claims contestable |
| Provenance and evaluation independence | Identify how evidence was obtained |
| Policy, license, and disclosure permissions | Preserve governance and ownership boundaries |
| Lineage, supersession, and revocation | Support repair and retirement |

The registry should distinguish **claims**, **observations**, **evaluations**, and **authorizations**. Their provenance and status may differ.

### 8.1 Precedent transfer is a hypothesis

A structural precedent successful in one environment is a candidate for transfer, not proof of universal applicability. Recipient-side tests should examine covariate shift, hidden assumptions, changed resource budgets, and interface semantics.

### 8.2 Negative knowledge and anti-repeat mechanisms

If a candidate repeatedly fails under a specific context, the registry can warn against uncritical reuse. Negative precedents should include confidence and scope: a failed test does not imply failure in all settings.

---

![Fig-005-Structural-Precedent-Intelligence.png](../../figures/Fig-005-Structural-Precedent-Intelligence.png)

---

## 9. Dual Maps and Bidirectional Growth

SIF-008 distinguishes:

- **Structural Problem-Solving Map (PSM):** what must be achieved, under which constraints and dependencies.
- **Structural Capability Map (SCM):** which capabilities exist, their interfaces, evidence, and compositional relationships.

**Bidirectional Structural Intelligence Mapping (BSIM)** connects the two maps through matching, precedents, adaptation, and residual diagnosis.

### 9.1 Problem-driven growth

A new task exposes a missing or weak capability. The system diagnoses the residual, searches precedents, proposes a candidate, and validates it. A successful candidate updates the SCM and relevant problem mappings.

### 9.2 Capability-driven growth

A new algorithm, relay adapter, or hardware platform expands the SCM. Reverse mapping asks which previously infeasible or unrecognized tasks become plausible. Candidate tasks are then validated and added to the PSM where justified.

### 9.3 Perspective-driven growth

A new representation may reveal that both maps were incomplete. For example, a supply-chain problem originally represented as route optimization may need to be reframed as a coupled resilience, policy, and inventory-control problem. This is not simply another solver; it is a change in what the system recognizes as the problem.

**The two maps must remain revisable.** Otherwise an ostensibly open architecture can become trapped by a closed taxonomy of problems and capabilities.

---

![Fig-003-Problem-Capability-Dual-Maps.png](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

## 10. Structural Recursive Self-Improvement with Bounded Governance

Structural recursive self-improvement (structural RSI) is a research hypothesis in which the architecture can propose improvements to components of its own intelligence-growth machinery: residual detectors, candidate generators, search strategies, evaluators, or relay policies.

The key risk is **self-confirmation**: a modified generator and its modified evaluator may jointly report progress while drifting away from the intended objective.

### 10.1 Separate improvement targets from approval rights

A growth candidate may target:

- A task solver or specialized PIRU.
- A localization or decomposition mechanism.
- A precedent retrieval or scoring function.
- An adversarial challenger or evaluator.
- A structural growth trigger or selection policy.

But a candidate's ability to modify a component does not grant authority to deploy that modification. The policy and authorization plane must remain separately controlled, and evaluator independence must be examined.

### 10.2 Bounded recursive evaluation

A practical evaluator challenge protocol can impose limits on challenge depth, compute budget, risk tier, independence criteria, and unresolved uncertainty. Failure to settle a dispute should produce a documented *unresolved* status, not forced consensus.

### 10.3 Meta-growth should be held to stronger baselines

Changes to evaluators and growth machinery have system-wide effects. They require more stringent longitudinal tests, replay of archived negative precedents, and rollback plans than a narrow local solver improvement.

## 11. Multi-Intelligence Adversarial Validation

The **Multi-Intelligence Adversarial Sandbox (MIAS)** is SIF's proposed laboratory for testing structural claims. Candidate roles include Builder, Challenger, Independent Evaluator, World/Simulation Engine, and Formal Checker. These roles may be implemented by different models, deterministic programs, humans, or combinations thereof.

### 11.1 Test the claim, not merely the output

A validation plan should test:

1. Task-level quality against baselines.
2. Structural assumptions and applicability boundaries.
3. Robustness to perturbations and distribution shift.
4. Contract conformance and relay semantics.
5. Compositional failure and error propagation.
6. Evidence provenance and evaluator independence.
7. Resource cost and operational feasibility.
8. Governance, authorization, and rollback behavior.

### 11.2 Three deployment boundaries

**Exploratory Sandbox** permits bounded experimentation without production authority. **Validated Shadow Runtime** permits non-authoritative observation against realistic inputs. **Authorized Production Runtime** permits only actions allowed by the relevant policy and contract. Passing one boundary does not automatically grant access to the next.

### 11.3 Structural counter-evidence as a growth resource

A challenger may expose a broken assumption, a misleading evaluator, or an unmodeled dependency. Such evidence should be retained in the registry and used to narrow, repair, or retire the claim. A system that deletes its negative cases cannot learn reliably from structural failure.

---

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

--

## 12. Scaling, Higher-Order Structures, and the Perception Horizon

Open-ended structural growth may operate along several axes:

| Axis | Research question |
|---|---|
| **Large structures** | Can more components be coordinated without combinatorial collapse? |
| **Structural depth** | Can deeper decompositions improve diagnosis without losing global coherence? |
| **Precision guidance** | Can localization, scoring, and policy direct compute to consequential subproblems? |
| **Compute investment** | When is additional computation justified by measured marginal value? |
| **Interoperability** | Can heterogeneous units compose while preserving meaning and authority? |
| **Evidence quality** | Can adversarial validation prevent accumulation of fragile structures? |
| **Collective relay** | Can validated structures transfer across organizational and contextual boundaries? |

### 12.1 Macro-Intelligence Pieces

A validated composition may be folded into a reusable **Macro-Intelligence Piece** with its own contract, evidence, and failure boundary. A former multi-stage system can become a node in a higher-order system. Folding must not erase the ability to inspect relevant internal evidence or unfold when a failure requires diagnosis.

### 12.2 Structural Perception Horizon

A system's **Structural Perception Horizon** is the boundary of distinctions, dependencies, and failure modes it can currently represent, detect, and evaluate. Growth may extend this horizon by introducing new representations or perspectives. This is a hypothesis to measure, not an assertion that scale automatically produces superior understanding.

### 12.3 World Model versus Worldview

A **World Model** represents states, dynamics, or causal relations in a modeled environment. A **Worldview**, in the narrower SIF research sense, concerns which perspectives, distinctions, scales, and causal questions the architecture considers salient. Structural growth may revise either or both; neither should be assumed complete.

---

![Fig-008-Perception-Horizon-and-Worldview-Growth.png](../../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png)

---

## 13. Illustrative Case: Federated Supply-Chain Resilience

Consider three independently governed participants: a logistics planner, a manufacturing scheduler, and a disruption simulation service.

**Initial condition.** The planner can optimize routes, and the scheduler can optimize production, but their combined workflow fails under port closures because the relay omits time-dependent inventory constraints.

**Residual diagnosis.** MIAS testing distinguishes a composition residual from a pure optimization failure. The existing solver is not necessarily defective; the shared representation is incomplete.

**Candidate generation.** A builder proposes a PIRP that translates shipment delays into inventory-feasibility constraints. The candidate includes an explicit SIC and provenance for the assumed time units, data freshness, and policy boundary.

**Adversarial challenge.** A challenger introduces asynchronous updates, stale data, and correlated port closures. An independent evaluator compares the new composition against the original workflow and a simpler hand-coded adapter.

**Local validation.** The manufacturing participant evaluates the candidate under its own operational constraints. A positive result in the logistics sandbox is not sufficient for local authorization.

**Collective learning.** The participants exchange a limited structural precedent and contract metadata rather than raw proprietary inventory data. A second manufacturing site can reproduce the test and report both positive and negative evidence.

**Higher-order growth.** If sufficiently validated, the combined resilience workflow becomes a bounded Macro-Intelligence Piece. Its contract retains the conditions under which the composition is trustworthy.

This case is illustrative. No implementation, measured performance gain, or operational deployment is claimed.

## 14. Failure Modes and Design Safeguards

| Failure mode | Why it matters | Proposed safeguard |
|---|---|---|
| Tool accumulation masquerading as growth | Larger inventories may not improve structural problem solving | Require structural baselines and ablation |
| Novelty inflation | Cosmetic changes overwhelm the registry | Distinguish structural changes from parameter and data changes |
| Cross-context overgeneralization | A precedent's assumptions fail after transfer | Recipient-side applicability tests |
| Registry contamination | Unsupported claims spread through collective relay | Provenance, counter-evidence, trust boundaries |
| Evaluator collusion or common-mode bias | Candidate and evaluator share blind spots | Heterogeneous challenge and independent checks |
| Goodhart-driven optimization | Proxy scores improve while intended outcomes worsen | Multi-objective evaluation and held-out adversarial tests |
| Semantic loss in relay | Units exchange syntactically valid but incorrect meanings | Typed contracts, semantic conformance, context checks |
| Uncontrolled recursive change | Growth machinery weakens its own safeguards | Separate policy authority, bounded meta-growth, rollback |
| Excessive coordination cost | Collective intelligence becomes slower or less reliable | Cost-aware dispatch and selective relay |
| Privacy or ownership leakage | Structural sharing reveals sensitive context | Data minimization, permissions, local validation |
| Fossilized negative precedents | Past failures block valid future innovation | Versioned scope, expiry, re-evaluation triggers |
| Worldview lock-in | Existing maps exclude unanticipated problems | Perspective challenges and open residual categories |

## 15. Testable Research Hypotheses

The following hypotheses are proposals for empirical study, not established findings.

**H1 — Residual specificity.** Systems that retain typed structural residuals will identify appropriate repairs or growth candidates more accurately than systems using undifferentiated failure labels.

**H2 — Precedent reuse.** A context- and evidence-aware precedent registry will reduce repeated unsuccessful candidate generation relative to a capability catalog without negative cases.

**H3 — Contracted portability.** PIRU-style explicit contracts will reduce cross-system relay failures compared with payload-only integration, controlling for implementation effort.

**H4 — Bidirectional discovery.** Capability-to-problem reverse mapping will identify additional valid applications beyond problem-driven matching alone, at an acceptable false-discovery cost.

**H5 — Collective transfer.** Sharing validated structural precedents will improve recipient task performance or reduce adaptation cost compared with outcome-only sharing, under matched information budgets.

**H6 — Counter-evidence retention.** Preserving structural counter-evidence will improve robustness under distribution shift compared with retaining only successful precedents.

**H7 — Adversarial governance.** MIAS with independent evaluator challenge will detect more structurally invalid candidates than outcome-only benchmarking, at measurable additional cost.

**H8 — Higher-order composition.** Contracted Macro-Intelligence Pieces will improve reuse or coordination efficiency without unacceptable loss of auditability compared with ad hoc compositions.

**H9 — Meta-growth controls.** Bounded, independently evaluated changes to growth machinery will exhibit fewer harmful regressions than self-evaluated unrestricted changes in a controlled experimental setting.

**H10 — Perception expansion.** Adding a new structural representation will improve detection of previously unmodeled dependency classes, measured against independently constructed ground truth.

## 16. Measurement and Experimental Design

### 16.1 Suggested metrics

| Construct | Possible operational metric |
|---|---|
| Structural improvement | Task quality gain under matched compute and data |
| Residual diagnosis | Correct residual-type classification; causal diagnosis precision |
| Reuse | Successful cross-context transfers / attempted transfers |
| Negative knowledge | Avoided repeated failures and false rejection rate |
| Interoperability | Contract conformance and semantic relay error rate |
| Collective learning | Transfer gain, adaptation cost, provenance completeness |
| Growth efficiency | Validated improvements per unit of experiment budget |
| Robustness | Worst-case and out-of-distribution performance |
| Evaluator integrity | Detected proxy gaming, challenge coverage, independence audit |
| Governance | Unauthorized action rate, rollback time, policy conformance |
| Perception horizon | Detection rate for held-out structural dependency classes |

Metrics must be interpreted jointly. For example, maximizing the number of discovered structures may reward low-quality novelty; maximizing transfer acceptance may reward unsafe overgeneralization.

### 16.2 Experimental controls

A credible experiment should pre-register evaluation criteria where feasible, use held-out contexts, distinguish model improvements from structural changes, control compute and human intervention, include ablations, preserve failed cases, and report uncertainty. Simulated environments should be complemented with real-world validation only where permissions and safety conditions permit.

### 16.3 Proposed baselines

- Single general-purpose LLM or agent without structural registry.
- Tool-augmented agent with a flat capability catalog.
- Workflow composition without typed SIC boundaries.
- Registry with successful cases only.
- Registry with positive and negative cases but no collective relay.
- Collective relay without recipient-side adversarial validation.

No baseline should be deliberately handicapped; each should receive a fair resource and information budget.

## 17. Staged Validation Roadmap

**Phase 1 — Controlled residual benchmark.** Construct tasks with known localization, composition, and representation failures. Measure diagnosis and repair selection against flat-error baselines.

**Phase 2 — Portable unit and precedent exchange.** Implement a small candidate SIC/PIRP/PIRU protocol and test cross-context transfer, versioning, and semantic compatibility.

**Phase 3 — Multi-intelligence adversarial laboratory.** Compare builder-only and builder–challenger–independent-evaluator regimes; record cost, counter-evidence, and false acceptance.

**Phase 4 — Federated collective learning.** Run multiple independently governed simulated BrainUnits that exchange selected precedents. Measure transfer gains and boundary violations.

**Phase 5 — Bounded meta-growth and perception tests.** Permit controlled revisions to a search or evaluation component, with independent tests and rollback. Evaluate whether new representations detect held-out dependencies.

Advancement between phases should be evidence-gated. Failure at an earlier phase is useful evidence for revising the architecture rather than a reason to assume later benefits.

## 18. Open Research Questions

1. How can structural novelty be defined without relying on a single closed ontology?
2. Which residual categories are stable across domains, and which require local extensions?
3. What is the smallest portable contract that preserves essential context and evidence?
4. How can independently governed systems exchange negative precedents without exposing sensitive data?
5. When does a composed Macro-Intelligence Piece merit treatment as a distinct reusable unit?
6. How should contradictory precedents be ranked without hiding minority or counter-evidence perspectives?
7. How can the system detect that its evaluator, rather than its solver, is the source of a failure?
8. What limits on recursive evaluator challenge provide useful assurance without prohibitive cost?
9. How should registry trust, licensing, ownership, and revocation work across federated participants?
10. Can a measurable structural perception horizon be defined independently of a particular model's vocabulary?
11. Under what conditions does collective structural learning outperform local learning after coordination costs?
12. What evidence would falsify the hypothesis that structural growth contributes beyond scaling model parameters and compute?

## 19. Conclusion

SIF proposes a shift from intelligence as an isolated model or an expanding tool inventory toward intelligence as an **open, evidence-governed structural ecosystem**. Its growth process is driven by diagnosed residuals and positive discoveries; its reusable artifacts are documented through precedents and portable contracts; its transfer mechanism relies on selective relay and recipient-side validation; and its governance separates exploration, evaluation, and authorized action.

Collective Structural Learning extends this process beyond the individual system. The central promise is not that all participants converge on one universal intelligence architecture. It is that independently governed participants can exchange tested structural knowledge while preserving local context, authority, and the right to disagree, adapt, or reject.

The deepest research possibility is reflexive: structural growth may improve not only a solver but also the architecture's ability to identify problems, challenge assumptions, and discover new perspectives. That possibility remains a testable hypothesis, not an accomplished result.

> **Open structural intelligence grows when a system can revise what it knows how to do, how it knows where to do it, and how it knows whether the change deserves to survive.**

---

## Relationship to Other SIF Documents

- **SIF-001:** From Isolated Intelligence to Open Structural Intelligence — overall motivation and architecture.
- **SIF-002:** Four Functional Domains of Structural Intelligence — functional growth surfaces.
- **SIF-003:** Structural Precedents and Open Intelligence Evolution — precedent reasoning and applicability.
- **SIF-007:** Residual-Based Structural Growth — residual taxonomy and candidate lifecycle.
- **SIF-008:** Dual Maps and Bidirectional Structural Mapping — problem- and capability-driven discovery.
- **SIF-009:** Structural Precedent Registry — versioned cases, evidence, and lineage.
- **SIF-010:** Universal Naming, Typing, and Relay — cross-system identity and relay.
- **SIF-011:** Structural Intelligence Contracts and Portable Units — SIC, PIRP, and PIRU.
- **SIF-012:** Multi-Intelligence Adversarial Sandbox — experimental challenge architecture.
- **SIF-013:** Structural Counter-Evidence and Evaluator Governance — falsification and control boundaries.
- **SIF-015 (planned):** Structural Perception Horizon and Worldview Growth — perspective evolution.
- **SIF-016 (planned):** Macro-Intelligence Pieces and Higher-Order Structures — structural composition.
- **SPEC-004 (planned):** Sandbox Evidence and Growth Lifecycle — candidate operational specification.

---

*Research status: Conceptual framework, candidate mechanisms, and falsifiable proposals. No experimental results, formal safety guarantees, or autonomous open-ended growth achievement are claimed.*
