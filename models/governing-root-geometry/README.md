# <img src="../../assets/signatures/governing-root-geometry.svg" alt="" width="32" height="32"> Governing Root Geometry

*A model of the independently constituted semantic contract governing a declared domain of consequence.*

> **The contract defines what may govern. Its publication does not establish its authority.**

## Definition

**Governing Root Geometry** is a domain-scoped semantic constitution defining the meanings, obligations, effect boundaries, delegation rules, and amendment procedures under which computational consequences may be authorized. Its governing status must be established through independently trusted sources and the domain's declared authority criteria.

It is a **model**, represented by a versioned governing specification. Its constraints and preservation requirements are invariants; its publication, qualification, and enforcement are separate mechanisms. A policy executable cannot constitute its own governing contract by describing itself as authoritative.

“Root” identifies the declared basis of authority for this scope. It does not establish universal legitimacy or remove the need to state trust assumptions. A deployment must explain why the root has standing over the particular actors, resources, operations, and effects being governed.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Model | An authoritative semantic specification, conditional on independently established constitutive origin and applicability. |
| Foundational primitive | No. It organizes ontology, constraints, authority, effects, scope, and change rules. |
| Invariant | No. Individual obligations and their preservation are separately specified properties. |
| Semantic type | `GoverningGeometrySpecification`. |
| Verification obligation | Establish authentic origin, governing scope, interpretation, delegation, applicability, and legitimate change. |
| Proof artifact | A version-bound governing qualification argument and its explicit trust assumptions. |

## Formal identity

- **Identifier:** `GOVERNING_ROOT_GEOMETRY`
- **Type:** `GoverningGeometrySpecification`

```math
L_v=\langle R,N,K,Q,J,U,V,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $R$ | Independently trusted constitutive sources and the criteria establishing their authority. |
| $N$ | Domain ontology and interpretation: actors, resources, states, relations, operations, and consequential meanings. |
| $K$ | Required constraints and invariants, including composition and shared-resource obligations. |
| $Q$ | Protected-effect definitions and their actual commitment boundaries. |
| $J$ | Delegation and jurisdiction rules: who may authorize which operations, targets, parameters, and joint effects. |
| $U$ | Amendment, promotion, succession, and conflict-resolution procedures. |
| $V$ | Version identity and applicability rules, including effective changes, expiry, and revocation. |
| $\Omega$ | Declared scope, trust, environmental, timing, and failure assumptions. |

The tuple records a specification; it does not establish the facts asserted by that specification. Qualification must bind the exact version and its interpretation to independently justified authority over the declared scope.

## Origin, delegation, and applicability

| Question | Required basis |
| --- | --- |
| Who published this artifact? | Authentic publication evidence tied to exact content and interpretation. |
| Why may that source govern this domain? | Independently established constitutive authority and declared trust assumptions. |
| What may a delegate authorize? | A valid chain whose scope covers the exact operation and its effects. |
| Which version applies? | Governed applicability and conflict rules at the relevant boundary. |
| May these rules change? | Authority under previously applicable amendment rules, including required continuity and transition obligations. |

A signature can authenticate publication under its assumptions. It does not independently prove jurisdiction, correctness, or current applicability. Likewise, an unrevoked delegation is insufficient if it does not cover the requested consequence.

Multiple contracts or roots may apply to one effect. The implementation must establish their applicable composition and precedence rules rather than choosing whichever contract admits the operation. Unresolved conflicts prevent commitments that depend on their resolution.

## Required obligations

| Obligation | Requirement |
| --- | --- |
| Independent constitution | Governing authority MUST be established outside the subject executable's unilateral declarations. |
| Exact meaning | Ontology, constraints, effect semantics, and material interpretation dependencies MUST be version-bound and unambiguous. |
| Explicit scope | Protected effects and governing jurisdiction MUST be defined independently of observed successes or the desired proof result. |
| Bounded delegation | Every authorization MUST remain within valid delegation, including aggregate limits and restrictions on further delegation. |
| Governed applicability | Effective-time, revocation, expiry, and conflict semantics MUST be explicit and enforced where consequences commit. |
| Prior change authority | A successor MUST NOT create the authority needed to approve its own introduction. Amendments follow previously applicable rules. |
| Preserved history | Changes MUST produce new records; later findings cannot silently rewrite the basis recorded for past commitments. |
| Deployment correspondence | Governing qualification MUST connect to the actual executable and effect mechanisms, including privileged and external routes. |

These are obligations on the governing architecture, not powers acquired by constructing a model object. [Authority Independence](../../invariants/authority-independence/README.md) defines the separation from subject control. Automated admission is possible under valid prior delegation.

## Lifecycle and enforcement

```text
INDEPENDENT CONSTITUTIVE SOURCES
    ↓ qualified publication and interpretation
