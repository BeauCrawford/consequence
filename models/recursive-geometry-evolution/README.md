# <img src="../../assets/signatures/recursive-geometry-evolution.svg" alt="" width="32" height="32"> Recursive Geometry Evolution

*An architectural model of governed self-modification of executable constraint geometries across semantic time.*

> **Geometry may propose its own evolution. It cannot authorize its own promotion.**

## Definition

**Recursive Geometry Evolution (RGE)** is an architectural model in which an autonomous computational system uses execution history and observations to evaluate its behavior and propose successor versions of its own executable constraint geometry. Independent verification and governance determine whether a candidate may become applicable to subsequent execution.

An evolution mechanism implements the model. It may be triggered by an individual transaction, accumulated observations, a schedule, a counterexample, or environmental change. Recursion means that admitted successors can participate in further proposal cycles; it does not require continuous execution, unlimited recursion, or a successful change on every cycle.

A candidate may revise state spaces, objectives, constraints, transitions, requested capabilities, or operational strategies. Each candidate receives an immutable [Semantic Time](../semantic-time/README.md) identity before qualification. Promotion requires verifiable constitutive lineage, satisfaction of applicable obligations, and independently established authority for the exact change and its effects.

**RGE is a model that requires invariants, not an invariant itself.** The name is proposed terminology for this architecture. Evolution describes change; improvement, preserved identity, and legitimate authority each require their own evidence.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | Computational definitions as artifacts that can participate in proposing their own successors. |
| Architectural model | **Yes.** A model of proposal, evaluation, verification, authorization, promotion, and continued execution. |
| Computational mechanism | An implementation of the model carries out the evolution cycle. |
| Foundational primitive | No. It depends on geometry, history, transformation, semantic identity, authority, and effect boundaries. |
| Invariant | **No.** Binding, continuity, preservation, and independent promotion are required properties. |
| Semantic type | `GovernedEvolutionModel`, with separately stated conformance and preservation obligations. |
| Mathematical structure | A transition system over versioned geometries, proposals, evidence, governance, deployment state, and in-flight work. |
| Verification obligation | Establish preservation through both candidate operation and its actual introduction into the running system. |
| Proof artifact | A version-bound evolution-conformance argument and independently checkable candidate qualification evidence. |
| Runtime relevance | Claims hold only where actual execution, promotion, and recovery remain within the verified scope. |

## Evolutionary cycle

```text
CURRENT GEOMETRY
    ↓
EXECUTE UNDER AN EXACT VERSION
    ↓
PERSIST EXECUTION HISTORY
    ↓ transaction, observation, schedule, or environment trigger
SELF-EVALUATION AND CANDIDATE GENERATION
    ↓
IMMUTABLE CANDIDATE AND CHANGE MANIFEST
    ↓
VERIFY REQUIRED INVARIANTS AND CONTINUITY
    ↓
INDEPENDENT AUTHORIZATION
    ↓
ORDERED PROMOTION AND STATE MIGRATION
    ↓
EXECUTION UNDER THE ADMITTED SUCCESSOR
    ↺ further proposals
```

Publication makes a candidate identifiable; promotion makes it applicable within an authorized scope. These are separate events. Rejection, unresolved evidence, or failed authorization leaves the candidate unpromoted. The previous geometry may continue only while its own applicability and standing remain valid.

Candidate evaluation can itself produce protected effects, including data access, resource consumption, and external calls. Such effects require their own standing. Calling an execution a simulation or an experiment does not exempt it from governance.

## Formal identity

- **Identifier:** `RECURSIVE_GEOMETRY_EVOLUTION`
- **Type:** `GovernedEvolutionModel`

A specification can be represented as:

