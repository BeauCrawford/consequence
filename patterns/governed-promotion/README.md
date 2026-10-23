# <img src="../../assets/signatures/governed-promotion.svg" alt="" width="32" height="32"> Governed Promotion

*A pattern for making an exact candidate authoritative through independent qualification and enforced activation.*

> **Publication identifies a candidate. Governed promotion establishes where and when it may become active.**

## Definition

**Governed Promotion** is a reusable architectural procedure for introducing a new executable geometry, policy, or governing artifact into an authorized operational scope. It binds the proposed change, independently establishes its admissibility and authority, preserves required obligations through migration, and controls actual activation under current standing.

It is a **pattern**, not an invariant or a proof produced by naming an API. Its implementations must establish Exact Semantic Binding, Semantic Conformance, Authority Independence, applicable Constitutive Continuity, and Temporal Standing. The relevant obligations cover the transition and coexistence with existing work, not only the candidate's final configuration.

The procedure applies whether the candidate comes from a human, a build system, or recursive generation. Generating an apparently better successor does not authorize its admission or its future effects.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Pattern | A reusable sequence for qualification, migration, activation, and recovery. |
| Model | Uses versioned definitions, governed lineage, and explicit deployment semantics. |
| Invariant | No. It is an implementation approach for separately stated preservation and authority obligations. |
| Semantic type | `GovernedTransitionPattern`. |
| Verification obligation | Show that every actual activation and intermediate protected effect follows the qualified change and current governing rules. |
| Evidence | A bound change manifest, qualification argument, promotion record, and actual deployment evidence. |

## When to use it

Use this pattern when replacing or revising a definition changes what may execute, how state is interpreted, which constraints apply, or what effects become possible. It is especially relevant to self-modification, policy updates, schema migration, capability changes, and recovery that reactivates historical artifacts.

An unadmitted candidate can be stored and evaluated without becoming authoritative. Evaluation itself remains subject to the boundaries governing its data access, resource use, and other protected effects.

## Formal identity and change binding

- **Identifier:** `GOVERNED_PROMOTION`
- **Type:** `GovernedTransitionPattern`

A conceptual change manifest is:

```math
P=\langle G_s,G_c,\Delta,D,W,Q\rangle
```

| Symbol | Meaning |
| --- | --- |
| $G_s$ | Exact source definition and the source-state conditions on which qualification depends. |
| $G_c$ | Immutable candidate definition, including material executable and interpretation artifacts. |
| $\Delta$ | State migration, configuration changes, and transition or reconciliation semantics. |
| $D$ | Material dependencies and the conditions under which their qualification remains valid. |
| $W$ | Rules for existing workers, queues, delegations, concurrent versions, and their continued eligibility. |
| $Q$ | Exact promotion, migration, deployment, and external-effect plan. |

Qualification binds this manifest to applicable governance, required invariants, evidence, and assumptions. Changing a material field requires new identification and applicable requalification. A valid manifest is not an activation receipt.

## Procedure

```text
IMMUTABLE CANDIDATE AND CHANGE MANIFEST
    ↓ independently qualify against prior governing rules
QUALIFIED CHANGE
    ↓ establish scoped authority and prepare enforcement
PREPARED TRANSITION
    ↓ revalidate and enforce actual activation ordering
COMMITTED PROMOTION
    ↓ reconcile participating receivers and record actual outcomes
QUALIFIED ACTIVE DEPLOYMENT
```

| Step | Required action |
| --- | --- |
| **1. Identify** | Publish the exact candidate and bind its source, material parents, migration, dependencies, coexistence policy, and effects. Preserve historical versions. |
| **2. Qualify** | Establish conformance and required preservation under independently specified criteria. Include migration, intermediate states, concurrent versions, failures, and shared limits. |
| **3. Authorize** | Establish valid prior authority for the exact change and its effects. The candidate cannot supply its own missing amendment or promotion authority. |
| **4. Prepare** | Stage artifacts and migration safely; prepare required fences, reservations, and recovery records. Preparation must not silently activate the candidate. Its own protected effects require standing. |
| **5. Commit activation** | At each actual activation boundary, enforce current authority, source and dependency conditions, required old-work restrictions, and ordering with conflicting changes. Bind activation and required evidence durably. |
| **6. Reconcile** | Establish which receivers actually activated, retain exact bindings, and resolve partial outcomes through the qualified recovery protocol. Future protected effects retain their own standing obligations. |

Qualification can be reused only while its material assumptions still hold. A recorded “verified” status is not evidence that the change remains eligible after revocation, source replacement, or dependency changes.

