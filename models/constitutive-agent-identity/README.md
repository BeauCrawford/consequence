# <img src="../../assets/signatures/constitutive-agent-identity.svg" alt="" width="32" height="32"> Constitutive Agent Identity

*Identity through governed becoming, not persistent execution.*

> **Identity does not require immutable form. It requires constitutively preserved continuity.**

## Definition

**Constitutive Agent Identity (CAI)** is an architectural model of a persistent, semantically distinguishable computational entity whose continuing identity is established through independently governed transformations of executable constraint geometry across semantic time.

An agent's logical identity is distinct from its language model, process, implementation, memory contents, and any particular geometry version. Its continued identity depends on an independently specified constitutive kernel and evidence that the required relationships, state, and inherited obligations survive the transformations claimed as its evolution.

An agent may change models, objectives, constraints, capabilities, implementation, or operational state without necessarily losing its identity. Each material change must satisfy the applicable identity criteria and independent promotion requirements. Permission to change an artifact does not itself establish identity preservation, and preserving identity does not authorize a present protected effect.

**CAI is a model.** Its distinction and preservation requirements are invariants. The name identifies the architecture specified here; creating an object, retaining an ID, or asserting ancestry establishes none of its guarantees.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | An identifiable computational entity whose continuity is governed across changing expressions. |
| Model | **Yes.** Specifies identity records, constitutive criteria, lineage, state relationships, and lifecycle. |
| Foundational primitive | No. It composes distinction, relation, version, transformation, preservation, state, and authority. |
| Invariant | **No.** Constitutive Distinction and Identity Continuity are separately stated properties of its implementations. |
| Semantic type | `AgentIdentitySpecification`. |
| Verification obligation | Establish identity origin, exact reference, required continuity, qualified lineage, relevant state preservation, and independent admission. |
| Proof artifact | A version-bound identity qualification argument with explicit criteria, evidence, scope, and trust assumptions. |
| Runtime relevance | An eligible runtime may realize the identity temporarily; continued logical identity does not depend on that particular process remaining alive. |

## Five constitutive dimensions

| Dimension | Role and classification |
| --- | --- |
| **Semantic identity** | The durable semantic distinction identifying the governed entity. It is a component of CAI; [Constitutive Distinction](../../invariants/constitutive-distinction/README.md) establishes unambiguous reference. |
| **Constitutive geometry** | The defining obligations and governing relationships represented by the [Constitutive Kernel](../constitutive-kernel/README.md) model. Its preservation is an invariant, not a property created by the specification itself. |
| **Semantic lineage** | The [Semantic Lineage](../semantic-lineage/README.md) model records exact origins, material parents, transformations, and admission evidence. The qualified admitted history supports the continuity claim. |
| **Durable state** | A model component containing required operational state, history, commitments, and evidence under an explicit retention and migration contract. Persistence alone is neither an identity model nor proof of continuity. |
| **Temporal continuity** | A composition of [Semantic Time](../semantic-time/README.md), [Exact Semantic Binding](../../invariants/exact-semantic-binding/README.md), and transaction-specific state bindings. Current consequence eligibility additionally requires [Temporal Standing](../../invariants/temporal-standing/README.md). |

[Identity Continuity](../../invariants/identity-continuity/README.md) specializes [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) to the preservation of this particular agent identity. Existing temporal and authority concepts are reused rather than assigned competing definitions.

## Formal identity model

- **Identifier:** `CONSTITUTIVE_AGENT_IDENTITY`
- **Type:** `AgentIdentitySpecification`
- **Abbreviation:** `CAI`

An immutable identity record at revision $r$ is:

```math
I_{A,r}=\langle D_A,K_{v(r)},\mathcal{L}_r\rangle
```

