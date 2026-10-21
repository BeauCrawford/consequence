# Structural Standing

*A derived invariant of consequential eligibility enforcement: no covered protected effect is enabled without its applicable requirements holding.*

> **Standing is structural when the mechanism makes eligibility and required decision support necessary conditions of every covered protected effect—not merely conclusions returned by an assessor.**

<!-- Optional hero image: ![](./images/structural-standing.png) -->

## Definition

**Structural Standing** is a first-class, derived **standing-enforcement invariant** stating that **every mechanically enabled protected effect, across every covered consequential route, depends on actual eligibility and sufficient decision support for its exact occurrence and governing boundary**.

This is an **architecture-level property of the mechanism**, not a Boolean attribute that an actor or request can award itself. An occurrence's substantive eligibility, the evidence supporting its admission, and the architecture's ability to enforce those prerequisites are separate questions.

The **Governing Root Geometry** supplies the authoritative meanings of admissibility, constraints, transitions, effects, and obligations. A reachable-state and effect-capability model describes the mechanisms that could actually produce a consequence. Structural Standing requires those mechanisms to make the applicable obligations necessary before the effect becomes enabled.

A correct decision on one request does not establish Structural Standing. The claim must cover materially equivalent routes, including direct writes, administrators, receivers, queued work, retries, delegated capabilities, recovery, and authorized changes to law or capability topology.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | A meaningful property of how consequential eligibility is enforced by a mechanism. |
| Foundational primitive | No. It depends on contract, state, eligibility, evidence, transition, effect, boundary, and scope. |
| Semantic type | A specialization of `StandingEnforcementInvariant`. |
| Mathematical property | Every covered enabled protected-effect transition requires actual eligibility and adequate decision support. |
| Verification obligation | Complete route coverage, sound evidence and rule binding, commit-time preservation, and model-to-deployment correspondence MUST be established. |
| Proof artifact | A separately certified, version-bound, independently checkable standing-enforcement proof or witness. |
| Runtime property | Applicable only while actual effect paths, deployed enforcement, governing rules, and environment assumptions satisfy the verified model. |

```text
GOVERNING ROOT GEOMETRY
  Defines eligibility, constraints, evidence, and permitted effects
    ↓
FOUNDATIONAL PRIMITIVES
  Contract · State · Transition · Effect · Evidence · Boundary · Scope
    ↓
REACHABLE STATE / CONSEQUENCE MODEL
  All covered conditions and routes that can enable protected effects
    ↓
STRUCTURAL STANDING
  Derived invariant: every enabled effect requires valid eligibility
  and sufficient support at its exact consequential boundary
    ↓
VERIFIED ENFORCEMENT PROOF / CERTIFICATE
  Independently checkable evidence bound to rules, routes, and versions

With a horizon-wide preservation argument:
    ↓
STRUCTURAL ZERO FOR INELIGIBLE EFFECTS
  No covered continuation can produce an ineligible protected effect
```

## Formal identity

- **Identifier:** `STRUCTURAL_STANDING_ENABLED_EFFECTS_REQUIRE_ELIGIBILITY_AND_SUPPORT`
- **Type:** `StandingEnforcementInvariant`

Using the underlying mechanism-model notation:

```math
\boxed{
\begin{aligned}
&H(M,\Omega)\\
&\quad\equiv\forall s\in\mathrm{Reach}(M,\Omega),\;\forall q\in\mathrm{Scope}(\Omega):\\
&\qquad E_q(M,s)\neq\varnothing
\Rightarrow\bigl(Q_q(s)\land D_q(e_s)\bigr).
\end{aligned}
}
```

Equivalently, for any covered reachable state:

```math
\boxed{
H(M,\Omega)\land\bigl(\neg Q_q(s)\lor\neg D_q(e_s)\bigr)
\Rightarrow E_q(M,s)=\varnothing.
}
```

