# SIF-008 — Dual Maps and Bidirectional Structural Mapping

**Structural Intelligence Framework (SIF)**  
**Series:** Interoperability · Paper 008  
**Version:** 1.0.0 (research architecture)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual framework and testable design; not an implemented interoperability standard  
**License:** Apache-2.0

## Abstract

An intelligence system cannot reliably compose its capabilities unless it can describe both the problems it faces and the capabilities it possesses. This paper proposes **Dual Maps**: a **Structural Problem-Solving Map (PSM)** representing demands, constraints, dependencies, and success conditions, and a **Structural Capability Map (SCM)** representing available intelligence structures, contracts, applicability conditions, and evidence. **Bidirectional Structural Intelligence Mapping (BSIM)** connects these maps. Demand-to-capability mapping locates, adapts, and composes existing intelligence; capability-to-demand mapping discovers additional uses, unmet needs, and new problem formulations. The maps are dynamic, perspective-dependent, and governed by evidence and policy rather than treated as universal taxonomies. We define graph semantics, matching outcomes, a bounded mapping algorithm, structural residuals, registry and relay integration, and a validation program. The central claim is architectural: separating what a system needs from what it can do makes reuse, accountability, and structural growth more explicit and testable. It does not guarantee optimal matching, general intelligence, or autonomous correctness.

**Keywords:** Structural Intelligence Framework; Dual Maps; BSIM; Task CallingGraph; Action CallingGraph; structural localization; capability registry; structural precedent; intelligence relay; counter-evidence; open-ended growth.

---

![Problem–Capability Dual Maps](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)

---

## 1. The interoperability problem

A conventional system may expose tools through names and APIs yet still lack a reliable account of *when* to use them. A task planner may specify desired outcomes but have no dependable representation of available solvers. A model can generate a plausible tool call while overlooking assumptions, permissions, evidence quality, or alternatives.

SIF treats this as a structural mapping problem:

- **Demand side:** What must be established, decided, predicted, transformed, or executed—and under which constraints?
- **Supply side:** What intelligence structures are available, under which conditions, with what evidence and permissions?
- **Mapping:** Which candidate structures can address which demands, alone or in composition, and what remains unresolved?

The separation is analogous to—but broader than—the distinction between a **Task CallingGraph** and an **Action CallingGraph**. A task graph encodes required work; an action graph encodes executable capabilities and their composition. Neither graph alone determines a valid solution.

**Design proposition:** An open intelligence architecture needs a first-class, inspectable relationship between its problem structures and capability structures.

## 2. Definitions and notation

### 2.1 Structural Problem-Solving Map (PSM)

Let the PSM be a typed, attributed graph:

\[
P = (V_P, E_P, A_P).
\]

A problem node represents a demand, subproblem, hypothesis, decision, observation, verification obligation, or outcome. Its attributes may include:

- Stable identity, semantic type, and version.
- Goal and required output or effect.
- Inputs, preconditions, and contextual assumptions.
- Dependencies, temporal order, and causal relationships.
- Quality thresholds, cost/latency limits, and risk tolerance.
- Evidence requirements, provenance, and failure conditions.
- Authorized scope of action and escalation requirements.

Edges may encode decomposition, prerequisite, alternative, temporal ordering, data flow, constraint propagation, or conditional branching. A PSM can be hierarchical and may contain uncertain or competing decompositions; it is not required to be a single tree.

### 2.2 Structural Capability Map (SCM)

Let the SCM be a typed, attributed graph:

\[
C = (V_C, E_C, A_C).
\]

A capability node represents an LLM, rule engine, CCC transformation, MDT locator, optimizer, simulation, world model, verifier, human decision function, composite service, or other intelligence piece. Attributes may include:

- Identity, type, version, ownership, and invocation endpoint.
- Input/output contracts, semantics, and preconditions.
- Applicable contexts, granularity, and perspective.
- Evidence of performance and known counter-evidence.
- Dependencies, resource requirements, and expected cost.
- Policy constraints, authorization boundaries, and audit hooks.
- Adaptation, composition, delegation, and growth interfaces.

