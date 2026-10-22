# <img src="../../assets/signatures/constraint-geometry.svg" alt="" width="32" height="32"> Constraint Geometry

*An executable behavioral model that shapes computational potentiality into a defined space of admissible behavior.*

> **Geometry defines admissible behavior. Enforcement makes it binding. Independent standing governs consequence.**

![](./images/Shape-of-Possibility.png)

## Definition

**Constraint Geometry (CG)** is a semantically defined, executable specification of the states, relationships, transitions, constraints, objectives, capabilities, and effect boundaries through which a computational system may operate.

Its dimensions define what can be represented. Its transition structure defines possible modeled changes. Constraints specify admissibility. Objectives influence which admissible trajectories are preferred. Effect definitions identify consequential operations, and authority-boundary bindings specify where independently established standing is required.

**Constraint Geometry belongs under Models.** More precisely, it is an executable behavioral specification whose instances are immutable semantic artifacts. An invariant is a property required to hold across the states, transitions, or executions of that model. The geometry can contain invariant definitions without itself being an invariant.

Each published geometry has an unambiguous identity and resolves through a [Semantic Time](../semantic-time/README.md) coordinate. [Exact Semantic Binding](../../invariants/exact-semantic-binding/README.md) requires actual execution to use that resolved definition. “Executable” requires defined interpretation, compilation, and runtime semantics; a document, prompt, or collection of predicates does not establish enforcement merely by declaring constraints.

The geometry defines computational structure. Actual operational state, a runtime instance, an intelligence model, and an agent's durable identity are separate entities. Their material bindings must be explicit wherever they affect execution or its consequences.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | The bounded structure through which computational capability can be expressed as behavior. |
| Model | **Yes.** An executable behavioral model with explicit state, transition, constraint, and effect semantics. |
| Foundational primitive | No. It composes more basic concepts such as state, relation, transition, constraint, effect, and scope. |
| Invariant | **No.** Exact binding, admissibility, continuity, and authority independence are required properties of its use. |
| Semantic type | `ExecutableBehaviorSpecification`, instantiated as an immutable geometry definition. |
| Mathematical structure | A versioned transition model with state and trace constraints, objectives, effect definitions, and governing bindings. |
| Verification obligation | Establish semantic consistency, conformance to independently constituted governing rules, and correspondence between the specification and actual execution. |
| Proof artifact | A version-bound Geometry Conformance Argument, with separate lineage and standing evidence where required. |
| Runtime relevance | The definition remains fixed while operational state, environmental facts, and current standing may change. |

## Architectural components

These are components of the specification, rather than a new set of foundational primitives.

| Component | Meaning |
| --- | --- |
| **Dimensions** | Types and domains for variables, inputs, context, state, and material relationships. They need not be numerical coordinates. |
| **Topology** | Relationships and possible reachability induced by the transition structure, including dependencies and effect routes. |
| **Constraints** | State, transition, and trace obligations defining admissible behavior; mandatory constraints remain distinct from preferences. |
| **Objectives** | Goals, priorities, or optimization criteria that influence choices within admissible behavior. |
| **Transitions** | Defined state changes, with input, observation, concurrency, failure, and effect semantics where material. |
| **Effects** | Declared operations and parameter schemas capable of producing consequential observations or changes. |
| **Authority boundaries** | Bindings to governing contracts and actual enforcement points; they identify obligations without granting authority. |
| **Continuity** | Version identity, provenance, material dependencies, and the relationships required for claimed constitutive lineage. |

“Geometry” and “topology” describe computational structure here. No Euclidean space, metric, or physical field is assumed. Objectives may be described metaphorically as **attractors**, but an objective function alone does not establish a dynamical attractor or guarantee convergence.

## Formal identity

- **Identifier:** `CONSTRAINT_GEOMETRY_EXECUTABLE_BEHAVIOR_MODEL`
- **Type:** `ExecutableBehaviorSpecification`
- **Abbreviation:** `CG`

