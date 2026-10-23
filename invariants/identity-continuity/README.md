# <img src="../../assets/signatures/identity-continuity.svg" alt="" width="32" height="32"> Identity Continuity

*A derived specialization of Constitutive Continuity for legitimate claims that an agent remains the same through change.*

> **Retaining an identifier does not establish that the identity it names survived the transformation.**

## Definition

**Identity Continuity** requires every covered use of a changed computational expression as the same governed agent to preserve the independently specified identity criteria, constitutive relationships, and inherited obligations on which that claim depends. Relevant transformations must have qualified lineage and independently authorized admission under the applicable prior governance.

It specializes [Constitutive Continuity](../constitutive-continuity/README.md). General constitutive continuity may hold between a root and a descendant that has a new identity. Identity Continuity additionally requires the domain's explicit same-agent relation to hold.

The invariant permits changes in geometry, implementation, models, objectives, and operational state where the applicable kernel allows them. Neither common ancestry nor a permanently running process establishes the result. Permission to introduce a successor likewise does not necessarily establish that the successor is the same agent.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A derived preservation property for operational claims of continuing agent identity. |
| Foundational primitive | No. It depends on distinction, independent identity criteria, lineage, preservation, and admission. |
| Semantic type | `IdentityContinuityInvariant`, specializing `ConstitutiveContinuityInvariant`. |
| Verification obligation | Establish complete relevant lineage, kernel preservation, the same-identity relation, and applicable admission authority. |
| Proof artifact | A version-bound identity continuity argument, including state migration and branching or merging where material. |
| Runtime relevance | Applies to promotion, restoration, transfer, migration, and other changes used to continue an existing identity. |

## Formal identity

- **Identifier:** `IDENTITY_CONTINUITY`
- **Type:** `IdentityContinuityInvariant`

For a mechanism $M$ within independently declared scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{IdentityContinuity}(M,\Omega)\iff\\
&\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall u\in\mathrm{SameIdentityUses}(\rho):\\
&\quad\mathrm{Continuous}_{K_u}(\mathrm{Target}(u))\\
&\quad\land\mathrm{IdentityRelation}_{K_u}
(\mathrm{Parents}(u),\mathrm{Target}(u),D_u)\\
&\quad\land\mathrm{AdmissionAuthorized}(u).
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| `SameIdentityUses` | Every actual covered use or admission of an expression as a continuation of an existing identity, including restoration, merge, transfer, and bypass paths. |
| $K_u$ | Independently established identity criteria and preservation rules applicable to this transformation, including any justified succession between kernel versions. |
| `Parents` | All material predecessor expressions and their governing relationships; a merge may include contributors with different identities. |
| `Target` | The actual resulting expression, including geometry, relevant state, commitments, and lifecycle bindings. |
| $D_u$ | The existing semantic identity the target claims to continue. |
| `Continuous` | The canonical Constitutive Continuity condition over the target's complete relevant lineage and kernel obligations. |
| `IdentityRelation` | The independently specified criterion establishing that this target legitimately continues the particular identity, including applicable fork, merge, and state rules. |
| `AdmissionAuthorized` | Actual admission is within valid previously applicable governance for the exact change; the candidate cannot authorize itself. |

An unadmitted proposal may fail these conditions. If it nevertheless operates as the continuing agent, it cannot be omitted from coverage. Root identity establishment is a separate qualification; this invariant constrains claims of continuation from it.

Local preservation judgments must compose across the full claimed lineage under the applicable kernel and its succession rules. Pairwise similarity or repeated reuse of an identifier cannot establish that composition.

The formula does not force every material parent to have the target's identity. A merge must specify which identity, if any, continues, account for every material parent's obligations, and establish the required reconciliation. A new successor identity is a possible legitimate outcome, but it is not a same-identity claim.

## Preservation obligations

| Obligation | Requirement |
| --- | --- |
| Independent identity criteria | Same-agent judgments MUST follow the applicable [Constitutive Kernel](../../models/constitutive-kernel/README.md), not a criterion chosen by the candidate to pass itself. |
| Stable distinction | Entity references MUST satisfy [Constitutive Distinction](../constitutive-distinction/README.md); shared labels alone cannot prove continuity. |
| Qualified lineage | Actual origins, transformations, and material parents MUST support the claimed continuity, with exact governing and kernel versions. |
| State and commitments | Migration, compression, forgetting, restoration, and reconciliation MUST preserve whatever state and obligations the identity contract requires. |
| Governed branching | Forks, replicas, merges, and transfers MUST follow explicit identity and obligation rules rather than infer identity from ancestry. |
| Independent admission | Changes MUST cross applicable promotion boundaries under [Authority Independence](../authority-independence/README.md). |
| Honest uncertainty | Missing evidence MUST remain unresolved. It establishes neither preserved identity nor actual severance. |

Preserving identity does not require retaining every memory byte. A verified transformation may change representation, compact history, or discard nonessential state within the retention and identity contract. Conversely, a surviving geometry hash cannot replace a lost commitment ledger where that ledger is essential to the continuity claim.

## Forks, replicas, and lifecycle

| Situation | Identity assessment |
| --- | --- |
| A runtime is replaced while the required definition, state, relationships, and evidence remain qualified | Identity may continue without uninterrupted execution. |
| Two agents share identical models and geometry artifacts | They need not share identity. |
| A fork copies its predecessor's history | Ancestry is preserved; same identity needs an explicit branching rule and evidence. |
| Replicas legitimately realize one identity | Identity may continue, but concurrency, commitments, and current authority must still be governed jointly. |
| A successor is authorized but changes a defining identity relationship | It may require a new identity under the applicable criteria. |
| An old snapshot is restored after additional commitments occurred | The identity claim must account for those commitments; historical state cannot silently erase them. |
| An agent's effect grant expires while its records remain qualified | Identity can remain established while current consequential standing is absent. |

Dormancy does not require a continuously running process, but it also does not guarantee indefinite recoverability. Resumption depends on the retained artifacts, relevant state, evidence, and governing conditions promised by the model. Retirement must preserve historical identity and govern any outstanding work or obligations.

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual specialization of constitutive preservation for agent identity.
public sealed class IdentityContinuity<TAgent>
    : IdentityContinuityInvariant<TAgent>
{
}
```

An **Identity Continuity Argument** binds the existing distinction, exact identity and kernel revisions, full material lineage, preservation mappings, actual source and target state, outstanding obligations, lifecycle and branching rules, admission evidence, deployment correspondence, and trust assumptions.

The argument must cover the transformations actually performed, including intermediate migration and recovery states. Passing a final-state comparison cannot establish a transition that temporarily discarded required obligations. Automated verification is useful where supported; unsupported obligations must remain visible and cannot be assumed true.

## Relationships and limits

[Constitutive Agent Identity](../../models/constitutive-agent-identity/README.md) is the model of what persists; this invariant states the conditions for a legitimate continuity claim. [Semantic Lineage](../../models/semantic-lineage/README.md) supplies the recorded derivation and admission relationships. [Governed Promotion](../../patterns/governed-promotion/README.md) provides the change procedure.

Identity Continuity does not imply behavioral equivalence, improved capability, deterministic replay, indefinite persistence, or current permission for any particular effect. [Temporal Standing](../temporal-standing/README.md) remains independently required at actual consequence commitment. Rejecting every change may satisfy continuity safety while providing no useful evolution.

## Governing principle

> **Identity survives change only where the relationships constituting that identity remain independently established.**

---

© 2026 Beau Crawford