Edges express composition, substitution, dependency, relay compatibility, provenance, specialization, and validated equivalence. A **Macro-Intelligence Piece** may appear as one SCM node while retaining an expandable internal graph.

### 2.3 Mapping relation

A mapping is not merely a string similarity score. Define a candidate relation:

\[
M \subseteq V_P \times 2^{V_C} \times \mathcal{K},
\]

where a problem node may map to a *set or subgraph* of capabilities, and \(\mathcal{K}\) holds contextual conditions, adaptations, evidence, and governance decisions. The relation may be one-to-one, one-to-many, many-to-one, or absent.

For a candidate mapping \(m\), define an assessment vector:

\[
Q(m) = (f, e, r, k, a, u),
\]

with **fitness** \(f\), **evidence strength** \(e\), **risk** \(r\), **resource cost** \(k\), **authorization status** \(a\), and **unresolved uncertainty** \(u\). This is a vector, not an automatic scalar score: policy and safety constraints may be non-compensatory.

## 3. Two directions of structural mapping

### 3.1 Demand → capability

Given a problem or subproblem, locate possible intelligence structures:

1. Parse and type the demand without discarding important context.
2. Search the Structural Precedent Registry and SCM for candidate structures.
3. Check semantic compatibility, assumptions, and contract signatures.
4. Explore direct reuse, parameterization, adaptation, or composition.
5. Compare evidence, counter-evidence, resource demands, and policy limits.
6. Produce a candidate solution graph, an explicit residual, or a request for clarification.

This is the **localization-and-composition direction**. It can use LLM semantic interpretation, CCC/MDT structural retrieval, two-phase search, rules, constraint solvers, and specialized matchers. No single matcher is privileged in every context.

### 3.2 Capability → demand

Given a new or underused capability, explore where it might apply:

1. Read its declared semantics, assumptions, and validated behaviors.
2. Search existing demands, unresolved residuals, and historical failure cases.
3. Generate plausible alternative problem formulations or applications.
4. Test transfer across contexts, granularity levels, and perspectives.
5. Record supported uses, unsupported analogies, and open questions.

This is the **opportunity-discovery direction**. It is especially important when a new algorithm, tool, world model, PIRP/PIRU, or composite intelligence becomes available. It should not confuse hypothetical applications with validated ones.

### 3.3 Why bidirectionality matters

One-way tool selection assumes the set of problems is already adequately expressed. One-way capability discovery assumes tools alone define valuable work. BSIM instead supports a feedback loop:

**New problem → candidate capability → evidence or residual → new/modified capability → newly visible problem.**

The feedback can expose previously invisible needs. It can also amplify spurious matches; evidence and counter-evidence are therefore essential.

## 4. Structural mapping outcomes

A mapping attempt should produce a typed result rather than only a success/failure boolean.

| Outcome | Meaning | Typical next step |
|---|---|---|
| **Exact precedent reuse** | Validated structure applies within recorded assumptions | Invoke if authorized |
| **Parameterized reuse** | Same structure applies after bounded configuration | Check parameter contract |
| **Adapted precedent** | Structure requires transformation or contextualization | Sandbox validation |
| **Composed solution** | Multiple capabilities jointly cover the demand | Validate interfaces and emergent interactions |
| **Partial coverage** | Some requirements are met; a residual remains | Record and route residual |
| **Conflicting candidates** | Multiple mappings disagree materially | Compare evidence and challenge evaluators |
| **Unsupported match** | Similarity exists without justified applicability | Reject or research |
| **Policy-blocked match** | Technically feasible but unauthorized | Escalate or select permissible alternative |
| **Unresolved demand** | No credible candidate found | Structural growth or human review |

An *unresolved demand* is not proof that a new capability is necessary; the map may be incomplete, the query poorly specified, or the relevant capability undiscovered.

## 5. Structural precedent as the bridge