| Symbol | Meaning |
| --- | --- |
| $D_A$ | The durable semantic distinction identifying agent A under qualified namespace and constitutive criteria. |
| $K_{v(r)}$ | The exact constitutive kernel version applicable to this record, with independently governed succession rules where kernels change. |
| $\mathcal{L}_r$ | The recorded lineage view and evidence supporting the admitted expressions represented by this record. |
| $r$ | The immutable revision of the identity record; it is not a new agent identity or a universal clock. |

The lineage grows through new records; a historical record remains unchanged. Consequently, the entire tuple must not be treated as one eternally fixed value. The semantic distinction can persist across record revisions only where the applicable identity-continuity requirements hold. Equality of identifiers is necessary for a same-reference claim, but insufficient to establish legitimate continuity.

An execution's computational expression is represented separately:

```math
E_x=\langle I_{A,r_x},\tau_x,G_{\tau_x},\nu_x,S_{\nu_x}\rangle
```

| Symbol | Meaning |
| --- | --- |
| $x$ | The logical execution unit, distinct from a process or retry attempt. |
| $I_{A,r_x}$ | The qualified identity-record revision bound to this execution. |
| $\tau_x$ | The exact semantic-time coordinate for its executable definition. |
| $G_{\tau_x}$ | The immutable geometry or component manifest resolved from that coordinate and actually used. |
| $\nu_x$ | The exact relevant state version or consistent state manifest bound to the execution. |
| $S_{\nu_x}$ | The corresponding operational state interpreted under the bound geometry. |

A geometry coordinate alone does not identify every transaction's state. Many executions may use the same geometry with different inputs and state versions. Transaction records additionally bind actual inputs, material dependencies, intermediate observations where required, resulting state, effects, and commitment evidence. Concurrency and consistency require their own enforcement.

These tuples organize a specification. They do not prove that a record is authentic, state is complete, lineage is valid, or actual execution matches the declared bindings.

## Required obligations and their classification

| Obligation | Canonical requirement |
| --- | --- |
| **Constitutive distinction** | [Constitutive Distinction](../../invariants/constitutive-distinction/README.md): established agent references MUST remain unambiguous across implementations, versions, and runtimes. |
| **Identity-preserving continuity** | [Identity Continuity](../../invariants/identity-continuity/README.md): any expression used as the same agent MUST satisfy independently specified preservation and identity criteria. |
| **Verifiable semantic lineage** | Semantic Lineage provides the model; Constitutive Continuity and identity qualification MUST establish actual derivation, complete material parents, applicable obligations, and admission evidence. |
| **Semantic-temporal binding** | Exact Semantic Binding MUST connect execution to the actual definition; transaction bindings MUST identify relevant state, inputs, dependencies, and effect context. |
| **Non-self-authorization** | [Authority Independence](../../invariants/authority-independence/README.md) and [Governed Promotion](../../patterns/governed-promotion/README.md): a candidate MUST NOT authorize its own admission or relax its own governing criteria. |
| **Identity–authority separation** | Identity, ancestry, and historical approval MUST NOT substitute for current consequence-specific standing at the actual effect boundary. |
| **Execution independence** | CAI separates logical identity from any particular runtime, model, or implementation. Continued identity and recovery still require the specified preservation and retention conditions. |

Execution independence is an architectural distinction. It does not imply that every implementation or model replacement preserves identity. The kernel determines what changes are permitted and which state or relationships must survive.

## Durable state and lifecycle

Durable state includes what the application must retain to interpret past activity, preserve commitments, and support qualified continuation. It need not include every historical observation or every memory byte. Retention, compaction, learning, forgetting, and migration must preserve the obligations on which the claim depends.

