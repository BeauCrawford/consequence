# <img src="../../assets/signatures/semantic-time.svg" alt="" width="32" height="32"> Semantic Time

*A logical temporal model of meaning, state, and transformation across immutable semantic versions.*

> **Semantic Time identifies the meaning bound to a transition. Standing governs whether its consequence may commit.**

## Definition

**Semantic Time** is a logical temporal model in which time is expressed through identifiable changes in a system's constituted semantic state and their causal relationships, rather than solely through elapsed physical time.

A **semantic-time coordinate** identifies an immutable version within a declared entity and lineage. Resolution connects that coordinate to an exact semantic definition: the geometry, interpretation rules, and material artifact references needed to understand the covered computation. Transaction records additionally bind the actual inputs, state, and dependencies used.

The model answers **under precisely what constituted meaning did this transition occur?** It does not independently establish that the bound definition was authorized, that its lineage was legitimate, or that its proposed effects retain current standing. Those are separate verification obligations.

**Semantic Time is a model, not an invariant.** This specification uses the term for the architecture described here. Immutable resolution, faithful execution binding, and verifiable continuity are properties an implementation must establish.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | The identity and causal continuity of computational meaning across change. |
| Architectural model | **Yes.** A logical temporal model for semantic versions, resolution, and lineage. |
| Foundational primitive | No. It depends on identity, state, version, relation, transformation, and scope. |
| Invariant | **No.** Particular binding and continuity properties are stated separately. |
| Semantic type | `LogicalTemporalModel`, with explicit resolution and preservation obligations. |
| Mathematical structure | Immutable semantic coordinates connected by an acyclic predecessor relation and a partial resolution function. |
| Verification obligation | Establish unambiguous resolution, immutable bindings, valid lineage, and correspondence to actual execution. |
| Proof artifact | A version-bound model-conformance argument with resolution, lineage, and execution-binding evidence. |
| Runtime relevance | Historical interpretation and reproducible semantic definitions, subject to artifact availability and declared assumptions. |

```text
SEMANTIC ENTITY AND LINEAGE
  Identify the subject and its branch of evolution
    ↓
IMMUTABLE SEMANTIC COORDINATE
  Version identity · Causal predecessor references
    ↓ resolves to
EXACT SEMANTIC DEFINITION
  Geometry · Interpretation · Material artifact references
    ↓ bound together with actual inputs, state, and dependencies
COMPUTATIONAL TRANSITION
  Execute and record under the identified definition
    ↓ independently qualified at each protected boundary
CONSEQUENCE COMMITMENT
  Current standing · Enforced ordering · Durable evidence
```

Resolution establishes a definition, not an execution permit. Governing applicability and effect authority remain subject to [Temporal Standing](../../invariants/temporal-standing/README.md).

## Formal identity

- **Identifier:** `SEMANTIC_TIME_CAUSAL_VERSION_MODEL`
- **Type:** `LogicalTemporalModel`
- **Coordinate notation:** $\tau$. In this page it denotes a semantic coordinate; some invariant pages use the same symbol locally for an execution trace.

A model can be represented as:

```math
\mathcal{T}=\langle C,\prec,\Sigma,R,\Omega\rangle
```

| Symbol | Meaning |
| --- | --- |
| $C$ | The recognized semantic-time coordinates. |
| $\prec$ | The strict causal ancestry relation induced by declared predecessor references. |
| $\Sigma$ | Immutable semantic descriptors or manifests, including their interpretation and material artifact bindings. |
| $R$ | A partial function resolving a coordinate to its exact descriptor. |
| $\Omega$ | Declared entity and lineage scope, roots, transformation rules, trust assumptions, retention commitments, and verification coverage. |

### Semantic-time coordinate

```math
\tau=\langle I,L,V,P\rangle
```

| Symbol | Meaning |
| --- | --- |
| $I$ | Semantic entity identity. A stable reference does not itself prove continuity of the referent. |
| $L$ | Lineage or branch identity, with an explicitly defined namespace. |
| $V$ | Immutable semantic version identity, unique within the entity and lineage. |
| $P$ | An immutable set of causal predecessor references, including material cross-lineage dependencies where applicable. |

The key $(I,L,V)$ must identify exactly one coordinate and descriptor. Changing its predecessor set or bound meaning requires a new version; repeating a version label with different content is equivocation, not evolution. Root coordinates have no predecessors and require explicitly declared origins.

A content digest can additionally bind the coordinate to artifact bytes under a specified encoding and integrity scheme. A digest does not establish their meaning, origin, admissibility, availability, or authority. Canonicalization and the relevant integrity assumptions must be explicit.

### Causal ordering and resolution

```math
\tau_a\prec\tau_b
\iff
\tau_a\in\mathrm{Ancestors}(\tau_b)
```