A **Structural Precedent** is a versioned record of a prior problem–capability relationship, including both successes and failures. Its useful content extends beyond the output:

- Problem signature and context.
- Capability graph and version used.
- Applicability boundaries and adaptations.
- Measured outcomes and confidence limits.
- Counter-evidence, known failure modes, and invalidated assumptions.
- Governance decisions and deployment history.

A precedent supports analogical retrieval but does not establish universal validity. As in legal reasoning, a precedent may be **followed**, **distinguished**, **limited**, or **overturned** when circumstances differ or stronger evidence appears. The analogy concerns disciplined reuse and exception handling, not the authority of legal institutions.

The Structural Precedent Registry, detailed in **SIF-009**, can index both sides of the relation. An SCM-only registry knows what exists; a precedent registry also records *what it has been shown to do, under what conditions*.

## 6. Universal naming, typing, relay, and contracts

Bidirectional maps become operational only if their nodes can be identified and connected across systems. SIF therefore proposes **Universal Naming, Typing and Relay (UNT-R)** as a candidate interoperability layer:

**Naming** supplies stable identities and versions. **Typing** captures semantic and interface constraints. **Relay** transfers tasks, context, evidence, and results between heterogeneous structures.

The **Structural Intelligence Contract (SIC)** binds these to execution and governance. A minimal mapping-relevant contract should declare:

| Field | Purpose |
|---|---|
| `id`, `version`, `type` | Resolve identity and interpretation |
| `capabilities` | Describe supported functions and limitations |
| `input`, `output` | Declare signatures and invariants |
| `context` | State assumptions and applicability boundaries |
| `relay` | Specify invocation and handoff protocol |
| `evidence` | Link validation records and uncertainty |
| `counter_evidence` | Link failures and challenges |
| `policy` | Declare authority and prohibited actions |
| `resources` | Estimate cost, latency, and resource needs |
| `growth_hooks` | Expose adaptation or candidate-improvement routes |

These are **proposed research fields**, not a finalized interoperable schema. Existing services can join through adapters; the goal is to standardize *contracts*, not force all intelligence into one internal representation. **SIF-010**, **SIF-011**, and **SPEC-001/002** develop this proposal.

## 7. A bounded BSIM procedure

The following procedure is architectural pseudocode, not a production algorithm.

```text
INPUT: Problem map P, capability map C, precedent registry R,
       policy G, evidence requirements E, resource budget B
OUTPUT: Candidate mapping graph M, unresolved residuals U,
        evidence trace T, authorization status A

1. Normalize and type problem nodes; preserve original context.
2. Decompose only where decomposition is justified and useful.
3. For each unresolved demand p in P:
     a. Retrieve candidate precedents and capabilities from R and C.
     b. Filter incompatible signatures and violated hard constraints.
     c. Propose direct, adapted, or composed mappings.
     d. Attach supporting and contradicting evidence.
     e. Estimate uncertainty, risk, resource usage, and coverage.
     f. Challenge high-impact or weakly supported mappings.
     g. Select a bounded candidate set; record unresolved residuals.
4. Verify cross-node dataflow, semantics, dependencies, and authority.
5. If evidence is insufficient, route to sandbox, shadow test,
   human review, or a structural growth proposal.
6. Return M, U, T, A. Never equate scoring with authorization.
```

The reverse direction uses capability nodes as seeds, retrieves potentially relevant demands, generates candidate applications, and subjects them to the same evidence and policy checks. Both directions need explicit stopping criteria; otherwise recursive exploration can consume unbounded resources.

### 7.1 Matching is not authorization

A candidate may be semantically excellent yet prohibited by policy, privacy, ownership, safety, or resource limits. SIF separates:

1. **Candidate generation:** What might work?
2. **Evaluation:** What evidence suggests it will work?
3. **Authorization:** What is permitted to run, by whom, and under which conditions?

A score cannot grant authority. This separation is developed in **SIF-006**.