## Concurrency and existing work

**Competing changes:** conflicting promotions must follow an enforceable ordering or an independently defined branching policy. If another change invalidates the qualified source conditions, prevent activation or establish a new qualification. Merely checking the source before an unprotected deployment leaves a race.

**In-flight execution:** an existing unit retains its exact definition or undergoes an explicitly qualified transition. Changing the default geometry cannot silently substitute a new definition inside admitted work. An old version may continue only where its applicability and effects retain standing.

**Old workers and capabilities:** retirement must reach the actual effect boundaries. Required fencing, revocation, or requalification must take effect when the governing cutover requires it, without a window in which stale workers retain prohibited powers. Merely changing a registry entry does not control old credentials or queued work.

**Shared state:** migration and concurrent versions need compatible schemas, semantic mappings, and allocation rules. Separate successful local checks cannot establish joint preservation of a shared budget or other aggregate constraint.

## Activation and external systems

[Protected Commitment](../protected-commitment/README.md) supplies the effect-boundary procedure. Within a local transactional boundary, the activation change and required evidence must commit consistently. Across independent systems, do not claim one atomic deployment unless the actual protocol and participants provide it.

An external deployment intent records authorized requested work. It does not establish completed activation. Each receiver must establish current standing and enforce the relevant ordering at its own activation boundary. Its completion evidence must identify the exact definition and actual result.

If mixed-version operation is permitted, qualification must cover that coexistence. If it is prohibited, the protocol must prevent unsupported intermediate execution. A controller's final success flag cannot retroactively repair an unsafe partial rollout.

## Failure, retry, and rollback

| Situation | Required response |
| --- | --- |
| Candidate qualification fails | Leave it unpromoted. The prior definition continues only if still independently eligible. |
| Authority expires after preparation | Prevent the dependent activation until valid current qualification is established. |
| Deployment outcome is unknown after a crash | Reconcile durable identities and receiver evidence; do not invent success or blindly duplicate effects. |
| A retry finds an already completed promotion | Retrieve its recorded result without repeating the change; any new protected operation needs its own standing. |
| A partial migration requires correction | Follow the qualified recovery path with current authority and preserved evidence. |
| An older artifact must be restored | Treat restoration as a new governed promotion, including current dependencies, migration, and grants. Historical approval does not revive authority. |

Compensation is a new consequential operation. It does not erase the original event or guarantee that every external effect is reversible.

## Verification and evidence

| Obligation | Canonical requirement |
| --- | --- |
| Exact candidate and deployed realization | [Exact Semantic Binding](../../invariants/exact-semantic-binding/README.md). |
| Contract, executable, and behavior correspondence | [Semantic Conformance](../../invariants/semantic-conformance/README.md). |
| Preserved constitutive relationships | [Constitutive Continuity](../../invariants/constitutive-continuity/README.md), for the specific continuity claims made. |
| Same-agent continuation, where claimed | [Identity Continuity](../../invariants/identity-continuity/README.md), including required state, commitments, and fork or merge rules. Authorized promotion may instead introduce a new identity. |
| Independent promotion basis | [Authority Independence](../../invariants/authority-independence/README.md). |
| Current standing and enforceable change ordering | [Temporal Standing](../../invariants/temporal-standing/README.md). |

The promotion argument must connect these properties to actual artifacts, administrators, credentials, workers, state stores, deployment systems, and external receivers. Passing independent checks with incompatible scopes or bindings does not establish their composition.

Relevant falsification cases include candidate substitution after verification, a competing source update, revocation during rollout, old-worker execution after cutover, a crash during migration, and an unauthorized rollback. Tests can expose failures; proof coverage and trusted assumptions must remain explicit.

## Relationships and limits

[Recursive Geometry Evolution](../../models/recursive-geometry-evolution/README.md) describes how a geometry can originate successors; this pattern describes their governed admission. [Semantic-Temporal Agent Geometry](../../models/semantic-temporal-agent-geometry/README.md) uses it to connect geometry history with actual activation. The [Verified Closure Flywheel](../verified-closure-flywheel/README.md) adds its specific improvement objective: reduce invalid reachability while preserving legitimate behavior.

This pattern does not prove that a candidate is better, that a deployment will finish, or that governing roots are ultimately legitimate. It specifies the procedure and evidence needed for the declared promotion claim. Always rejecting candidates can satisfy admission safety without delivering useful evolution.

## Governing principle

> **A successor becomes authoritative only through a qualified, independently authorized transition that controls its actual activation.**

---

© 2026 Beau Crawford