```math
\mathcal{E}=\langle\mathcal{G},\mathcal{H},\Pi,L,M,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $\mathcal{G}$ | Immutable geometry versions, including proposed, admitted, retired, and rejected versions. |
| $\mathcal{H}$ | Execution-history and observation records, with exact version bindings, provenance, and declared coverage. |
| $\Pi$ | The candidate-generation relation, which may produce zero, one, or several proposals. |
| $L$ | Independently constituted governing contracts, delegation, continuity criteria, and amendment rules. |
| $M$ | The full mechanism, including generation, validation, authorization, deployment, migration, concurrent workers, recovery, and external effects. |
| $\Omega$ | Initial conditions, protected-effect scope, required invariants, evaluation criteria, trust and failure assumptions, and any claimed horizon. |

For a source geometry $G_s$, a bound history snapshot $H_b$, and a trigger with its relevant context $z$, a proposed candidate satisfies:

```math
G_c\in\Pi(G_s,H_b,z),\qquad
\mathrm{Geometry}(\mathrm{Resolve}(\tau_c))=G_c.
```

Here $\tau_c$ is the candidate's immutable semantic-time coordinate. Its lineage records the source and all other material parents; merged candidates require explicit reconciliation semantics. Candidate generation need not be deterministic, and $G_c$ is not an assertion of improvement or authorization.

The change manifest binds source and candidate coordinates, executable artifacts, changed dependencies, state migration, requested capabilities, and proposed effects. Evaluation evidence also binds the history snapshot, evaluator version, criteria, and relevant execution conditions. A change to a material binding requires requalification of the affected claims.

## Core properties

| Property | Meaning and obligation |
| --- | --- |
| **Recursion** | An admitted geometry may help propose its own successor, including changes to its proposal strategy. Admission remains independently governed. |
| **Adaptation** | History and observations may inform changes; their provenance, coverage, and relevance must be established for the claims made. |
| **Immutability** | Historical geometries remain unchanged. Corrections and transformations receive new versions. |
| **Continuity** | Admitted successors preserve the constitutive relationships required by the independently specified continuity contract. |
| **Identity** | Logical identity, geometry version, and runtime instance remain distinct. Branching or common ancestry alone does not establish the same agent identity. |
| **Authority** | Neither the current geometry nor a candidate can independently authorize its own promotion or expand its grants. |
| **Temporal binding** | Every covered execution unit binds one exact immutable geometry or component manifest; promotion cannot silently replace that binding. |
| **Evolutionary freedom** | New behaviors and capabilities may be proposed within governing boundaries. Capability emergence and beneficial improvement require evaluation. |

“Independent” describes control over admission, not merely a separate process or a second model. The proposer must not unilaterally replace the governing contract, choose easier acceptance criteria, forge qualification evidence, or bypass the enforcing boundary. Changes to those mechanisms require their own authority under the previously applicable rules.

Admission may be automated under valid prior delegation; independence does not require a person approving each cycle.

## Required invariant kernel

> **A geometry may propose transformations of its future behavior, but no transformation may authorize itself or bypass the constituted obligations governing its consequences.**

Let $\rho$ range over executions of $M$ within $\Omega$, and let $\mathrm{Promotions}(\rho)$ include every actual introduction of a geometry into governing execution, including administrative and recovery paths:

```math
\begin{aligned}
&\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall p\in\mathrm{Promotions}(\rho):\\
&\quad\mathrm{ExactBinding}(p)\\
&\qquad\land\mathrm{LineageEstablished}(p)\\
&\qquad\land\mathrm{IndependentAdmission}(p)\\
&\qquad\land\mathrm{Preserves}(p,K)\\
&\qquad\land\mathrm{StandingAndOrder}(p)\\
&\qquad\land\mathrm{DeploymentCorresponds}(p).
\end{aligned}
```

| Predicate | Required meaning |
| --- | --- |
| `ExactBinding` | Qualification and deployment refer to the same source, candidate, migration, dependencies, and effect plan. |
| `LineageEstablished` | Trustworthy evidence establishes the origin and required constitutive relationships of the actual transformation. |
| `IndependentAdmission` | Applicable verification obligations and consequence-specific change authority are established outside the proposer's unilateral control. |
| `Preserves` | The transition and resulting operation preserve the required invariants $K$, including coexistence with outstanding work. |
| `StandingAndOrder` | Promotion itself satisfies current standing and enforceable ordering with relevant changes at its actual commitment boundary. |
| `DeploymentCorresponds` | The deployed artifacts and effect mechanisms correspond to those covered by the evidence and its assumptions. |

These predicates denote substantive obligations, not approval flags. The formula constrains promotions; preservation across all other execution transitions must also be established. It does not confer standing on every future effect of an admitted geometry.

### Preservation through change

Let $K(s)$ express the required invariant kernel over the complete mechanism state. An inductive preservation argument requires:

```math
\begin{aligned}
&\forall s_0\in S_0:\;K(s_0),\\
&\forall s,s':\;
\bigl(K(s)\land\mathrm{Step}_{M,\Omega}(s,s')\bigr)
\Rightarrow K(s').
\end{aligned}
```

$S_0$ is the declared initial-state set. `Step` includes generation, evaluation, promotion, state migration, revocation, dependency changes, retries, recovery, and actual effect commitment. Version-dependent state representations require explicit mappings and preservation arguments; checking only the candidate's final configuration misses unsafe intermediate states.

$K$ is specified independently of the candidate and may refer to the governing rules applicable in each state. Domain policies may change through authorized amendment under previously applicable rules; this does not permit a candidate to erase the obligations used to judge its own admission. Claimed safety properties, their evidence, and changes to policy values must remain distinguishable.

## Promotion, concurrency, and recovery

| Obligation | Requirement |
| --- | --- |
| **Bind evidence to the actual change** | Qualification MUST cover exact artifacts, dependencies, migration, and effects. Substitution after verification invalidates the affected qualification. |
| **Check current conditions** | Promotion MUST establish its own current standing. Earlier approval cannot override effective revocation, expiry, or changed dependencies. |
| **Order competing promotions** | Conflicting changes MUST follow an enforceable ordering or explicit branch policy. Evidence for one source state cannot silently authorize deployment over another. |
| **Preserve in-flight bindings** | Existing work MUST retain its exact version or undergo an explicitly qualified transition. Publishing a new default cannot rewrite an admitted execution. |
| **Account for old workers** | Retired instances, credentials, queues, and delegated tasks MUST be fenced, revoked, or explicitly requalified under applicable rules. |
| **Record actual commitment** | Promotion and its evidence MUST be durably bound. An external deployment intent must be distinguished from completed activation; receivers enforce standing at their actual boundary. |
| **Govern rollback and retries** | Reactivating an old artifact MUST satisfy current authority and migration requirements. A retry must distinguish retrieving an existing result from creating a new effect. |
| **Preserve evidence on failure** | Failed migrations and partial deployments MUST follow a verified recovery path; they cannot silently count as successful promotion. |

An older geometry can remain authorized after a newer version is published. Conversely, successful promotion does not freeze authority or dependencies for future transactions. [Temporal Standing](../../invariants/temporal-standing/README.md) applies at each protected effect boundary, including external receivers.

## Evolution, improvement, and authority

| Claim | Required basis |
| --- | --- |
| **A different geometry exists** | An immutable candidate with an exact change manifest. |
| **The candidate improves a chosen outcome** | Evaluation against independently governed criteria, representative conditions, and declared tradeoffs. |
| **The transformation preserves required properties** | Evidence covering the candidate, migration, coexistence, and relevant failure schedules. |
| **The successor has legitimate continuity** | Established lineage and satisfaction of the application's explicit identity and continuity criteria. |
| **The successor may become active** | Current, independently established promotion authority and enforced admission. |
| **An active successor may perform an effect** | Current standing for that exact effect at commitment. |

Performance gains cannot compensate for violated mandatory invariants. A proposal need not improve every metric; its acceptance criteria must state permissible tradeoffs. Changes to those criteria require independent governance rather than selection by the candidate seeking admission.

[Authority Independence](../../invariants/authority-independence/README.md) supplies the canonical separation requirement. Broader capability grants require valid independent delegation or amendment; recursive proposal generation cannot create that authority.

History supplies observations, not complete coverage of possible behavior. Missing failures, biased workloads, or unmodeled effect paths limit the claims supported by an evaluation. Tests can reveal counterexamples; finite successful runs are not a proof over all future evolutions.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual model specification; it does not prove safe or beneficial evolution.
public sealed class RecursiveGeometryEvolution<TGeometry, TConsequence>
    : GovernedEvolutionModel<TGeometry, TConsequence>
{
}
```

The specification identifies geometry and history schemas, triggers, proposal mechanisms, required invariants, independent admission rules, promotion and migration semantics, recovery paths, protected effects, and trust assumptions.

A separate **Evolution Conformance Argument** binds those obligations to exact model and deployment versions. Each promoted change needs independently checkable qualification evidence, which may reuse valid preservation results where their assumptions still hold. Evidence for one candidate does not establish arbitrary future candidates or implementations.

## Relationship to the existing architecture

| Concept | Relationship to RGE |
| --- | --- |
| [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) | Defines the shared preservation obligation for admitted successors, migrations, and merged lineages. |
| [Constraint Geometry](../constraint-geometry/README.md) | Defines the executable state, transition, constraint, and effect semantics that RGE proposes to transform under independent governance. |
| [Constraint-Governed Agency](../constraint-governed-agency/README.md) | Defines agents as governed configurations. RGE specifies how those configurations can participate in proposing and admitting their successors. |
| [Semantic Time](../semantic-time/README.md) | Gives candidates and executions exact immutable identities and causal lineage; version publication alone does not authorize activation. |
| [Semantic-Temporal Agent Geometry](../semantic-temporal-agent-geometry/README.md) | Integrates RGE with persistent semantic identity, temporary execution, and linked geometry and transaction histories. |
| [Generative Root Geometry](../generative-root-geometry/README.md) | Supplies the distinction between differentiated expression and preservation of constitutive origin. |
| [Structural Standing](../../invariants/structural-standing/README.md) | Requires actual eligibility and support for enabled protected effects throughout evolution. |
| [Temporal Standing](../../invariants/temporal-standing/README.md) | Applies current standing and enforced ordering to promotion, migration, and subsequent effects. |
| [Verified Closure Flywheel](../../patterns/verified-closure-flywheel/README.md) | A compatible engineering pattern focused on reducing invalid reachability while preserving legitimate behavior. RGE more broadly models changes to an agent's own computational definition. |
| [Constitutive Floor](../../arguments/constitutive-floor/README.md) | Supplies proof obligations connecting claimed preservation to actual implementation and deployed effect mechanisms. |

These relationships support an assurance argument only when their scopes, bindings, and assumptions agree. Listing the concepts does not establish their properties.

## Examples

| Situation | RGE assessment |
| --- | --- |
| An agent proposes a strategy that uses fewer tool calls | Evaluate the benefit and required invariants separately; a favorable metric does not authorize promotion. |
| A candidate removes the verifier or relaxes the tests that admit it | Its proposal cannot independently authorize the change or redefine the conditions of its own acceptance. |
| Two candidates are qualified against the same source, then one is promoted first | The second needs a justified branch or requalification against the changed source and migration conditions. |
| A successor introduces a new schema while old workers still write the previous format | The migration and coexistence period require explicit preservation and fencing semantics. |
| Recovery restores a previously authorized version after its grant expires | Historical qualification cannot reactivate authority; restoration is a new governed transition. |
| A runtime terminates and later resumes from a semantic coordinate | Execution may resume only with the exact definition and required current standing; identity continuity remains a separate claim. |

## Scope and limits

RGE does not guarantee increasing intelligence, monotonic performance, indefinite useful evolution, or legitimate identity merely from an unbroken sequence of version references. It does not require a permanently running process or exclude human participation in evaluation and governance.

Rejecting every proposal can satisfy promotion-safety requirements vacuously. A claim of useful adaptation additionally requires feasible admissible changes and evidence of progress. A lineage may branch, merge, retire, or terminate; a single sequence is only one possible history.

The architectural shift is to make the computational definition an explicit, versioned object of governed transformation. Runtime continuity is optional. Legitimate continuity and authority depend on evidence and enforcement.

## Governing principle

> **Behavior may evolve. Constituted obligations remain binding. Authority cannot self-expand.**

**The geometry proposes its successor. Independent evidence qualifies the change. Governance admits its consequences.**

---

© 2026 Beau Crawford
