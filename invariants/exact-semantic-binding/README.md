# <img src="../../assets/signatures/exact-semantic-binding.svg" alt="" width="32" height="32"> Exact Semantic Binding

*A derived invariant connecting each covered execution unit to one immutable computational definition.*

> **A version reference is meaningful only when it identifies the definition actually used.**

## Definition

**Exact Semantic Binding** requires every covered execution unit to bind exactly one immutable semantic descriptor and to use the computational definition that descriptor resolves. The binding covers material executable, interpretation, and dependency semantics throughout that unit's execution.

A descriptor may identify one executable geometry or an immutable manifest of explicitly identified components. The invariant does not require every participant in a distributed interaction to execute the same geometry. It requires the declared unit and its component boundaries to be unambiguous, with no silent substitution through a mutable “latest” reference.

Binding answers **which definition actually governed this computation?** It does not establish that the definition conforms to governing rules, preserves legitimate lineage, or retains authority for a consequence. Those claims need separate evidence.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Invariant | A derived identity and correspondence property over covered executions. |
| Foundational primitive | No. It depends on execution units, version identity, resolution, and definition semantics. |
| Semantic type | `SemanticBindingInvariant`. |
| Verification obligation | Establish unique immutable resolution and correspondence to every material definition actually used. |
| Proof artifact | A version-bound binding argument covering resolution, artifacts, interpretation, and deployment. |
| Runtime relevance | Prevents qualification for one definition from silently transferring to another. |

## Formal identity

- **Identifier:** `EXACT_SEMANTIC_BINDING`
- **Type:** `SemanticBindingInvariant`

Let $C$ contain semantic coordinates, $\Sigma$ contain immutable descriptors, and $R:C\rightharpoonup\Sigma$ be the declared partial resolution function. For mechanism $M$ and independently specified scope and assumptions $\Omega$:

```math
\begin{aligned}
&\mathrm{ExactSemanticBinding}(M,\Omega)\iff\\
&\forall\rho\in\mathrm{Exec}(M,\Omega),\;
\forall x\in\mathrm{Units}(\rho):\\
&\quad\exists\tau\in C,\;\sigma\in\Sigma:\\
&\qquad\mathrm{Bindings}(x)=\{\tau\}\\
&\qquad\land R(\tau)=\sigma\\
&\qquad\land\mathrm{StableResolution}(\tau,\sigma,\Omega)\\
&\qquad\land\mathrm{DefinitionUsed}(x)=\sigma.
\end{aligned}
```

| Term | Meaning |
| --- | --- |
| `Units` | Every actual execution unit in the independently declared coverage, including unauthorized execution, fallback routes, retries, and recovery. |
| `Bindings` | Coordinates bound before their governed execution and retained throughout that unit; the singleton excludes absent or ambiguous bindings. |
| `StableResolution` | A coordinate has one fixed descriptor and material artifact closure across its declared namespace and lifetime. Publication or later resolution cannot silently replace either. |
| `DefinitionUsed` | The complete descriptor of the semantics actually used, including executables, interpreters, configuration affecting meaning, and material component definitions. |

The equality expresses actual correspondence, not agreement between two self-reported labels. A digest can support artifact integrity under explicit encoding and cryptographic assumptions; it does not prove that the runtime used those artifacts or interpreted them as claimed.

A rejected request that never begins the covered computation need not acquire a successful execution binding. If work nevertheless executes or produces an effect, failed admission cannot remove it from coverage. A unit spanning a material definition change must be explicitly divided and rebound, or use an already qualified manifest whose transition semantics cover that change.

## Binding obligations

| Obligation | Requirement |
| --- | --- |
| Explicit units | The scope MUST identify the work, component boundaries, and material semantics covered by each binding. |
| Unambiguous identity | Namespaces and resolution MUST prevent the same coordinate from acquiring conflicting definitions. |
| Immutable closure | Material executable and interpretation dependencies MUST resolve to exact versions; mutable aliases cannot redefine a bound artifact. |
| Actual correspondence | Loaders, compilers, runtimes, caches, and delegated execution MUST preserve the declared binding. |
| No silent fallback | Missing, conflicting, or unavailable resolution MUST prevent execution that depends on it; choosing a different definition requires explicit rebinding and qualification. |
| Compound execution | Component manifests MUST identify participating definitions and their interaction semantics. An aggregate identifier alone is insufficient. |
| Evidence | Records MUST identify the binding actually used; writing the intended version afterward cannot repair substituted execution. |
| Coverage | Privileged paths, dynamic loading, migration, retry, and recovery MUST remain within the established argument. |

**Definition and operational data are distinct.** A geometry can define a state schema while its current state evolves. Actual inputs, observations, and state versions must be bound where required by the transaction's qualification contract; this invariant does not freeze all data or imply that every external observation is an immutable artifact. Dependencies that determine meaning belong in the semantic descriptor. Dependencies whose changing values affect standing additionally require commit-time qualification.

## Distinct guarantees

| Established claim | What still needs evidence |
| --- | --- |
| One immutable definition actually executed | Whether its behavior conforms to the governing contract. |
| The coordinate identifies authentic artifact bytes | Whether those artifacts have legitimate constitutive lineage. |
| A historical execution can be interpreted | Whether retained state and nondeterministic choices permit deterministic replay. |
| A component manifest resolves exactly | Whether component interactions preserve shared constraints. |
| A formerly authorized geometry is reconstructed | Whether any new consequence has current standing. |

Version identity is neither a grant nor a global clock. An older definition can remain applicable; publishing a newer one does not by itself revoke it. Conversely, an exact immutable binding does not preserve an expired permission.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual correspondence claim; storing a version does not prove it.
public sealed class ExactSemanticBinding<TExecutionUnit>
    : SemanticBindingInvariant<TExecutionUnit>
{
}
```

A **Binding Argument** identifies unit boundaries, namespaces, resolution rules, exact artifacts and interpreters, loading and delegation mechanisms, deployment versions, retention scope, and trusted assumptions. It must justify how recorded bindings correspond to actual execution and how equivocation or substitution is prevented.

Useful counterexamples include a cache returning different bytes for one coordinate, an undeclared interpreter update, and a worker consulting “latest” after qualification. Tests can expose these failures; successful examples alone do not prove all covered paths.

## Relationships and examples

| Concept or situation | Relationship or assessment |
| --- | --- |
| [Semantic Time](../../models/semantic-time/README.md) | Supplies a model of coordinates and immutable resolution; this invariant states the required execution-binding property. |
| [Constraint Geometry](../../models/constraint-geometry/README.md) | Supplies the computational definition that execution must actually use. |
| [Constitutive Continuity](../constitutive-continuity/README.md) | Separately establishes preservation across the bound definition's lineage. |
| [Temporal Standing](../temporal-standing/README.md) | Requires the exact bound definition and effect to remain eligible at actual commitment. |
| A transaction records version 4 but loads version 5 | Binding fails even if both versions are individually valid. |
| Two components use different versions named in one immutable manifest | Binding may hold; interaction correctness remains a separate obligation. |
| The same geometry yields different outputs from different observations | Binding may hold; identical outputs are not required. |

## Scope and limits

The invariant is relative to an explicit definition of material semantics and execution coverage. Omitting a behavior-changing dependency cannot make a binding complete. It does not prove authority, semantic correctness, availability, or useful progress, and it does not prescribe a particular version format or storage system.

## Governing principle

> **Bind the exact meaning before execution. Preserve that binding through its realization.**

---

© 2026 Beau Crawford
