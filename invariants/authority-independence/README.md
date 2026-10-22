# <img src="../../assets/signatures/authority-independence.svg" alt="" width="32" height="32"> Authority Independence

*A derived invariant preventing a subject from constituting the authority required for its own admission or protected effects.*

> **A subject may propose an action and supply evidence. It cannot manufacture the authority that makes the action legitimate.**

## Definition

**Authority Independence** requires every covered admission, promotion, grant expansion, and protected consequence to depend on a valid governing basis that the subject cannot unilaterally create or weaken to authorize itself. The rules, evidence requirements, and enforcement on which admission depends must remain governed by that independent basis.

Independence is a relationship between the subject's actual control and the source and enforcement of authority. Different processes, accounts, models, or organizations do not establish it by themselves. A reviewer whose rules, credentials, or decision records the proposer can overwrite is not independent in the relevant sense.

The invariant permits automated admission under valid prior delegation. A subject can request an operation, choose parameters, present a proof, or exercise an existing grant. Those actions influence the decision without creating new jurisdiction or enlarging the authority under which the decision is made.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A derived separation property between subject control and its necessary authorization basis. |
| Foundational primitive | No. It depends on authority, delegation, subject control, admission, and enforcement. |
| Semantic type | `AuthorityIndependenceInvariant`. |
| Verification obligation | Establish an independent constitutive basis and prevent unilateral substitution or weakening within the declared control model. |
| Proof artifact | A version-bound authority and control argument covering rules, credentials, evidence, and enforcement. |
| Runtime relevance | Applies to ordinary effects and changes to the mechanisms that authorize future effects. |

## Formal identity

- **Identifier:** `AUTHORITY_INDEPENDENCE`
- **Type:** `AuthorityIndependenceInvariant`

For a subject $q$, mechanism $M$, and independently specified scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{AuthorityIndependence}(M,q,\Omega)\iff\\
&\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall a\in\mathrm{AuthorityUses}(\rho,q):\\
&\quad\exists b:\\
&\qquad\mathrm{IndependentBasis}(b,q,a)\\
&\qquad\land\mathrm{Authorizes}(b,a)\\
&\qquad\land\mathrm{IndependentlyEnforced}(M,b,q,a).
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| `AuthorityUses` | Actual covered admissions and protected commitments that rely on the subject's authority, including self-modification, delegation, administrative paths, and bypasses. |
| $b$ | The independently constituted contract, relevant delegation, amendment rules, and evidence establishing authority for the occurrence. |
| `IndependentBasis` | The basis derives from declared trusted sources and valid prior governance; the subject's claims or candidate rules cannot supply their own missing authority. |
| `Authorizes` | The basis covers the actual actor, operation, target, parameters, effects, and governing applicability of this occurrence. |
| `IndependentlyEnforced` | Admission actually depends on that basis, with no subject-controlled route to substitute authority or weaken the relevant checks beyond independently authorized bounds. |

These are substantive authority and control properties. A signed approval or Boolean named `Independent` cannot discharge them. The mechanism model must cover what the subject can actually cause, including helper processes, delegated actors, storage mutation, credential use, and changes to the admission machinery.

The claim is relative to declared trusted sources. A chain may terminate at an explicitly assumed constitutive authority; formal verification cannot establish the ultimate legitimacy of that assumption. A cycle of mutually approving subject-controlled components does not create an independent origin.

## Independence obligations

| Obligation | Requirement |
| --- | --- |
| Explicit control scope | Subject-controlled capabilities, principals, collaborators, artifacts, and infrastructure MUST be modeled, including relevant compromise assumptions. |
| Independent origin | Governing authority MUST trace to a justified source outside the subject's unilateral assertions. |
| Bounded delegation | Exercised authority MUST remain within valid prior scope, including aggregate limits and restrictions on further delegation. |
| Protected admission criteria | The subject MUST NOT replace the rules or evidence criteria judging its own request without independently valid change authority. |
| Trustworthy evidence | Subject-supplied evidence MAY contribute, but its required properties MUST be independently checkable under protected criteria. |
| Enforced dependence | Actual admission MUST depend on the qualified basis; an advisory reviewer beside an unrestricted execution path is insufficient. |
| Governed amendment | Changes to roots, validators, delegation, or enforcement MUST follow previously applicable governance. A candidate cannot approve itself under its proposed rules. |
| Continued applicability | Revocation, expiry, scope changes, and dependency changes MUST be enforced at the applicable consequence boundary. |

