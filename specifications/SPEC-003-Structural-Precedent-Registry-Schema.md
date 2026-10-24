# SPEC-003 — Structural Precedent Registry Schema

**Structural Intelligence Framework (SIF)**  
**Candidate Research Specification:** v0.1.0  
**Repository release:** v1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposal — not an adopted standard, production guarantee, or validated implementation  
**Location:** `specifications/SPEC-003-Structural-Precedent-Registry-Schema.md`

## Abstract

The Structural Precedent Registry (SPR) is a proposed, versioned, evidence-bearing repository for claims about reusable intelligence structures and their observed performance under specific conditions. Rather than storing an answer as a precedent, SPR records **what structure was used, for which problem, under what assumptions, with what evidence, and where it failed**. It connects the Structural Problem-Solving Map (PSM) and Structural Capability Map (SCM) through discoverable capability definitions, precedent cases, evidence records, counter-evidence, and lineage. This specification proposes a minimal interoperable schema, lifecycle rules, retrieval semantics, integrity requirements, and conformance tests. It complements SPEC-001 (Structural Intelligence Contract) and SPEC-002 (Universal Name, Type, and Relay API).

> **Design principle:** A precedent is a reusable *structural claim with conditions and evidence*, not an automatically transferable solution.

## 1. Scope and Non-Goals

### 1.1 In scope

- A logical data model for capability definitions, precedent cases, evidence, counter-evidence, and provenance.
- Stable identity, versioning, supersession, and references between records.
- Matching between PSM requirements and SCM capabilities with explicit applicability checks.
- Evidence provenance, uncertainty, negative findings, and evaluator independence.
- Lifecycle states, governance boundaries, retention, and federation considerations.
- Candidate JSON representations, validation rules, and conformance tests.

### 1.2 Out of scope

This proposal does not mandate a database engine, a single ontology, an embedding model, a scoring formula, a consensus protocol, or any intelligence algorithm. It does not imply that stored evidence is true, that a matching case is safe to reuse, or that a registry can authorize an action. Domain-specific schemas and privacy controls may add constraints.

### 1.3 Normative terminology

**MUST**, **MUST NOT**, **SHOULD**, and **MAY** describe requirements *within this candidate specification*, not obligations imposed by an established external standard. A conforming implementation is one tested against a stated version and profile of this proposal.

## 2. Position in the SIF Architecture

```text
Problem / PSM                               Capability / SCM
   |                                               |
   v                                               v
Requirements & context                  Capability definitions
   |                                               |
   +------------> Precedent retrieval <-------------+
                          |
               Structural Precedent Registry
              /            |              \
       Precedent cases   Evidence       Counter-evidence
              \            |              /
               Applicability & risk review
                          |
                 Candidate composition
                          |
               MIAS / independent validation
                          |
               Policy-authorized execution
                          |
                Outcome and failure records
                          |
                     Registry update
```

The SPR serves discovery, comparison, and learning. The **Policy & Authority** function remains separate. The **Evidence & Audit** function must preserve provenance and negative results. The **Scoring & Decision** function may rank candidates but must not silently replace hard applicability constraints.

## 3. Core Object Model

SPR v0.1 proposes five first-class record kinds and two optional supporting kinds.

| Kind | Purpose | Required relationships |
|---|---|---|
| `capability_definition` | Describes a reusable intelligence capability and its contract | `contract_ref` |
| `precedent_case` | Records a specific application of one or more capabilities | `problem_ref`, `capability_refs`, `outcome` |
| `evidence_record` | Supports or qualifies a claim with a reproducible observation | `subject_ref`, `method`, `provenance` |
| `counter_evidence_record` | Challenges a claim, assumption, evaluator, or transfer boundary | `target_refs`, `failure_mode`, `provenance` |
| `lineage_record` | Records adaptation, composition, replacement, or derivation | `source_refs`, `target_ref`, `relation` |
| `evaluation_protocol` (optional) | Identifies test criteria, baselines, and evaluator configuration | `protocol_version` |
| `context_profile` (optional) | Reusable representation of environment and boundary conditions | `context_signature` |