| Symbol | Meaning |
| --- | --- |
| $M$ | The mechanism model, including actual effect transitions, relevant capabilities, and their evolution. |
| $\Omega$ | Declared initial conditions, effect scope, environment behavior, failure assumptions, governing applicability rules, and horizon where one is claimed. |
| $\mathrm{Reach}(M,\Omega)$ | Every reachable mechanism state within the declared scope and assumptions. |
| $q$ | An exact consequential occurrence: subject, protected effect, applicable boundary, and material parameters. |
| $E_q(M,s)$ | The set of *mechanically enabled* protected-effect transitions for $q$ from state $s$, not merely returned decisions. |
| $Q_q(s)$ | Actual eligibility under the contract applicable to that occurrence and state. |
| $D_q(e_s)$ | Sufficient decision support for the exact occurrence, evaluated using evidence and source assumptions applicable at $s$. |
| $e_s$ | The evidence and decision-support basis relevant to the occurrence at state $s$. |
| $H(M,\Omega)$ | The Structural Standing property over the entire declared reachable mechanism. |

The implication is **one-way**: eligible and adequately supported effects can still be unavailable because of resource, scheduling, or additional execution constraints. Structural Standing is a **safety property**, not a guarantee of execution or progress.

The state-predicate form is appropriate when the required effect parameters and obligations are represented by $Q_q(s)$ and $D_q(e_s)$. **Successor-dependent requirements and atomic multi-effect transitions** also require checking the complete transition and its joint obligations; a simplified predicate must not erase them.

## Minimal invariant kernel

| # | Invariant ID | Obligation |
| --- | --- | --- |
| 1 | `STRUCTURAL_STANDING_PROTECTED_OCCURRENCE_IS_EXPLICIT` | The exact consequence, subject, effect parameters, and consequential boundary MUST be identified independently of the claimed authorization result. |
| 2 | `STRUCTURAL_STANDING_GOVERNING_CONTRACT_IS_AUTHENTIC` | Applicable rules, authorized versions, requirements, and amendment authority MUST be established rather than inferred from an implementation's assertions. |
| 3 | `STRUCTURAL_STANDING_SCOPE_AND_REACHABILITY_ARE_DEFINED` | Covered initial states, effects, environment and failure assumptions, trust dependencies, and claimed horizon MUST be declared. |
| 4 | `STRUCTURAL_STANDING_ALL_EFFECT_ROUTES_ARE_COVERED` | Every materially equivalent in-scope route capable of producing the effect MUST be included, including administrative, asynchronous, recovery, and delegated routes. |
| 5 | `STRUCTURAL_STANDING_ENABLED_EFFECTS_REQUIRE_ELIGIBILITY_AND_SUPPORT` | No covered protected effect MAY be mechanically enabled unless its exact applicable contractual eligibility holds. |
| 6 | `STRUCTURAL_STANDING_REQUIRED_SUPPORT_IS_ESTABLISHED` | Every required decision-support obligation MUST be satisfied by appropriately verified evidence; caller assertions and receipt signatures alone MUST NOT establish factual truth. |
| 7 | `STRUCTURAL_STANDING_AUTHORIZATION_BINDS_EXACT_OCCURRENCE` | Eligibility and decision support MUST bind the actual actor, target, parameters, resource quantities, transition, and consequence; substitution MUST require new qualification. |
| 8 | `STRUCTURAL_STANDING_ELIGIBILITY_SURVIVES_TO_EFFECT` | Concurrency, revocation, expiry, delivery, retries, and state changes MUST NOT enable an effect after its required conditions cease to hold. |
| 9 | `STRUCTURAL_STANDING_COMPOSITE_EFFECTS_PRESERVE_SHARED_OBLIGATIONS` | Joint effects and shared resources MUST preserve aggregate constraints through valid ordering or atomic allocation; independent local checks MUST NOT substitute. |
| 10 | `STRUCTURAL_STANDING_GOVERNANCE_CHANGES_REQUIRE_PRIOR_AUTHORITY` | Changes to contracts, capabilities, and enforcement MUST be admitted under previously governing rules and MUST account for existing workers and in-flight effects. |
| 11 | `STRUCTURAL_STANDING_IMPLEMENTATION_PRESERVES_MODEL` | The proof MUST account for actual deployed effect paths, permissions, configuration, external actors, and failures; model-only safety MUST NOT be presented as runtime safety. |
| 12 | `STRUCTURAL_STANDING_PROOF_IS_INDEPENDENTLY_CHECKABLE` | Claims of enforcement MUST bind scope, rules, evidence assumptions, versions, and an independently checkable proof or adequately justified verification argument. |
| 13 | `STRUCTURAL_STANDING_CHANGES_REQUIRE_REQUALIFICATION` | Uncovered material changes to facts, dependencies, code, effect routes, policies, or assumptions MUST reopen the affected standing claims. |