EXACT GOVERNING CONTRACT
    ↓ authorized derivation and implementation
EXECUTABLE CONSTRAINT GEOMETRY
    ↓ current standing and actual effect enforcement
PROTECTED CONSEQUENCE
```

Publication, admission, and effect commitment are separate events. An older contract may remain applicable after a newer version is published. A new contract cannot silently rebind in-flight work or revive revoked grants. Amendments must account for migration, concurrent versions, outstanding delegation, and external receivers.

[Semantic Conformance](../../invariants/semantic-conformance/README.md) requires the executable geometry and its actual realization to preserve the independently constituted contract. Even correct conformance does not establish that a particular effect currently has standing; actual authority, dependencies, and required support must hold at its commitment boundary.

## Semantic type and evidence

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual specification; its existence does not constitute authority.
public sealed class GoverningRootGeometry<TDomain, TConsequence>
    : GoverningGeometrySpecification<TDomain, TConsequence>
{
}
```

A **Governing Qualification Argument** binds the contract, constitutive sources, delegation, scope, interpretation, applicability rules, and evidence. It states where the trust argument terminates. It must not imply that formal verification supplies the ultimate legitimacy of assumed governing sources.

Qualification of one version does not automatically qualify amendments, translations, compiled artifacts, or deployments. Each claimed transfer requires justified correspondence and preservation under the relevant assumptions.

## Relationship to the architecture

| Concept | Relationship |
| --- | --- |
| [Constitutive Kernel](../constitutive-kernel/README.md) | Specifies the obligations and preservation criteria for particular continuity claims under this governing basis. |
| [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) | Qualifies preservation of constitutive relationships through governed amendment and succession. |
| [Constitutive Authority Closure](../../invariants/constitutive-authority-closure/README.md) | Connects qualified governing meaning to standing, conforming execution, and actual protected effects. |
| [Generative Root Geometry](../generative-root-geometry/README.md) | Describes differentiation and origin continuity. Governing status requires the additional constitutive authority modeled here. |
| [Constraint Geometry](../constraint-geometry/README.md) | Supplies executable behavioral definitions that must conform to applicable governing meaning. |
| [Structural Standing](../../invariants/structural-standing/README.md) | Requires actual eligibility and support for enabled protected effects. |
| [Temporal Standing](../../invariants/temporal-standing/README.md) | Requires current applicability and standing under enforceable ordering at commitment. |
| [Boolean Standing Fallacy](../../anti-patterns/Boolean-Standing-Fallacy.md) | Explains why an approval, signature, or self-description cannot constitute governing authority. |

## Examples and limits

| Situation | Assessment |
| --- | --- |
| A signed policy claims control over resources outside its publisher's jurisdiction | Authentic publication does not establish governing scope. |
| A delegate approves an operation outside its grant | An otherwise valid chain does not authorize the specific effect. |
| A candidate changes the rule that would reject its own promotion | The candidate cannot supply the missing prior amendment authority. |
| Two applicable contracts impose incompatible requirements | Resolve the conflict through valid governing rules or prevent the dependent effect. |

This model defines how governing claims are represented and qualified. It does not guarantee factual truth, useful service, correct implementation, or complete effect coverage. Those need separate evidence and enforcement.

## Governing principle

> **Origin establishes the claimed source. Independent constitution establishes its governing role. Current standing qualifies the consequence.**

---

© 2026 Beau Crawford
