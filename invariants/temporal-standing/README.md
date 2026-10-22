# <img src="../../assets/signatures/temporal-standing.svg" alt="" width="32" height="32"> Temporal Standing

*A derived invariant of standing at consequence commitment under changing semantics, authority, and dependencies.*

> **A valid past decision does not confer permanent execution authority. Standing must hold when the consequence becomes committed.**

## Definition

**Temporal Standing** is a first-class, derived invariant requiring every covered protected consequence to be bound to an exact semantic definition and independently established standing at its actual commitment boundary. Changes that can affect that standing must participate in an enforceable authoritative ordering relative to commitment.

The relevant changes include revocation, expiry, delegation, governing amendments, geometry promotion, dependency updates, resource consumption, and state migration. Earlier approval, an immutable version identifier, a timestamp, or a signed receipt cannot establish that their conditions still hold when the effect occurs.

Temporal Standing is a **temporal specialization of standing enforcement**. It makes explicit obligations already present in [Structural Standing](../structural-standing/README.md), whose scope includes changing state and commit-time eligibility. It does not replace complete route coverage, sound governing semantics, or actual enforcement.

“Current” means applicable at the effect boundary under independently established governance. It does not necessarily mean the newest published geometry: an older version may remain authorized, while a newer one may lack standing.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | The relationship between standing, changing conditions, and the point at which a consequence becomes committed. |
| Foundational primitive | No. It depends on semantic identity, state, effect, authority, evidence, temporal applicability, and ordering. |
| Semantic type | `TemporalStandingInvariant`, a temporal specialization of `StandingEnforcementInvariant`. |
| Mathematical property | Every covered protected commitment has an unambiguous semantic binding and valid standing under an enforced ordering of relevant changes. |
| Verification obligation | Establish semantic binding, source validity, effective-time rules, conflict ordering, and enforcement at every covered commitment boundary. |
| Proof artifact | A separately established, version-bound Temporal Standing proof or verification argument. |
| Runtime property | Applicable only while the actual deployment, timing assumptions, dependencies, and effect boundaries remain within the verified scope. |

```text
EXACT SEMANTIC DEFINITION
  Identify what computation and effect are being admitted
    ↓ evaluated against
APPLICABLE GOVERNING STATE
  Authority · Eligibility · Evidence · Dependencies
    ↓ remains subject to change before commitment
ACTUAL EFFECT BOUNDARY
  Enforce ordering with revocation, expiry, and material updates
    ↓ only with current standing
COMMITTED CONSEQUENCE
  Record the exact binding and evidence of commitment
```

## Formal identity

- **Identifier:** `TEMPORAL_STANDING_CURRENT_AT_EFFECT_COMMITMENT`
- **Type:** `TemporalStandingInvariant`