**Separation rule:** A capability definition describes a proposed ability; a precedent case records an application; an evidence record supports an observation. These are not interchangeable. A single case may cite many evidence and counter-evidence records; a capability may have multiple successful and failed cases.

## 4. Common Record Envelope

Every first-class record MUST contain the following fields:

| Field | Type | Meaning |
|---|---|---|
| `schema_version` | string | Schema release, e.g. `0.1.0` |
| `record_id` | string | Stable, globally distinguishable logical identifier |
| `record_kind` | enum | One of the five core kinds |
| `record_version` | string | Version of this record's substantive content |
| `created_at` | RFC 3339 timestamp | Initial creation time |
| `updated_at` | RFC 3339 timestamp | Most recent content update |
| `issuer` | object | Issuing organization or agent and accountable contact reference |
| `lifecycle_state` | enum | See Section 10 |
| `visibility` | enum | `public`, `restricted`, or `private` |
| `payload` | object | Kind-specific content |

Recommended fields: `digest`, `signature_ref`, `provenance_refs`, `supersedes`, `tags`, `ontology_refs`, `access_policy_ref`, `retention_policy_ref`, and `extensions`.

A `record_id` MUST NOT be silently reassigned. Substantive changes MUST increment `record_version` and preserve a traceable predecessor. A content digest SHOULD cover a canonical serialization; implementations MUST declare their canonicalization procedure if digests are used. Timestamps alone do not prove chronology or authenticity.

### 4.1 Identifier guidance

The identifier syntax is deliberately implementation-neutral. A possible profile is `urn:sif:spr:<issuer>:<kind>:<local-id>`; this is illustrative, not a registered URN namespace. Resolution and authorization follow the UNT-R contract in SPEC-002. Human-readable names are aliases, not primary identity.

### 4.2 Reference structure

```json
{
  "record_id": "urn:sif:spr:example:capability:route-opt-v2",
  "record_version": "2.1.0",
  "digest": "sha256:<hex-digest-if-available>"
}
```

A reference MUST distinguish an immutable pinned version from a moving alias. Critical validation and execution SHOULD use pinned references. The placeholder digest above is not an actual hash.

## 5. Capability Definition Schema

A `capability_definition.payload` MUST include:

- `name`, `summary`, and `contract_ref`;
- `input_signature` and `output_signature`;
- `applicability` (positive conditions and exclusions);
- `resource_profile` and `governance_requirements`;
- `evidence_refs` (which MAY initially be empty for a declared candidate).

It SHOULD include `algorithm_families`, `application_domains`, `special_signatures`, `granularity`, `relay_endpoints`, `uncertainty_profile`, `known_limitations`, and `counter_evidence_refs`. A capability MAY be an LLM, CCC-based matcher, MDT navigator, optimizer, simulator, World Model, composite Macro-Intelligence Piece, or other future structure. No closed taxonomy is assumed.

**Important:** `evidence_refs: []` means no cited evidence, not demonstrated reliability. Capability claims must not be promoted to validated status solely from their metadata.

## 6. Precedent Case Schema

A `precedent_case.payload` MUST include:

| Field | Meaning |
|---|---|
| `problem_ref` | PSM problem/task identity or a self-contained task description |
| `problem_signature` | Goals, constraints, inputs, and expected outputs |
| `context` | Domain, operating conditions, assumptions, and exclusions |
| `capability_refs` | Version-pinned capabilities or composition graph |
| `adaptations` | Differences from the retrieved precedent or baseline |
| `evaluation_protocol_ref` or `evaluation_description` | How outcome was assessed |
| `outcome` | `success`, `partial`, `failure`, `inconclusive`, or `not_evaluated` |
| `evidence_refs` | Supporting observations; may be empty for unvalidated cases |
| `counter_evidence_refs` | Known challenges, including unresolved ones |

