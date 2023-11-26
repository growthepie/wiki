# 🔐 Validiums

{% hint style="info" %}
Validiums can not be considered as Layer 2 per se. When we talk about Validiums we are talking from the Data Avalability point of view.
{% endhint %}

It is an approach that different Layer 2s can take towards their Data Availability concerns to read more about this go to our more detailed breakdown in General Layer 2 Knowledge [data-availability](../../general-layer-2-knowledge/data-availability/ "mention")



As discussed on [offchain-data-availability](../../general-layer-2-knowledge/data-availability/offchain-data-availability/ "mention") page no respectable project uses pure validiums. Though it can be used for use cases with no critical security need, there are a few Rollups that use ggeneral-purposedata availability committees as a part of their Validium choice.

## Mechanism :gear:

#### There are usually three parties in the process:

1- The L2 Chain that receives and records transactions

2- The offchain DA provider

3- Ethereum Mainnet

<figure><img src="../../.gitbook/assets/da.png" alt=""><figcaption></figcaption></figure>

The actual Transaction Data is sent to the Offchain DA provider and is put into a block ensuring that the data is available.

On the Offchain DA provider side validators sign the Merkle Root of DA Attestation and send it to the DA Bridge Contract on Ethereum for verification and storage.

In the meantime, the proofs of transactions from the L2 Chain are also published to Ethereum Mainnet to the L2 contract on the Mainnet, which handles fraud and validity proofs and checks that the underlying data is available via the DA Bridge contract.

## Ups and Downs :arrow\_up::arrow\_down:

**Upsides:**

* These permissionless DACs come with extra-economic guarantees on data availability because the committee can be slashed if they misbehave.
* they are more credibly neutral as a DA layer than a DAC, because it exists as an independent chain in its own right as a general-purpose DA layer, rather than a DA layer for a specific Ethereum L2.

**Downsides:**

* They are cost-effective and less costly than pure Rollups, but the more decentralized they get and the more signatures they need per attestation, the costlier they get.

#### Examples of these DA providers

Celestia, Polygon Avail, and EigenDA



## Optimal for 🎯

To see what kind of applications this approach is optimal for go to [validium-hybrids.md](../../transaction-costs/validium-hybrids.md "mention")