For a mechanism model $M$ and declared scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{TemporalStanding}(M,\Omega)\iff\\
&\forall\tau\in\mathrm{Exec}(M,\Omega),\;
\forall c\in\mathrm{ProtectedCommits}(\tau):\\
&\quad\exists\sigma:\;
\mathrm{Bindings}(c)=\{\sigma\}\\
&\qquad\land\mathrm{Applicable}_{\tau}(\sigma,c)\\
&\qquad\land\mathrm{Standing}_{\tau}(q_c,\sigma,c)\\
&\qquad\land\mathrm{OrderEnforced}_{\tau}(q_c,c).
\end{aligned}
```

| Symbol | Meaning |
| --- | --- |
| $M$ | The mechanism model, including effect commitment, relevant changes, and their enforcement semantics. |
| $\Omega$ | Initial states, protected-effect scope, governing applicability rules, environment and timing assumptions, trust dependencies, and any claimed horizon. |
| $\mathrm{Exec}(M,\Omega)$ | All admissible executions and prefixes within the declared scope, including concurrency and failures. |
| $c$ | An actual commitment event at the boundary where the covered effect becomes consequential. |
| $q_c$ | The exact consequential occurrence: actor, target, operation, parameters, and joint obligations. |
| $\sigma$ | An immutable semantic descriptor identifying the executable definition and interpretation relevant to this commitment. |
| $\mathrm{Bindings}(c)$ | The semantic descriptors bound to actual execution; the singleton requirement excludes missing or ambiguous bindings. |
| $\mathrm{Applicable}_{\tau}(\sigma,c)$ | The bound definition is permitted for this occurrence under the governing applicability rules at commitment. |
| $\mathrm{Standing}_{\tau}(q_c,\sigma,c)$ | Actual eligibility, consequence-specific authority, dependency conditions, and required support hold at commitment. |
| $\mathrm{OrderEnforced}_{\tau}(q_c,c)$ | The mechanism enforces an authoritative order between commitment and every change that can alter its standing or joint obligations. |

These predicates describe substantive properties and proof obligations, not caller-supplied flags. A local log order is insufficient unless the actual effect mechanism obeys it. A composite effect may bind one immutable manifest of explicitly identified component definitions; the requirement does not force every participant to run the same geometry.

The formula is a safety property over committed effects. Proving it requires modeling **every** route capable of producing those effects. A system that merely records successful checks, while omitting bypasses or failed receivers, has not established the property.

### Evidence binding

A commitment record should bind at least:

```math
b_c=\langle q_c,\sigma_c,\alpha_c,\delta_c,\kappa_c\rangle
```

| Symbol | Meaning |
| --- | --- |
| $q_c$ | The exact committed effect or, where explicitly identified, an authorized external-effect intent. |
| $\sigma_c$ | The immutable semantic descriptor actually used. |
| $\alpha_c$ | The applicable governing and delegation versions and their authoritative state at commitment. |
| $\delta_c$ | The material dependency versions and evidence supporting standing. |
| $\kappa_c$ | The commit identity and evidence locating it in the relevant authoritative ordering. |

The record provides an auditable binding. Its existence or signature does not prove the facts it records, constitute authority, or enforce an ordering after the fact. An intent record must not be represented as evidence that an external effect completed.

## Temporal distinctions

| Dimension | Question | What it cannot establish alone |
| --- | --- | --- |
| **Semantic version** | Which computational definition governed this execution? | Whether that definition or its requested effect is currently authorized. |
| **Effective time** | When does a grant, amendment, revocation, or expiry become applicable? | Whether every relevant receiver enforces that applicability. |
| **Authoritative ordering** | Does this change take effect before or after this commitment? | The substantive correctness of the governing rules or evidence. |
| **Recording time** | When was an event observed or written to a log? | Its actual effect time or its position in a governing order. |

[Exact Semantic Binding](../exact-semantic-binding/README.md) establishes the correspondence between an immutable definition and actual execution. A semantic-time identifier, where used, must resolve unambiguously to that definition. It is not a substitute for current standing, and Temporal Standing does not prescribe a particular identifier format or timeline architecture.

Conflicting changes and commitments require a common enforceable order at the relevant boundary. Unrelated operations need not share a global total order. Wall-clock expiry additionally requires a justified time source and uncertainty policy; timestamps from unsynchronized observers cannot settle an otherwise unresolved authorization race.

The specification must define **when a revocation becomes effective**, including what an acknowledgment guarantees. A local request to revoke, delayed notification, or cached status cannot silently stand in for that definition. If a receiver cannot establish the required order or standing, it must prevent commitment.

## Minimal invariant kernel

| # | Invariant ID | Obligation |
| --- | --- | --- |
| 1 | `TEMPORAL_STANDING_SCOPE_AND_COMMIT_BOUNDARIES_ARE_EXPLICIT` | Protected occurrences, actual commitment boundaries, failure cases, timing assumptions, and coverage MUST be declared independently of observed successes. |
| 2 | `TEMPORAL_STANDING_SEMANTIC_BINDING_IS_IMMUTABLE` | Execution MUST bind an exact immutable definition or component manifest. A mutable “latest” reference cannot silently change an admitted computation. |
| 3 | `TEMPORAL_STANDING_APPLICABILITY_IS_GOVERNED` | Governing versions, delegation, effective-time rules, and change authority MUST be independently established; historical validity cannot determine current applicability by itself. |
| 4 | `TEMPORAL_STANDING_HOLDS_AT_ACTUAL_COMMITMENT` | Eligibility, exact authority scope, dependencies, and required evidence MUST hold at the actual effect boundary. An earlier assessment cannot substitute. |
| 5 | `TEMPORAL_STANDING_CHANGES_AND_EFFECTS_ARE_ORDERED` | Every standing-changing event MUST be enforceably ordered relative to affected commitments. A check followed by an unprotected write cannot establish this obligation. |
| 6 | `TEMPORAL_STANDING_INVALIDATION_PREVENTS_STALE_EFFECTS` | Once a relevant invalidation is effective, old approvals and capabilities MUST NOT enable affected effects while that invalidation remains applicable. Restored standing requires valid requalification. |
| 7 | `TEMPORAL_STANDING_SHARED_OBLIGATIONS_ARE_SERIALIZED` | Concurrent commitments MUST preserve shared limits through atomic allocation or equivalent enforcement; individually current checks cannot authorize incompatible joint effects. |
| 8 | `TEMPORAL_STANDING_RETRIES_DO_NOT_RESURRECT_AUTHORITY` | Retries, replay, recovery, and delayed work MUST distinguish retrieval of an existing result from a new effect. New effects require standing at their own commitment. |
| 9 | `TEMPORAL_STANDING_EXTERNAL_RECEIVERS_ENFORCE_CURRENT_STANDING` | External receivers MUST enforce applicable standing and ordering at actual effect commitment, with fencing and duplicate-effect prevention appropriate to the operation. |
| 10 | `TEMPORAL_STANDING_HISTORY_AND_EVIDENCE_REMAIN_BOUND` | Durable records MUST bind exact semantic, authority, dependency, and commit identities. Later changes cannot silently rewrite the evidence of what governed an earlier effect. |
| 11 | `TEMPORAL_STANDING_DEPLOYMENT_MATCHES_THE_PROOF` | The argument MUST cover actual clocks where relevant, authoritative sources, credentials, queues, privileged paths, receiving systems, and failures. Material uncovered changes require requalification. |

An earlier approval may remain usable if the mechanism establishes that all its material conditions remain applicable through commitment. This may use reservations, transactional validation, or another justified protocol; no particular mechanism is mandated. Its actual revocation, expiry, failure, and concurrency semantics must satisfy the invariant.

## Delayed effects, retries, and continuing operations

**Intent and effect are separate boundaries.** Committing an authorized intent establishes only that intent's standing. A later external effect needs its own current standing and enforceable ordering at the receiving system. If the receiving system cannot provide that enforcement, the stronger end-to-end claim is not established and the protected effect must fail closed.

**Revalidation can restore eligibility; it cannot rewrite history.** If standing lapses during computation, a new qualification may permit a later effect, provided no protected effect occurred during the lapse and the governing contract permits continuation. Continuous validity from initial assessment is required only where the operation's contract demands it.

**Continuing effects need explicit interval semantics.** If an operation remains consequential over an interval, its standing obligations must cover that interval and each relevant sub-effect. Occasional checks alone do not prove continuous validity.

**Replay separates reconstruction from action.** Restoring an old geometry and its recorded inputs can support historical analysis. It does not renew old grants. A new external write is a new consequential occurrence, even if the same transaction payload or historical definition is reused. Reproducing a definition also does not guarantee identical outputs without the relevant state, dependencies, and nondeterministic choices.

**Later invalidation does not undo an earlier commitment.** A commitment that preceded effective revocation is assessed under its governing conditions. Any correction or compensation is a separate governed effect; retrospective findings must preserve the original event and its recorded basis.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual specialization; recording a time or version does not prove standing.
public sealed class TemporalStanding<TConsequence>
    : TemporalStandingInvariant<TConsequence>
{
}
```

