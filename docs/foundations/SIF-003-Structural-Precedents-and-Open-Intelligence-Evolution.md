# SIF-003 — Structural Precedents and Open Intelligence Evolution

**Structural Intelligence Framework (SIF) — Foundations, Paper 003**  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Date:** 2026-10-18  
**Status:** Research framework and proposed architecture; not an implemented standard  
**License:** Apache-2.0

## Abstract

The Structural Intelligence Framework (SIF) treats known intelligence structures as an open, revisable body of reusable problem-solving precedents. Rather than requiring each new problem to be solved from a blank slate—or routed exclusively to a single general-purpose model—SIF proposes identifying relevant prior structures, examining their applicability, adapting or composing them, and documenting the evidence that supports or limits their use. When no precedent suffices, residuals and counter-evidence initiate a governed process of structural discovery. Inspired by case-based reasoning and the use of precedents in legal practice, this paper introduces **Structural Precedent Intelligence (SPI)**, distinguishes precedents from mere examples and reusable code, specifies a candidate precedent record and retrieval workflow, and connects the precedent lifecycle to SIF's four functional domains, dual Problem–Capability maps, universal naming and relay contracts, adversarial evaluation, and open-ended structural growth. The paper also addresses failure cases: superficial analogy, inherited bias, precedent lock-in, false confidence, and uncontrolled structural proliferation. Its claims are architectural proposals and testable hypotheses, not empirical demonstrations.

**Keywords:** Structural Intelligence Framework; Structural Precedent Intelligence; case-based reasoning; intelligence reuse; Problem–Capability maps; structural counter-evidence; open-ended evolution; relay contracts; evaluator governance.

---

