# <img src="../../assets/signatures/protected-commitment.svg" alt="" width="32" height="32"> Protected Commitment

*A pattern coupling exact semantic qualification, current standing, actual effect control, and durable evidence at consequence boundaries.*

> **An approved decision becomes a protected consequence only through an enforced commitment boundary.**

## Definition

**Protected Commitment** is a reusable architectural procedure for making a qualified computational decision consequential. It binds the governing contract, executable semantics, inputs, dependencies, and proposed effects; establishes their applicable obligations; and enforces current standing where each actual effect commits.

The boundary durably couples a local consequence with its required evidence. For external effects, it initially records an authorized intent; the receiving system separately qualifies and controls actual effect commitment. A subsequent signature can attest a durable record without becoming a prerequisite whose failure leaves an already committed effect unrecorded.

It is a **pattern**, not a foundational primitive or an invariant created by a method named `CommitAtomically`. The implementation must establish complete effect coverage, faithful execution, authoritative ordering, and the claimed durability under its actual failure model.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Pattern | A reusable qualification, enforcement, and recording procedure. |
| Invariant | No. Its implementations must establish the applicable standing, binding, conformance, and coverage properties. |
| Semantic type | `ProtectedCommitmentPattern`. |
| Verification obligation | Connect qualification to the exact actual consequence under enforceable ordering and durable evidence semantics. |
| Evidence | Bound qualification, local commitment or external-intent records, and distinct receiver completion evidence. |
| Runtime relevance | Covers ordinary execution, delayed delivery, retries, recovery, and continuing effects. |

## When to use it

Use this pattern wherever an operation crosses a protected consequence boundary: modifying governed state, allocating a scarce resource, publishing information, activating a geometry, or causing an external effect. The scope must include every route capable of producing the effect, including administrative, delegated, and recovery routes.

The boundary must have custody of the actual effect mechanism. A policy service beside an unrestricted write credential cannot provide the claimed protection, even if every intended caller consults it.

## Formal identity and snapshot

- **Identifier:** `PROTECTED_COMMITMENT`
- **Type:** `ProtectedCommitmentPattern`

A conceptual qualification snapshot is:

```math
S=\langle L,G,X,D,Q\rangle
```

| Symbol | Meaning |
| --- | --- |
| $L$ | The independently constituted governing contract and its exact interpretation. |
| $G$ | The executable definition or immutable component manifest actually used. |
| $X$ | Captured request, input, and relevant state bindings. |
| $D$ | Material decision and execution dependencies, including their validation or reservation conditions. |
| $Q$ | The proposed transition and effect plan, including exact targets, operations, parameters, and shared obligations. |

Capturing a snapshot fixes what is being qualified. It does not freeze authority, dependency facts, or external state. The implementation must establish that all material conditions remain applicable through commitment, using enforceable validation, reservations, or another justified protocol.

Where execution determines an effect's final parameters, those parameters must be bound and qualified before that effect commits. An open-ended permission to execute arbitrary effects is not a substitute for the declared effect plan.

## Procedure

| Step | Required action |
| --- | --- |
| **1. Bind** | Capture the exact contract, definition, request, relevant state, dependencies, and effect plan. Identify the logical unit and relevant commitment boundaries. |
| **2. Qualify** | Establish contract origin and applicability, semantic conformance, actual eligibility, and consequence-specific delegation. Bind evidence to the captured plan. |
| **3. Confine** | Ensure evaluation and execution use the qualified artifacts and inputs. Prevent undeclared reads or effects from silently changing the decision or its realization. |
| **4. Order and admit** | At the actual boundary, enforce current standing and an authoritative ordering with revocation, dependency changes, competing allocations, and other relevant invalidations. |
| **5. Apply and record** | Durably couple the local consequence or authorized external intent with its evidence and commit identity. A failed precondition must prevent the dependent effect. |
| **6. Attest and reconcile** | Attest the durable record separately where needed; reconcile uncertain outcomes and external completion without repeating a consequence merely to regenerate evidence. |

Preliminary computation can be speculative. Its own protected reads, resource use, or intermediate effects still require their applicable standing. Failed qualification cannot excuse an effect already produced outside the boundary.

The corrected example in [Boolean Standing Fallacy](../../anti-patterns/Boolean-Standing-Fallacy.md) illustrates this procedure through conceptual APIs. Those APIs are enforcement contracts to implement and verify, not evidence that ordinary callbacks or Boolean checks provide atomicity.

## Local commitment and durable evidence

Within a local boundary, the consequence and required evidence must share the claimed failure and durability semantics. The record binds the snapshot, qualification evidence, applicable authority and dependency state, exact outcome, and commit identity. If the required record cannot be committed, the corresponding local consequence must not become committed.