The claim identifies protected occurrences and commitment boundaries; semantic-resolution rules; applicable governance and effective-time semantics; authority and dependency sources; ordering, clock, and failure assumptions; and the covered execution model.

A separate **Temporal Standing Proof** establishes that all covered commitments satisfy the binding, applicability, standing, and ordering obligations. It must bind exact model and deployment versions and independently checkable evidence. Tests can expose stale-execution counterexamples; a finite collection of successful schedules is not a proof over every admissible interleaving.

## Relationship to Structural Standing and the Zero invariants

| Concept | Focus | Relationship to Temporal Standing |
| --- | --- | --- |
| [Structural Standing](../structural-standing/README.md) | Every enabled protected effect depends on its actual eligibility and required support across covered reachable states. | Already includes temporal preservation. Temporal Standing makes semantic binding, applicability, and commitment ordering explicit proof obligations within that broader enforcement argument. |
| **Temporal Standing** | Every actual protected commitment uses an exact applicable definition and standing that holds at that boundary under enforced ordering. | Specializes the temporal aspect; a past approval or an isolated snapshot cannot discharge it. |
| [Topological Zero](../topological-zero/README.md) | No covered effect-producing route bypasses independently governed mediation. | Supplies route coverage; mediation that accepts stale authority does not establish Temporal Standing. |
| [Structural Zero](../structural-zero/README.md) | A specified consequence never occurs within the declared scope and horizon. | Temporal Standing can support unreachability of effects committed without current standing, with matching effect definitions, complete coverage, and verified deployment correspondence. |