A subject may be delegated authority to administer part of a system. The independent basis must specify the bounds of that administration and preserve the constraints needed for this invariant. Giving the subject unrestricted control over its own necessary admission conditions defeats the claimed separation, even when that control is exercised through a different account.

## Proposal, verification, and authorization

```text
SUBJECT PROPOSAL
  Candidate · Requested operation · Supporting evidence
    ↓ assessed under protected, previously applicable rules
INDEPENDENT QUALIFICATION
  Semantic validity · Continuity · Exact scope of authority
    ↓ enforced against the actual occurrence
ADMISSION OR PROTECTED COMMITMENT
  Bound outcome · Current standing · Durable evidence
```

A valid proof can establish that a candidate satisfies a specification. It does not establish that the specification had governing authority. Conversely, legitimate authorization does not establish semantic correctness. Both obligations remain necessary where the architecture requires them.

Independence does not require a human approving every transaction or a physically separate machine. The protection boundary must be justified against the subject's actual capabilities. Two models reviewing one another can still share a subject-controlled prompt, evaluator, administrator, or effect credential.

Promotion authority and effect authority also differ. Admitting a successor does not give it every capability it describes, and granting one operation does not authorize changes to the grant's own restrictions.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual separation claim; a distinct reviewer identity is insufficient.
public sealed class AuthorityIndependence<TSubject, TConsequence>
    : AuthorityIndependenceInvariant<TSubject, TConsequence>
{
}
```

An **Authority Independence Argument** binds the subject and control closure, constitutive sources, exact governance and delegation versions, amendment rules, protected validation mechanisms, effect routes, deployment configuration, and trusted assumptions. It must identify which resources the subject can modify and why those capabilities cannot manufacture a missing authorization basis.

A proof limited to application code cannot silently assume that mutable policy storage, administrative credentials, or an external receiver preserve the same separation. Material changes to those dependencies require applicable requalification.

## Relationships and examples

| Concept or situation | Relationship or assessment |
| --- | --- |
| [Governing Root Geometry](../../models/governing-root-geometry/README.md) | Describes the independent governing basis and permitted amendment procedures. |
| [Semantic Conformance](../semantic-conformance/README.md) | Establishes semantic correctness under a contract; it does not constitute that contract's authority. |
| [Temporal Standing](../temporal-standing/README.md) | Requires the independent authority and other standing conditions to hold at actual commitment. |
| [Topological Zero](../topological-zero/README.md) | Requires complete mediation; this invariant qualifies the independence of the authority used by that mediation. |
| A subject provides a proof checked against independently governed rules | Can satisfy independence; originating evidence is not the same as controlling its acceptance criteria. |
| A candidate disables its validator and then approves its own deployment | Cannot establish independent promotion authority. |
| A separate reviewer uses policy files writable by the proposer | Process separation does not establish authority separation. |
| An automated gate approves an operation within a valid prior grant | Automation is compatible with independence when the basis and enforcement remain protected. |

## Scope and limits

Authority Independence does not establish factual truth, useful service, or the soundness of every governing rule. It is relative to explicit trust and control assumptions; a claim that excludes a compromised trust root cannot be presented as covering that compromise. An end-to-end claim also needs exact binding, semantic conformance, current standing, complete effect coverage, and faithful evidence.

## Governing principle

> **Intelligence may originate proposals. Legitimate authority must originate beyond the proposal's power to authorize itself.**

---

© 2026 Beau Crawford
