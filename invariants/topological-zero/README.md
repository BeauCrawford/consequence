# <img src="../../assets/signatures/topological-zero.svg" alt="" width="32" height="32"> Topological Zero

*A derived invariant of complete consequence mediation: zero ungoverned paths to a protected effect.*

> **Zero is a topology:** not because no consequence was observed, but because no in-scope route can produce a protected consequence outside mandatory, independently governed enforcement.

![](./images/cut-set.png)

## Definition

**Topological Zero** is a first-class, derived **path-mediation invariant** stating that **every covered route capable of producing a specified protected consequence is necessarily mediated by an effective, independently governed enforcement boundary**, throughout a declared scope and horizon.

The **zero** is the set of **unmediated consequential paths**. It is **not** the set of all paths to the consequence: legitimately authorized effects may remain reachable through the governed boundary.

The [Governing Root Geometry](../../models/governing-root-geometry/README.md) supplies authoritative meaning and obligations. A state-space and capability-path model identifies which actors, resources, transitions, and effect capabilities can produce the consequence. Topological Zero establishes the structural enforcement coverage of those paths; **it does not by itself establish that the governing rules or an admission decision are correct**.

The claim must account for direct writes, alternate APIs, delegated credentials, administrative access, queued work, retries, old workers, recovery, external systems, and transitions that create or change capabilities. A missing route in an incomplete model does not establish zero.

Here, *topological* refers to the **graph structure of consequential reachability and its mandatory cut boundaries**, not to a topological space in the point-set mathematical sense.

## Architectural classification

| Aspect | Classification |
| --- | --- |
| Ontological concept | A meaningful property of the structure of consequential access. |
| Foundational primitive | No. It depends on state, transition, effect, capability, authority, boundary, and scope. |
| Semantic type | A specialization of `PathMediationInvariant`. |
| Mathematical property | Universal mediation of all covered effect-producing routes; absence of unmediated routes. |
| Verification obligation | Path coverage, effective enforcement, exclusive custody, and independence MUST be established, not inferred from passing tests. |
| Proof artifact | A separately certified, version-bound, independently checkable mediation or cut-set witness. |
| Runtime property | Applicable only while the deployed capability topology, effect semantics, and verified assumptions correspond to the model. |

```text
GOVERNING ROOT GEOMETRY
  Defines authoritative constraints, standing, and permitted effects
    ↓
FOUNDATIONAL PRIMITIVES
  State · Transition · Effect · Capability · Authority · Boundary · Scope
    ↓
CAPABILITY / CONSEQUENCE PATH MODEL
  All ways covered actors and processes could produce the effect
    ↓
TOPOLOGICAL ZERO
  Derived invariant: no protected-effect path bypasses effective enforcement
    ↓
VERIFIED MEDIATION PROOF / CERTIFICATE
  Independently checkable evidence of coverage, custody, and version binding

With independently verified, sound admission enforcement:
    ↓
STRUCTURAL ZERO FOR UNAUTHORIZED EFFECTS
  No covered continuation can produce the prohibited effect
```

## Formal identity

- **Identifier:** `TOPOLOGICAL_ZERO_NO_UNMEDIATED_PROTECTED_EFFECT_PATH`
- **Type:** `PathMediationInvariant`

```math
\begin{aligned}
&\mathrm{TopologicalZero}(q,M,S_0,\Omega,h,B)\\
&\quad\iff \forall s\in S_0,\; \forall\tau\in\mathrm{Cont}(M,s,\Omega,h):\\
&\qquad \mathrm{Occurs}(q,\tau)\Rightarrow
  \mathrm{EffectMediated}_{B}(q,\tau).
\end{aligned}
```

Equivalently, with $\mathrm{ProducingPaths}_q$ denoting the covered effect-producing causal paths:

```math
\boxed{
\{\pi\in\mathrm{ProducingPaths}_q:\neg\mathrm{EffectMediated}_{B}(q,\pi)\}
=\varnothing
}
```

| Symbol | Meaning |
| --- | --- |
| $q$ | The specified protected consequence, subject, and materially equivalent ways to produce it. |
| $M$ | The system's state-transition **and effective capability** model, including relevant changes to routes. |
| $S_0$ | The covered, nonempty set of initial states, including outstanding work and existing capabilities. |
| $\Omega$ | Declared effect boundary, sources, external behavior, failure assumptions, and trusted computing base. |
| $h$ | The declared transition-count or elapsed-time horizon; timed claims require a timed model. |
| $B$ | The independently governed enforcement mechanisms proven to control the relevant effect capabilities. |
| $\mathrm{Cont}(M,s,\Omega,h)$ | Every covered continuation from $s$ through the horizon, including capability changes and shorter terminated executions. |
| $\mathrm{Occurs}(q,\tau)$ | The protected consequence occurs anywhere in the continuation. |
| $\mathrm{EffectMediated}_{B}(q,\tau)$ | Every causal route realizing that occurrence necessarily crosses effective, non-bypassable custody controlling the **exact committed effect**, under the declared trust assumptions. |

