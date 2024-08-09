---
description: Almost complete (Still needs a trusted guardian role)
---

# ✅ Permissionless Proof System

Previously, we explored OP Stacks' expansion to Superchain, highlighting the **Chain Factory**. This innovative function allows for the creation of unlimited OP chains using only the bedrock bridge and SystemConfigs on Layer 1.

🚨 But, like all Optimistic rollups, **Withdrawal Claims** are a major issue, particularly with invalid state roots from malicious block proposers.

**Trust Issues**: Befor the upgrade users needed to rely on block proposers to accurately submit the Layer 1 state root on all OP Chains. The risks?

1. **Stolen Funds**: If an invalid state root is submitted.
2. **MEV Extraction**: If operators exploit their position to front-run transactions.
3. **Frozen Funds**: If the centralized validator fails.

## Optimism's Leap Towards Decentralization:&#x20;

### The Fault Proof Upgrade ⚙️&#x20;

Optimism is taking a giant stride towards decentralization with its latest upgrade: the Fault Proof system. It serves as a fundamental shift in how the Layer 2 network operates and interacts with Ethereum.

#### The Fault Proof Game 🕹️

Here's how the new system works now:

1. Anyone can propose an L2 state root (with a financial stake)
2. Others can challenge this proposal (also with a stake)
3. A back-and-forth proving process ensues
4. The game resolves, determining the valid state

However this bicycle still has some safety wheels

#### The Guardian's Watch 🛡️&#x20;

While this system is more decentralized, it's not without safeguards:

* A Guardian role can pause the system in emergencies
* Delayed WETH contracts hold bonds, allowing for corrections
* Off-chain monitoring ensures proposed roots align with the correct state

This upgrade lays the groundwork for tomorrow:

* A smart contract framework for multi-proof systems
* Easier addition of new proof systems in the future
* Moving towards Stage 2 decentralization in the OP Stack

### Technicalities (For the Curious)

* New contracts deployed: DisputeGameFactory, FaultDisputeGame, and more
* OptimismPortal upgrade for new withdrawal proving process
* SystemConfig updates for dispute game integration

<details>

<summary>Let's dive deeper into the new contracts that form the backbone of this upgrade:</summary>

#### DisputeGameFactory 🏭

* Purpose: Creates and manages dispute games
* Key feature: Acts as the new source of proposed output roots
* Address: 0xe5965Ab5962eDc7477C8520243A95517CD252fA9

Think of this as the grand arena where all disputes are born and settled. It's the factory that produces the games that keep Optimism honest!

#### FaultDisputeGame 🎮

* Purpose: Implements the actual dispute game logic
* Key feature: Uses permissionless, interactive bi-section of chain state
* Address: 0x4146DF64D83acB0DcB0c1a4884a16f090165e122

#### PermissionedFaultDisputeGame 🔐

* Purpose: A restricted version of FaultDisputeGame
* Key feature: Limits participation to privileged roles
* Use case: Serves as a fallback in case of emergencies

#### AnchorStateRegistry ⚓

* Purpose: Stores the latest "anchor" state for each game type
* Key feature: Allows games to start from a more recent state
* Benefit: Reduces required off-chain computation

Imagine this as a checkpoint system in a video game - you don't always have to start from the very beginning!

#### DelayedWETH ⏳

* Purpose: Extends WETH9 with delayed withdrawals
* Key feature: Introduces a time delay for bond withdrawals
* Safety measure: Allows for bond reallocation if bugs are found

#### PreimageOracle 🔮

* Purpose: Stores validated pre-images retrievable by hash
* Use: Supports the derivation process in fault proofs

#### MIPS 💻

* Purpose: Implements the Cannon MIPS VM
* Key feature: Executes single MIPS CPU instructions on-chain

This is like having a tiny computer within the blockchain, capable of running one instruction at a time to verify complex computations.

</details>

## What This Means for Users

1. Pending withdrawals will need to be re-proven (but don't worry, it's for the better!)
2. Slightly longer withdrawal times in some cases (up to 16 days in extreme scenarios)
3. A more robust, decentralized network overall

This upgrade is like replacing the foundations of a bridge while cars are still crossing. It's complex, but necessary for a stronger, more resilient Optimism.&#x20;

Remember, this isn't just a technical upgrade – it's a step towards a more open, trustless, and powerful Layer 2 ecosystem. It's not just optimizing Optimism; it's reimagining what blockchain infrastructure can be!

### Devsources

_Here you get quick access to the most important pieces of docs and articles, curated for devs._

***

This bookmark takes you to the more technical talk and the discourse around this upgrade:

{% embed url="https://gov.optimism.io/t/final-protocol-upgrade-7-fault-proofs/8161" %}