`Ancestors` is the transitive closure of the predecessor relation. It must be acyclic. Coordinates on independent branches may be incomparable: the model defines a **partial causal order**, not a universal sequence. A higher version number or later wall-clock timestamp does not establish causal descent.

```math
R:C\rightharpoonup\Sigma,\qquad
\mathrm{Resolve}(\tau)=\sigma_{\tau},\qquad
G_{\tau}=\mathrm{Geometry}(\sigma_{\tau}).
```

`Resolve` implements $R$; `Geometry` selects the geometry from a descriptor when the modeled entity is an agent geometry. Entity identity is already contained in the coordinate. An API that accepts it separately must verify that the identities agree.

Resolution is partial because an artifact or required binding may be absent or unresolved. It must report that condition explicitly rather than substitute a mutable “latest” version. Successful qualified resolution requires the exact descriptor and the material artifact closure promised by the declared scope, not merely a matching label.

## Core properties and required obligations

| Property | Obligation |
| --- | --- |
| **Identity** | Entity, branch, and version namespaces MUST prevent ambiguous bindings within the covered system. |
| **Causality** | Predecessor and material dependency relationships MUST preserve actual modeled derivation; recording an edge alone does not prove it. |
| **Immutability** | A published coordinate MUST NOT silently acquire different meaning, artifacts, or predecessors. Corrections create new versions with explicit relationships. |
| **Resolution** | Each covered execution unit MUST bind its exact immutable semantic definition. Missing or conflicting resolution MUST prevent dependent consequential execution. |
| **Branching** | Independent branches MAY coexist without an invented total order. Their identities and dependency relationships MUST remain distinguishable. |
| **Continuity** | Claimed constitutive lineage MUST be independently verifiable under declared transformation and continuity rules. Common ancestry alone is insufficient. |
| **Reconstruction** | Claims of historical interpretation MUST be backed by retained descriptors, artifacts, state, and evidence sufficient for the claimed scope and retention period. |

These are conformance requirements, not guarantees created by naming a data structure. The model may record proposals and unadmitted branches; recording them must not be confused with certifying their lineage or authorizing their use.

### Required semantic-binding invariant

> **Every covered consequential transition must bind an exact, immutable semantic definition with independently verifiable constitutive lineage.**

For a mechanism $M$, let $X(M,\Omega)$ contain every consequential execution unit in the declared coverage, including failed admissions that nevertheless produce an effect and any bypass routes:

```math
\begin{aligned}
&\forall x\in X(M,\Omega),\;
\exists\tau\in C,\;\sigma\in\Sigma:\\
&\quad\mathrm{Bindings}(x)=\{\tau\}\\
&\qquad\land R(\tau)=\sigma\\
&\qquad\land\mathrm{ActualDefinition}(x)=\sigma\\
&\qquad\land\mathrm{LineageEstablished}(\tau).
\end{aligned}
```

`Bindings` identifies the coordinates bound to execution; the singleton excludes missing or ambiguous bindings. `ActualDefinition` requires correspondence to the definition actually used, including material interpreter and dependency semantics. `LineageEstablished` requires independently checkable evidence of origin and admissible transformations under the declared continuity rules, not an executable's self-description.

The formula assumes the model's immutable-resolution obligations. It does not prove them, establish current effect authority, or guarantee that an implementation conforms. A compound interaction may contain several explicitly bound units, or one immutable manifest identifying its component definitions. Changing a material definition requires a new binding and applicable qualification.

## Branching, merging, and change

A branch preserves a declared relationship to its predecessors while allowing independent evolution. Two branches may share ancestry without preserving identical behavior, identity criteria, or permission.

A merge creates a **new coordinate**, records all material parents, and defines how conflicting semantics, state, constraints, and inherited obligations are reconciled. Listing two parents is not a merge rule. Unresolved conflicts remain explicit and prevent uses that depend on their resolution.

Version creation, lineage verification, and authorized promotion are distinct events. A candidate geometry cannot establish its own promotion authority by changing the rules used to assess it. Previously applicable amendment and delegation rules govern that decision.

Historical corrections likewise add a new record rather than silently rewriting the original. Retention or deletion policies must state which reconstruction claims remain supportable; a surviving hash cannot recover an unavailable artifact.

## Transaction binding and reconstruction

A transaction record should identify its execution units and bind:

- The semantic coordinate and exact descriptor, including executable and interpretation versions.
- Actual input and state versions, material dependency snapshots, and relevant external observations.
- Outputs, state transitions, proposed intents, actual effects, and evidence locating their commitment.
- The governing versions and commitment evidence required by Temporal Standing, separately from the semantic coordinate.

Distinguish three claims:

