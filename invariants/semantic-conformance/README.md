# <img src="../../assets/signatures/semantic-conformance.svg" alt="" width="32" height="32"> Semantic Conformance

*A derived invariant of preserving independently specified meaning from governing contract through executable definition to actual behavior.*

> **The executable must preserve the contract. Execution must preserve the executable's qualified semantics.**

## Definition

**Semantic Conformance** requires covered executable behavior to satisfy an independently specified governing contract, and actual execution to realize that behavior under justified interpretations. Both relationships must preserve every state change, observation, and effect material to the claim.

A policy describing itself as compliant is not an independent specification. Nor does a successful comparison between expected and recorded outputs establish correspondence to actual effects. The contract, executable semantics, mechanism semantics, and interpretation mappings need independently justified definitions and evidence.

This is a **derived conformance invariant**. It establishes preservation of declared meaning and constraints within a specified scope. It does not establish the governing contract's legitimate origin, current authority, or applicability to a particular consequence.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A semantic preservation property across specification and implementation boundaries. |
| Foundational primitive | No. It depends on independently defined semantics, constraints, observations, and correspondence. |
| Semantic type | `SemanticConformanceInvariant`. |
| Verification obligation | Establish faithful, total interpretations and preservation of the covered contract obligations. |
| Proof artifact | A version-bound conformance argument connecting contract, executable, mechanism, and deployed artifacts. |
| Runtime relevance | Qualification remains applicable only while execution and its dependencies match the verified semantics and assumptions. |

## Formal identity

- **Identifier:** `SEMANTIC_CONFORMANCE`
- **Type:** `SemanticConformanceInvariant`

For a fixed qualified configuration, let $L$ be the independently specified governing contract, $G$ the executable definition, $M$ the actual mechanism model, and $\Omega$ the independently declared scope and assumptions. A safety formulation is:

```math
\begin{aligned}
&\mathrm{SemanticConformance}(L,G,M,\Omega)\iff\\
&\quad\mathrm{FaithfulTotal}(\alpha,\beta,\Omega)\\
&\quad\land\forall\rho\in\mathrm{Exec}(M,\Omega):\;
\alpha(\rho)\in\mathrm{Adm}(G,\Omega)\\
&\quad\land\forall\gamma\in\mathrm{Adm}(G,\Omega):\;
\beta(\gamma)\in\mathrm{Adm}(L,\Omega).
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| `Exec` | All covered actual executions and prefixes, including failures, concurrency, privileged paths, and bypass behavior. |
| `Adm` | Behaviors and prefixes permitted by the independently defined transition semantics and safety constraints of the named specification. |
| $\alpha$ | An interpretation from actual execution into the executable definition's semantics. |
| $\beta$ | An interpretation from executable behavior into the governing contract's semantics. |
| `FaithfulTotal` | Both interpretations cover their complete declared domains and preserve every observation and consequence material to the claim under independently justified correspondence rules. |

The composed interpretation $\beta\circ\alpha$ must agree with the independently established meaning of actual effects. It cannot conceal a transfer by mapping it to a no-op, discard a failed authorization path, or rename a protected operation to escape the contract. Abstracting an internal step is acceptable only when its irrelevance to the claim is justified.

The formula requires both **executable-to-contract** and **execution-to-executable** conformance. Demonstrating only that a runtime obeyed its own policy leaves the policy's relationship to the contract unproved. Demonstrating a correct abstract policy leaves its deployed realization unproved.

For changing versions, qualify each exact binding and separately establish interaction, migration, and shared-resource obligations. An unbound execution cannot disappear by selecting only traces already labeled with the desired version. [Exact Semantic Binding](../exact-semantic-binding/README.md) supplies that separate correspondence obligation.

## Conformance obligations

| Obligation | Requirement |
| --- | --- |
| Independent contract | Governing meanings and admissibility criteria MUST be established independently of the executable outcome being certified. |
| Actual mechanism | The mechanism model MUST describe actual execution rules, including disallowed behavior the implementation could produce. |
| Total interpretation | Every covered behavior MUST have a justified interpretation; exceptional or adversarial paths cannot be excluded for failing the desired property. |
| Faithful effects | Mappings MUST preserve material actors, targets, operations, parameters, ordering, and shared obligations. |
| Exact artifacts | Proofs MUST bind contract, geometry, compiler, interpreter, dependency, configuration, and deployment versions material to the claim. |
| Composition | Component conformance MUST be supplemented by evidence for their interactions and aggregate effects. |
| Change control | Material changes MUST trigger applicable requalification; an old proof cannot silently cover a new implementation. |
| Explicit limits | Unsupported semantics, assumptions, horizons, and obligations MUST remain visible in the assurance claim. |

A proof may be specialized to captured inputs and effects, or cover all executions under broader assumptions. The result must state which. Evidence for one request does not qualify arbitrary future requests, and restricting the proof to a snapshot requires actual execution to remain confined to it.

## Safety, progress, and authority

The safety formulation excludes behavior outside the specified admissible set. It does not prove that required useful behavior will occur. An implementation that never commits an effect can satisfy many safety constraints while providing no service.

If the governing contract includes progress, responsiveness, termination, or availability requirements, a complete conformance claim needs additional evidence for those obligations under explicit scheduling, timing, and failure assumptions. They cannot be discharged by finite-prefix inclusion alone.

Likewise, correct behavior under a contract does not establish that the contract had standing to govern it. Authentic constitution and consequence-specific authority remain separate from semantic correctness. Current authority and dependencies must satisfy [Temporal Standing](../temporal-standing/README.md) at actual effect commitment.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual preservation claim; comparing labels or outputs is insufficient.
public sealed class SemanticConformance<TContract, TExecution>
    : SemanticConformanceInvariant<TContract, TExecution>
{
}
```

A **Conformance Argument** binds exact specifications, actual mechanism semantics, interpretation mappings, coverage, deployment correspondence, proof methods, and assumptions. It identifies which safety and additional temporal obligations are established, and the conditions invalidating that evidence.

Model checking, proof, and testing can contribute evidence with different coverage. A bounded exploration or a set of passing examples must not be presented as an unrestricted guarantee. The [Constitutive Floor Proof Standard](../../arguments/constitutive-floor/README.md) requires independent operational semantics and justified refinement for the broader constitutive claim.

## Relationships and examples

| Concept or situation | Relationship or assessment |
| --- | --- |
| [Governing Root Geometry](../../models/governing-root-geometry/README.md) | Supplies the independently constituted semantic contract. |
| [Constraint Geometry](../../models/constraint-geometry/README.md) | Supplies the executable behavioral specification. |
| [Constitutive Authority Closure](../constitutive-authority-closure/README.md) | Requires conformance together with authentic authority, exact binding, current standing, effect control, and evidence. |
| A policy faithfully enforces a rule absent from the governing contract | Runtime correctness alone does not establish contract conformance. |
| A verified policy is deployed with an interpreter that changes an effect's meaning | Qualification does not cover the altered realization. |
| A mapping omits an unauthorized external write | The interpretation is not faithful or complete. |
| All components obey individual budgets but jointly exceed a shared limit | Local conformance does not establish composed conformance. |

## Scope and limits

Semantic Conformance is relative to declared specifications and justified interpretations. It does not establish factual truth, optimal decisions, deterministic outputs, or the ultimate legitimacy of governing sources. Contradictory specifications and vacuous implementations require separate feasibility and useful-service analysis.

## Governing principle

> **Preserve meaning across every boundary between the rule, its executable realization, and its actual effects.**

---

© 2026 Beau Crawford
