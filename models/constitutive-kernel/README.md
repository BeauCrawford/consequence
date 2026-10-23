# <img src="../../assets/signatures/constitutive-kernel.svg" alt="" width="32" height="32"> Constitutive Kernel

*A model of the obligations and relationships that a claimed continuation must preserve.*

> **Define what must survive before judging whether a transformation preserved it.**

## Definition

A **Constitutive Kernel** is an independently governed, versioned specification of the obligations, semantic relationships, and preservation criteria on which a continuity claim depends. It states what a transformation must retain, which correspondences count as preservation, and how those requirements may legitimately change.

It is a **model**, specifically a preservation specification. The kernel contains invariant definitions; the property that actual transformations preserve it is [Constitutive Continuity](../../invariants/constitutive-continuity/README.md). For agent identity, [Identity Continuity](../../invariants/identity-continuity/README.md) specializes that property to the domain's explicit same-agent criteria.

In [Constitutive Agent Identity](../constitutive-agent-identity/README.md), the proposal's **constitutive geometry** is represented by this kernel and its governing relationships. It is distinct from [Constraint Geometry](../constraint-geometry/README.md), the full executable definition of available behavior. A kernel is not an operating-system kernel, a fixed personality, or an exhaustive copy of an implementation.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Model | An independently specified contract for preservation through change. |
| Foundational primitive | No. It composes obligations, relations, interpretation, change rules, and scope. |
| Invariant | No. Preservation of the kernel is a separately established invariant. |
| Semantic type | `PreservationSpecification`. |
| Verification obligation | Establish governing origin, exact interpretation, applicability, and the adequacy of the stated preservation criteria. |
| Evidence | A qualified kernel version and independently checkable preservation obligations. |

## Formal identity

- **Identifier:** `CONSTITUTIVE_KERNEL`
- **Type:** `PreservationSpecification`

```math
K_v=\langle R,C,\Pi,U,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $R$ | References to the constitutive sources and governing contracts that establish the kernel's role. |
| $C$ | Required state, transition, trace, and relational obligations; identity criteria are included when identity preservation is claimed. |
| $\Pi$ | Independently specified preservation correspondences, permitted equivalences, and evidence requirements. |
| $U$ | Applicable amendment and succession rules, including the conditions under which an amended kernel still supports the original continuity claim. |
| $\Omega$ | Covered structures, transformation classes, scope, trust assumptions, and verification limits. |
| $v$ | The immutable version of this specification and its material interpretation dependencies. |

References in $R$ do not authenticate themselves. The kernel's authority and applicability must be established under [Governing Root Geometry](../governing-root-geometry/README.md) or another explicitly justified governing basis. A candidate cannot select its own acceptance criteria merely to make preservation true.

## What belongs in an agent kernel

| Requirement | Example of a domain-specific obligation |
| --- | --- |
| Semantic distinction | Maintain the qualified identity reference and its established relationship to the governed entity. |
| Defining relationships | Preserve the specified organizational role, accountability relationships, or other identity criteria where the domain requires them. |
| Commitments and state | Preserve outstanding obligations and the state necessary to interpret or discharge them through migration. |
| Branching and composition | State when a fork creates a new identity, when replicas may share one identity, and how merges reconcile applicable obligations. |
| Governance | Preserve independent admission and the restrictions on changing authority or the kernel itself. |
| Lifecycle | Define dormant, active, retired, transferred, and successor states without silently erasing history or obligations. |

These are examples, not a universal essence of every agent. A domain may permit broad changes to objectives, models, memory, and implementation while requiring particular relationships to survive. If an obligation makes one such feature essential, replacing it requires the applicable preservation or succession argument.

## Preservation and amendment

A published kernel version remains immutable. Its application may depend on governed effective-time rules, and a valid amendment may introduce a new version. The amendment must be authorized under the previously applicable rules and identify what continuity it preserves.

**Authorized change and preserved identity are separate judgments.** Governance may authorize replacing an entity with a successor that does not retain the same identity. Permission to change the kernel is not proof that every original identity claim survives the change.

Where a higher-order contract permits kernel evolution, the preservation argument must cover that succession rule and the entire relevant transformation. A candidate cannot erase an inconvenient obligation and then claim continuity under the newly weakened specification. Earlier records retain the exact criteria under which they were qualified.

Branches and merges must cover all material parents and their applicable obligations. Conflicting requirements need explicit reconciliation; retaining one favorable ancestor is insufficient.

## Required obligations

| Obligation | Requirement |
| --- | --- |
| Exact specification | A kernel version MUST bind its obligations, interpretations, preservation mappings, and material dependencies. |
| Independent criteria | The subject seeking admission MUST NOT unilaterally determine what constitutes preservation for its own change. |
| Explicit continuity scope | Claims MUST identify which relationships and properties survive, rather than implying every property is inherited. |
| Governed succession | Kernel changes MUST follow valid prior change authority and separately establish any claimed continuity. |
| State and composition | Preservation MUST cover material migration, concurrency, branches, merges, and outstanding commitments. |
| Honest assurance | Inconsistent, undecidable, unmodeled, or unsupported obligations MUST remain explicit; declaration alone proves none of them. |

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual preservation specification; construction proves no continuity.
public sealed class ConstitutiveKernel<TStructure>
    : PreservationSpecification<TStructure>
{
}
```

A **Kernel Qualification Argument** binds the version, its independently established sources, interpretation, scope, amendment rules, and verification obligations. A separate continuity argument establishes that a particular transformation or mechanism preserves those obligations. A qualified specification is not a proof of its implementation.

## Relationships and limits

| Concept | Relationship |
| --- | --- |
| [Governing Root Geometry](../governing-root-geometry/README.md) | Supplies governing meaning and authority; the kernel selects the obligations relevant to a declared continuity claim. |
| [Constraint Geometry](../constraint-geometry/README.md) | Defines executable behavior whose transformations may be constrained by the kernel. |
| [Semantic Lineage](../semantic-lineage/README.md) | Records versions, transformations, and evidence against exact kernel versions. |
| [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) | Requires preservation of the independently specified kernel across covered transformations. |
| [Identity Continuity](../../invariants/identity-continuity/README.md) | Adds the explicit same-identity judgment when an agent claims to persist. |

A kernel need not describe every possible future capability. It constrains what future changes may legitimately preserve. It does not guarantee useful evolution, factual correctness, or present authority for an effect.

## Governing principle

> **The form may change. The obligations defining its claimed continuity require independently established preservation.**

---

© 2026 Beau Crawford
