# <img src="../../assets/signatures/semantic-temporal-agent-geometry.svg" alt="" width="32" height="32"> Semantic-Temporal Agent Geometry

*An architectural model of persistent semantic identity, temporary execution, and governed geometry evolution across semantic time.*

> **Identity persists through governed continuity. Geometry defines execution. Independent standing governs consequence.**

## Definition

**Semantic-Temporal Agent Geometry (STAG)** is an architectural model in which an agent has a durable logical identity associated with a versioned causal lineage of immutable executable constraint geometries. Each execution resolves an exact geometry through a semantic-time coordinate, binds its inputs and operational state, and runs within independently governed consequence boundaries.

A geometry defines state spaces, objectives, constraints, transitions, requested capabilities, effect semantics, and bindings to governing authority. Its declarations do not create that authority. Promotion and protected execution require independently established standing.

The runtime is a temporary realization of the agent's definition. It may end while the agent's identity, state, commitments, and records persist. A service may reuse a process to host several executions; process reuse neither establishes nor breaks logical continuity.

Two linked histories preserve the architecture's meaning and activity: the **Geometry Timeline** records definitions and their governed evolution; the **Transaction Timeline** records executions, their exact bindings, and their outcomes. Through [Recursive Geometry Evolution](../recursive-geometry-evolution/README.md), an agent may use these records and other observations to propose successors. Independent verification and authorization govern promotion.

**STAG is an integrated architectural model, not an invariant.** The name is proposed terminology for this architecture. Exact binding, continuity, independent admission, and consequence standing are separately stated properties that implementations must establish.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | An agent as a governed continuity of computational definitions and recorded activity, independent of any particular runtime instance. |
| Architectural model | **Yes.** Integrates identity, semantic resolution, execution, linked histories, and recursive evolution. |
| Foundational primitive | No. It composes identity, geometry, state, causal relations, transactions, authority, and evidence. |
| Invariant | **No.** Its required invariant kernel governs the behavior of an implementation. |
| Semantic type | `AgentArchitectureSpecification`, specialized for semantic version resolution and governed evolution. |
| Mathematical structure | A transition system over identities, immutable definitions, causal histories, operational state, runtime instances, and effect commitments. |
| Verification obligation | Establish exact execution bindings, identity continuity, durable evidence, sound promotion, and current standing at every covered effect boundary. |
| Proof artifact | A version-bound architecture-conformance argument with supporting binding, lineage, history, and enforcement evidence. |
| Runtime relevance | A resolved version identifies the definition; actual applicability and authority remain subject to current conditions. |

## Architectural components

These are components of the model, rather than additional foundational primitives.

| Component | Role |
| --- | --- |
| **Semantic identity** | A durable logical reference with explicitly governed criteria for continuity, branching, transfer, and retirement. |
| **Constraint geometry** | An immutable executable definition and its interpretation, material dependencies, constraints, and effect boundaries. |
| **Semantic Time** | The model of immutable version coordinates and causal lineage used to resolve exact definitions. |
| **Geometry Timeline** | Records definitions, transformations, qualification evidence, promotions, and retirement or applicability changes. |
| **Transaction Timeline** | Records execution identities, attempts, inputs, state transitions, outputs, effects, and evidence under exact geometry bindings. |
| **Ephemeral execution** | A bounded runtime realization of a resolved definition against identified input, state, and dependencies. |
| **Recursive Geometry Evolution** | Generates successor proposals from history and observations under independent admission requirements. |
| **Independent standing** | Establishes current eligibility, consequence-specific authority, and required support at promotion and effect commitment. |

## Recursive lifecycle

```text
SEMANTIC IDENTITY AND REQUEST
    ↓ governed version selection
EXACT SEMANTIC-TIME RESOLUTION
    ↓ applicability, input, state, and dependency binding
DURABLE EXECUTION ADMISSION
    ↓
TEMPORARY RUNTIME EXECUTION
    ↓ current standing at each protected boundary
CONSEQUENCE COMMITMENT AND DURABLE EVIDENCE
    ↓
RECORDED OUTCOME AND RUNTIME RELEASE
    ↓ optional transaction, schedule, or environment trigger
RECURSIVE EVALUATION
    ↓
IMMUTABLE CANDIDATE GEOMETRY
    ↓ independent verification and authorization
PROMOTE UNDER ENFORCED ORDERING / REJECT
    ↓ promoted version available for qualified future executions
SEMANTIC-TIME RESOLUTION
```

Resolution does not by itself yield an authoritative geometry. Version selection and admission must establish applicability. Candidate rejection does not renew the previous version's standing; that version may continue only while independently eligible.

Execution records begin before consequential work and acquire further events as work proceeds. The diagram does not postpone recording until after effects or imply that every runtime reaches a successful terminal outcome.