![Structural Growth and Evolution Loop](../../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

![Perception Horizon and Worldview Growth](../../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png)

---

## 1. Introduction: From Isolated Solutions to an Evolving Body of Intelligence

Contemporary intelligent systems often solve problems by applying a model, algorithm, workflow, or toolchain selected for a particular task. These methods can be powerful, yet the reusable *structure of the solution* is not always made explicit. A successful deployment may remain a one-off application; a failed deployment may disappear without leaving a useful record of its limits.

SIF proposes a different organizing principle: treat validated problem-solving structures as **structural precedents** that can be discovered, compared, adapted, composed, challenged, and revised. The goal is not to replace foundation models, established algorithms, or specialist software. It is to make their capabilities and boundaries more legible and reusable within an open intelligence ecosystem.

A precedent-first approach is **not** precedent-only. A mature framework must recognize when an existing precedent does not apply and must preserve pathways for new structures, perspectives, and forms of intelligence to emerge.

### 1.1 Central thesis

> Intelligence should accumulate not only outputs and models, but also reusable, evidence-bounded structures for solving classes of problems—and the means to challenge and evolve those structures.

This paper develops that thesis as an architectural proposal.

## 2. The Legal-Precedent Analogy: What Transfers and What Does Not

Legal precedent provides a useful analogy because a past decision is not applied merely because it resembles a new dispute. Relevant facts, governing rules, jurisdiction, exceptions, subsequent decisions, and competing interpretations matter. Similarly, a structural precedent must carry its **conditions of applicability**, not merely its name or success story.

The analogy suggests six useful operations:

1. **Identify** the new problem's material features and constraints.
2. **Retrieve** prior cases with related structures or objectives.
3. **Distinguish** relevant similarities from differences that invalidate transfer.
4. **Adapt or compose** prior approaches for the new context.
5. **Evaluate** outcomes against explicit criteria and counter-evidence.
6. **Record** the revised precedent, exception, failure, or unresolved question.

The analogy has limits. Legal precedent is embedded in institutions, jurisdiction, and authority; an algorithmic precedent does not acquire normative authority merely by being stored or frequently reused. SIF must explicitly separate **empirical applicability**, **evaluation quality**, and **permission to act**. A high-scoring structural match does not grant deployment authorization.

## 3. Defining Structural Precedent Intelligence (SPI)

**Structural Precedent Intelligence (SPI)** is the proposed capability to retrieve, interpret, adapt, compose, evaluate, and revise previously documented intelligence structures in response to a new problem.

A **structural precedent** is a versioned record of a problem-solving structure, including:

- a problem class and contextual signature;
- a capability or composition that addresses that class;
- assumptions, constraints, and known boundaries;
- interface and relay requirements;
- evaluation evidence, counter-evidence, and failure modes;
- provenance, revision history, and governance status.

A precedent is more than a sample input/output pair. It is also more than an executable library function: it preserves *why* a structure is appropriate, *where* it fails, and *how* its use can be independently examined.

### 3.1 Precedent versus neighboring artifacts

| Artifact | Primary purpose | What SPI additionally requires |
|---|---|---|
| Code library | Reuse an implementation | Problem signature, applicability, evidence |
| Model card | Describe a model and its limitations | Cross-structure matching and composition history |
| Benchmark result | Report measured performance | Context-specific transfer and counterexamples |
| Workflow template | Reuse procedural steps | Explicit structural assumptions and validation |
| Case-based reasoning record | Reuse a previous case | Cross-domain contracts, governance, structural growth |
| Structural precedent | Reuse and challenge problem-solving structure | Versioned integration into SIF's open registry |

SPI is an extension and synthesis of related engineering ideas, not a claim that precedent-based computation is wholly new.

## 4. Two Maps and a Precedent Bridge

SIF separates two complementary views:

**Problem-Solving Map (Task CG perspective).** Represents goals, constraints, problem decomposition, context, and required capabilities.

**Structural Capability Map (Action CG perspective).** Represents available models, algorithms, nodes, composite structures, interfaces, and evidence-bounded capabilities.

The **Structural Precedent Registry** links the maps. It supports bidirectional queries:

- **Problem → Capability:** What known structures might solve this problem?
- **Capability → Problem:** Which existing or newly recognizable problems could benefit from this capability?

This second direction matters: new capabilities can reveal applications that were not part of the original design. Thus SPI supports both reuse and discovery.

A conceptual mapping is:

\[
\mathcal{M}: (P, C, E, G) \rightarrow \{\text{reuse},\text{adapt},\text{compose},\text{explore}\}
\]

where \(P\) is the problem signature, \(C\) the available capability descriptions, \(E\) the evidence and counter-evidence, and \(G\) the governing constraints. This is a functional abstraction, not a specified scoring algorithm.

**Figure placement:** Insert `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` after this section when available.

## 5. A Candidate Structural Precedent Record

A useful registry entry must be minimal enough for broad adoption and rich enough to prevent misleading reuse. The following is a **non-normative illustrative schema**; the formal candidate schema belongs in `SPEC-003-Structural-Precedent-Registry-Schema.md`.

```yaml
precedent:
  id: "sif:precedent:example-two-phase-retrieval"
  version: "0.1.0"
  title: "Two-phase retrieval under incomplete target specification"
  status: "candidate"
  provenance:
    origin: "research-example"
    references: []
  problem_signature:
    task_family: "retrieval"
    target_completeness: "partial"
    constraints: ["bounded-latency"]
  capability:
    structure_type: "two-phase-search"
    required_interfaces: ["candidate-retrieval", "reranking"]
  assumptions:
    - "first-phase recall is sufficient for downstream reranking"
  applicability:
    known_good_contexts: []
    known_exclusions: []
  evaluation:
    metrics: ["recall", "precision", "latency", "cost"]
    evidence_refs: []
    counter_evidence_refs: []
  relay:
    input_contract: "sif:contract:retrieval-input:0.1"
    output_contract: "sif:contract:ranked-candidates:0.1"
  governance:
    allowed_actions: ["sandbox-evaluation"]
    production_authorized: false
  lifecycle:
    supersedes: []
    revision_notes: "Illustrative record only"
```

The registry must distinguish **unknown** evidence from **negative** evidence. An empty evidence list is not proof of reliability.

## 6. Precedent Retrieval, Distinguishing, and Adaptation

A proposed SPI workflow has eight steps.

### Step 1 — Problem signature extraction

Extract the task objective, input and output semantics, context, constraints, acceptable failure modes, evaluation criteria, and deployment authority. LLMs may help with initial extraction, but deterministic checks or expert review may be needed for critical requirements.

### Step 2 — Candidate localization

Use one or more mechanisms—LLM, semantic retrieval, CCC, Metric Differential Tree, graph navigation, Universal Types/Names, or other suitable indexing—to find plausible precedents. No single retrieval mechanism should be presumed universally best.

### Step 3 — Applicability and boundary matching

Evaluate assumptions, domain shift, granularity, data quality, operational context, policy, and resource budgets. A semantic match is not enough: an apparently similar precedent may fail under different constraints.

### Step 4 — Precedent distinction

Record the material differences between the new problem and retrieved precedents. Differences may call for parameter adaptation, composition, a different perspective, or rejection.

### Step 5 — Reuse, adaptation, or composition

Choose a single structure, adapt an existing structure, or compose multiple nodes through explicit contracts and Relay APIs. Compositions are new candidates until validated in their target context.

### Step 6 — Sandbox evaluation

Test correctness, robustness, cost, latency, policy compliance, and relevant downstream outcomes. For novel or high-stakes compositions, invoke multi-intelligence adversarial evaluation and independent checks.

### Step 7 — Governed authorization

Keep the evidence decision distinct from authorization. Production deployment requires the appropriate policy, human or institutional authority, monitoring, and rollback arrangements.

### Step 8 — Record the outcome

Update the registry with success, failure, boundary changes, counter-evidence, new composition patterns, or unresolved residuals. This step makes the system cumulative rather than episodic.

## 7. Four Functional Domains in the Precedent Lifecycle

SPI cuts across SIF's four **functional domains**, which are overlapping roles rather than mutually exclusive layers.

| Domain | SPI responsibility | Illustrative structures |
|---|---|---|
| Localization | Find and distinguish candidate precedents | LLM, CCC, MDT, Two-Phase Search, CallingGraph |
| Per-Node Intelligence | Execute or evaluate precedent capabilities | LLM, rules, optimization, simulation, statistical engines |
| Control & Scoring | Rank alternatives, enforce policy, audit evidence | Scoring Tree/Forest, policy plane, evidence evaluators |
| Residual-Based Growth | Identify gaps and propose new precedents | Counter-evidence, structural search, RSI, collective learning |

A structure can appear in several roles. For example, an LLM may extract problem signatures, execute a local reasoning task, and generate structural hypotheses, without thereby becoming the sole authority for evaluation or deployment.

## 8. Structural Counter-Evidence: Preserving Failed and Limited Precedents

A registry containing only successful examples risks confirmation bias and premature convergence. SPI should store **negative precedents** and **boundary precedents** with the same care as positive ones.

Structural counter-evidence may challenge:

- **Output validity:** the produced result is incorrect.
- **Structural applicability:** assumptions do not hold in a target context.
- **Localization:** the wrong capability was selected.
- **Composition:** individually valid nodes fail when combined.
- **Relay semantics:** context or meaning is lost during handoff.
- **Evaluation:** the metric rewards the wrong behavior.
- **Governance:** a proposed action exceeds permitted authority.
- **Resource viability:** benefits disappear under real cost or latency constraints.

A counterexample does not always invalidate an entire structure. It may narrow the scope of the precedent or motivate a more precise contract. Such *distinguishing* is often more useful than binary acceptance or rejection.

## 9. Multi-Intelligence Adversarial Sandbox (MIAS)

The proposed **Multi-Intelligence Adversarial Sandbox** can carry much of the scalable burden of testing structural precedents. Its candidate roles include:

- **Builder:** proposes a structure or adaptation and declares its expected advantage.
- **Challenger:** seeks adversarial inputs, missing assumptions, or contradictory evidence.
- **Independent evaluator:** checks claims against explicit tests and independent evidence.
- **World/simulation engine:** generates environmental states, perturbations, and trajectories.

Heterogeneous challengers—formal methods, simulators, statistical tests, and diverse models—may be more informative than homogeneous model debate alone. Nevertheless, multiple agents can share errors, game metrics, or coordinate around false assumptions. Independence must be designed and tested, not inferred from agent count.

Evaluation may be recursive, including challenges to evaluators themselves, but must be bounded by risk, budget, and stopping criteria. Sandbox exploration must not be confused with authorization for external action.

**Figure placement:** Insert `../../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png` after this section when available.

## 10. From Residual to New Structural Precedent

When existing precedents are weak or absent, SIF proposes a growth lifecycle:

1. Detect a residual, leftover, or unexplained structural mismatch.
2. Classify the residual: noise, missing data, inadequate context, missing capability, or flawed evaluation.
3. Search again for overlooked precedents and alternative perspectives.
4. Generate candidate adaptations, compositions, or new structures.
5. Challenge candidates with counter-evidence and ablation tests.
6. Validate against held-out contexts and resource constraints.
7. Register the result as accepted, restricted, provisional, rejected, or open.
8. Revisit prior decisions when new evidence or structures emerge.

The important distinction is that **not every residual justifies a new structure**. New structures incur complexity, maintenance, interoperability, and governance costs. The framework should prefer the simplest adequate solution, subject to evidence and policy.

**Figure placement:** Insert `../../figures/Fig-005-Structural-Precedent-Intelligence.png` here when available.

## 11. Universal Names, Types, Relay, and Structural Contracts

Precedent reuse across systems requires more than a textual description. The proposed **Universal Naming, Typing and Relay (UNT-R)** foundation supports stable identities, type semantics, discovery, invocation, and context handoff. A **Structural Intelligence Contract (SIC)** describes capability, input/output signatures, assumptions, evidence, constraints, and governance.

This should not force all intelligence into one internal representation. An LLM, solver, rule engine, simulation service, or portable intelligence piece may retain its own execution model while exposing interoperable descriptions or adapters.

Related SIF specifications are planned as:

- `SPEC-001-SIF-Structural-Intelligence-Contract.md`
- `SPEC-002-Universal-Name-Type-and-Relay-API.md`
- `SPEC-003-Structural-Precedent-Registry-Schema.md`
- `SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md`

These are proposed interfaces and should remain explicitly versioned and revisable until conformance testing establishes their practical utility.

## 12. Example: A Supply-Chain Risk Planning Problem

Consider a planning task: find a robust supply-chain response under incomplete demand forecasts, changing transport conditions, and hard policy constraints.

**Problem Map:** identify demand uncertainty, network topology, feasible actions, risk limits, and time horizon.

**Candidate Capability Map:** retrieve precedents involving graph localization, time-series forecasting, optimization, scenario simulation, and scoring under policy constraints.

**Composition:** connect forecast, route, optimization, and simulation nodes through explicit data and context contracts. Use a policy plane to exclude unauthorized or infeasible actions.

**Adversarial validation:** challenge the proposal with forecast shifts, supplier failures, misleading correlations, rare disruptions, and alternative objectives.

**Registry outcome:** document the context in which the composition works, cases where it fails, evidence quality, and whether a new composite precedent is justified.

This is a **conceptual example**, not a claim of an implemented SIF supply-chain system or measured performance gain.

## 13. Failure Modes and Safeguards

| Failure mode | Consequence | Candidate safeguard |
|---|---|---|
| Superficial analogy | Wrong precedent selected | Assumption-level matching and distinction |
| Precedent lock-in | Novel structures overlooked | Exploration quotas and alternative-perspective search |
| Positive-case bias | Inflated confidence | Negative precedents and counter-evidence indexing |
| Shared evaluator bias | False validation consensus | Heterogeneous checks and external benchmarks |
| Contract mismatch | Silent semantic errors | Conformance tests and explicit adapters |
| Structural proliferation | High complexity and cost | Reuse-first policy, pruning, deprecation |
| Authority confusion | Unapproved external actions | Evaluation/authorization separation |
| Stale evidence | Unsafe reuse after environment change | Versioning, expiry triggers, revalidation |

The registry itself must be governed: records need provenance, access controls where appropriate, immutable or auditable revision history, and mechanisms for superseding flawed entries.

## 14. Testable Research Hypotheses

The following hypotheses require empirical evaluation:

**H1 — Reuse efficiency.** For recurring task families, precedent-guided structure selection reduces development or inference cost compared with reasonable baselines at comparable outcome quality.

**H2 — Boundary-aware reliability.** Recording assumptions and counter-evidence lowers out-of-domain failures relative to precedent retrieval based only on semantic similarity.

**H3 — Composition value.** Contract-guided multi-structure composition outperforms a single selected structure on at least some heterogeneous tasks after accounting for coordination overhead.

**H4 — Adversarial discovery.** Heterogeneous challenger/evaluator ensembles uncover more distinct structural failure modes per unit budget than homogeneous debate or fixed test sets in selected settings.

**H5 — Open growth.** A versioned registry with explicit negative precedents yields better long-term adaptability than a success-only or append-only registry.

**H6 — Capability-to-problem discovery.** Reverse mapping from newly registered capabilities identifies valuable problem classes not present in the original capability specification.

Each hypothesis should be tested against strong baselines, with preregistered metrics where practical, held-out evaluation tasks, cost accounting, and ablation studies.

## 15. Research Agenda and Open Questions

1. How should a structural precedent's problem signature be represented across domains and granularities?
2. What combination of semantic, graph, type, and evidence retrieval gives the best cost–quality tradeoff?
3. How can a registry distinguish genuine novelty from repackaged existing structures?
4. When should negative evidence restrict a precedent rather than retire it?
5. How should confidence transfer—or fail to transfer—across composed intelligence units?
6. How can policy and authorization be represented without conflating them with performance scores?
7. What mechanisms prevent self-reinforcing errors in automated precedent generation and validation?
8. Can structural precedent accumulation measurably expand the system's *perception horizon*, rather than merely improve known benchmark performance?
9. How should open registries federate across organizations while preserving provenance and access boundaries?
10. What is the right balance between discovery computation and adversarial validation computation?

## 16. Relationship to the Broader SIF Research Program

This paper is the third foundations paper in the proposed SIF series:

- **SIF-001:** From Isolated Intelligence to Open Structural Intelligence — the open-framework thesis.
- **SIF-002:** Four Functional Domains of Structural Intelligence — the functional architecture.
- **SIF-003 (this paper):** Structural Precedents and Open Intelligence Evolution — the reuse-and-growth method.

Subsequent planned papers address localization, per-node capabilities, control and scoring, residual growth, dual maps, registry design, UNT-R, contracts, adversarial sandboxes, and perception/worldview growth. Prior Structural Intelligence research on CCC, Metric Differential Trees, CallingGraphs, PIRP/PIRU, counter-evidence, and structural recursive self-improvement provides conceptual context; this paper does not claim those ideas have been integrated into a single verified production system.

## 17. Conclusion

Structural Precedent Intelligence offers a practical organizing idea for an open Structural Intelligence Framework: preserve the *structure* of prior problem solving, including the evidence and conditions that make reuse justified. The combination of a Problem-Solving Map, a Structural Capability Map, and a versioned precedent registry supports reuse without requiring intellectual closure. Where precedent is insufficient, residual analysis and adversarial evaluation provide a disciplined route to new structures.

The central design principle is:

> **Precedent-first, not precedent-only: reuse what is justified, challenge what is uncertain, and leave the future of intelligence structurally open.**

---

## References and Research Context

The following are conceptual reference points, not claims of direct empirical validation of SIF:

1. Kolodner, J. L. (1992). *An Introduction to Case-Based Reasoning*. Artificial Intelligence Review, 6, 3–34.
2. Aamodt, A., & Plaza, E. (1994). *Case-Based Reasoning: Foundational Issues, Methodological Variations, and System Approaches*. AI Communications, 7(1), 39–59.
3. Sutton, R. S. (2019). *The Bitter Lesson*. Essay on computation and general methods.
4. SIF research program, papers SIF-001 and SIF-002, and planned specifications listed above.

## Citation

Tan, S., & GPT-Obot. (2026). *SIF-003: Structural Precedents and Open Intelligence Evolution*. Structural Intelligence Framework, version 1.0.0. Repository DOI to be added after release.

## License

Apache License 2.0. See the repository root `LICENSE` file.
