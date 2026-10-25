# SIF-004 — Localization and Intelligence Addressing

**Structural Intelligence Framework (SIF) — Functional Domains Series**  
**Version:** 1.0.0 (research framework)  
**Authors:** Sizhe Tan & GPT-Obot  
**Date:** 2026-10-26  
**Status:** Conceptual architecture and testable research agenda; not a validated implementation

## Abstract

Localization in a Structural Intelligence Framework (SIF) is more than information retrieval. It identifies where a problem belongs, which contexts and representations matter, which intelligence capabilities can address it, and how work should be routed across heterogeneous nodes. This paper defines **Intelligence Addressing** as the discovery and selection of context-qualified computational capabilities. It organizes known mechanisms—large language models (LLMs), metric-space Comment Concept Cores (CCCs), Metric Differential Trees (MDTs), two-phase search, intelligence relay networks, CallingGraphs, Core + Delta growth, Universal Types and Names (UTN), and world models—within an open, multi-perspective localization domain. It proposes interfaces, routing procedures, failure modes, and experiments. The intent is not to replace existing retrieval or planning systems but to provide an interoperable framework in which they can cooperate and be revised as new structures emerge.

**Keywords:** Structural Intelligence Framework; intelligence localization; capability routing; LLM; CCC; MDT; two-phase search; CallingGraph; UTN; relay; world model; structural precedent.

---

## 1. From Information Retrieval to Intelligence Addressing

Traditional retrieval asks: **Where is relevant information?** Intelligence Addressing asks a broader set of questions:

1. What is the problem, including its goals, constraints, uncertainty, and operating context?
2. Which structural representation makes it tractable?
3. Which available intelligence node, composition, or precedent can handle it?
4. Which evidence and permissions are needed before invoking that capability?
5. What residual remains when localization or execution fails?

A localization result is therefore not merely a document ID or vector neighbor. It may be a typed address of a capability, a task subgraph, a contextualized precedent, or a relay route.

> **Principle L1 — Locate intelligence, not only information.** A localization mechanism should be able to identify relevant capabilities and their conditions of use, not just retrieve similar content.

This is a *functional domain*, not a claim that every algorithm listed below performs every localization role.

## 2. Four Complementary Localization Perspectives

| Perspective | Main question | Candidate mechanisms | Typical output |
|---|---|---|---|
| Semantic | What does the request mean? | LLM, embeddings, semantic CCC | Interpreted intent and candidate concepts |
| Structural | Where does it fit in a decomposition? | MDT, Core + Delta, CallingGraph | Region, branch, subproblem or dependency path |
| Relational | Who or what should receive it? | Relay network, UTN, capability registry | Qualified node or composition address |
| State/world | What situation does it refer to? | State estimation, domain world model, simulation | State hypothesis, dynamics and uncertainty |

These perspectives can overlap. The same LLM may help interpret a task, propose a graph decomposition, and choose a candidate tool; none of those uses makes its output self-validating.

### 2.1 LLM as the first listed localization structure

LLMs deserve first position in this registry because of their breadth and practical utility for interpreting natural-language requests, resolving contextual references, and suggesting decomposition. Their limitations include hallucinated capability names, brittle exact matching, context-window constraints, and inconsistent calibration. Use schema validation, retrieval grounding, and independent checks when addresses have operational consequences.

### 2.2 Metric-space CCC: common core and residual

A **Comment Concept Core (CCC)** represents a context-qualified common structure; a residual captures what that core does not explain. A useful conceptual notation is

\[
X \approx C_{\mathrm{structural}} \oplus R_{\mathrm{residual}},
\]

where \(\oplus\) denotes a domain-specific reconstruction, **not necessarily numerical addition**. Unlike a mean and standard deviation, a CCC may encode conditions, semantics, causal hypotheses, or behavior. A residual may be structural rather than random noise. Metric-space CCC localization should specify the distance function, normalization, context, and rejection criteria; otherwise scores are not comparable.

### 2.3 Metric Differential Tree (MDT)

