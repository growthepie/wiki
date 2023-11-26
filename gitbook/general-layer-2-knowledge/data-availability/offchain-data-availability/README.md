# 🕊 Offchain Data Availability

## Offchain :bird: :chains:

Now let’s dive deep into the world of Offchain Data Availability

By using Data Availability layers, one can make sure, true and valid transaction Data is still there without having to call and download all of Ethereum’s data. This ensures that Ethereum L1 is not overwhelmed by all the other L2s trying to scale it.

There are different kinds of Offchain Data Availability approaches:

1. [Pure Validium](./#pure-validium)
2. [Data Availability Committees (DACs)](./#data-availability-committees-dacs)
3. [General purpose or permissionless DACs](./#general-purpose-permissionless-dacs)

### Pure Validium&#x20;

Pure Validums take advantage of zk proofs to prove that transactions are valid without showing the complete data. these proofs are like the signature of someone who validated the data. The original transaction data is stored offchain.

#### Pros :thumbsup:

* The cheapest offchain DA option

#### Cons :thumbsdown:

* If the offchain data provider is offline or misbehaves, there is no data Availability so no DA guarantee and low-security

{% hint style="info" %}
There are currently no respectable L2 chains that only use pure Validiums, they generally also have something else on top which we will discuss as our next solution.
{% endhint %}

### Data Availability Committees (DACs)

These committees hold a limited number of trusted nodes or members who keep copies of data offchain and can an attestation that the data is there and valid if problems arise. These attestations are like signatures in the form of a transaction.

#### Pros :thumbsup:

Because of the fact that there is no need for additional transaction data to be posted onchain in case of a need for validation of the integrity of the chain, the costs are fixed and relatively cheap, no matter the size of the needed transaction data.

#### Cons :thumbsdown:

End users need to trust a potentially non-neutral, small number of 7-10 members, which is a considerable security risk if enough of these members decide to freeze or steal funds from the chain.

#### Examples

Immutable X, Arbitrum Nova, StarkEX, and zkPorter all leverage DACs



### **General purpose, permissionless DACs**

#### The chains that take this approach:

* Usually take a neutral stance in regard to data availability and give offchain Data Availability services to clients like Rollups and other L2 chains
* Have their own consensus mechanism
* Generally already have Fraud Proofs and DAS enabled for all the participating nodes, light or full

{% hint style="info" %}
The last item gives them the ability to be permissionless as anybody can propose challenges, alert their P2P neighbors if something fishy is being gossiped around.
{% endhint %}

