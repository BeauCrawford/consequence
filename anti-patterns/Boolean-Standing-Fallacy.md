# <img src="../assets/signatures/boolean-standing-fallacy.svg" alt="" width="32" height="32"> Boolean Standing Fallacy

*A Boolean can assert authority. It cannot constitute it.*

![](./images/Boolean-King.png)

## Definition

An architectural anti-pattern in which a Boolean predicate is treated as sufficient proof of governing authority without independently establishing its constitutive origin, semantic derivation, provenance, and continued validity at the moment of consequence.

A predicate evaluating to `true` establishes only its computed result—not its legitimate standing. Even cryptographic attestation cannot substitute for verifiable continuity to the authority that constitutes the predicate.

## Governing Principle

No Boolean may authorize consequence solely by asserting its own validity.

## Problematic Version

Assume `IsActive` is a locally stored flag, and neither `GetCurrent()` nor `Evaluate()` validates governing authority. No commitment-time synchronization protects against revocation or dependency changes.

```
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

var policy = Policies.GetCurrent();

if (policy.IsActive)
{
    var approved = policy.Evaluate(request);

    if (approved)
    {
        var result = Execute(request);

        var receipt = Hmac.Sign(
            policy.Hash, request.Hash, result);

        return new { result, receipt };
    }
}
```

### Issues

- **Verifying that a decision faithfully followed a rule is not the same as proving that the rule had standing to govern the decision.**

- **A Boolean can assert standing. It cannot constitute it.**

- **The HMAC authenticates the recorded data under a shared key; it establishes neither correct evaluation nor governing authority.**

## Corrected Version

Here, *governing geometry* is the independently constituted specification obtained from trusted governance, never the executable's self-description. `Geometry.Verify` establishes that the exact policy executable conforms to that specification for the captured inputs and effects.

`Capture` freezes the contract, policy executable, request, complete decision- and execution-relevant dependencies, and effect plan. Evaluation and execution are confined to that snapshot; undeclared reads or effects are blocked and abort commitment.

```
// Copyright 2026 Beau Crawford
// SPDX-License-Identifier: Apache-2.0

var policy = Policies.GetCurrent();
var contract = Governance.GetContract(TrustedRoot);
var snapshot = Boundary.Capture(contract, policy, request);
var proof = Geometry.DeriveProof(snapshot);

var record = Boundary.CommitAtomically(snapshot, commit =>
{
    commit.Require(Governance.VerifyAuthorityChain(
        snapshot.Policy, TrustedRoot));

    commit.Require(Geometry.Verify(
        proof, snapshot, TrustedRoot));

    commit.Require(Governance.Authorizes(
        snapshot.Policy, snapshot.Request, snapshot.Effects));

    commit.Require(commit.DependenciesAreCurrent(snapshot));
    commit.Require(commit.AuthorityIsCurrentAndUnrevoked(
        snapshot.Policy));

    commit.Require(commit.Evaluate(snapshot));

    return commit.ExecuteAndRecord(snapshot, proof);
});

return record; // Durable receipt; asymmetric attestation may be pending.
```

### What Changed

- **Constitutive origin:** The policy must trace to an independently trusted governance root.
- **Semantic continuity:** The evaluated decision is covered by the verified contract.
- **Consequence-specific authority:** Delegation must authorize the requested operation and its exact effects.
- **Current standing:** Authority, revocation, and dependency currency are revalidated at commitment.
- **Protected consequence:** Every protected effect must pass through the boundary and satisfy every obligation.
- **Durable evidence:** The boundary atomically records the committed local consequence—or, for external effects, the authorized intent—and its evidence, binding the snapshot, proof, authority version, outcome, and commit identity.
- **Independent attestation:** A retryable worker signs the canonical receipt with an asymmetric key for [third-party verification](https://csrc.nist.gov/pubs/fips/186-5/final). Signing failure leaves the durable record intact and never re-executes the consequence.

`CommitAtomically` is a conceptual primitive: all protected effects must pass through it, and a failed requirement must prevent commitment and effects. Its implementation must enforce a common authoritative ordering among commitment, revocation, and dependency changes, with fencing for external effects.

For external effects, the atomic record covers a durable intent and its evidence. Delivery must be fenced and idempotent; completion evidence is recorded separately, so an intent receipt does not assert completion.

**External consequence standing:** A committed intent does not confer permanent execution authority. At the receiving system's effect boundary, governing authority and dependencies must be revalidated and remain current through effect commitment. The receiver must enforce authoritative ordering among revocation, dependency changes, and effect commitment. If standing or that ordering cannot be established, execution fails closed.

## Core Invariant

A Boolean may participate in authorization, but it cannot independently constitute the authority upon which execution depends.

---

© 2026 Beau Crawford
