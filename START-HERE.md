# START HERE — Structural Intelligence Framework (SIF)

**An Open Architecture for Intelligence Localization, Composition, Governance, and Structural Growth**  
**Release:** v1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Research framework and candidate engineering specifications; not an implemented or independently validated standard.

> **Central proposition:** Intelligence need not be confined to a single model or a fixed toolchain. It can be organized as an open, interoperable, evidence-governed ecosystem of reusable and evolving structures.

## 1. What Is SIF?

The **Structural Intelligence Framework (SIF)** is a research architecture for finding, composing, evaluating, governing, and improving heterogeneous intelligence capabilities. It treats large language models (LLMs) as important foundational capabilities without assuming that any one model or present-day architecture exhausts future intelligence.

SIF asks five connected questions:

1. **Where** is the relevant intelligence for a problem, and how can it be addressed?
2. **What** can each intelligence node do, under which conditions?
3. **Who** evaluates, selects, and authorizes its use?
4. **What remains unresolved**, and how can residuals motivate structural growth?
5. **How might growth change what a system can perceive and represent?**

The first four questions organize SIF's four functional domains. The fifth is a research frontier, not an established consequence.

## 2. The Four Functional Domains

| Domain | Main question | Representative mechanisms | Primary manuscript |
|---|---|---|---|
| **Localization and Intelligence Addressing** | Where should intelligence be found or routed? | LLMs, CCC, MDT, two-phase search, CallingGraphs, relay networks, world models | [SIF-004](docs/functional-domains/SIF-004-Localization-and-Intelligence-Addressing.md) |
| **Per-Node Intelligence** | Which capability should operate at a node? | LLMs, rules, optimization, simulation, ANN, mathematics, specialized programs | [SIF-005](docs/functional-domains/SIF-005-Per-Node-Intelligence-and-Multi-Perspective-Capabilities.md) |
| **Universal Control Planes and Scoring/Folding** | How are decisions evaluated, governed, and audited? | Policy and authority, scoring trees/forests, evidence, folding/unfolding | [SIF-006](docs/functional-domains/SIF-006-Universal-Control-Planes-and-Scoring-Folding.md) |
| **Residual-Based Structural Growth** | How can gaps become testable proposals for better structures? | Residual diagnosis, structural precedents, adversarial validation, collective learning | [SIF-007](docs/functional-domains/SIF-007-Residual-Based-Structural-Growth.md) |

These are **functional roles, not mutually exclusive software layers**. A component may serve several domains. For the conceptual overview, read [SIF-002](docs/foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md).

## 3. Choose Your Reading Path

### Path A — First-time reader (approximately 30–45 minutes)

1. [README.md](README.md) — project overview and navigation.
2. [SIF-001 — From Isolated Intelligence to Open Structural Intelligence](docs/foundations/SIF-001-From-Isolated-Intelligence-to-Open-Structural-Intelligence.md) — motivation and scope.
3. [SIF-002 — Four Functional Domains](docs/foundations/SIF-002-Four-Functional-Domains-of-Structural-Intelligence.md) — organizing framework.
4. [SIF-003 — Structural Precedents and Open Intelligence Evolution](docs/foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md) — reuse, applicability, and growth.
5. [OPEN-QUESTIONS.md](research/OPEN-QUESTIONS.md) — what is still unknown.

### Path B — Architect or systems engineer

Begin with the problem-to-capability interface, then examine the candidate contracts and data models:

1. [SIF-008 — Dual Maps and Bidirectional Structural Mapping](docs/interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md)
2. [SIF-009 — Structural Precedent Registry](docs/interoperability/SIF-009-Structural-Precedent-Registry.md)
3. [SIF-010 — Universal Naming, Typing and Relay](docs/interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md)
4. [SIF-011 — Structural Intelligence Contracts and Portable Units](docs/interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md)
5. [SPEC-001 — Structural Intelligence Contract](specifications/SPEC-001-SIF-Structural-Intelligence-Contract.md)
6. [SPEC-002 — Universal Name, Type and Relay API](specifications/SPEC-002-Universal-Name-Type-and-Relay-API.md)
7. [SPEC-003 — Structural Precedent Registry Schema](specifications/SPEC-003-Structural-Precedent-Registry-Schema.md)
8. [SPEC-004 — Sandbox Evidence and Growth Lifecycle](specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md)