These thirteen obligations specify **how a system establishes Structural Standing**. Their satisfaction is a proof obligation, not a property bestowed by naming a policy, compiling a rule, returning `ADMIT`, or signing a receipt.

A permanently disabled system may satisfy the formal implication **vacuously**. A useful-service claim additionally needs a feasible eligible operation and a separate progress argument; blanket prevention cannot be marketed as successful governance of productive effects.

## Semantic type and proof artifact

```csharp
// Conceptual specialization; a claim object is not its own proof.
public sealed class StructuralStanding<TConsequence>
    : StandingEnforcementInvariant<TConsequence>
{
}
```

A Structural Standing claim identifies the governed contract and version; protected occurrence class; applicable eligibility and evidence obligations; reachable-state and effect-route model; scope and environment assumptions; commit-time preservation conditions; and verification obligations.

A separate **Structural Standing Proof** certifies that mechanically enabled effect transitions imply the corresponding eligibility and decision support across the covered reachable states. The certificate must bind these facts to exact model, dependency, and deployment versions and to independently checkable evidence.

Proving a model does **not** prove a deployment. Applying the guarantee to an actual system requires a justified, effect-preserving model-to-implementation correspondence, including authoritative fact sources, configured credentials and permissions, privileged write paths, concurrency behavior, and external effects.

## Relationship to Procedural Standing

**Procedural Standing** concerns an assessment or determination. **Structural Standing** concerns whether the actual mechanism enforces the assessed obligations at **every covered effect boundary**.

| Dimension | Procedural Standing | Structural Standing |
| --- | --- | --- |
| Question | Did an assessment establish a qualifying basis for this request? | Can any covered effect be enabled without the applicable requirements holding? |
| Object | Individual evaluation, finding, or decision. | Reachable behavior of the effect-producing mechanism. |
| Evidence | A decision record and its warranted basis. | Complete coverage and preservation of enabling conditions. |
| Failure example | An assessor accepts false evidence. | A bypass or stale receiver enables the effect despite invalid eligibility. |

A runtime evaluator, compiled predicate, or human approval may participate in enforcement, but **none constitutes Structural Standing on its own**. An authentically signed decision proves only what its evidence and trusted checks actually warrant; it does not establish all underlying facts or close unrelated paths.

## Relationship to Topological Zero and Structural Zero

These are **distinct first-class derived invariants**. They address different questions about the same consequential mechanism.

| Dimension | Structural Standing | Topological Zero | Structural Zero |
| --- | --- | --- | --- |
| **Question** | Does every enabled effect satisfy its actual eligibility and support obligations? | Can any protected effect path bypass independently governed enforcement? | Can this specified consequence occur at all? |
| **Formal focus** | $E_q\neq\varnothing\Rightarrow Q_q\land D_q$. | $\mathrm{Occurs}(q)\Rightarrow\mathrm{EffectMediated}_B(q)$. | $\forall\tau:\neg\mathrm{Occurs}(q,\tau)$. |
| **Property class** | `StandingEnforcementInvariant`. | `PathMediationInvariant`. | `ReachabilityInvariant`. |
| **What it rules out** | Enabled effects lacking their governing eligibility/support. | Unmediated ways of producing a protected effect. | All occurrences of the specifically prohibited effect. |
| **Authorized effects** | May remain enabled if obligations hold. | May remain reachable through the governed boundary. | Unreachable only if they are the specified excluded consequence. |
| **Does not establish alone** | Availability, progress, or a single exclusive custody topology. | Correctness of standing, evidence, or governing law. | The cause of unreachability or that governance is functioning. |