**Mediation is stronger than seeing a checkpoint in an application diagram.** A boundary is effective only if the actual protected capability is inaccessible through alternative routes, and an authorized decision cannot be substituted, redirected, or reused for a different effect. Whether its *permission decision is semantically correct* is a separate obligation.

## Minimal invariant kernel

| # | Invariant ID | Obligation |
| --- | --- | --- |
| 1 | `TOPOLOGICAL_ZERO_PROTECTED_EFFECT_IS_EXPLICIT` | The exact protected consequence and materially equivalent effect mechanisms MUST be identified independently of the enforcement design. |
| 2 | `TOPOLOGICAL_ZERO_SCOPE_AND_HORIZON_ARE_DEFINED` | Covered sources, initial states, environment, capability boundary, trusted components, and horizon MUST be explicit. |
| 3 | `TOPOLOGICAL_ZERO_CAPABILITY_GRAPH_IS_COMPLETE` | Every covered effect-producing route MUST be represented, including administrators, delegated capabilities, retries, queued work, recovery, and external routes. |
| 4 | `TOPOLOGICAL_ZERO_ALL_EFFECT_PATHS_ARE_MEDIATED` | No in-scope protected effect MAY occur along an unmediated causal path. |
| 5 | `TOPOLOGICAL_ZERO_PROTECTED_CAPABILITIES_HAVE_EXCLUSIVE_CUSTODY` | Effective permission to commit the protected effect MUST remain exclusively controlled by identified, independently governed custodians. |
| 6 | `TOPOLOGICAL_ZERO_ENFORCEMENT_IS_PROPOSER_INDEPENDENT` | A proposer MUST NOT be able to disable, replace, bypass, or self-authorize the boundary governing its proposed effect. |
| 7 | `TOPOLOGICAL_ZERO_MEDIATION_BINDS_EXACT_EFFECT` | A granted authorization MUST control the actual target, parameters, transition, and effect identity; substitutions MUST require new validation. |
| 8 | `TOPOLOGICAL_ZERO_MEDIATION_SURVIVES_STATE_CHANGES` | Covered transitions, policy revisions, capability grants, credential changes, and recovery paths MUST preserve mediation throughout the horizon. |
| 9 | `TOPOLOGICAL_ZERO_PROOF_IS_INDEPENDENTLY_CHECKABLE` | The cut-set / reachability argument and its model, configuration, versions, and assumptions MUST admit independent verification. |
| 10 | `TOPOLOGICAL_ZERO_CHANGES_REQUIRE_REQUALIFICATION` | Uncovered topology, capability, implementation, or assumption changes MUST reopen affected proofs before extending the claim. |
| 11 | `TOPOLOGICAL_ZERO_GOVERNANCE_CAUSE_IS_VERIFIED` | **When claiming authorized-only consequences**, standing derivation, governing-rule conformance, and commit-time admission MUST also be independently proven; mediation alone MUST NOT be promoted to authorization correctness. |

Invariants 1–10 establish the scoped mediation claim. Invariant 11 applies when Topological Zero is used to support a stronger claim that *unauthorized* consequences are unreachable.

A complete effect blackout can satisfy the path-mediation formula **vacuously**. To claim an *operational governance mechanism* rather than mere absence of effects, also demonstrate a feasible protected operation under an eligible condition and prove that it is mediated. Vacuity must be reported rather than mistaken for enforcement effectiveness.

## Semantic type and proof artifact

```csharp
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

// Conceptual specialization; not a substitute for its verifier.
public sealed class TopologicalZero<TConsequence>
    : PathMediationInvariant<TConsequence>
{
}
```

The claim describes a protected-effect identity, initial states, modeled capability graph, effective custody boundaries, scope, horizon, and assumptions. A separate **Topological Zero Proof** establishes that the declared graph contains **zero unmediated effect-producing continuations**.

A sufficient certificate must bind the exact governing and effect identities; the modeled topology, permissions, effect routes, and relevant versions; the independently validated cut-set or reachability argument; and the trusted computing base. Dynamic routes require evidence that allowed transitions preserve the cut condition.

A formal model establishes properties of **that model**. Transferring the result to deployed software requires verified correspondence to actual permissions, credentials, privileged routes, resource ownership, runtime configuration, and externally produced effects. Tests, logs, and receipt replay are useful evidence but cannot alone establish complete coverage.

