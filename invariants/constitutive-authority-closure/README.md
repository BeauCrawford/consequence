# <img src="../../assets/signatures/constitutive-authority-closure.svg" alt="" width="32" height="32"> Constitutive Authority Closure

*A composite invariant connecting authentic governing meaning, current standing, conforming execution, and actual consequence.*

> **No protected consequence may cross a missing link between governing authority and actual effect.**

## Definition

**Constitutive Authority Closure** requires every covered protected commitment to remain bound to an independently constituted, applicable governing contract; its exact executable semantics; current consequence-specific standing; and the mechanism controlling the actual effect. Complete route coverage and faithful commitment evidence are part of the claim.

It is a **derived, composite invariant**. Naming its component properties does not prove their composition. The contracts, executable versions, actors, inputs, dependencies, effects, boundaries, and ordering used by their proofs must refer to the same consequential occurrence under compatible assumptions.

Closure does not require every consequence to be impossible. Legitimate effects may remain reachable. The excluded condition is a protected effect whose governing authority, meaning, standing, or enforced realization is disconnected from the claimed contract.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A composite safety property across covered executions and commitment boundaries. |
| Foundational primitive | No. It depends on authority, semantics, binding, standing, coverage, and effect control. |
| Semantic type | `AuthorityClosureInvariant`. |
| Verification obligation | Establish each required property and the compatibility of their bindings, scopes, assumptions, and deployed mechanisms. |
| Proof artifact | An independently checkable, version-bound closure argument. |
| Runtime property | Applies only while actual enforcement and material assumptions remain within the established scope. |

## Formal identity

- **Identifier:** `CONSTITUTIVE_AUTHORITY_CLOSURE`
- **Type:** `AuthorityClosureInvariant`

For a mechanism $M$ and independently declared scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{AuthorityClosure}(M,\Omega)\iff\\
&\quad\mathrm{CoverageComplete}(M,\Omega)\\
&\quad\land\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall c\in\mathrm{ProtectedCommits}(\rho):\\
&\qquad\mathrm{ExactBindings}(c)\\
&\qquad\land\mathrm{AuthenticApplicableLaw}(c)\\
&\qquad\land\mathrm{SemanticsPreserved}(c)\\
&\qquad\land\mathrm{CurrentStanding}(c)\\
&\qquad\land\mathrm{EffectCustody}(c)\\
&\qquad\land\mathrm{EvidenceBound}(c).
\end{aligned}
```

| Term | Required meaning |
| --- | --- |
| `CoverageComplete` | The scope accounts for every actual route to its independently defined protected effects, including privileged, delegated, recovery, and external routes. |
| `ExactBindings` | The contract, executable definition, actor, inputs, dependencies, and actual effect have unambiguous, mutually consistent bindings. |
| `AuthenticApplicableLaw` | Constitutive origin, governing jurisdiction, delegation, interpretation, and applicability are independently established for this occurrence. |
| `SemanticsPreserved` | The executable conforms to the governing contract, and actual execution preserves the required transition and effect semantics. |
| `CurrentStanding` | Actual eligibility, exact authority scope, and required support hold at commitment under enforceable ordering of relevant changes. |
| `EffectCustody` | The real effect mechanism prevents bypass or substitution and controls the exact consequence at its actual boundary. |
| `EvidenceBound` | Durable evidence identifies the actual commitment and its governing basis without confusing intent, authorization, and completion. |

$\rho$ ranges over all covered executions, including failures and adversarial paths allowed by the assumptions. The predicates describe substantive obligations, not independent approval flags. The scope cannot exclude an unauthorized occurrence merely because it failed the intended admission process.

## Composition obligations

```text
AUTHENTIC GOVERNING CONTRACT
    ↓ exact, independently checked semantic derivation
EXECUTABLE DEFINITION
    ↓ faithful execution with bound inputs and dependencies
CURRENT CONSEQUENCE-SPECIFIC STANDING
    ↓ complete mediation and enforced commitment ordering
ACTUAL PROTECTED EFFECT
    ↓ evidence bound to the real outcome
