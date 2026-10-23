# <img src="../../assets/signatures/semantic-lineage.svg" alt="" width="32" height="32"> Semantic Lineage

*A model of versioned semantic derivation, governed admission, and the evidence connecting computational expressions.*

> **An ancestry reference records a claim. A qualified lineage establishes the relationships that claim depends on.**

## Definition

**Semantic Lineage** is a versioned causal graph describing the origins, material parents, transformations, and governing relationships of semantic artifacts. It binds derivation claims to exact definitions and evidence, and distinguishes candidate creation, qualification, admission, activation, and later lifecycle events.

It is a **model**, not an invariant or proof. A recorded edge may be accurate, mistaken, unsupported, or evidence of an inadmissible transformation. [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) establishes required preservation; [Identity Continuity](../../invariants/identity-continuity/README.md) separately establishes whether the transformation retains an agent's identity.

[Constitutive Agent Identity](../constitutive-agent-identity/README.md) uses the independently admitted portion of this lineage for its continuing identity claim. Retaining proposals and rejected changes alongside that projection preserves the history without representing them as authoritative revisions.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Model | A causal derivation and admission model over exact semantic versions. |
| Foundational primitive | No. It depends on identity, version, relation, transformation, evidence, and scope. |
| Invariant | No. Immutability, completeness, truthful correspondence, and preservation are obligations on an implementation. |
| Semantic type | `CausalLineageModel`. |
| Verification obligation | Establish exact references, actual derivation, complete material parents, and justified admission status. |
| Evidence | A version-bound lineage argument with source, transformation, and actual activation evidence where claimed. |

## Formal identity

- **Identifier:** `SEMANTIC_LINEAGE`
- **Type:** `CausalLineageModel`

A particular recorded view is:

```math
\mathcal{L}_r=\langle V_r,E_r,P_r,H_r,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $V_r$ | Immutable semantic artifact versions, including geometry, governing definitions, kernel versions, and state references where material. |
| $E_r$ | Declared derivation edges, each binding all material source versions, an exact transformation, and its target version. |
| $P_r$ | Provenance and verification evidence supporting origins, derivation, correspondence, and preservation claims. |
| $H_r$ | Immutable lifecycle records identifying qualification, admission, activation, retirement, correction, and other material events. |
| $\Omega$ | Required lineage depth, parent-completeness criteria, interpretation, trust, retention, and coverage assumptions. |
| $r$ | An immutable view or revision identifier; it does not require a global total order among independent branches. |

A transformation with multiple material parents can be represented as:

```math
(U,t,v)\in E_r,\qquad U\subseteq V_r,\quad v\in V_r.
```

Here $U$ contains every parent material to the claimed derivation, $t$ identifies the transformation and its relevant context, and $v$ is the resulting artifact version. The induced derivation relation must be acyclic; roots have explicitly qualified origins. A version can have several parents without sharing the logical identity of all of them.

References to lifecycle events and evidence have their own typed meanings. An artifact referencing a later assessment does not create a causal derivation edge back into its own ancestry.

## Recorded lineage and actual lineage

The graph describes what is claimed. Its assurance argument must connect it to what actually happened. Copying a parent's digest does not prove derivation, and signing an edge does not prove that the transformation preserved its obligations.

[Semantic Time](../semantic-time/README.md) supplies exact coordinates and causal resolution. Semantic Lineage adds explicit derivation, material-parent coverage, transformation evidence, and admission history. A branch identifier inside a semantic-time coordinate is a reference into that model, not the complete graph or a continuity certificate.

Qualification must distinguish:

| Claim | Required evidence |
| --- | --- |
| The artifact exists | Exact version and material artifact resolution. |
| It was derived from these sources | Trustworthy origin and transformation evidence covering all material parents. |
| It preserves the required relationships | A preservation argument against the applicable independent kernel. |
| It was admitted for use | Valid admission authority and the exact scope of that admission. |
| It became active | Evidence of actual activation at the relevant deployment boundary. |
| It may act now | Current standing for the particular consequence. |

## Branches, merges, and corrections

A branch records a new causal trajectory. Whether it continues the same agent, creates another agent, or remains an unadmitted proposal depends on explicit identity and governance rules.

A merge creates a new version, retains every material parent, and records the reconciliation of applicable obligations and state. Common ancestry cannot decide which commitments survive or whether two agent identities become one. Those judgments require the [Constitutive Kernel](../constitutive-kernel/README.md) and applicable authority.

Reactivating an old artifact appends a new activation or restoration event. It does not rewrite ancestry or add a derivation edge from a descendant back to its own ancestor.

Later discoveries append correction or invalidation records. A previously recorded admission remains a historical event even if subsequent evidence undermines its claimed basis. Current qualification must consider applicable corrections; immutable history is not perpetual endorsement.

## Required obligations

| Obligation | Requirement |
| --- | --- |
| Exact versions | Nodes and transformations MUST resolve to the artifacts and interpretations actually claimed. |
| Complete derivation | The scope MUST identify and include every material parent, dependency, and transformation. |
| Typed relationships | Derivation, identity succession, delegation, and admission MUST remain distinguishable. One relationship cannot stand in for another. |
| Independent admission | A candidate's provenance claims MUST NOT constitute its authority for promotion. |
| Actual correspondence | Claimed derivation and activation MUST have evidence connecting the graph to real transformations and deployment. |
| Preserved history | Corrections and lifecycle changes MUST retain their historical bindings without silently rewriting earlier records. |
| Explicit retention | Required payloads, state references, and evidence MUST remain available for the claimed reconstruction and verification period. |

If retained evidence becomes insufficient, the corresponding qualification becomes unresolved unless another adequate basis exists. That does not itself prove the historical transformation was invalid. A surviving digest cannot reconstruct a deleted payload.

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual lineage model; graph connectivity is not proof of derivation.
public sealed class SemanticLineage<TArtifact>
    : CausalLineageModel<TArtifact>
{
}
```

A **Lineage Argument** binds exact views, sources, transformations, material-parent criteria, kernel and governing versions, evidence, deployment correspondence, retention, and trust assumptions. It must identify the distinction between established, refuted, and unresolved claims and the depth to which lineage was checked.

## Relationships and limits

| Concept | Relationship |
| --- | --- |
| [Generative Root Geometry](../generative-root-geometry/README.md) | Describes differentiation and origin relationships whose specific derivations this model represents. |
| [Semantic Time](../semantic-time/README.md) | Supplies immutable version coordinates and causal resolution. |
| [Constitutive Agent Identity](../constitutive-agent-identity/README.md) | Uses qualified lineage to connect successive expressions of a governed identity. |
| [Governed Promotion](../../patterns/governed-promotion/README.md) | Supplies the qualification and activation procedure whose distinct events the lineage records. |

A complete ancestry graph does not imply identical behavior, preserved identity, correct facts, or current effect authority. A lineage may branch, merge, stop, or outlive executable artifact availability under an explicit retention contract; assurance claims must reflect those limits.

## Governing principle

> **Record where an expression came from, what governed its transformation, and what the evidence actually establishes.**

---

© 2026 Beau Crawford