At an immutable semantic-time coordinate $\tau$:

```math
G_{\tau}=\langle S,T,C,O,E,A,D\rangle
```

| Symbol | Meaning |
| --- | --- |
| $S$ | The state space, including schemas for relevant context and relationships. An actual state $s\in S$ is an execution value, not the geometry itself. |
| $T$ | The modeled transition relation, including material inputs, observations, successor states, and effect descriptions. |
| $C$ | The specified state, transition, and trace constraints, with defined interpretation and verification obligations. |
| $O$ | Objectives, priorities, and selection criteria. These do not override mandatory constraints or confer effect authority. |
| $E$ | Effect definitions: operation meanings, targets and parameter types, observable consequences, and commitment semantics. |
| $A$ | References to governing contracts, delegation requirements, and enforcement boundaries. Actual grants and current standing are established separately. |
| $D$ | Constitutive dependencies, provenance, lineage, interpretation and executable-artifact bindings, and relevant trust assumptions. |
| $\tau$ | The immutable coordinate identifying this exact definition within its entity and lineage. |

The tuple is a schema for specifying meaning, not evidence that the meaning is correct or enforced. Protected-effect scope, governing applicability, and continuity criteria must come from independently established rules rather than the candidate geometry's self-description.

### Local admissibility

For a modeled transition $t$ and bound evaluation context $\kappa$, its local constraints can define:

```math
T^{\mathrm{adm}}_{\tau}(\kappa)
=\left\{t\in T_{\tau}\;\middle|\;
C^{\mathrm{step}}_{\tau}(t,\kappa)\right\}.
```

$C^{\mathrm{step}}$ denotes the transition-level part of $C$. The context binds the material inputs, observations, dependency versions, and governing facts used by that evaluation. State and trace invariants, aggregate limits, and continuing effects may impose obligations beyond a local predicate.

This defines **model-level admissibility**. A proof that an implementation always produces admissible behavior is a separate obligation. A local check also cannot establish current authority for a later effect without the applicability and ordering required at commitment.

### Execution conformance

[Semantic Conformance](../../invariants/semantic-conformance/README.md) supplies the canonical preservation obligation: the executable geometry must conform to the independently specified governing contract, and actual execution must conform to the geometry. Both interpretations must cover every material transition and effect without filtering out violations or bypass paths.

A qualification may cover one captured request or a broader execution scope; its evidence must state which. Multi-version systems qualify each exact binding and separately verify interactions, migration, and shared obligations. Progress and useful-service claims need evidence beyond safety conformance.

Geometry conformance does not establish the legitimacy of its governing rules. A perfectly enforced but unauthorized definition still lacks standing to govern a protected consequence.

## From definition to consequential execution

```text
IMMUTABLE GEOMETRY
  State and transition semantics · Constraints · Objectives
    ↓ interpreted through bound artifacts and dependencies
EXECUTION INSTANCE
  Exact version · Actual inputs · Operational state
    ↓ constrained selection and state evolution
PROPOSED EFFECT
  Exact operation · Actor · Target · Parameters
    ↓ independent qualification at the actual boundary
PROTECTED COMMITMENT
  Current standing · Enforced ordering · Durable evidence
```

A language model, planner, or other generator may suggest a transition or effect. Its output is a proposal until the applicable mechanism establishes admissibility and standing. A prompt requesting compliance is behavioral guidance; any claimed prohibition additionally needs enforcement over every covered route.

Material model versions, interpreter semantics, tool contracts, and context-construction rules belong in the definition or its explicit dependencies. Actual input values, memory contents, observations, and nondeterministic choices belong in the execution binding and history. Updating a definition requires a new geometry version; ordinary state evolution follows the bound version's transition rules.

If a material assumption becomes false, prior qualification cannot silently carry forward. The mechanism must prevent dependent protected effects or establish a valid new qualification. Defining an effect in $E$ does not supply the capability or authority to perform it.

## Required invariant kernel