An MDT organizes local distinctions and branches, allowing coarse-to-fine addressing. Candidate benefits include search-space reduction, explainable branch selection, and localized revision. Risks include early misrouting, stale branch boundaries, and poor treatment of cross-branch tasks. A robust MDT implementation should support fallback search, uncertainty propagation, and branch re-evaluation.

### 2.4 Two-phase search for partial targets

For an incomplete or approximate target, separate:

- **Phase 1 — Candidate localization:** inexpensive broad search, routing, or pruning.
- **Phase 2 — Candidate verification:** richer computation, exact constraints, independent scoring, or simulation.

The first phase optimizes coverage and cost; the second optimizes justified selection. Report both candidate recall and final precision. If the first phase excludes the correct candidate, no second-phase sophistication can recover it without fallback.

### 2.5 Intelligence Relay Network

A relay network routes work among nodes with different skills, contexts, costs, and permissions. A route is not valid merely because an endpoint is reachable: its input contract, evidence requirements, policy, and context-transfer semantics must also match. Relay paths may involve delegation, escalation, or composition rather than a single handoff.

### 2.6 CallingGraph for AI coding and beyond

CallingGraphs represent task dependencies and executable action relationships. In SIF, a **Problem-Solving Map** resembles a Task CallingGraph, while a **Capability Map** resembles an Action CallingGraph. Their alignment is many-to-many: one task may require multiple capabilities, and one capability may serve multiple tasks. The analogy is architectural rather than an assertion of formal equivalence.

### 2.7 Core + Delta growth

Core + Delta supports localization by distinguishing reusable structure from local differences. It can facilitate adaptation of a precedent to a new problem without assuming exact identity. Delta quality matters: an unmodeled critical constraint may invalidate a seemingly close match.

### 2.8 Universal Types, Names, and Relay APIs

Universal naming identifies an intelligence unit; typing states its meaning and contracts; Relay APIs mediate interaction. Universality should mean **interoperable extension**, not a closed global taxonomy. Namespaces, versions, adapters, type refinements, and conformance tests are essential. JSON syntactic compatibility alone does not establish semantic compatibility.

### 2.9 World models as cross-domain structures

World models provide estimates of state, dynamics, and consequences, but they are not simply another search index. They can inform localization, operate as per-node predictors, support control-plane decisions, and expose growth residuals. Mature specialized models exist in many domains; general cross-domain, multi-scale grounding remains difficult. Model uncertainty and validity regions must accompany world-state-based routing.

---

## 3. Intelligence Addresses and the Structural Intelligence Contract

An **intelligence address** is a context-qualified reference to a candidate capability, not just a URL or model name. Its conceptual fields include:

| Field | Purpose |
|---|---|
| `identity` and `version` | Stable reference and compatibility tracking |
| `capability_signature` | Supported problem and output types |
| `context_requirements` | Required state, domain, granularity, time horizon |
| `input_output_contract` | Typed payloads and semantics |
| `evidence_profile` | Validation basis, limitations, counter-evidence |
| `policy_profile` | Permissions, prohibited actions, review gates |
| `cost_latency_profile` | Resource and timing expectations |
| `relay_endpoint` | Optional invocation or handoff mechanism |

A candidate research representation—not a frozen protocol—might look like:

```yaml
intelligence_address:
  identity: "example.org/optimizer/routing"
  version: "0.1"
  capability_signature: "constrained-route-planning"
  context_requirements:
    domain: "logistics"
    time_horizon: "hours"
  input_output_contract:
    input_type: "RouteProblem/v1"
    output_type: "RouteCandidates/v1"
  evidence_profile:
    validation_status: "experimental"
    known_limits: ["unmodeled disruptions"]
  policy_profile:
    execution_authority: "recommendation-only"
  relay_endpoint: "adapter://route-planner"
```

A capability may be indexed without an executable endpoint; retrieval and authorization are distinct.

> **Principle L2 — A match is not an authorization.** Capability relevance does not grant permission to act.

## 4. A Reference Localization Procedure