The case SHOULD record baselines, environment version, resource consumption, operational constraints, human interventions, and transfer limits. **Negative and inconclusive cases are first-class precedents**, not records to suppress.

### 6.1 Applicability envelope

The `context` object SHOULD distinguish:

1. **Observed context** — conditions actually tested.
2. **Claimed applicability** — conditions under which reuse is proposed.
3. **Exclusions** — known unsupported or unsafe settings.
4. **Unknowns** — dimensions not measured or insufficiently characterized.

The claimed applicability envelope MUST NOT be treated as proven beyond the observed evidence. Adaptation outside the observed envelope requires renewed validation proportional to risk.

## 7. Evidence Record Schema

An `evidence_record.payload` MUST contain:

- `subject_ref`: the exact claim, capability, case, or evaluation being supported;
- `claim`: the proposition evaluated;
- `method`: test, formal proof, simulation, observation, human review, or other declared method;
- `provenance`: origin, actor, tool/model versions, and collection context;
- `result`: observations and outcome interpretation;
- `limitations`: uncertainty, sampling restrictions, and known threats to validity.

It SHOULD include `dataset_ref`, `evaluation_protocol_ref`, `baseline_refs`, `metrics`, `confidence_description`, `reproduction_instructions`, `artifact_digests`, `independence_declaration`, and `time_window`. Numeric confidence values MUST declare their meaning and calibration method; otherwise use qualitative uncertainty statements rather than unsupported precision.

Evidence MUST NOT be assumed independent merely because two different model names appear. Shared training data, common prompts, shared tools, common evaluation scripts, or common incentives may correlate errors.

## 8. Counter-Evidence Record Schema

A `counter_evidence_record.payload` MUST include:

- `target_refs`: one or more challenged records or claims;
- `failure_mode`: controlled vocabulary plus optional free text;
- `challenge`: falsifiable statement, counterexample, or observed violation;
- `context`: where the challenge applies;
- `method` and `provenance`;
- `observed_result`;
- `resolution_state`: `open`, `confirmed`, `disputed`, `mitigated`, or `refuted`;
- `impact`: effects on applicability, confidence, authorization, or lineage.

Suggested failure-mode categories: `representation`, `localization`, `applicability`, `composition`, `semantic_type`, `context_loss`, `evaluator`, `distribution_shift`, `governance`, `resource`, `security`, `perspective`, and `unknown`.

Counter-evidence MUST remain discoverable after mitigation or supersession. A resolution is a new, attributable claim; it does not erase the historical observation. Claims of refutation SHOULD cite new evidence and identify what was actually disproven.

## 9. Lineage and Structural Evolution

A `lineage_record.payload` MUST include `source_refs`, `target_ref`, `relation`, `reason`, and `evidence_refs`. Candidate relations include:

- `adapted_from` — context-specific transformation;
- `composed_from` — assembly of multiple capabilities;
- `folded_from` — macro-node abstraction retaining traceability;
- `replaces` — operational successor;
- `supersedes_claim` — updated claim, not deletion of earlier evidence;
- `derived_from_failure` — candidate growth motivated by residual/counter-evidence;
- `forked_from` — independent development lineage.

A lineage link asserts a relationship, not equivalent behavior. Composition and folding require new end-to-end evidence where component interactions could change outcomes.

## 10. Lifecycle and Governance

Proposed lifecycle states:

```text
proposed -> registered -> under_review -> validated -> eligible
   |           |               |           |           |
   +--------> rejected <--------+           +--------> suspended
   |                                        |           |
   +-------------------------------> superseded <-------+
                                              |
                                           retired
```

These transitions are illustrative, not an exhaustive finite-state machine. Implementations MUST define authorized transition actors and audit events. `validated` means a specified claim passed a specified protocol within a stated scope; it does **not** mean universally correct. `eligible` means the record may be considered for an operation under an external policy; it does **not** grant permission to execute.