### 7.2 Partial target and two-phase search

The PSM may be only partially specified. **Phase 1** can perform broad, inexpensive localization; **Phase 2** can use stronger evidence, deeper computation, or specialized verification on shortlisted candidates. This improves tractability in some workloads but can fail if early pruning removes the correct candidate. Validation must measure both cost and recall.

## 8. Composition, hierarchy, and perspective

### 8.1 Composition across nodes

A valid local match does not guarantee a valid composed solution. Interfaces may align syntactically while disagreeing about units, temporal scope, causal assumptions, or uncertainty. BSIM should therefore verify **cross-node invariants** and preserve provenance at relay boundaries.

### 8.2 Folding and macro-intelligence

A validated subgraph may be **folded** into a reusable macro-node. Folding reduces repeated planning and execution overhead, but it can conceal internal assumptions. The contract must retain enough evidence and **unfolding hooks** to inspect or challenge the macro-node when circumstances change.

### 8.3 Multiple perspectives

A demand can be represented through operational, mathematical, causal, economic, legal, or other perspectives. A capability can likewise have multiple classifications. The PSM and SCM should therefore support **perspective-indexed views** rather than one permanent taxonomy. Disagreement between views may reveal an important residual, not merely noise.

## 9. Residuals as mapping diagnostics

BSIM exposes several distinguishable failure types:

| Residual | Example | Research response |
|---|---|---|
| Localization | Relevant capability exists but was not retrieved | Improve indexing or routing |
| Representation | Demand cannot be expressed with available types | Extend semantic representation |
| Capability | No known structure meets the requirement | Discover or adapt capability |
| Composition | Components work separately but not together | Improve relay or invariants |
| Evidence | Candidate appears suitable but lacks validation | Test and gather counter-evidence |
| Control | Candidate is effective but unauthorized | Change workflow, not bypass policy |
| Resource | Feasible mapping exceeds budget | Optimize, fold, or defer |
| Perspective | Important distinctions are absent from the maps | Introduce a new view or world model |

Residual classification is provisional and may change after investigation. **SIF-007** defines the broader residual-based growth lifecycle.

## 10. Adversarial validation and evaluator governance

A mapping system risks Goodhart effects: optimizing retrieval precision on a benchmark may reward superficial signatures; optimizing tool success may conceal costly failures. The **Multi-Intelligence Adversarial Sandbox (MIAS)** should test:

- **Builder:** Proposes mapping and composition.
- **Challenger:** Constructs near misses, changed contexts, and adversarial demands.
- **Independent evaluator:** Measures success using criteria not fully controlled by the builder.
- **World/simulation or formal verifier:** Checks dynamics, constraints, or invariants where available.
- **Governance function:** Controls which results may enter shadow or production use.

Challenge the **evaluator** as well as the candidate mapping: Does the metric miss distribution shifts, unobserved harms, long-term consequences, or context leakage? Recursive challenges must be bounded by risk and resources. Sandbox validation can strengthen confidence but cannot prove complete correctness across all future contexts.

## 11. Conceptual case: supply-chain disruption response

Consider a company facing a supplier outage. Its PSM contains nodes for detecting disruption, estimating inventory exposure, forecasting demand, generating feasible alternative sourcing plans, comparing costs and service levels, verifying constraints, and authorizing procurement changes.

The SCM contains a monitoring classifier, an LLM analyst, a time-series forecaster, an optimization solver, a policy rules engine, and a simulation service.

**Demand → capability:** The system maps inventory exposure to database/analytical tools, forecasting to a time-series model, alternative plans to an optimizer, and feasibility checks to rules and simulation. An LLM can interpret ambiguous reports but should not substitute for constraint verification.

**Capability → demand:** A newly added simulation service may reveal that the organization can now test multi-week disruption scenarios previously treated only qualitatively. That is a candidate new problem-solving opportunity, not a validated benefit until tested.

**Residual:** The optimizer assumes stable lead times, but observed transportation conditions violate that assumption. The failure should be recorded as a contextual counterexample, not averaged away as a low score.