**Engineering caution:** These specifications are research candidates. Their example schemas, interfaces, profiles, and tests are proposals requiring interoperability trials and revision, not claims of deployed conformance.

### Path C — AI evaluation, safety, and governance researcher

1. [SIF-006 — Universal Control Planes and Scoring Folding](docs/functional-domains/SIF-006-Universal-Control-Planes-and-Scoring-Folding.md)
2. [SIF-012 — Multi-Intelligence Adversarial Sandbox](docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
3. [SIF-013 — Structural Counter-Evidence and Evaluator Governance](docs/validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md)
4. [SPEC-004 — Sandbox Evidence and Growth Lifecycle](specifications/SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md)
5. [VALIDATION-ROADMAP.md](research/VALIDATION-ROADMAP.md)

Focus on the distinction between **discovery, evidence qualification, and authorization**. A favorable score or successful test does not itself grant authority to act.

### Path D — Researcher interested in continual learning and intelligence growth

1. [SIF-007 — Residual-Based Structural Growth](docs/functional-domains/SIF-007-Residual-Based-Structural-Growth.md)
2. [SIF-014 — Open-Ended Structural Growth and Collective Learning](docs/validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md)
3. [SIF-015 — Structural Perception Horizon and Worldview Growth](docs/frontiers/SIF-015-Structural-Perception-Horizon-and-Worldview-Growth.md)
4. [SIF-016 — Macro-Intelligence Pieces and Higher-Order Structures](docs/frontiers/SIF-016-Macro-Intelligence-Pieces-and-Higher-Order-Structures.md)
5. [SIF-017 — Scaling Axes and Computational Intelligence Growth](docs/frontiers/SIF-017-Scaling-Axes-and-Computational-Intelligence-Growth.md)
6. [SIF-018 — Perspective ASI and the Open Future of Intelligence](docs/frontiers/SIF-018-Perspective-ASI-and-the-Open-Future-of-Intelligence.md)
7. [TESTABLE-HYPOTHESES.md](research/TESTABLE-HYPOTHESES.md)

**Scientific caution:** Larger compositions, expanded capability inventories, and increased compute do not automatically demonstrate higher-order intelligence or a reconstructed worldview. Those claims need controlled tests and independent counter-evidence.

### Path E — Experimental researcher

Read [TESTABLE-HYPOTHESES.md](research/TESTABLE-HYPOTHESES.md) alongside [VALIDATION-ROADMAP.md](research/VALIDATION-ROADMAP.md). Select a bounded hypothesis, pre-register baselines and failure criteria, and preserve negative results. Consult the relevant candidate specification only after deciding what the experiment must measure.

## 4. The SIF System in One View

```text
                STRUCTURAL PROBLEM-SOLVING MAP
              (requirements, contexts, constraints)
                              |
                  bidirectional mapping
                              |
                   STRUCTURAL CAPABILITY MAP
              (capabilities, contracts, evidence)
                              |
             STRUCTURAL PRECEDENT REGISTRY
              (successes, failures, boundaries)
                              |
                 UNT-R + SIC INTERFACES
                (identity, type, relay, policy)
                              |
               GOVERNED INTELLIGENCE RUNTIME
                   (compose and execute)
                              |
                 OUTCOMES + COUNTER-EVIDENCE
                              |
               RESIDUAL DIAGNOSIS + MIAS
               (challenge, evaluate, revise)
                              |
                 CANDIDATE STRUCTURAL GROWTH
                              |
                 REGISTRY / MAPS / CONTRACTS
                         (versioned update)
```

This diagram illustrates a **research workflow**, not a mandated execution topology. A practical implementation may be federated, distributed, or specialized.

## 5. Key Terms in Two Minutes

- **PSM / SCM:** Problem-Solving Map and Capability Map; complementary descriptions of demand and available intelligence.
- **BSIM:** Bidirectional Structural Intelligence Mapping between problems and capabilities.
- **SPI / SPR:** Structural Precedent Intelligence / Registry; evidence-bearing records of reusable structural claims and their limits.
- **SIC:** Structural Intelligence Contract; a proposed description of capability, context, interface, evidence, policy, and lifecycle.
- **UNT-R:** Universal Naming, Typing and Relay; proposed interoperability conventions.
- **PIRP / PIRU:** Portable Intelligence Runtime Piece / Unit; flexible exploratory pieces versus more formalized units.
- **MIAS:** Multi-Intelligence Adversarial Sandbox; a controlled setting for challenging candidate structures and evaluators.
- **SCE:** Structural Counter-Evidence; evidence against structural assumptions, applicability, composition, or evaluation—not just against a final answer.
- **SPH:** Structural Perception Horizon; a proposed way to study what a system can currently distinguish, represent, and test.
- **Perspective ASI:** A context- and evaluation-dependent description of extraordinary intelligence performance, not a claim of universal supremacy.

For detailed terminology, see [GLOSSARY.md](GLOSSARY.md).

## 6. Figures and Visual Navigation

The planned figure set is indexed in [FIGURE-INDEX.md](FIGURE-INDEX.md):

| Figure | Subject |
|---|---|
| [Fig-001](figures/Fig-001-SIF-Grand-Architecture.png) | SIF Grand Architecture |
| [Fig-002](figures/Fig-002-Four-Functional-Domains.png) | Four Functional Domains |
| [Fig-003](figures/Fig-003-Problem-Capability-Dual-Maps.png) | Problem–Capability Dual Maps |
| [Fig-004](figures/Fig-004-Universal-Contracts-and-Relay.png) | Universal Contracts and Relay |
| [Fig-005](figures/Fig-005-Structural-Precedent-Intelligence.png) | Structural Precedent Intelligence |
| [Fig-006](figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png) | Multi-Intelligence Adversarial Sandbox |
| [Fig-007](figures/Fig-007-Structural-Growth-and-Evolution-Loop.png) | Structural Growth and Evolution Loop |
| [Fig-008](figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png) | Perception Horizon and Worldview Growth |

These links assume that each figure has been exported as a **separate PNG** with the specified filename. A combined figure sheet is not interchangeable with the eight individual assets.

## 7. What This Release Does—and Does Not—Claim

**This release provides:** a conceptual architecture, research manuscripts, candidate interface specifications, a catalog of open questions, falsifiable hypotheses, and a validation roadmap.

**It does not provide:** a production runtime, verified universal interoperability, a complete implementation of the proposed registry and relay interfaces, proof of open-ended recursive self-improvement, or evidence that worldview reconstruction has occurred.

The intended progression is **conceptual clarity → bounded prototypes → controlled comparison → adversarial testing → independent replication → governed deployment**, with revision or rejection possible at each stage.

## 8. Explore the Complete Repository

- [CONTENTS.md](CONTENTS.md) — full document index.
- [README.md](README.md) — high-level project presentation.
- [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md) — possible next research directions.
- [CHANGELOG.md](CHANGELOG.md) — release history.
- [CITATION.cff](CITATION.cff) — citation metadata.
- [LICENSE.txt](LICENSE.txt) — Apache-2.0 licensing terms.

## 9. Suggested First Contribution

Choose one claim in [TESTABLE-HYPOTHESES.md](research/TESTABLE-HYPOTHESES.md), define a reproducible benchmark and at least one meaningful baseline, specify what result would count against the claim, and report both positive and negative evidence. For architecture proposals, describe the structural residual they address, their SIC boundary assumptions, and what independent evaluation would be needed before adoption.

---

**Guiding principle:** *Standardize the contract, not the intelligence. Preserve the evidence, not merely the answer. Govern the action, not the possibility of discovery.*

**Authors:** Sizhe Tan & GPT-Obot  
**Project:** Structural Intelligence Framework (SIF)  
**License:** Apache-2.0