Governance requirements:

1. Registration MUST NOT imply validation.
2. Validation MUST NOT imply authorization.
3. Scoring or retrieval rank MUST NOT override hard policy constraints.
4. Counter-evidence and adverse outcomes MUST be retained according to declared policy.
5. Critical status changes SHOULD be independently reviewable and auditable.
6. Privacy, confidentiality, and security restrictions MUST be enforced before retrieval output is disclosed.

A sandbox may discover and test candidates without allowing production effects. Promotion to a production runtime requires a separate policy decision with explicit scope, actor, and expiry/review conditions where applicable.

## 11. Retrieval and Matching Semantics

### 11.1 Candidate retrieval

An implementation MAY combine lexical search, embedding similarity, CCC matching, MDT navigation, Two-Phase Search, CallingGraph traversal, and registry graph queries. Retrieval should return *candidates*, not verdicts.

### 11.2 Hard gates before ranking

Before presenting a candidate as usable, the system MUST evaluate, to the extent supported by available metadata:

- identity and pinned version resolution;
- type/signature compatibility;
- context and applicability constraints;
- exclusions and known counter-evidence;
- required evidence and risk thresholds;
- policy/authority and data-access restrictions;
- resource and operational feasibility.

Unknown metadata SHOULD produce an `unknown` or `needs_validation` result, not a silent pass. A retrieval system MAY surface ineligible candidates for research if clearly labeled and access controls permit it.

### 11.3 Example retrieval response

```json
{
  "query_id": "query-42",
  "candidate_ref": {
    "record_id": "urn:sif:spr:example:precedent:case-17",
    "record_version": "1.0.0"
  },
  "similarity_score": 0.84,
  "similarity_score_semantics": "illustrative, uncalibrated rank score",
  "applicability": "needs_validation",
  "unmet_conditions": ["new demand distribution"],
  "counter_evidence_refs": [],
  "recommended_next_step": "sandbox_adaptation_test",
  "authorization": "not_granted"
}
```

A numeric similarity score is not a probability of success unless separately calibrated and validated. `counter_evidence_refs: []` means no references were returned, not proof that no counter-evidence exists.

### 11.4 Candidate adaptation workflow

```text
1. Parse PSM request and context.
2. Resolve SCM capabilities and relevant precedent cases.
3. Retrieve broad candidates (recall-oriented phase).
4. Apply identity, type, context, policy, and evidence gates.
5. Compare candidate with task: matched structure + structural delta.
6. Estimate adaptation cost, residuals, and validation requirements.
7. Test in MIAS; invite independent challenge and evaluator review.
8. If authorized, deploy within a specified boundary.
9. Record outcomes, failures, and new evidence in SPR.
```

The system SHOULD preserve both the selected precedent and plausible rejected alternatives to support audit and anti-Goodhart analysis.

## 12. Example Records (Illustrative JSON)

The following examples are pedagogical and omit some common-envelope metadata for brevity. They are **not complete schema-valid fixtures** until all mandatory envelope fields from Section 4 are supplied.

### 12.1 Capability definition

```json
{
  "schema_version": "0.1.0",
  "record_id": "urn:sif:spr:example:capability:route-opt-v2",
  "record_kind": "capability_definition",
  "record_version": "2.1.0",
  "created_at": "2026-10-01T00:00:00Z",
  "updated_at": "2026-10-01T00:00:00Z",
  "issuer": {"id": "example-research-lab"},
  "lifecycle_state": "registered",
  "visibility": "public",
  "payload": {
    "name": "Constrained Route Optimizer",
    "summary": "Candidate route selection under capacity constraints",
    "contract_ref": "urn:sif:sic:example:route-opt:2.1.0",
    "input_signature": {"type_ref": "example:route-problem:v2"},
    "output_signature": {"type_ref": "example:route-plan:v2"},
    "applicability": {
      "required": ["static road graph", "known capacities"],
      "exclusions": ["unmodeled real-time hazards"]
    },
    "resource_profile": {"compute_class": "medium"},
    "governance_requirements": ["human_approval_for_live_dispatch"],
    "evidence_refs": []
  }
}
```