**Governance:** Even a high-scoring procurement plan remains a recommendation until an authorized actor or approved control process permits execution.

This example illustrates mapping semantics; it is not evidence of deployed performance.

## 12. Relationship to SIF's four functional domains

| SIF domain | Role in Dual Maps |
|---|---|
| **Localization** | Finds candidate nodes and routes from problem to capability |
| **Per-Node Intelligence** | Supplies heterogeneous executable and evaluative functions |
| **Control Planes / Scoring / Folding** | Governs selection, comparison, authorization, and abstraction |
| **Residual-Based Growth** | Converts unsupported mappings and failures into research candidates |

The domains are **functional roles**, not isolated layers. For example, an LLM may help type a problem, implement a node, critique evidence, and propose new structures. Its role must be identified per operation.

The three complementary SIF engineering systems are: **Structural Intelligence Registry** (what exists and what evidence supports it), **Structural Intelligence Runtime** (how it is composed and executed), and **Structural Intelligence Evolution Laboratory** (how candidates are challenged, improved, and admitted). Dual Maps span all three.

## 13. Testable hypotheses

The following hypotheses are proposals requiring controlled studies:

**H1 — Coverage:** Compared with a single flat tool list, Dual Maps increase the proportion of multi-step demands for which a semantically valid capability composition is found under equal compute budgets.

**H2 — Reuse:** Structural precedent retrieval reduces repeated planning effort on recurring problem families without increasing out-of-context failures.

**H3 — Bidirectional discovery:** Capability-to-demand exploration identifies useful applications that demand-only routing misses, after independent validation.

**H4 — Contract fidelity:** Explicit semantic/context contracts reduce composition failures relative to signature-only interfaces.

**H5 — Residual quality:** Typed residuals improve the accuracy of diagnosis and choice of remedial action compared with generic failure labels.

**H6 — Evidence governance:** Counter-evidence-aware ranking reduces unsafe or unsupported mapping selections relative to success-only scoring.

**H7 — Cost and recall:** Two-phase localization lowers average compute cost at a specified minimum valid-match recall, compared with exhaustive deep evaluation.

**H8 — Perspective expansion:** Multi-perspective maps reveal previously unrepresented task distinctions, measured by independently validated novel requirements rather than raw novelty counts.

None of these results is established by this paper.

## 14. Validation design and metrics

A practical evaluation program should include:

1. **Benchmark corpus:** Versioned problem graphs, capability graphs, known valid/invalid matches, and context-shift cases.
2. **Baselines:** Flat tool selection, keyword/API matching, LLM-only orchestration, and one-way task-to-tool mapping.
3. **Ablations:** Remove precedent records, reverse mapping, contracts, counter-evidence, or multi-perspective views separately.
4. **Independent adjudication:** Expert-reviewed validity labels and hidden challenge sets.
5. **Shadow execution:** Evaluate outcomes without granting real-world actuation.
6. **Governed pilot:** Limited deployment only after safety and authority checks.

Primary metrics should include **valid-match recall**, **precision of applicable mappings**, **compositional success**, **out-of-context failure rate**, **calibration of uncertainty**, **policy violation rate**, **resource cost**, **time-to-diagnose residual**, and **validated opportunity yield**. Report confidence intervals and failure distributions, not only average scores. Test on held-out contexts to limit precedent memorization.

## 15. Failure modes and design constraints

- **False analogy:** Two problems share surface features but differ in causal structure.
- **Ontology rigidity:** Fixed types prevent discovery of new perspectives.
- **Ontology drift:** Unversioned type changes silently break mappings.
- **Registry contamination:** Self-reported success is treated as independent evidence.
- **Circular validation:** The same model generates and grades its own mapping.
- **Composition mismatch:** Individually valid nodes violate joint invariants.
- **Premature folding:** Macro-nodes hide unresolved assumptions.
- **Policy laundering:** A forbidden action is re-described as a permissible tool call.
- **Search explosion:** Bidirectional discovery grows without useful bounds.
- **Stale precedent:** Past success is applied after environment change.