## Formal identity

- **Identifier:** `SEMANTIC_TEMPORAL_AGENT_GEOMETRY`
- **Type:** `AgentArchitectureSpecification`
- **Abbreviation:** `STAG`

A specification can be represented as:

```math
\mathcal{S}=\langle\mathcal{I},\mathcal{T},H_G,H_X,\mathcal{E},L,M,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $\mathcal{I}$ | Semantic identities and their independently specified continuity and lifecycle criteria. |
| $\mathcal{T}$ | The Semantic Time model, including coordinates, causal relations, and immutable definition resolution. |
| $H_G$ | Geometry-history records and the exact artifacts and evidence they reference. |
| $H_X$ | Transaction-history records and their bindings to definitions, operational state, effects, and outcomes. |
| $\mathcal{E}$ | The Recursive Geometry Evolution specification, including proposal and preservation obligations. |
| $L$ | Independently constituted governing contracts, delegation, amendment, and applicability rules. |
| $M$ | The complete mechanism, including runtime execution, state storage, admission, promotion, commitment, recovery, and external receivers. |
| $\Omega$ | Initial states, protected-effect scope, required invariants, retention commitments, environment and failure assumptions, and claimed horizon. |

The tuple defines responsibilities and relationships. It does not prove that histories are trustworthy, that identity persists, or that a deployment enforces its declared rules.

### Exact temporal binding

A **transaction** here is a declared logical execution unit, not an assertion that all its work is one atomic database transaction. A compound interaction identifies its constituent units or binds one immutable manifest of component definitions. Protected effects can have several distinct commitment boundaries within the interaction.

Let $\rho$ be a covered execution and $\mathrm{Units}(\rho)$ its actual executed units, including units that execute through a bypass. With $C$ denoting the semantic coordinates in $\mathcal{T}$:

```math
\begin{aligned}
&\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall x\in\mathrm{Units}(\rho):\\
&\quad\exists\tau\in C:\;
\mathrm{Bindings}(x)=\{\tau\}\\
&\qquad\land\mathrm{Entity}(\tau)=\mathrm{Agent}(x)\\
&\qquad\land\mathrm{DefinitionUsed}(x)
=\mathrm{Geometry}(\mathrm{Resolve}(\tau)).
\end{aligned}
```

`Bindings` identifies the coordinates actually bound to execution; the singleton excludes missing or ambiguous bindings. `Entity` identifies the coordinate's agent namespace. `DefinitionUsed` includes the executable and material interpretation semantics actually used. Reusable components may have their own identities, explicitly referenced by the agent's manifest.

This condition is **exact temporal binding**, rather than deterministic execution. Identical geometry versions can produce different outputs because inputs, state, observations, runtime behavior, or nondeterministic choices differ. Reproducible outputs require additional captured conditions and evidence.

The formula is one required invariant, not a complete STAG conformance test. An unresolved request may be rejected before execution and recorded as such; it must not silently execute under a fallback definition. Immutable resolution, verifiable lineage, current standing, and faithful records require their own enforcement.

## Two linked histories

| History | Required content | Relationship to the other history |
| --- | --- | --- |
| **Geometry Timeline** | Immutable coordinates and artifact references; predecessors; transformation and migration specifications; qualification evidence; promotion, retirement, and applicability events. | Identifies the definitions used by transactions and the transactions or observations supporting evolution proposals. |
| **Transaction Timeline** | Transaction and attempt identities; agent and geometry bindings; inputs, state and dependency versions; transitions, outputs, failures, effect intents, actual commitments, and evidence. | References the exact geometry governing each execution and supplies declared evidence for later evaluation. |

“Timeline” does not require one global total order. Geometry histories may branch and merge; concurrent transactions may be causally independent. Material dependency references and conflicting commitments require explicit relations and enforceable ordering. Recording timestamps cannot substitute for those semantics.

Historical records are immutable within the declared retention contract. Later outcomes, corrections, revocations, and recovery findings append new facts rather than silently replacing earlier records. A mutable routing pointer may select a version for new work, but its changes must be governed and the selected version must be durably bound before use.

Cross-history references must resolve to the actual recorded artifacts and events. A promotion record and its activation cannot disagree about the admitted version. The mechanism must commit the relevant facts consistently or use a justified recovery protocol that prevents unsupported activation. A prepared record is not proof of completed activation.

Retain payloads or trustworthy references sufficient for the claimed interpretation and retention scope. A surviving identifier or digest cannot reconstruct deleted state, missing model artifacts, or unavailable external observations. Unknown results must remain unknown until supported by evidence.

## Identity, geometry, state, and runtime

| Dimension | What persists or changes |
| --- | --- |
| **Logical identity** | Can persist across versions and process lifetimes when independently defined continuity criteria hold. |
| **Geometry** | An individual version remains immutable; authorized successors may change behavior, schemas, or requested capabilities. |
| **Operational state** | Evolves through recorded transitions and explicitly qualified migrations; it is not recoverable from geometry alone. |
| **Runtime instance** | Realizes a particular execution and may be started, replaced, resumed, or released without constituting the agent's identity. |
| **Authority** | Depends on current grants, applicability, dependencies, and the exact consequence, regardless of which artifacts persist. |

A process identifier, stable agent name, or common ancestor is insufficient evidence of legitimate continuity. Branches need explicit identity rules: two descendants may share ancestry without both being interchangeable realizations of the same agent. Merges and identity transfers require defined reconciliation and governing authority.

Continuity does not imply constant behavior or uninterrupted operation. Conversely, an uninterrupted process can lose standing or violate identity obligations when its definition, relationships, or governing conditions change.

## Required invariant kernel

> **Every covered execution binds an exact immutable geometry with verifiable continuity, and every protected consequence requires independently established current standing at commitment. No geometry may authorize its own promotion or expansion of authority.**

| Invariant ID | Obligation |
| --- | --- |
| `STAG_EXECUTION_HAS_ONE_EXACT_BINDING` | Every actual executed unit MUST retain its immutable geometry or component-manifest binding. Changing that definition requires a new explicitly qualified unit. |
| `STAG_ACTUAL_EXECUTION_MATCHES_BINDING` | Inputs, executable artifacts, state, dependencies, and effect paths MUST correspond to the declared execution binding; undeclared mutable substitutions cannot be omitted from the claim. |
| `STAG_CONTINUITY_IS_INDEPENDENTLY_ESTABLISHED` | Claimed identity and constitutive lineage MUST satisfy independently specified criteria with trustworthy evidence. |
| `STAG_HISTORY_PRESERVES_ACTUAL_EVENTS` | Geometry and execution records MUST retain exact identities and distinguish requests, admissions, intents, actual commitments, and unresolved or failed outcomes. |
| `STAG_PROMOTION_HAS_INDEPENDENT_AUTHORITY` | Candidate verification and promotion MUST follow previously applicable governance, preserve required obligations, and remain outside the proposer's unilateral control. |
| `STAG_EFFECTS_REQUIRE_CURRENT_STANDING` | Each protected effect MUST have current standing and enforced ordering with relevant changes at its actual commitment boundary, including external receivers. |
| `STAG_RECOVERY_PRESERVES_BINDING_AND_AUTHORITY` | Retries, restart, rollback, and recovery MUST preserve historical bindings and prevent duplicate or newly unauthorized effects. |
| `STAG_CLAIMS_COVER_THE_DEPLOYMENT` | Verification MUST cover all actual consequential routes and trust assumptions, including administrative changes, old workers, delegated tasks, and failures. |

Recursive proposal generation is an architectural capability, rather than a safety invariant requiring an agent to modify itself. Cycles may produce no candidate, reject every candidate, or stop. Useful-adaptation and availability claims require separate progress evidence.

## Commitment, failure, and recovery

**Bind before executing.** Persist the admitted unit identity, exact geometry, input and state references, and relevant dependency bindings before consequential execution. State reads, concurrent writes, and shared budgets need mechanisms that preserve the operation's actual consistency requirements; versioned geometry alone cannot prevent conflicting updates.

**Record effects at their actual boundaries.** Local consequence and required evidence must be committed atomically under the boundary's semantics. For external effects, the initial durable record covers an authorized intent. The receiver must establish current standing and enforce ordering at actual effect commitment; completion evidence is recorded separately. An intent cannot be presented as a completed effect.

**Represent incomplete work honestly.** A crash may leave an admitted unit or external intent unresolved. Durable lifecycle records must support reconciliation without inventing outputs or assuming that an uncertain effect never happened. Continuing effects and intermediate protected sub-effects need explicit standing and recording semantics.

**Distinguish attempts from new work.** A retry has its own attempt identity linked to the original unit and binding. It must recover the known result or use appropriate duplicate-effect prevention before performing a new effect. Rebinding to a newer geometry creates a separately identified, requalified unit; it cannot rewrite the original transaction. Any new effect still requires current standing.

**Retain or fence old execution deliberately.** Promotion can change the default for future work without changing in-flight bindings. Existing work may continue only where its version and conditions remain applicable. Otherwise it must stop, be fenced, or undergo an explicitly qualified transition. Runtime termination alone does not revoke delegated credentials or cancel external work.

## Recursive evolution and promotion

RGE may evaluate individual transactions, accumulated history, scheduled observations, or environmental changes. Every candidate is recorded under an immutable coordinate before qualification. Promotion adds a governed applicability event; it does not manufacture a new authority merely by publishing a version identifier.

Qualification covers the exact source, candidate, dependency changes, state migration, and coexistence with old work. Competing promotions and rollback must respect an enforceable ordering or explicit branch policy. Preservation must hold during deployment and recovery, not only in the candidate's final configuration.

The proposer cannot independently replace the rules, evidence, or enforcement that admit its own successor. Admission may be automated under valid prior delegation. Broader capabilities require independently authorized grants or amendments; an improvement score cannot supply them. Successful promotion likewise does not preauthorize every subsequent consequence.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual architecture specification; it does not establish its invariants.
public sealed class SemanticTemporalAgentGeometry<TState, TConsequence>
    : AgentArchitectureSpecification<TState, TConsequence>
{
}
```