1. **Parse the problem:** extract goals, constraints, context, uncertainty, and requested authority.
2. **Build a problem signature:** include semantic, structural, relational, and state/world descriptors.
3. **Retrieve precedents and capabilities:** query the Structural Precedent Registry and Capability Map with multiple perspectives.
4. **Generate candidate decompositions:** consider single nodes, composite graphs, and alternative granularities.
5. **Check contracts:** verify types, context requirements, versions, permissions, and evidence coverage.
6. **Rank provisionally:** evaluate fit, confidence, risk, latency, and cost; do not collapse hard policy constraints into a soft score.
7. **Verify and relay:** apply phase-two tests, invoke approved adapters, or return an explainable shortlist.
8. **Record residuals:** identify missing capabilities, ambiguous contexts, failed relays, and counter-evidence.
9. **Escalate for growth when justified:** adapt, compose, experiment with a new structure, or retain an open problem.

The procedure may be iterative: new evidence from a node can change the localization address. Failed localization should be observable rather than silently replaced by a confident guess.

### 4.1 Candidate selection as a constrained problem

Let \(c\) be a capability candidate, \(p\) a problem signature, and \(\Gamma\) the relevant context. A conceptual selection rule is:

\[
 c^* \in \operatorname*{arg\,max}_{c\in\mathcal{C}_{\mathrm{admissible}}(p,\Gamma)}
 S(c,p,\Gamma),
\]

where admissibility enforces hard type, policy, and resource constraints. The score \(S\) is a configurable evaluation function, not a universal scalar measure of intelligence. Multiobjective or Pareto selection may be preferable where objectives conflict.

## 5. Dual Maps and Bidirectional Discovery

The **Problem-Solving Map** describes what must be accomplished; the **Capability Map** describes what structures can do. A Structural Precedent Registry links them through known applications, contracts, evidence, and failures.

**Problem → Capability:** discover or compose structures for a given task.  
**Capability → Problem:** discover tasks newly feasible because a capability or composition has emerged.

A failed match can mean an absent capability, an unsuitable decomposition, a missing type adapter, insufficient evidence, or a genuine unsolved problem. These outcomes require different growth responses.

**Figure placement:** `../../figures/Fig-003-Problem-Capability-Dual-Maps.png` is recommended immediately after this section in the illustrated edition.

## 6. Worked Conceptual Example: Disruption-Aware Supply-Chain Planning

**Problem:** select a feasible, low-risk response to a supply disruption when the objective is incomplete and operating conditions change.

| Localization stage | Candidate structure | Why it matters |
|---|---|---|
| Intent interpretation | LLM | Extract objectives and ambiguous constraints |
| Network region | Graph/MDT | Identify affected suppliers and routes |
| Partial-target search | Two-phase search | Broad candidates then exact feasibility checks |
| State grounding | Logistics world model | Estimate current disruptions and consequences |
| Capability addressing | UTN + Relay | Find approved optimization and simulation nodes |
| Structural adaptation | Core + Delta | Reuse a precedent while isolating new constraints |
| Governance | Policy plane | Enforce authority and risk limits |

The output should include candidate actions, assumptions, evidence gaps, and a route for human or authorized system review. This is an architectural illustration, **not a measured demonstration**.

## 7. Failure Modes and Countermeasures

| Failure | Consequence | Mitigation |
|---|---|---|
| LLM invents a node | Invalid or unsafe dispatch | Registry-backed resolution and signature validation |
| Coarse routing prunes a good candidate | Irrecoverable false negative | Recall audits and fallback search |
| Semantic match hides type mismatch | Runtime or conceptual failure | Explicit contracts and adapter conformance |
| Stale world state | Mislocalized intervention | State freshness checks and uncertainty bounds |
| Relay drops context | Incorrect downstream interpretation | Context handoff manifests and provenance |
| Score dominates policy | Unauthorized action | Hard authorization gate outside ranking |
| One perspective dominates | Systematic blind spots | Independent perspectives and adversarial challenge |
| Registry becomes stale | Repeated poor matches | Versioning, expiration, counter-evidence, revalidation |

## 8. Evaluation and Falsifiable Hypotheses

Localization should be assessed with task-specific baselines and controlled compute budgets. Useful metrics include **candidate recall@k**, end-to-end task success, constraint violations, calibration, routing latency, compute cost, contract mismatch rate, fallback frequency, and robustness under distribution shift.