> **Every covered realized transition must conform to its exact governing geometry, and every protected consequence must possess independently established current standing at commitment.**

| Invariant ID | Obligation |
| --- | --- |
| `CG_PUBLISHED_MEANING_IS_IMMUTABLE` | A published coordinate MUST resolve to one exact definition and artifact binding. Material semantic changes require a new version. |
| `CG_EXECUTION_HAS_AN_EXACT_BINDING` | Each covered execution unit MUST bind one immutable geometry or explicit component manifest. Missing or ambiguous resolution prevents dependent execution. |
| `CG_ACTUAL_BEHAVIOR_CONFORMS` | Realized transitions and effects MUST satisfy the applicable semantics and constraints; every claimed route requires justified model correspondence. |
| `CG_OBJECTIVES_RESPECT_MANDATORY_CONSTRAINTS` | Optimization and selection MUST operate within the admissible set. A favorable score cannot compensate for violating a mandatory obligation. |
| `CG_EFFECTS_REQUIRE_INDEPENDENT_STANDING` | Effect scope, governing authority, eligibility, and required support MUST be independently established at actual commitment, with enforced ordering of relevant changes. |
| `CG_CONTINUITY_CLAIMS_REQUIRE_EVIDENCE` | Successors claimed as legitimate continuations MUST preserve the required constitutive relationships and obligations under independently specified rules. |
| `CG_GEOMETRY_CANNOT_SELF_AUTHORIZE` | A geometry MUST NOT independently authorize its own promotion, expand its grants, or replace the rules judging its admission. |
| `CG_COMPOSITION_PRESERVES_OBLIGATIONS` | Interacting geometries, shared resources, migration, and delegated effects MUST satisfy their joint obligations; separate local checks are insufficient. |

Exact binding is sometimes described as **geometric determinacy**. It identifies the governing definition; it does not imply one possible trajectory or identical outputs. Nondeterministic behavior can be admissible when all permitted outcomes satisfy the required constraints.

Identity independence is an architectural distinction. Recursive evolution is an optional capability. Neither is, by itself, a safety invariant requiring every geometry to preserve an agent identity or generate a successor.

## Identity, continuity, and evolution

A geometry's immutable version identity differs from an agent's durable logical identity. A changed geometry can remain associated with the same agent only where independently defined continuity criteria hold. The geometry's current state, runtime process, and referenced intelligence model do not settle that question.

Under [Recursive Geometry Evolution](../recursive-geometry-evolution/README.md), an execution may propose successor definitions. A candidate receives a new coordinate, records material parents and transformations, and undergoes independent verification and authorization before promotion. Branches and merges require explicit identity, reconciliation, and migration semantics.

Continuity does not require every policy value or behavior to remain unchanged. Authorized amendments follow previously applicable governance while preserving the required obligations. A candidate cannot make an otherwise invalid transformation legitimate by relaxing its own admission criteria.