A signature may be generated afterward by a retryable worker. Signing failure leaves the durable record intact; it must never trigger the consequence again. For independently verifiable attestation, use an appropriate asymmetric signature over the canonical record. A valid signature authenticates the record under its assumptions; it does not establish the truth of its claims or create authority.

A local record describing an external request is an intent record. Naming it a receipt does not make the external consequence complete.

## External intent and actual effect

```text
LOCAL QUALIFICATION
    ↓ current standing for the intent
DURABLE INTENT AND EVIDENCE
    ↓ delivery may be delayed, retried, or interrupted
RECEIVER QUALIFICATION
    ↓ current standing and enforceable ordering at the real boundary
ACTUAL EXTERNAL EFFECT
    ↓ receiver evidence and reconciliation
DISTINCT COMPLETION RECORD
```

**A committed intent does not confer permanent execution authority.** Before an external effect becomes consequential, the receiving system must establish current authority, eligibility, dependencies, and shared obligations for that exact occurrence. Revocation and other relevant changes must participate in an enforceable authoritative ordering with effect commitment.

Fencing must be enforced by the effect mechanism, not merely carried as metadata. Duplicate-effect prevention must cover the actual operation and its retry identity. Neither fencing nor idempotency alone establishes substantive authority or current standing.

The receiver must durably couple its actual effect with the required completion evidence under the supported commitment protocol. If a separate physical or external mechanism cannot supply the necessary coupling, control, or ordering, the stronger guarantee is unsupported and an effect requiring it must not proceed. An eventual log entry cannot retroactively make an unprotected effect atomic.

Delivery acknowledgments, accepted intents, completed effects, and observed outcomes must remain distinguishable. A timeout means the result may be unknown; it does not establish that nothing happened.

## Concurrency, retry, and recovery

| Situation | Required treatment |
| --- | --- |
| Two requests each observe the last available budget unit | Enforce allocation so their joint effects cannot exceed the limit; current individual checks are insufficient. |
| Authority is revoked after approval but before effect commitment | Prevent the affected effect under the governing effective-order rules, or establish valid new standing. |
| A request retries after an effect already committed | Recover the known result using durable identity and duplicate-effect prevention; do not repeat the effect to recreate a receipt. |
| A receiver's outcome is uncertain | Reconcile authoritative records before deciding whether a new effect is needed. |
| A historical transaction is replayed | Reconstruction does not authorize renewed action. Any new protected effect requires current standing. |
| An operation remains consequential over an interval | Cover the interval and relevant sub-effects according to explicit continuing-standing obligations. |
| Compensation is required | Treat it as a new governed effect while preserving the original commitment and evidence. |

Independent operations need not share one global total order. Conflicting commitments and standing-changing events need the enforceable order required by their actual governing obligations. Timestamps or a controller's local log do not supply that enforcement by themselves.

## Verification and evidence

| Obligation | Canonical requirement |
| --- | --- |
| Exact definition and realization | [Exact Semantic Binding](../../invariants/exact-semantic-binding/README.md). |
| Preserved governing meaning | [Semantic Conformance](../../invariants/semantic-conformance/README.md). |
| Independent authorization basis | [Authority Independence](../../invariants/authority-independence/README.md). |
| Actual eligibility and required support | [Structural Standing](../../invariants/structural-standing/README.md). |
| Standing at the real effect boundary | [Temporal Standing](../../invariants/temporal-standing/README.md). |
| No unmediated effect paths | [Topological Zero](../../invariants/topological-zero/README.md). |
| Compatible end-to-end composition | [Constitutive Authority Closure](../../invariants/constitutive-authority-closure/README.md). |

The implementation argument must bind exact code, configuration, credentials, authoritative sources, effect routes, receivers, persistence mechanisms, and failure assumptions. Qualification for a logical model is insufficient without deployment correspondence.

Relevant falsification cases include executable substitution, an undeclared dependency, revocation between check and write, concurrent overspending, record failure during commitment, a crash after external delivery, and a stale worker bypassing a fence. Tests can expose counterexamples; assurance remains limited to the coverage actually established.

## Relationships and limits

[Governed Promotion](../governed-promotion/README.md) applies this pattern when activation or migration is consequential. [Semantic-Temporal Agent Geometry](../../models/semantic-temporal-agent-geometry/README.md) uses its bindings and records to connect execution history to actual effects.

The pattern does not make arbitrary distributed or physical effects atomic, guarantee availability, or supply legitimate governing roots. Required guarantees depend on actual participant support and explicit assumptions. Rejecting every operation may satisfy safety while failing separate useful-service obligations.

## Governing principle

> **Qualify the exact operation. Enforce standing where its effect commits. Preserve evidence of what actually happened.**

---

© 2026 Beau Crawford
