# 💳 Economics

### Fees Paid by Users

The amount of (gas) fees that users paid in order to use the chain. We think that this is one of the most important metrics for a Layer 2. If people are willing to pay more for a certain Layer 2 that means that this Layer 2 has more to offer in terms of applications or security. This metric is also often referred to as a Layer 2's revenue.

* **Arbitrum**: Gas usage \* gas price \* ETH price of all transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Ethereum**: Gas usage \* gas price \* ETH price of all transactions.
* **Linea:** Gas usage \* gas price \* ETH price of all transactions.
* **Loopring:** TBD&#x20;
* **ImmutableX**: Users only pay fees to the protocol when they buy or sell NFTs. Usually, 1% of buy and sell orders go to the protocol. The sum of these protocol fees is our fees paid metric (marketplace fees not included because they don't go to the protocol).
* **Mantle:** Gas usage \* gas price \* MNT price of all transactions.
* **OP chains (OP Mainnet, Base, Zora, PGN)**: L1 fee + gas usage \* gas price \* ETH price of all transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Polygon zkEVM**: Gas usage \* gas price \* ETH price of all transactions.
* **Scroll:** Gas usage \* gas price \* ETH price of all transactions.
* **zkSync Era**: Gas usage \* effective gas price \* ETH price.

### Rent Paid to L1

The gas fees paid by L2s to post transaction data & verification states onto Ethereum. We query Ethereum mainnet (full query: [https://dune.com/queries/2986216](https://dune.com/queries/2986216)) and use a Dune spell (thanks [https://twitter.com/0xKofi](https://twitter.com/0xKofi)).

### Onchain Profit

Profit = Fees paid by users - Rent paid to L1.