Under [Semantic-Temporal Agent Geometry](../semantic-temporal-agent-geometry/README.md), a qualified geometry is instantiated for a transaction and its exact use is recorded. Promotion affects qualified future work; it cannot silently change the definition of an execution already in progress. Older versions may remain applicable, but historical qualification never guarantees current standing.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual executable specification; construction does not prove conformance.
public sealed class ConstraintGeometry<TState, TTransition, TConsequence>
    : ExecutableBehaviorSpecification<TState, TTransition, TConsequence>
{
}
```

The specification carries exact semantic and executable bindings, state and transition schemas, constraints, objectives, effect definitions, governing references, and constitutive dependencies. It remains distinct from an execution instance containing actual inputs, state, observations, and results.

A separate **Geometry Conformance Argument** establishes the properties claimed for the model and its implementation. It must bind exact artifacts, the interpretation or compilation path, governing sources, effect coverage, assumptions, and independently checkable evidence. A proof against an executable's own invented contract cannot establish conformity to independently constituted governance.

Lineage evidence establishes the relevant derivation. Standing evidence qualifies particular consequences. Neither a geometry object, a successful predicate, nor a cryptographic receipt establishes all three claims at once.

## Relationship to the existing architecture

| Concept | Relationship to Constraint Geometry |
| --- | --- |
| [Constitutive Continuity](../../invariants/constitutive-continuity/README.md) | Specifies preservation of the required kernel and relationships when a successor claims legitimate continuity. |
| [Constraint-Governed Agency](../constraint-governed-agency/README.md) | Organizes generative capability and enforcement around agent configurations; CG specifies their executable behavioral semantics. |
| [Semantic Time](../semantic-time/README.md) | Identifies exact geometry versions and causal lineage without independently granting execution authority. |
| [Recursive Geometry Evolution](../recursive-geometry-evolution/README.md) | Governs the proposal, qualification, and promotion of successor geometries. |
| [Semantic-Temporal Agent Geometry](../semantic-temporal-agent-geometry/README.md) | Integrates geometry versions with persistent identity, temporary execution, and linked histories. |
| [Generative Root Geometry](../generative-root-geometry/README.md) | Supplies a framework for differentiation and constitutive continuity; a particular CG is an executable behavioral specification. |
| [Governing Root Geometry](../governing-root-geometry/README.md) | Supplies independently constituted semantic obligations to which an admitted geometry must conform. |
| [Structural Standing](../../invariants/structural-standing/README.md) and [Temporal Standing](../../invariants/temporal-standing/README.md) | Require actual eligibility, support, and current authority at protected effect boundaries across changing conditions. |
| [Topological Zero](../../invariants/topological-zero/README.md) | Establishes mandatory mediation across all covered consequential routes; drawing a boundary in a geometry does not establish this coverage. |
| [Structural Zero](../../invariants/structural-zero/README.md) | States that a specified consequence is unreachable within the declared model and scope. It is a property evaluated over geometry and mechanism semantics. |
| [Boolean Standing Fallacy](../../anti-patterns/Boolean-Standing-Fallacy.md) | Identifies the error of treating a geometry's own approval as sufficient proof of governing authority. |

## Examples

| Situation | Constraint Geometry assessment |
| --- | --- |
| A document-processing geometry restricts writes to a declared workspace | The restriction has defined meaning; actual enforcement must also cover tools, delegated workers, and alternate write paths. |
| An optimizer finds a faster trajectory that violates a required output constraint | The trajectory remains inadmissible regardless of its score. |
| A memory value changes through a permitted transition | Operational state evolves; the immutable geometry need not change. |
| The memory schema or interpretation of a transition changes | The definition changes and requires a new version and applicable qualification. |
| Two agents instantiate the same geometry with different input and state | Shared computational structure does not imply identical output, identity, or authority. |
| An effect is geometrically admissible, but its grant expires before commitment | The effect lacks current standing and must be prevented while that condition applies. |
| A candidate removes a constraint and reports that its own checks pass | Its report cannot establish independently governed admissibility or authorize promotion. |

## Scope and limits

Constraint Geometry can describe systems beyond autonomous agents. It does not require a particular model provider, programming language, runtime duration, or storage system. “Potentiality” refers to available computational possibilities within the declared model and assumptions.

Declaring a constraint does not make it decidable, prove it consistent, or provide an enforcement mechanism. Unsupported verification obligations remain explicit. Contradictory constraints or a system that disables all effects may satisfy some safety claims vacuously; useful operation requires separate feasibility and progress evidence.

An immutable definition may still be incorrect, incomplete, or unauthorized. Governing legitimacy, semantic conformance, route coverage, and actual execution must remain connected through independent evidence and enforcement.

## Governing principle

> **The field provides potentiality. Geometry defines admissible behavior. Semantic time identifies meaning across change. Independent standing governs consequence.**

**The geometry specifies the computational structure. Its realized behavior requires conformance; its protected consequences require authority.**

---

© 2026 Beau Crawford