### 12.2 Precedent case

```json
{
  "schema_version": "0.1.0",
  "record_id": "urn:sif:spr:example:precedent:case-17",
  "record_kind": "precedent_case",
  "record_version": "1.0.0",
  "created_at": "2026-10-02T00:00:00Z",
  "updated_at": "2026-10-02T00:00:00Z",
  "issuer": {"id": "example-research-lab"},
  "lifecycle_state": "under_review",
  "visibility": "public",
  "payload": {
    "problem_ref": "example:psm:regional-delivery-17",
    "problem_signature": {"goal": "reduce simulated delivery cost", "constraints": ["vehicle capacity"]},
    "context": {
      "observed": ["synthetic demand", "static road graph"],
      "claimed_applicability": ["similar static planning scenarios"],
      "exclusions": ["emergency response"],
      "unknowns": ["distribution shift robustness"]
    },
    "capability_refs": [{"record_id": "urn:sif:spr:example:capability:route-opt-v2", "record_version": "2.1.0"}],
    "adaptations": ["changed vehicle capacity parameters"],
    "evaluation_description": "illustrative simulation comparison; no empirical claim",
    "outcome": "not_evaluated",
    "evidence_refs": [],
    "counter_evidence_refs": []
  }
}
```

### 12.3 Counter-evidence

```json
{
  "schema_version": "0.1.0",
  "record_id": "urn:sif:spr:example:counter-evidence:ce-04",
  "record_kind": "counter_evidence_record",
  "record_version": "1.0.0",
  "created_at": "2026-10-03T00:00:00Z",
  "updated_at": "2026-10-03T00:00:00Z",
  "issuer": {"id": "example-challenger"},
  "lifecycle_state": "registered",
  "visibility": "public",
  "payload": {
    "target_refs": [{"record_id": "urn:sif:spr:example:precedent:case-17", "record_version": "1.0.0"}],
    "failure_mode": "distribution_shift",
    "challenge": "Static-demand precedent may fail when demand spikes unpredictably",
    "context": {"scenario": "hypothetical demand spike"},
    "method": "proposed stress test; not executed",
    "provenance": {"author": "example-challenger", "status": "hypothesis"},
    "observed_result": "not_tested",
    "resolution_state": "open",
    "impact": "requires robustness evaluation before transfer"
  }
}
```

**Example integrity note:** The counter-evidence example is an untested challenge, not a demonstrated failure. Implementations SHOULD distinguish proposed challenges from observed falsifications, including in user-facing summaries.

## 13. Query and Update Interface (Candidate)

This schema does not prescribe REST, GraphQL, SQL, or message buses. The following logical operations MAY be exposed via adapters and SPEC-002 relay mechanisms:

| Operation | Input | Output | Minimum safeguards |
|---|---|---|---|
| `registerRecord` | typed record | ID, pinned version, validation report | schema check, authenticated issuer |
| `resolveRecord` | ID + version/alias | record or access-denied/not-found | access control, version semantics |
| `searchPrecedents` | problem signature, context, filters | candidate references + gate results | no unauthorized disclosure |
| `getEvidenceGraph` | subject reference | evidence/counter-evidence lineage | provenance, visibility filtering |
| `submitChallenge` | counter-evidence record | challenge reference | immutable audit trail |
| `proposeSupersession` | old ref, new ref, rationale | pending lineage/status event | authorized review |
| `appendOutcome` | case ref, outcome evidence | new case/evidence version | preserve original history |

The registry MUST NOT offer an implicit `authorizeProduction` side effect as part of `searchPrecedents`. Authorization belongs to the external policy control plane.

## 14. Validation Rules

At minimum, a conforming validator MUST check:

