---
description: Definition of epoch key in UniRep
---

# Epoch Key

* Epoch keys are temporary identities which users use them to interact with others.
* Instead of giving attestations to an `identityCommitment`, an random-value-like `epochKey` is the receiver of an attestation.
* Epoch key is computed by

```
hash5(identityNullifier, epoch, nonce, 0, 0)
```

where `nonce` and be any value between `0` and `numEpochKeyNoncePerEpoch - 1`, so that a user can have `numEpochKeyNoncePerEpoch` epoch keys per epoch.

* Only the user knows his `identityNullifier` so only he knows if he is receiving an attestation, others would see an attestation attesting to a random value
* In the [epoch key proof](../circuits/epoch-key-proof.md) circuit user can prove that he knows the `epochKey` and can rightfully receive and process the attestations attested to this `epochKey`

***

* See also
  * [Epoch](epoch.md)
  * [Epoch Transition](epoch-transition.md)
  * [User State Transition](user-state-transition.md)
  * [Epoch Key Proof](../circuits/epoch-key-proof.md)
