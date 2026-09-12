# The Constitutive Floor Proof Standard

- See: [Argument](./Argument.md)

A constitutive computational Floor requires some **non-bypassable contract** that valid protected consequence actually depends on.

The central question is not whether the system has rules, checks, receipts, replay, or changed-condition behavior.

The question is:

> **Can valid protected consequence form without preserving the claimed constitutive contract?**

If yes, the contract is not constitutive.

---

## 1. Show Non-Vacuous Formation

First, show that the system can actually form a valid protected consequence when the constitutive contract holds.

A system that never permits consequence cannot establish constitution merely because nothing ever violates its rules.

> **Something valid must actually be able to form.**

---

## 2. Show Minimal Counterfactual Dependency

Construct a clean counterfactual where the constitutive contract is violated while materially unrelated conditions remain unchanged.

Then show that protected consequence no longer forms.

Conceptually:

`Contract Preserved → Valid Consequence`

`Contract Violated → No Valid Consequence`

This demonstrates **local dependency**.

It does not yet prove that every possible consequential path obeys the same law.

---

## 3. Prove Scope-Wide Closure

Now prove that the result is not merely one successful example.

Across the entire declared scope:

> **No valid protected consequence may exist without the constitutive contract.**

Critically, that scope must be mechanically bounded and must not be constructed to exclude inconvenient counterexamples.

The proof scope itself is therefore part of the proof.

> **Prove there is no bypass inside a scope that was not constructed to hide bypasses.**

---

## 4. Prove the Implementation Preserves the Model

A formal model proves properties about the model.

It does not automatically prove those properties about the running implementation.

Every implementation path covered by the claim must map into the proven model.

The implementation must also define, from its own operational semantics:

- what counts as a valid protected consequence;
- what constitutes preservation of the governing contract.

Those definitions cannot simply be inherited from the abstraction used to prove them.

> **The abstraction cannot manufacture the property it is supposed to preserve.**

---

## 5. Bind the Deployment to the Verified Implementation

Finally, establish that the deployed artifact is actually the implementation to which the proof applies.

This requires an explicit trust boundary that may include:

- build and artifact identity;
- compiler assumptions;
- configuration;
- dependencies;
- runtime integrity;
- deployment provenance;
- attestation;
- hardware or platform assumptions.

The deployment guarantee is therefore conditional on a declared Trusted Computing Base.

> **State the trust assumptions instead of hiding them inside the theorem.**

---

# Assurance Ladder

These are different levels of evidence and should not be conflated.

### Sensitivity

Changing a condition changes the result.

Useful, but it proves only condition sensitivity.

### Local Dependency

Changing only the claimed constitutive property prevents a particular consequence from forming.

Stronger, but still local.

### Model Closure

No valid consequence exists without the constitutive property anywhere inside the formally declared model scope.

This proves constitution of the model.

### Implementation Refinement

The real implementation is proven to remain within that model and preserve its constitutive semantics.

This transfers the guarantee from model to implementation.

### TCB-Bound Deployment

The deployed artifact is bound to the verified implementation under explicitly declared trust assumptions.

Only here does the proof become a deployed-system assurance claim.

---

# What Lower-Level Evidence Can Show

The following may all be useful evidence:

- changed-condition behavior;
- deterministic outcomes;
- receipts;
- replay;
- tests;
- documentation;
- pilots;
- production use.

But none of them, by itself, establishes the full constitutive claim.

They occupy lower assurance rungs unless connected to the stronger proof obligations above.

---

# Minimal Kernel

> **Show that the law is necessary.**

> **Prove there is no bypass inside the claimed scope.**

> **Prove the implementation preserves that law.**

> **State the trust assumptions under which the deployed system inherits the guarantee.**

If those obligations have not been discharged, the constitutive claim may still be true.

It simply has not been formally established.

---

# Governing Principle

> **Never claim above the highest assurance rung your evidence has actually earned.**