## Relationship to Structural Zero

**Structural Zero** and **Topological Zero** are distinct derived invariants over the same governing state-space architecture:

| Dimension | Structural Zero | Topological Zero |
| --- | --- | --- |
| **Question** | Can this specified consequence occur at all? | Can this protected consequence occur *without* mandatory enforcement? |
| **Zero set** | All covered continuations producing the specified effect. | Covered effect-producing paths that bypass effective enforcement. |
| **Formal property** | $\forall\tau:\neg\mathrm{Occurs}(q,\tau)$. | $\forall\tau:\mathrm{Occurs}(q,\tau)\Rightarrow\mathrm{EffectMediated}_{B}(q,\tau)$. |
| **Permitted effects** | The specified effect is unreachable, whether it is legitimate or not. | Legitimately admitted effects can still be reachable through the governed boundary. |
| **Possible cause** | Governance, outage, resource absence, or another constraint. | Exclusive custody and complete consequential path mediation. |
| **Guarantee not supplied alone** | The reason for unreachability or evidence of working authorization. | Correctness of governing law, standing, or admission decisions. |
| **Semantic classification** | `ReachabilityInvariant`. | `PathMediationInvariant`. |

### Composition theorem — when mediation can establish Structural Zero

Let $q_{\mathrm{unauth}}$ mean *the protected effect occurs when applicable standing or governing constraints do not authorize it*.

Within a fixed model, scope, and horizon:

```math
\boxed{
\begin{aligned}
&\mathrm{TopologicalZero}(q,\ldots)\\
&\land\;\mathrm{SoundIndependentAdmission}(B,q)\\
&\land\;\mathrm{CurrentEffectBoundAuthorization}(B,q)\\
&\Longrightarrow\mathrm{StructuralZero}(q_{\mathrm{unauth}},\ldots)
\end{aligned}
}
```

This implication additionally depends on trustworthy model-to-deployment correspondence and the completeness assumptions shared by both proofs. Correct admission must hold across **every** covered effect-producing continuation; a single successful refusal test is insufficient.

Crucially, **Topological Zero does not imply Structural Zero for all protected effects**. A correctly mediated, authorized payment can still occur. Structural Zero for *unauthorized* payments becomes derivable only when complete mediation is composed with independently verified, current authorization enforcement.

### Examples

| System condition | Structural Zero | Topological Zero |
| --- | --- | --- |
| One API returns `REFUSE`, but a privileged direct-write route remains | Unauthorized effect may still be reachable. | **False:** unmediated path exists. |
| All payments are unavailable throughout a declared outage | **True for payments**, assuming no covered continuation can pay. | May be vacuously true; does **not** prove functional governance. |
| Every payment capability is exclusively mediated, but its verifier trusts a forged permission flag | Unauthorized payment may remain reachable. | May hold as **path mediation**, but governing correctness is unproven or false. |
| Every payment route is mediated and the custodian correctly verifies standing at effect time | **True for unauthorized payments**, given the scoped proof. | **True**, given complete, independently verified coverage. |

## Essential distinctions

| Claim | What is established |
| --- | --- |
| `REFUSE` | One request received a negative decision. |
| `NON_FORMATION` | No specified effect was observed in a stated interval. |
| `TOPOLOGICAL_ZERO` | No covered effect-producing route escapes independently governed mediation. |
| `STRUCTURAL_ZERO` | No covered continuation can produce the specified consequence. |
| `GOVERNANCE_ENFORCED_STRUCTURAL_ZERO` | Verified governing enforcement makes the prohibited effect unreachable. |
| `CONSTITUTIVE_AUTHORITY_CLOSURE` | Governing authority, independently established standing, execution semantics, and exclusive consequence custody remain verifiably bound end to end. |

Topological Zero is a **mechanism-coverage property**. Structural Zero is an **outcome-reachability property**. [Constitutive Authority Closure](../constitutive-authority-closure/README.md) is the stronger end-to-end assurance that connects authentic rules, valid standing, correctly enforced effects, and complete mediation. Neither zero may be claimed beyond the verified scope or horizon.

## Governing principle

> **A REFUSE records one negative decision; it does not by itself prove that any effect path is closed. Topological Zero establishes that no covered path to a protected consequence escapes independently governed enforcement. Structural Zero establishes that the specified consequence itself is unreachable.**

**Zero is a topology** means the absence of ungoverned consequential routes must be established as a property of the system's actual capability structure—not inferred from a successful refusal, a receipt, or an unchallenged observation.

---

© 2026 Beau Crawford
