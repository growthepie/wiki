# 🔐 Validiums

{% hint style="info" %}
Validiums can not be considered as Layer 2 per se. When we talk about Validiums we are talking from the Data Availability point of view.
{% endhint %}

It is an approach that different Layer 2s can take towards their Data Availability concerns. To read more about this, go to our more detailed breakdown in General Layer 2 Knowledge [data-availability](../../general-layer-2-knowledge/data-availability/ "mention")



As discussed on [offchain-data-availability](../../general-layer-2-knowledge/data-availability/offchain-data-availability/ "mention") page no respectable project uses pure Validiums. Though it can be used for use cases with no critical security need, there are a few Rollups that use general-purpose data availability committees as a part of their Validium choice.

{% hint style="info" %}
The following scenario uses a Permissionless DAC Validium, check other variations [offchain-data-availability](../../general-layer-2-knowledge/data-availability/offchain-data-availability/ "mention")
{% endhint %}

## Scenario 🌟

**Peter is a developer working on an online multiplayer game that involves frequent in-game transactions, such as trading items or in-game currency. You're exploring blockchain solutions to enhance security and transparency but are concerned about high transaction costs and scalability. This is where Validium comes into play.**

### **Understanding Validium**&#x20;

Validium is a Layer 2 scaling solution that offers high throughput and low transaction costs, making it an attractive option for gaming applications. Here's how it works:

#### **The Three Parties in Validium**

1. **The L2 Chain**: This is where your game's transactions (like item trades or currency exchanges) are initially recorded. It's fast and efficient, handling the bulk of transaction processing.
2. **The Offchain Data Availability (DA) Provider**: This entity stores the actual transaction data off-chain. In our gaming context, this could include details of every item trade, player interactions, and other in-game activities.
3. **Ethereum Mainnet**: This is the ultimate layer of security and trust, where final validations and checks occur.

<figure><img src="../../.gitbook/assets/da.png" alt=""><figcaption></figcaption></figure>

**The Process**

1. **Transaction Recording on L2**: When a player trades an item in your game, this transaction is first recorded on the L2 Chain.
2. **Data Handling by Offchain DA Provider**: The details of this transaction are sent to the Offchain DA provider. The provider ensures the data is available and securely stored, which is crucial for later verification.
3. **Signing and Sending Merkle Root**: Validators at the Offchain DA provider sign the Merkle Root of the Data Availability (DA) Attestation. This signed root is then sent to the DA Bridge Contract on the Ethereum Mainnet.
4. **Publishing Proofs to Ethereum Mainnet**: Concurrently, proofs of the transactions from the L2 Chain (like the item trade in your game) are published to the Ethereum Mainnet. This is done through the L2 contract on the Mainnet.
5. **Fraud and Validity Checks**: The L2 contract on Ethereum Mainnet handles fraud and validity proofs. It ensures that the underlying data for each transaction (stored off-chain) is available and valid via the DA Bridge contract.

## Ups and Downs :arrow\_up::arrow\_down:

**Upsides:**

* These permissionless DACs come with extra-economic guarantees on data availability because the committee can be slashed if they misbehave.
* They are more credibly neutral as a DA layer than a DAC because it exists as an independent chain in its own right as a general-purpose DA layer, rather than a DA layer for a specific Ethereum L2.

**Downsides:**

* They are cost-effective and less costly than pure Rollups, but the more decentralized they get and the more signatures they need per attestation, the costlier they get.
* If the Offchain DA provider fails or acts maliciously, there's a risk of data loss. However, this risk is mitigated by the system's design and the use of trusted DA providers.

#### Examples of these DA providers

Celestia, Polygon Avail, and EigenDA



## Optimal for 🎯

* Scale-demanding applications where security isn't an issue
* Non-financial apps
* Gaming
* Centrally-governed Ecosystems

##