### Composition — from enforced standing to consequence unreachability

Define $q_{\mathrm{invalid}}$ as the event **a protected effect actually occurs when its applicable eligibility or required decision support does not hold**.

Under a model and deployment whose effect semantics, route coverage, and preservation assumptions have been independently justified:

```math
\boxed{
\mathrm{StructuralStanding}(M,\Omega)
\Longrightarrow
\mathrm{StructuralZero}(q_{\mathrm{invalid}},M,\Omega).
}
```

This is **Structural Zero for invalid effects**, not Structural Zero for every protected effect. Valid, authorized effects can still occur. A state-local failure of eligibility provides only *immediate disablement*; to claim zero for a fixed consequence across a future horizon, establish that all covered future continuations also exclude it.

**Topological Zero** can contribute the separate proof that no covered consequence path escapes independently governed enforcement. With independent verification that every such enforcement mechanism correctly evaluates the exact eligibility and required support, and that authorization remains valid at effect time, the two properties can be composed.

Neither property should be silently inferred from the other: **complete mediation can route every request through a verifier that accepts false premises**, while Structural Standing might arise from enforceable constraints distributed throughout the mechanism rather than a single custodial checkpoint. Both guarantees still require independently verified scope and model-to-deployment correspondence.

**Constitutive Authority Closure** demands the larger end-to-end continuity: authenticated governing meaning, independently established standing, preserved execution semantics, and effectively governed protected effects. No decision or receipt can supply a missing link in that chain.

### Examples

| System condition | Structural Standing | Related implication |
| --- | --- | --- |
| One API checks eligibility, but an administrator can directly modify the protected resource | **False** for the combined scope. | The bypass also defeats Topological Zero if it avoids required mediation. |
| Every path passes an independent checkpoint, but it accepts caller-supplied `standing_active=true` without verifying actual eligibility | **Not established**; **false** if an invalid effect becomes enabled. | Topological Zero may still hold as mediation, without sound standing. |
| Revocation occurs after dispatch, but an old receiver still executes using cached approval | **False** when the effect is enabled after applicable eligibility has ceased. | Sender-side refusal does not close the receiver's effect path. |
| Two concurrent effects each consume the last available authority unit | **False** if their combined execution violates a governing quantity constraint. | Per-request checks do not establish aggregate standing. |
| Every protected effect is disabled during a complete outage | **May hold vacuously**. | Structural Zero for the disabled effect may hold; useful governance and progress are unproven. |
| Every covered effect route enforces valid, current eligibility and required support with verified implementation correspondence | **Established**, assuming the proof obligations are discharged. | Invalid effects are structurally unreachable within the declared scope. |

## Essential distinctions

| Claim | What is established |
| --- | --- |
| `ASSESSMENT` | A particular evaluator produced a determination under its recorded premises. |
| `SUBSTANTIVE_STANDING` | Actual eligibility and required support hold for a specified occurrence. |
| `STRUCTURAL_STANDING` | Every covered enabled protected-effect transition necessarily satisfies its applicable eligibility and support obligations. |
| `TOPOLOGICAL_ZERO` | No covered consequence-producing path escapes effective, independently governed mediation. |
| `STRUCTURAL_ZERO` | No covered continuation produces the specified protected consequence throughout the declared scope and horizon. |
| `CONSTITUTIVE_AUTHORITY_CLOSURE` | Authentic law, legitimate standing, semantic execution, and actual consequence enforcement remain verifiably connected. |

A successful assessment is not proof of enforcement. A working gate is not proof of complete coverage. A correct current denial is not proof of future unreachability. **Structural Standing is established only when the real mechanism's covered effect transitions preserve the governing eligibility obligations.**

## Governing principle

> **Eligibility must not merely be evaluated; it must be a necessary condition of every covered protected consequence.**

**A decision can assert standing. Structural Standing requires the mechanism to enforce it.**