1. Presence and types of all required envelope fields.
2. Recognized `record_kind` and matching payload requirements.
3. Well-formed timestamps and declared schema versions.
4. No duplicate `(record_id, record_version)` with conflicting content.
5. Reference syntax and declared handling of unresolved references.
6. Valid lifecycle transitions according to the implementation's policy.
7. Non-erasure of evidence and counter-evidence through supersession.
8. Explicit `unknown` semantics for absent evidence and applicability.
9. Separation of retrieval rank, validation status, and authorization status.
10. Access-control enforcement for private and restricted records.

An implementation SHOULD also check circular lineage, dangling references, incompatible contract versions, false claims of evaluator independence, and inconsistent evidence interpretation. Cycles may be meaningful in general graphs but MUST NOT masquerade as a valid acyclic derivation chain.

## 15. Conformance Profiles

| Profile | Required capabilities | Intended use |
|---|---|---|
| **SPR-D — Discovery** | envelope, capabilities, cases, basic retrieval, visibility | research inventory |
| **SPR-E — Evidence-Aware** | SPR-D + evidence, counter-evidence, pinned refs, provenance, applicability gates | research validation |
| **SPR-G — Governed Evolution** | SPR-E + lifecycle audit, lineage, policy integration, independent review hooks | controlled evolution |

A system MUST declare its profile and schema version. Passing SPR-D does not imply SPR-E or SPR-G. A claimed profile is not independently certified unless a separately documented conformance process has actually been completed.

### 15.1 Candidate conformance tests

| ID | Test | Expected behavior |
|---|---|---|
| SPR-T01 | Register a valid capability | Accept with pinned identity |
| SPR-T02 | Omit mandatory envelope field | Reject with field-level error |
| SPR-T03 | Duplicate ID/version with different payload | Reject conflict |
| SPR-T04 | Resolve pinned historic version | Return original content |
| SPR-T05 | Query capability with incompatible input type | Mark incompatible |
| SPR-T06 | Query outside applicability envelope | Flag needs validation/ineligible |
| SPR-T07 | Query without evidence | Do not label validated |
| SPR-T08 | Attach counter-evidence | Preserve and surface it |
| SPR-T09 | Supersede a failed case | Keep historical failure retrievable |
| SPR-T10 | Retrieve private case without permission | Deny disclosure |
| SPR-T11 | Rank high-similarity but policy-blocked case | Keep blocked |
| SPR-T12 | Attempt validation-to-authorization shortcut | Reject shortcut |
| SPR-T13 | Submit untested counterexample | Label challenge as untested |
| SPR-T14 | Pin dependency and change latest alias | Preserve pinned dependency |
| SPR-T15 | Record evaluator conflicts | Preserve independence metadata |
| SPR-T16 | Derive Macro-Intelligence Piece from components | Require new composition evidence |
| SPR-T17 | Query unknown context attribute | Return explicit uncertainty |
| SPR-T18 | Export/import across two registry implementations | Preserve identity and provenance |

These are proposed test cases, not results of tests performed for this document.

## 16. Security, Privacy, and Threat Model

Threats include forged evidence, malicious registry entries, prompt-injection payloads in descriptions, capability impersonation, poisoned retrieval scores, privacy leakage, unauthorized execution, stale dependencies, and coordinated evaluator manipulation.

Recommended controls include signed provenance where appropriate, access control before search-result generation, isolation of untrusted descriptions from executable instructions, immutable audit logs or equivalent tamper-evident histories, least-privilege relay credentials, rate limits, revocation mechanisms, and periodic re-evaluation of high-impact claims. A cryptographic signature establishes an attributable signer only to the extent that identity and key management are trustworthy; it does not establish scientific validity.

Federated registries SHOULD distinguish source trust from claim validity, preserve original issuer identity, prevent silent semantic coercion during import, and make conflicting evidence discoverable to authorized reviewers. Data minimization and retention constraints may require keeping only secure references rather than raw sensitive datasets.