The specification carries identity criteria, geometry and history schemas, semantic resolution, execution-unit boundaries, operational state and migration rules, evolution mechanisms, independent governance, protected effects, and recovery and retention assumptions.

A separate **STAG Conformance Argument** establishes the claimed properties for exact model and deployment versions. Supporting evidence must connect definition resolution to actual execution, both histories to real events, promotion to independent authority, and all protected effects to current standing. Evidence for components does not automatically establish their composition: scope, bindings, concurrency, failure semantics, and trusted mechanisms must agree.

## Relationship to the existing architecture

| Concept | Relationship to STAG |
| --- | --- |
| [Constraint Geometry](../constraint-geometry/README.md) | Specifies the immutable executable behavioral artifact instantiated by a STAG execution, distinct from runtime state, agent identity, and current authority. |
| [Constraint-Governed Agency](../constraint-governed-agency/README.md) | Supplies the broader model of agents as governed configurations. STAG specializes it with persistent semantic identity, temporary execution, linked histories, and recursive evolution. |
| [Semantic Time](../semantic-time/README.md) | Identifies exact definitions and their causal relationships; STAG binds those coordinates to agent executions and recorded outcomes. |
| [Recursive Geometry Evolution](../recursive-geometry-evolution/README.md) | Provides the governed proposal and promotion model for successor geometries. |
| [Generative Root Geometry](../../invariants/generative-root-geometry/README.md) | Supplies the distinction between differentiated expression and verifiable constitutive continuity. |
| [Structural Standing](../../invariants/structural-standing/README.md) | Requires actual eligibility and support for every enabled protected effect throughout the mechanism. |
| [Temporal Standing](../../invariants/temporal-standing/README.md) | Makes current applicability, exact binding, and enforced commitment ordering explicit at promotion and every effect boundary. |
| [Constitutive Floor](../../arguments/constitutive-floor/README.md) | Requires evidence that implementation and deployment actually preserve the claimed necessary contracts. |

