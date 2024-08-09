---
description: Complete
cover: ../../.gitbook/assets/GAL4z0AWUAEnv4L.jpeg
coverY: 0
---

# ✅ Chain Factories

The first step is to turn the Bedrock Bridge into a Chain Factory through the derivation function offered by Bedrock.&#x20;

How? Let's get digging :pick:

### :bridge\_at\_night: Bedrock's SystemConfig&#x20;

Contract Bedrock has revolutionized the way Layer 2 chains interact with Layer 1 smart contracts through the introduction of the SystemConfig contract. This innovation marks the beginning of defining L2 chains directly within L1 smart contracts.

The potential of this system can be further harnessed by transferring all L2 chain-defining information onto the blockchain. This includes essentials like a unique chain ID, block gas limits, and other key configuration values.

### :factory: The Birth of a Chain Factory&#x20;

With all chain data available Onchain, we can create a factory that deploys the configuration and all necessary contracts for each chain.

* Streamlining efficient chain creation

#### Deterministic Contract Addresses with CREATE2 :chains:

By utilizing CREATE2, contract addresses can be made deterministic. Given a chain configuration, all bridge addresses associated with that chain can be predetermined. – Simplifying interactions and enhancing efficiency.

#### Counterfactual Chain Deployment :bulb:

This new system allows for counterfactual chain deployment, which is virtually free. Chains can be interacted with without deploying their bridge contracts

* Inheriting standard security properties.
* Significantly reducing deployment costs

#### Deriving OP Chain Data Using the Chain Factory :tada:

The L1 chain factory extends Bedrock's capability to derive L2 chain data from an L1 chain. This enables Optimism nodes to sync any OP Chain deterministically using just a single L1 address and a connection to L1.&#x20;

#### Secure and Permissionless Chain State Computation :lock:

When an OP Chain is synced, its state is computed locally. This process is fully permissionless and secure, eliminating the need for a proof system for chain derivation. Invalid transactions are automatically disregarded!

If you're wondering how they are automatically disregarded this example from [@karl\_dot\_tech](https://x.com/karl\_dot\_tech) works best:

{% embed url="https://www.youtube.com/watch?feature=youtu.be&t=952&v=O6vYNgrQ1LE" %}

Maintaining Proof System for Superchain Withdrawals&#x20;

Despite the advancements in chain derivation, a proof system remains necessary for enabling Superchain withdrawals, ensuring the security and integrity of cross-chain transactions. Which is coming on Next