## 17. Relationship to the Four Functional Domains

**Localization:** The SPR improves intelligence addressing by connecting problem signatures, capability contracts, and tested application contexts. LLM, CCC, MDT, Two-Phase Search, and CallingGraph may act as complementary retrieval and navigation mechanisms.

**Per-Node Intelligence:** The SPR is algorithm-neutral and can register deterministic tools, learned models, World Models, policy evaluators, and composite intelligence units, including PIRP/PIRU transitions.

**Universal Control Planes and Scoring Folding:** Evidence and counter-evidence constrain scoring and selection; external policy governs action. Folded macro-structures retain links to internal components, tests, and applicable constraints.

**Residual-Based Structural Growth:** Failed retrieval, type mismatches, unvalidated transfer, poor composition, or contradictory evidence become typed residuals. These can trigger MIAS exploration, candidate adaptation, or new structural discovery without automatic promotion.

## 18. Experimental Validation Roadmap

**Phase 1 — Schema integrity:** Implement a small reference dataset of capabilities, cases, evidence, and counter-evidence; test identity and versioning invariants.

**Phase 2 — Retrieval quality:** Compare lexical, embedding, CCC/MDT, and hybrid retrieval on labeled problem–capability matching tasks; measure recall, ranking, and failure detection.

**Phase 3 — Applicability calibration:** Introduce context shifts and exclusions; measure how often hard gates prevent unjustified precedent transfer.

**Phase 4 — Adversarial challenge:** Use independent challengers and evaluators to seed false claims, ambiguous cases, and evaluator vulnerabilities; track detection and false-positive rates.

**Phase 5 — Collective evolution:** Exchange versioned records between independently managed registries; evaluate portability, provenance preservation, conflicts, and useful structural reuse.

Metrics SHOULD include transfer success under declared conditions, harmful-transfer rate, counter-evidence retrieval rate, provenance completeness, calibration of applicability judgments, audit reconstruction time, and registry operating cost. Pre-register evaluation criteria when feasible; publish negative findings.

## 19. Testable Hypotheses

- **H1:** Evidence-aware precedent retrieval reduces invalid structural transfers relative to similarity-only retrieval.
- **H2:** Explicit applicability exclusions reduce deployment of superficially similar but unsuitable capabilities.
- **H3:** Storing failed cases improves future failure prediction compared with success-only registries.
- **H4:** Version-pinned contract and case references improve reproducibility across model and runtime updates.
- **H5:** Counter-evidence-aware ranking yields better risk-adjusted selection than positive-score-only ranking.
- **H6:** Independent evaluator provenance improves detection of correlated validation failures.
- **H7:** Registry lineage improves adaptation efficiency without erasing provenance or adverse results.
- **H8:** Federated record exchange enables useful collective structural learning under constrained trust boundaries.

These are research hypotheses, not empirical conclusions. They require appropriate baselines, controlled experiments, and independent replication.

## 20. Open Questions

1. How should an applicability envelope be represented when domain ontologies disagree?
2. Which retrieval features predict reliable transfer rather than superficial similarity?
3. How should contradictory evidence be aggregated without hiding minority but important failure modes?
4. How can evaluators be challenged without creating unbounded recursive review costs?
5. Which privacy-preserving evidence summaries retain enough information for independent verification?
6. When does a folded Macro-Intelligence Piece deserve a new capability identity versus a new version?
7. How should dynamic environments trigger revalidation or suspension of old precedents?
8. How can the registry discover previously unrepresented perspectives rather than merely index familiar ones?

## 21. Related SIF Documents