DURABLE COMMITMENT RECORD
```

| Obligation | Requirement |
| --- | --- |
| Shared meaning | Component arguments MUST use compatible definitions of the actor, transition, protected effect, and commitment boundary. |
| Shared bindings | Qualification, execution, and recording MUST refer to the same immutable definitions and actual effect parameters. |
| Independent authority | The subject executable MUST NOT establish its own governing jurisdiction, admission authority, or permission to change the rules judging it. |
| Complete custody | Every covered effect path MUST satisfy the required enforcement, including paths that do not use the nominal policy engine. |
| Current qualification | Authority and material conditions MUST remain applicable at the actual effect boundary; cached approval alone is insufficient. |
| Compatible assumptions | Composed proofs MUST agree on state, trust, clock, concurrency, and failure assumptions. One component cannot assume the property another only intends to enforce. |
| Real deployment | The argument MUST connect to actual artifacts, configuration, credentials, receivers, and relevant infrastructure. |
| Faithful evidence | Local commitments and their required evidence MUST be durably coupled; external intents and completed external effects MUST remain distinct. |

A mediated route can enforce an unauthorized contract. A correct executable can act under an expired grant. A valid decision can be followed by a different effect. Each breaks a different part of closure; success in the remaining components does not repair that break.

## Local and external commitment

At a local boundary, consequence and required evidence must be recorded under the same enforceable commitment semantics. A receipt or later signature attests a record; it cannot supply missing authority or retroactively prevent an effect.

For external work, the first commitment may cover only an authorized intent. The receiving system must establish current standing and control the actual effect under the relevant ordering, with fencing and duplicate-effect prevention appropriate to the operation. Completion evidence is separate. If the receiver cannot meet these obligations, the end-to-end closure claim is unsupported and the dependent protected effect must not proceed.

Continuing effects and joint operations require coverage of their intervals, sub-effects, and shared limits. A collection of individually valid local approvals does not establish a valid aggregate consequence.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual claim; its construction does not prove end-to-end closure.
public sealed class ConstitutiveAuthorityClosure<TConsequence>
    : AuthorityClosureInvariant<TConsequence>
{
}
```

A **Closure Argument** binds exact contracts, executable and deployment versions, effect definitions, all covered routes, applicability and ordering rules, trust assumptions, and component evidence. It separately justifies the connections between those components. A signed bundle of incompatible proofs is still incompatible.

The argument must identify what would falsify the claim: an uncovered effect path, mismatched semantic binding, unauthorized source, stale grant, substituted effect, or unsupported completion record. Tests can expose these failures; successful samples do not establish universal closure.

## Relationship to existing concepts

| Concept | Contribution and limit |
| --- | --- |
| [Governing Root Geometry](../../models/governing-root-geometry/README.md) | Defines governing meaning and authority criteria; its declaration alone does not enforce effects. |
| [Authority Independence](../authority-independence/README.md) | Prevents the subject from manufacturing or weakening its necessary authorization basis. |
| [Semantic Conformance](../semantic-conformance/README.md) | Establishes preservation from the governing contract through executable semantics to actual behavior; authority remains a separate obligation. |
| [Exact Semantic Binding](../exact-semantic-binding/README.md) | Connects each execution unit to its actual immutable definition; closure additionally binds the governing contract, inputs, dependencies, and effect. |
| [Constraint Geometry](../../models/constraint-geometry/README.md) | Defines executable behavior; conformance and independent authority still need evidence. |
| [Structural Standing](../structural-standing/README.md) | Requires actual eligibility and support for enabled effects. |
| [Temporal Standing](../temporal-standing/README.md) | Makes exact applicability, current standing, and authoritative ordering explicit at commitment. |
| [Topological Zero](../topological-zero/README.md) | Establishes complete mediation; it does not establish the truth of a mediated decision. |
| [Structural Zero](../structural-zero/README.md) | Can describe unreachability of unauthorized effects under the composed assumptions. Closure does not require zero legitimate effects. |
| [Constitutive Floor](../../arguments/constitutive-floor/README.md) | Requires non-vacuous evidence, independent operational semantics, refinement, and explicit deployment trust for constitutive claims. |

## Scope and limits

Closure is relative to declared governing criteria and trust assumptions; formal verification cannot manufacture the ultimate legitimacy of its assumed roots. Nor does closure establish factual truth, deterministic replay, useful service, or optimal policy.

As a safety invariant, it may hold when no protected effects occur. A claim that the contract actually constitutes useful consequence additionally needs feasible legitimate executions, non-vacuous evidence, and any required progress guarantees.

## Governing principle

> **Authentic law, preserved meaning, current standing, and actual effect control must meet at the same consequence.**

---

© 2026 Beau Crawford
