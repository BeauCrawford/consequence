# <img src="../../assets/signatures/constitutive-continuity.svg" alt="" width="32" height="32"> Constitutive Continuity

*A derived invariant of preserving independently specified constitutive relationships through transformation.*

> **Change may alter expression. Continuity requires preserving the relationships that constitute the claim.**

## Definition

**Constitutive Continuity** requires each covered transformation admitted as a legitimate continuation to preserve the independently specified kernel and relationships on which that continuity claim depends. Its actual lineage must be established to the depth required by the claim, including every material parent and transformation.

It is a **derived preservation invariant**, not a requirement that all versions have identical structure, state, behavior, or capabilities. A domain specifies what must survive, which transformations are admissible, and what equivalence or correspondence counts as preservation. A candidate cannot choose those criteria solely to certify itself.

Traceable ancestry, preserved constitutive relationships, logical identity, and current authority are distinct claims. A provenance graph may record an actual but invalid transformation. A valid descendant may have a new identity or lack authority for a particular effect.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A domain-relative preservation property across covered transformations and compositions. |
| Foundational primitive | No. It depends on origins, relationships, admissible transformations, and a declared constitutive kernel. |
| Semantic type | `ConstitutiveContinuityInvariant`; root continuity is a specialization. |
| Verification obligation | Establish actual origins, complete material lineage, admissibility, and kernel preservation under independent criteria. |
| Proof artifact | A version-bound continuity argument with independently checkable transformation evidence. |
| Runtime relevance | Deployment and migration must preserve the same relationships claimed by the model. |

## Formal identity

- **Identifier:** `CONSTITUTIVE_CONTINUITY`
- **Type:** `ConstitutiveContinuityInvariant`

Let $L_d$ be the actual constitutive lineage of a descendant $d$, and let $K$ specify the required kernel, admissible transformations, and preservation criteria:

```math
\begin{aligned}
&\mathrm{Continuous}_{K}(d)\iff\\
&\quad\mathrm{OriginsEstablished}(L_d,K)\\
&\quad\land\mathrm{MaterialParentsComplete}(L_d)\\
&\quad\land\forall(u,t,v)\in\mathrm{Edges}(L_d):\\
&\qquad\mathrm{Admissible}_{K}(t,u,v)\\
&\qquad\land\mathrm{Preserves}_{K}(t,u,v).
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| $L_d$ | The relevant actual derivation graph, including transformations and material dependencies; a claimed graph needs evidence of correspondence. |
| $K$ | Independently defined constitutive requirements and their interpretation, including permitted equivalences or mappings. |
| $(u,t,v)$ | A transformation $t$ from a predecessor configuration $u$ to a successor $v$, including material context. |
| `OriginsEstablished` | The claimed origins and their relevant constitutive role are supported by trustworthy evidence. |
| `MaterialParentsComplete` | No parent, relation, or transformation material to the continuity claim has been omitted. |
| `Admissible` | The transformation satisfies the applicable independently specified change rules. |
| `Preserves` | The required kernel and relationships survive according to the declared correspondence, including joint obligations. |

For a mechanism $M$ within independently declared scope and assumptions $\Omega$, the invariant requires:

```math
\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall d\in\mathrm{AdmittedContinuations}(\rho):\;
\mathrm{Continuous}_{K}(d).
```

`AdmittedContinuations` includes actual promotions and transformations that rely on the continuity claim, even if they bypass intended validation. Unadmitted proposals may fail preservation. The formula does not turn an incomplete or self-reported history into proof of actual derivation.

For a single root-relative path, this specializes to the root-continuous descent condition used by [Generative Root Geometry](../../models/generative-root-geometry/README.md). For composition or merging, validating one favorable path is insufficient: all material parents and their reconciliation must be covered.

## Preservation obligations

| Obligation | Requirement |
| --- | --- |
| Independent criteria | The kernel, transformation rules, and preservation mappings MUST be defined independently of the candidate outcome being certified. |
| Complete derivation | Every material origin, dependency, and transformation MUST be represented with justified evidence of actual correspondence. |
| Distinguishable versions | Changes MUST retain exact predecessor and successor identities without silently rewriting earlier definitions or evidence. |
| Semantic preservation | Mappings between different representations MUST preserve the relationships and obligations required by the claim, not merely output similarity. |
| Composition | Branches, merges, and higher-order structures MUST account for every applicable parent's obligations and explicit conflict-resolution rules. |
| Governed amendment | When governance is involved, amendment and promotion MUST follow previously applicable authority. Changed criteria cannot retroactively manufacture continuity. |
| Transition coverage | Migration, partial rollout, concurrent versions, and recovery MUST preserve required relationships throughout the covered transition. |
| Honest uncertainty | Missing evidence MUST remain unresolved. It proves neither continuity nor actual severance. |

An authorized amendment can change local policy while preserving the domain's higher-order constitution. If it changes the basis of the continuity claim itself, the specification must identify which guarantees survive and which require a new origin or a separately justified succession rule.

## What continuity does not establish

| Established claim | Separate question |
| --- | --- |
| Shared origin | Do the descendants have identical behavior, state, or properties? |
| Preserved constitutive kernel | Do the application's logical identity criteria hold? |
| Valid lineage | Does the actor have current authority for this consequence? |
| Identical observable outputs | Was either output derived through the claimed lineage? |
| A signed parent reference | Did the declared transformation actually occur and preserve the required relationships? |

Identity continuity can be one domain's preservation requirement, but it must be defined explicitly. It is not a universal consequence of common ancestry. Current consequence standing remains subject to [Temporal Standing](../temporal-standing/README.md).

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual preservation claim; lineage references alone do not prove it.
public sealed class ConstitutiveContinuity<TStructure, TRelation>
    : ConstitutiveContinuityInvariant<TStructure, TRelation>
{
}
```

A **Continuity Argument** binds exact origins, kernel versions, actual lineage, transformation evidence, admissibility rules, preservation mappings, deployment correspondence, and assumptions. A proof for one path does not qualify an arbitrary merge, a different migration, or every future descendant.

The claim's truth and the available evidence are distinct. If evidence is lost, the property may still hold, but the corresponding assurance claim cannot remain independently established without adequate support.

## Relationships and examples

| Concept or situation | Relationship or assessment |
| --- | --- |
| [Generative Root Geometry](../../models/generative-root-geometry/README.md) | Supplies the model of differentiation and relation; this invariant specifies the preservation requirement. |
| [Governing Root Geometry](../../models/governing-root-geometry/README.md) | Supplies independently constituted change obligations when the lineage is governed. |
| [Recursive Geometry Evolution](../../models/recursive-geometry-evolution/README.md) | Requires legitimate successors and migration to preserve the applicable kernel. |
| A schema changes while its required semantic relationships survive under a verified mapping | Different representations may preserve continuity. |
| A merge retains one parent's provenance but omits the other's conflicting obligations | The continuity argument is incomplete. |
| A descendant preserves its lineage but its grant expires | Continuity may hold while consequential standing does not. |

## Scope and limits

The invariant is relative to explicit, domain-specific constitutive criteria. It does not establish a universal identity relation or prove that every property of a descendant was present in its root. Claims of useful evolution require separate feasibility and progress evidence; rejecting every transformation can satisfy admission safety vacuously.

## Governing principle

> **A lineage records where change came from. Constitutive Continuity establishes what the change preserved.**

---

© 2026 Beau Crawford