Structural Standing is not merely a spatial property, and Temporal Standing is not proof that a timestamped permission is legitimate. A complete proof must connect substantive rules, actual enforcement, changing facts, and the exact effect boundary.

For [Constraint-Governed Agency](../../models/constraint-governed-agency/README.md), the same obligations cover geometry promotion, old workers, delegated tasks, retirement, and delayed effects. Agent identity, executable lineage, and current authority remain separate claims.

## Examples

| Situation | Temporal Standing assessment |
| --- | --- |
| A payment was approved, then revocation became effective before the receiver committed it | The payment must be prevented while the invalidation applies; cached approval is insufficient. |
| A geometry identifier resolves to different executable bytes between evaluation and execution | Immutable semantic binding is absent; the claimed qualification cannot silently transfer. |
| An older geometry remains explicitly authorized after a newer version is published | Execution may proceed if its exact effects retain current standing; newest and applicable are different properties. |
| Two workers each validate the final unit of a shared budget, then both spend it | Current local checks do not establish valid joint commitment; allocation must prevent overspending. |
| A retry retrieves an already committed result without producing another protected effect | The earlier commitment retains its historical identity; any independently protected disclosure still needs its own standing. |
| An archived transaction is replayed after its former capability expires | Reconstruction does not reauthorize action; a new effect requires new current qualification. |
| A disconnected receiver cannot establish whether revocation precedes its proposed effect | It must prevent commitment until the required standing and ordering can be established. |
| Revocation becomes effective after an already valid commitment | The prior event is not erased; further effects and any compensation require their own standing. |

## Scope and limits

Temporal Standing does not supply legitimate governing rules, factual truth, deterministic replay, or an identity-continuity criterion. Those require their own specifications and evidence. It also does not require a universal clock, one global sequence, or a particular distributed protocol.

As a safety invariant, it can hold vacuously when no protected effects occur. Useful-service claims additionally require feasible authorized operations and separate progress or availability arguments. No bounded model or collection of logs should be presented as proof beyond its declared coverage and trusted assumptions.

## Governing principle

> **Historical validity identifies what was justified then. Temporal Standing establishes what may become consequential now.**

**An immutable definition can survive indefinitely. Its authority to produce a consequence cannot be presumed to do so.**

---

© 2026 Beau Crawford