Proposed hypotheses:

- **H1:** Multi-perspective routing improves candidate recall under partial-target ambiguity versus semantic-only retrieval at matched budget.
- **H2:** Two-phase search reduces expensive downstream evaluation without materially reducing final task success when phase-one recall is controlled.
- **H3:** Typed Relay contracts reduce cross-node interpretation failures versus untyped payload transfer.
- **H4:** Registry-backed LLM routing reduces fabricated capability selection compared with unconstrained LLM tool choice.
- **H5:** State-aware localization improves decisions in dynamic environments relative to static capability routing.
- **H6:** Explicit residual logging increases the yield of validated structural improvements compared with unstructured error collection.

These are research questions, not reported findings. Tests should use held-out scenarios, independent adjudication, ablations, and negative results.

## 9. Localization as an Open Evolutionary Domain

SIF localization must accept new algorithms and replacement mechanisms without requiring the entire framework to be redesigned. A new capability can enter the Registry as a research candidate, undergo contract and evidence checks, run in an adversarial sandbox, and then become eligible for approved routing. Previously accepted methods may be restricted, superseded, or retired as counter-evidence accumulates.

This supports an important distinction:

- **Discovery freedom:** candidate structures may be explored within appropriate sandbox boundaries.
- **Deployment authority:** production use requires independent evidence and explicit permission.

Growth is not guaranteed to be beneficial: new layers may increase coordination overhead, error propagation, or evaluation complexity. SIF therefore needs measurements of net system benefit, not merely the number of registered nodes.

## 10. Relationship to the Other SIF Domains

- **Per-Node Intelligence:** localization selects or composes computational capabilities; those capabilities can return evidence that revises the route.
- **Universal Control Planes and Scoring/Folding:** policy gates determine admissibility, while scoring and folding organize candidates and trade-offs.
- **Residual-Based Structural Growth:** failed matches, context gaps, and unexplained outcomes become candidate signals for new representations or structures.

These interactions are bidirectional. A world model or LLM can participate in several domains without being duplicated as a separate underlying artifact.

**Figure placement:** `../../figures/Fig-002-Four-Functional-Domains.png` may be cited here to illustrate cross-domain roles.

## 11. Open Questions

1. What is the smallest interoperable intelligence-address schema that preserves context and authority?
2. How should localization represent uncertainty across incompatible scoring systems?
3. When should a routing system prefer a composite graph over a single stronger model?
4. Can capability-to-problem discovery be measured independently of existing benchmark taxonomies?
5. What evidence is sufficient to promote an experimental localization mechanism to production eligibility?
6. How can world-model freshness and domain validity be checked automatically?
7. How can a Registry avoid centralization, taxonomy lock-in, and structural Goodhart effects?

## 12. Conclusion

Localization is the addressing function of an open structural intelligence ecosystem. It transforms a problem into a context-qualified search for representations, precedents, capabilities, and relay paths. LLMs provide a broad and important first mechanism, but CCCs, MDTs, two-phase search, CallingGraphs, Core + Delta, UTN, relay networks, and world models contribute distinct strengths. Their coordination requires explicit contracts, evidence, policy boundaries, and residual handling. The central research proposition is that **intelligence addressing can become more capable through structured composition and independently validated growth**, without presuming that any fixed algorithm or taxonomy exhausts future intelligence.

---

## Related SIF Documents

- `SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md`
- `SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md`
- `SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md`
- `SIF-005-Per-Node-Intelligence-and-Multi-Perspective-Capabilities.md` (planned)
- `SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md` (planned)
- `SIF-010-Universal-Naming-Typing-and-Relay.md` (planned)

## Research Integrity Note

This article synthesizes a proposed architecture and design hypotheses. Its terminology is not asserted to be an established industry standard, and its example and hypotheses are not empirical validation. External prior art and formal citations should be added and checked before any claim of novelty or comparative performance is made.

**Suggested repository path:** `docs/functional-domains/SIF-004-Localization-and-Intelligence-Addressing.md`

**License:** Apache-2.0 (subject to repository license and applicable attribution requirements).