| Lifecycle event | Required treatment |
| --- | --- |
| Establish identity | Qualify its origin, distinction, kernel, initial state, governing relationships, and admission basis. |
| Instantiate execution | Resolve the exact definition and bind the required identity, state, inputs, and dependencies. |
| Release a runtime | Preserve the required records and commitments. Process termination does not cancel delegated powers or outstanding work. |
| Remain dormant | Retain artifacts and evidence according to the declared contract; logical persistence does not promise indefinite storage or availability. |
| Resume or restore | Reconcile relevant history and outstanding commitments, qualify state and identity continuity, and establish current standing for new effects. |
| Evolve | Create an immutable candidate, verify its material lineage and preservation, and independently govern activation. |
| Retire or transfer | Preserve historical attribution and explicitly govern remaining commitments, credentials, queued work, and any proposed successor relationship. |

A surviving identity reference cannot recover deleted state. An old snapshot cannot erase commitments made after it was captured. Lost evidence may make continuity unresolved without proving the underlying history invalid; dependent qualified operation must not assume the missing facts.

## Forks, merges, and authority

A fork can preserve ancestry while creating a new identity. Multiple replicas can realize one identity where explicit rules permit it, but they must coordinate shared state, commitments, and effects. Copying a history cannot duplicate a limited grant or resource allocation.

A merge must identify every material parent, reconcile applicable obligations, and establish which identity continues or whether a new one is created. Related descendants are not automatically interchangeable, and common ancestry does not establish identity equality.

A valid continuing identity can have no current permission to act. Conversely, governance may authorize introducing a new successor identity. Identity preservation, authorized promotion, and standing for a particular effect remain distinct judgments with separate evidence.

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual identity model; a persistent key does not prove continuity.
public sealed class ConstitutiveAgentIdentity<TState>
    : AgentIdentitySpecification<TState>
{
}
```

An **Identity Qualification Argument** binds the constituted origin, semantic distinction, exact identity and kernel revisions, actual material lineage, relevant state and commitments, preservation criteria, admission evidence, lifecycle rules, deployment correspondence, retention, and trust assumptions.

Verification must cover the actual mechanism, including migration, restoration, concurrent expressions, privileged changes, and external effects. A proof for one transition does not qualify every future successor. Unsupported obligations remain explicit rather than becoming assumptions hidden behind the identity label.

## Relationship to the architecture

| Concept | Relationship |
| --- | --- |
| [Generative Root Geometry](../generative-root-geometry/README.md) | Supplies distinction, relation, and continuity as a model of differentiation. CAI adds explicit criteria for governed agent identity. |
| [Governing Root Geometry](../governing-root-geometry/README.md) | Supplies independently constituted authority and amendment rules for the identity's kernel and lifecycle. |
| [Constraint Geometry](../constraint-geometry/README.md) | Defines each executable expression; its version is distinct from the continuing agent identity. |
| [Constraint-Governed Agency](../constraint-governed-agency/README.md) | Describes governed configurations of generative capability; CAI specifies the identity relationships that may persist across their changes. |
| [Semantic-Temporal Agent Geometry](../semantic-temporal-agent-geometry/README.md) | Integrates this identity model with exact execution, operational state, two linked histories, and consequence enforcement. |
| [Recursive Geometry Evolution](../recursive-geometry-evolution/README.md) | Describes successor proposal generation. CAI does not require recursion or successful evolution. |
| [Protected Commitment](../../patterns/protected-commitment/README.md) | Controls actual effects and their evidence; valid identity alone does not discharge its obligations. |

## Scope and limits

CAI defines a domain-specific computational identity contract. It does not establish a universal identity relation or guarantee indefinite persistence. The river-and-whirlpool image is a metaphor for continuity through changing realization; actual identity claims require explicit criteria and evidence.

The model permits dormant or continuously hosted agents. Persistence of a process neither proves nor defeats CAI. Changes may preserve identity, require a new identity, or remain unresolved. Useful evolution, factual correctness, availability, and current authority need their own arguments.

## Governing principle

> **The field provides possibility. Geometry defines an expression. Governed continuity establishes the agent's identity. Current standing governs its consequences.**

**An agent's computational form may evolve while its identity remains independently established through the relationships that constitute its continuity.**

---

© 2026 Beau Crawford
