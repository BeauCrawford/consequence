# <img src="../../assets/signatures/constitutive-distinction.svg" alt="" width="32" height="32"> Constitutive Distinction

*A derived invariant of unambiguous semantic reference across implementations, versions, and runtime instances.*

> **A durable identifier must continue to distinguish the entity it was constituted to identify.**

## Definition

**Constitutive Distinction** requires every covered use of an established semantic identity to resolve unambiguously to the intended governed entity, under independently specified namespace and identity criteria. A durable canonical reference must not be silently reassigned to a different entity within its declared lifetime.

For agents, a model version, process identifier, memory snapshot, or geometry digest is not sufficient by itself to establish that distinction. Two agents may use identical artifacts and remain distinct. Several runtime instances may realize one agent when the model's concurrency and identity rules permit it.

This is a **derived invariant of identity reference**, not a complete identity model. [Constitutive Agent Identity](../../models/constitutive-agent-identity/README.md) defines the continuing entity; [Identity Continuity](../identity-continuity/README.md) establishes whether changed expressions may legitimately retain that identity.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | Unambiguous identity reference and stable canonical bindings within declared scope. |
| Foundational primitive | No. It depends on constituted entities, namespaces, reference resolution, and correspondence. |
| Semantic type | `IdentityDistinctionInvariant`. |
| Verification obligation | Establish exact reference meaning and prevent collision, silent reassignment, or ambiguous attribution. |
| Proof artifact | A version-bound distinction argument covering identity sources, mappings, lifecycle, and actual use. |
| Runtime relevance | Separates agent identity from the identifiers of its components and executions. |

## Formal identity

- **Identifier:** `CONSTITUTIVE_DISTINCTION`
- **Type:** `IdentityDistinctionInvariant`

Let $D$ contain the entities distinguished under the domain's independently specified identity criteria. For mechanism $M$ and declared scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{ConstitutiveDistinction}(M,\Omega)\iff\\
&\quad\mathrm{StableCanonicalBindings}(M,\Omega)\\
&\quad\land\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall s\in\mathrm{States}(\rho),\;
\forall r\in\mathrm{IdentityUses}(s):\\
&\qquad\exists d\in D:\;
\mathrm{ResolveIdentity}_{s}(r)=\{d\}\\
&\qquad\land\mathrm{Corresponds}_{s}(r,d).
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| `IdentityUses` | All covered references actually used as established entity identities, including administrative, migration, recovery, and bypass uses. |
| `ResolveIdentity` | Resolution under the qualified namespace and mapping version; the singleton excludes absent or ambiguous resolution. |
| `Corresponds` | The binding identifies the intended constituted entity under independent criteria, rather than merely matching a self-reported label. |
| `StableCanonicalBindings` | A canonical reference is not silently reused for another entity across the executions and lifetime covered by the claim. Historical bindings retain their meaning. |

Raw names or unverified claims may be received and rejected without successful resolution. If the mechanism nevertheless relies on them as established identities, those uses remain covered. The scope cannot exclude ambiguous attribution simply because intended validation would have rejected it.

The entity criteria must exist independently of whatever a mutable registry happens to return. Otherwise a registry could change its answer and manufacture compliance by redefining the referent.

## Reference obligations

| Obligation | Requirement |
| --- | --- |
| Qualified namespaces | Identity references MUST include enough namespace and binding context to distinguish the intended entity. Global uniqueness outside the declared scope is not implied. |
| Stable canonical meaning | A canonical identity reference MUST NOT silently acquire a different referent. Retirement and reuse rules must preserve historical interpretation. |
| Explicit aliases | Renaming, aliases, and identifier migration MUST retain qualified relationships to the canonical entity and exact historical mapping versions. |
| Separated identities | Agent, geometry, model, runtime, transaction, attempt, and state identifiers MUST remain distinguishable. |
| Consistent replicas | Replication and concurrent resolution MUST prevent conflicting authoritative bindings; unresolved mappings cannot support dependent qualified use. |
| Complete coverage | Creation, transfer, fork, merge, restoration, administrative changes, and recovery MUST preserve reference meaning under declared rules. |

Aliases may change through explicit governed updates. Multiple references may identify one entity. The requirement is that each qualified use is unambiguous and historically interpretable, not that every display label is globally unique.

## Distinction, continuity, and authentication

| Claim | Separate question |
| --- | --- |
| A reference uniquely identifies agent A | Does this caller legitimately act for A? |
| A record retains A's canonical identifier | Did the transformation preserve A's identity obligations? |
| Two executions share an agent identity | Are their concurrent actions and combined effects authorized? |
| Two artifacts have the same bytes | Do they belong to the same governed entity? |

Constitutive Distinction does not authenticate a credential holder or supply consequence authority. It also does not make an identity continuity claim true merely because the same key remains in a database. Those properties require their own evidence and enforcement.

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual reference claim; uniqueness of a string is insufficient.
public sealed class ConstitutiveDistinction<TIdentity>
    : IdentityDistinctionInvariant<TIdentity>
{
}
```

A **Distinction Argument** binds the identity criteria and origin records, namespaces, canonical and alias rules, mapping versions, replica and recovery semantics, actual attribution paths, retention, and trust assumptions. It must explain why the qualified references continue to denote the intended entities.

Counterexamples include recycling a retired agent ID for another entity, restoring conflicting registry snapshots, treating one shared model digest as the identity of every agent using it, and attributing work through a mutable alias without its historical mapping.

## Relationships and limits

[Exact Semantic Binding](../exact-semantic-binding/README.md) identifies the computational definition actually used; this invariant identifies the entity to which the definition or action is attributed. [Semantic Time](../../models/semantic-time/README.md) uses such a distinction in its entity coordinate. [Identity Continuity](../identity-continuity/README.md) determines which transformations may retain it.

The claim is relative to domain criteria, explicit namespaces, lifetime, retention, and trust assumptions. It does not establish a universal notion of identity, uninterrupted execution, factual truth, or current standing. Missing identity evidence must remain unresolved rather than being replaced by a convenient label.

## Governing principle

> **Keep the entity distinguishable while its implementations and expressions change.**

---

© 2026 Beau Crawford