- [SIF-003 — Structural Precedents and Open Intelligence Evolution](../docs/foundations/SIF-003-Structural-Precedents-and-Open-Intelligence-Evolution.md)
- [SIF-008 — Dual Maps and Bidirectional Structural Mapping](../docs/interoperability/SIF-008-Dual-Maps-and-Bidirectional-Structural-Mapping.md)
- [SIF-009 — Structural Precedent Registry](../docs/interoperability/SIF-009-Structural-Precedent-Registry.md)
- [SIF-010 — Universal Naming, Typing and Relay](../docs/interoperability/SIF-010-Universal-Naming-Typing-and-Relay.md)
- [SIF-011 — Structural Intelligence Contracts and Portable Units](../docs/interoperability/SIF-011-Structural-Intelligence-Contracts-and-Portable-Units.md)
- [SIF-012 — Multi-Intelligence Adversarial Sandbox](../docs/validation-and-evolution/SIF-012-Multi-Intelligence-Adversarial-Sandbox.md)
- [SIF-013 — Structural Counter-Evidence and Evaluator Governance](../docs/validation-and-evolution/SIF-013-Structural-Counter-Evidence-and-Evaluator-Governance.md)
- [SIF-014 — Open-Ended Structural Growth and Collective Learning](../docs/validation-and-evolution/SIF-014-Open-Ended-Structural-Growth-and-Collective-Learning.md)
- [SPEC-001 — SIF Structural Intelligence Contract](SPEC-001-SIF-Structural-Intelligence-Contract.md)
- [SPEC-002 — Universal Name, Type and Relay API](SPEC-002-Universal-Name-Type-and-Relay-API.md)
- [SPEC-004 — Sandbox Evidence and Growth Lifecycle](SPEC-004-Sandbox-Evidence-and-Growth-Lifecycle.md) *(planned)*

## 22. Figure Placement Guidance

- **Fig-003 — Problem–Capability Dual Maps:** after Section 2, to show the two maps joined by the registry.
- **Fig-005 — Structural Precedent Intelligence:** after Section 3, illustrating capability definitions, cases, evidence, and counter-evidence.
- **Fig-004 — Universal Contracts and Relay:** after Section 4 or Section 13, illustrating identity, typed references, and interface exchange.
- **Fig-006 — Multi-Intelligence Adversarial Sandbox:** after Section 11, illustrating candidate testing and independent challenge.
- **Fig-007 — Structural Growth and Evolution Loop:** after Section 17, illustrating how failures and residuals return to discovery.

![Fig-003-Problem-Capability-Dual-Maps.png](../figures/Fig-003-Problem-Capability-Dual-Maps.png)

![Fig-005-Structural-Precedent-Intelligence.png](../figures/Fig-005-Structural-Precedent-Intelligence.png)

![Fig-004-Universal-Contracts-and-Relay.png](../figures/Fig-004-Universal-Contracts-and-Relay.png)

![Fig-006-Multi-Intelligence-Adversarial-Sandbox.png](../figures/Fig-006-Multi-Intelligence-Adversarial-Sandbox.png)

![Fig-007-Structural-Growth-and-Evolution-Loop.png](../figures/Fig-007-Structural-Growth-and-Evolution-Loop.png)

![Fig-008-Perception-Horizon-and-Worldview-Growth.png](../figures/Fig-008-Perception-Horizon-and-Worldview-Growth.png)

## 23. Conclusion

The Structural Precedent Registry is proposed as a bridge between *having intelligence capabilities* and *knowing when, why, and under what conditions to reuse them*. Its central architectural discipline is to separate capability declarations, observed precedent cases, supporting evidence, counter-evidence, and authorization. Versioned identities, explicit applicability envelopes, negative precedents, and auditable lineage make structural reuse contestable rather than automatic. Combined with dual maps, SIC, UNT-R, and MIAS, SPR offers a testable path toward evidence-governed, open-ended structural intelligence evolution.

---

**Citation guidance:** Cite this document as a candidate research specification by Sizhe Tan & GPT-Obot, within the *Structural Intelligence Framework* repository, v1.0.0. Do not describe the schema as a ratified standard or a validated production implementation.

**License:** Apache-2.0 (repository-level license, subject to the published `LICENSE` file).