Mitigations include versioned contracts, counterexample retention, independent tests, bounded search, explicit authorization, and reversibility. None removes all failure modes.

## 16. Open research questions

1. What is the minimal shared type system that preserves semantic interoperability without freezing structural innovation?
2. How should BSIM represent uncertain, competing, or evolving problem decompositions?
3. Which graph-retrieval strategies offer the best cost–recall tradeoff for large registries?
4. How can causal compatibility be checked beyond lexical or embedding similarity?
5. When should a validated composite be folded into a macro-node, and when should it be unfolded?
6. How can negative precedents be indexed without overgeneralizing failure?
7. What independent evidence is sufficient to promote a sandbox mapping into authorized runtime use?
8. How should capability-to-demand discovery be evaluated without rewarding meaningless novelty?
9. How can different owners preserve sovereignty while exchanging capability descriptions and evidence?
10. How do maps change when a new perspective alters what counts as a problem or solution?

## 17. Roadmap and neighboring documents

This paper establishes the conceptual interface between the problem and capability sides of SIF. Subsequent documents develop the mechanisms:

- **SIF-009 — Structural Precedent Registry:** evidence-bearing, versioned problem–capability records.
- **SIF-010 — Universal Naming, Typing and Relay:** identity, semantic typing, and cross-system handoff.
- **SIF-011 — Structural Intelligence Contracts and Portable Units:** SIC and PIRP/PIRU integration.
- **SIF-012 — Multi-Intelligence Adversarial Sandbox:** systematic challenge and validation.
- **SIF-013 — Structural Counter-Evidence and Evaluator Governance:** evaluator failure and Anti-Goodhart design.
- **SIF-014 — Open-Ended Structural Growth and Collective Learning:** lifecycle and ecosystem-level evolution.

Candidate specifications **SPEC-001–004** are intended to translate these ideas into reviewable schemas and protocols before runtime commitments.

## 18. Conclusion

The Structural Problem-Solving Map and Structural Capability Map answer complementary questions: **What intelligence does the problem require?** and **What intelligence can the system currently supply?** BSIM makes the relationship explicit, bidirectional, and revisable. It enables disciplined structural precedent reuse, heterogeneous composition, transparent residual diagnosis, and exploration of new capability applications.

The deeper implication is that an intelligence architecture should not assume either its task ontology or its capability inventory is complete. A new problem can reveal a missing capability; a new capability can reveal a previously unrecognized problem; evidence and counter-evidence determine whether the proposed connection deserves trust. **Open structural intelligence is therefore not merely a larger tool collection—it is a governed process for revising the relationship between problems, capabilities, and the perspectives through which both are understood.**

---

## Figure placement guidance

- **Fig-003 — Problem-Capability Dual Maps:** After Section 3, showing both directions, the precedent bridge, and residual feedback.
- **Fig-004 — Universal Contracts and Relay:** After Section 6, showing SIC/UNT-R and cross-node interoperability.
- **Fig-005 — Structural Precedent Intelligence:** After Section 5, showing precedent records, applicability boundaries, and counter-evidence.
- **Fig-007 — Structural Growth and Evolution Loop:** After Section 9 or Section 12, showing residual diagnosis and governed growth.

Suggested Markdown embed, once the figures exist:

```markdown
![Problem–Capability Dual Maps](../../figures/Fig-003-Problem-Capability-Dual-Maps.png)
```

## Citation and provenance note

**Suggested citation:** Tan, S., & GPT-Obot. (2026). *SIF-008: Dual Maps and Bidirectional Structural Mapping*. Structural Intelligence Framework, v1.0.0. Repository manuscript. DOI: pending release.

This manuscript proposes a research architecture and hypotheses. It does not report experimental results or claim an implemented standard. Related SIF concepts are developed in the companion manuscripts and specifications of this repository.