| Claim | Required basis |
| --- | --- |
| **Semantic reconstruction** | Recover the exact definition and recorded context needed to interpret the historical transition. |
| **Deterministic replay** | Additionally control or capture relevant nondeterminism, model/runtime behavior, external responses, and execution conditions. |
| **Renewed execution** | Independently establish current standing for any new protected effects; historical grants are insufficient. |

The coordinate alone contains neither the entire transaction state nor all these guarantees. Reconstructing a past definition must not refresh its dependencies silently or present a newly generated output as the original recorded result.

## Semantic Time and Temporal Standing

| Dimension | Semantic Time | Temporal Standing |
| --- | --- | --- |
| Architectural role | A model of semantic identity, versions, and causal relationships. | An invariant of valid standing at actual effect commitment. |
| Primary question | Which exact meaning was bound to this transition? | May this exact consequence commit under applicable conditions? |
| Historical version | Preserves its identity and interpretation within the retention scope. | May remain applicable or become ineligible under governing rules. |
| Ordering | Captures causal ancestry; independent branches can be incomparable. | Requires enforceable ordering between affected commitments and standing-changing events. |
| Failure | Unresolved meaning cannot support a qualified dependent execution. | Unresolved current standing prevents protected commitment. |

A causal record does not itself enforce revocation. A transaction may resolve perfectly to an old geometry while its former grant has expired. Conversely, publication of a newer geometry need not invalidate an older one that remains authorized.

Wall-clock time remains relevant for deadlines, expiry, latency, and recording. Semantic version, physical time, and governing effective time are separate coordinates. Where they interact, the implementation must specify the mapping and enforce the applicable ordering and clock assumptions.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual model specification; constructing it proves no lineage or binding.
public sealed class SemanticTime<TSemanticDefinition>
    : LogicalTemporalModel<TSemanticDefinition>
{
}
```

The specification carries coordinate and descriptor schemas, predecessor semantics, resolution rules, branching and merge rules, retention scope, trust assumptions, and required invariants.

A separate **Semantic Time Conformance Argument** establishes immutable resolution, valid lineage, and execution correspondence for the claimed model and deployment. It binds exact versions and evidence. Checks should expose conflicting version publication, missing artifacts, cycles, ambiguous bindings, undeclared dependency changes, and silent substitution. Successful examples alone do not establish preservation across every covered transition or failure.

## Relationship to the existing architecture

| Concept | Relationship to Semantic Time |
| --- | --- |
| [Generative Root Geometry](../../invariants/generative-root-geometry/README.md) | Supplies a framework for differentiation and continuity; Semantic Time identifies versions and records the causal relationships whose validity must be established. |
| [Constraint-Governed Agency](../constraint-governed-agency/README.md) | Can use semantic coordinates to instantiate exact agent geometries while processes start, stop, and change. Persistent identity additionally requires explicit continuity criteria. |
| [Temporal Standing](../../invariants/temporal-standing/README.md) | Qualifies exact semantic bindings against current applicability, authority, dependencies, and enforced commitment ordering. |
| [Structural Standing](../../invariants/structural-standing/README.md) | Requires actual eligibility and support for enabled effects; precise version identity supplies context for that argument, not its enforcement. |
| [Boolean Standing Fallacy](../../anti-patterns/Boolean-Standing-Fallacy.md) | A successful resolution flag, digest match, or lineage assertion cannot constitute authority to produce a consequence. |

## Examples

| Situation | Model interpretation |
| --- | --- |
| Two branches evolve from the same geometry without depending on each other | Their versions are causally incomparable; a later merge has both as ancestors without changing their earlier relationship. |
| A registry returns different executable bytes for the same entity, branch, and version | Immutable resolution is violated; the conflict cannot be treated as an ordinary update. |
| A merge names both parents but omits how conflicting constraints are reconciled | Ancestry is recorded, but a usable merged semantic definition is not yet established. |
| An archived transaction resolves correctly after its authority was revoked | Historical interpretation can remain valid; a new protected effect still requires current standing. |
| A coordinate survives but its model weights or interpreter artifact are unavailable | Identification may remain possible; full reconstruction is unsupported. |

## Scope and limits

Semantic Time does not require a universal clock, a globally linear history, continuously running agents, or any particular storage technology. Its relationships are relative to the declared computational model; undeclared external causes cannot be assumed covered.

An immutable record can preserve an error or an unauthorized proposal. Hashes and signatures can support integrity and attribution under their assumptions, but do not independently establish semantic correctness, legitimate lineage, or current authority. Formal claims require separately justified evidence and correspondence to actual execution.

## Governing principle

> **Chronological time locates events in physical time. Semantic Time locates computation within an identified lineage of meaning.**

**The coordinate identifies the definition. The lineage explains its derivation. Independent standing governs its consequences.**

---

© 2026 Beau Crawford