## Examples

| Situation | STAG assessment |
| --- | --- |
| A worker terminates, and another loads the same agent's qualified geometry and durable state | Logical continuity can survive the runtime change when identity criteria, bindings, and current standing hold. |
| A newer geometry is promoted while a transaction is still running | The transaction retains its original binding; continuation depends on current applicability rather than automatic substitution. |
| Two executions use the same geometry and produce different outputs | Exact binding may still hold. Deterministic replay is a separate claim about inputs, state, dependencies, and nondeterminism. |
| A receiver may have completed an effect before the sender crashed | The transaction remains unresolved until reconciliation establishes the outcome; blind replay risks a duplicate effect. |
| A candidate grants itself broader effect authority in its own definition | The declaration cannot authorize promotion or the expanded effects. Independent authority is required. |
| Two branches descend from the same agent geometry | Shared lineage does not decide whether they retain one identity, become distinct identities, or can later merge. |

## Scope and limits

STAG does not assert that intelligence requires temporary processes or that persistent software cannot implement this model. The defining relationship is between governed identity, exact definitions, recorded execution, and current authority. Its guarantees do not depend on anthropomorphic names or a continuous worker process.

The model does not establish improved intelligence, beneficial recursive evolution, deterministic output, or factual correctness merely by retaining histories. Signatures and content digests can support integrity under declared assumptions; they cannot establish legitimate continuity or authority by themselves.

A system that never admits work may satisfy safety obligations vacuously. Claims of useful agency need feasible legitimate executions and separate progress or availability arguments. Deployment guarantees remain conditional on verified correspondence and explicit trust, scope, timing, and failure assumptions.

## Governing principle

> **The agent's continuity is governed across definitions and executions. No individual process constitutes that continuity or its authority.**

**The geometry defines. The transaction realizes and records. Semantic time identifies. Evolution proposes. Independent standing governs consequence.**

---

© 2026 Beau Crawford
