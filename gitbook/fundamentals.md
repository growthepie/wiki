# Fundamentals

### Transaction count

A transaction is an action that is triggered either by an EOA or smart contract and it is stored on-chain. Some examples for transactions are transfers (ETH, ERC20, ERC721), swaps, etc. Our goa with this metric is to analyze how many actions are executed. We exclude know system transactions.

* **Ethereum:** All transactions that are stored on-chain.&#x20;
* **zkSync Era**: All transactions that are stored on-chain.&#x20;
* **Arbitrum**: All transactions but we exclude transactions that are sent from `0x00000000000000000000000000000000000a4b05` (internal system transaction)
* &#x20;**Optimism**: All transactions but we exclude `0x420000000000000000000000000000000000000f` (internal system transaction)&#x20;
* **Polygon zkEVM**: All transactions that are stored on-chain
* **ImmutableX**: All actions that have a `transaction_id` assigned (deposits, withdrawals, mints, trades, transfers)

### Daily active addresses

The number of daily active addresses is a simple heuristic for the number of active users on a chain. Some analytics sites count sender and receiver addresses but we only count unique sender addresses (because we see receiver addresses as passive addresses). This metric is far from being a perfect proxy for the number of users of a chain but it is still a good first step.

* **Ethereum**: All unique addresses that sent a transaction.&#x20;
* **zkSync Era**: All unique addresses that sent a transaction.&#x20;
* **Arbitrum**: All unique addresses that sent a transaction but we exclude transactions that are sent from `0x00000000000000000000000000000000000a4b05` (internal system transaction)
* **Optimism**: All unique addresses that sent a transaction but we exclude `0x420000000000000000000000000000000000000f`(internal system transaction)
* **Polygon zkEVM**: All unique addresses that sent a transaction&#x20;
* **ImmutableX**: All unique addresses that actively interacted on ImmutableX (not mints, because they are not triggered by users themselves). We only consider the unique sender addresses for deposits, withdrawals, orders, and transfers.

### Total value locked (TVL)

This metric was mainly coined by L2Beat. It measures the net bridged value to a Layer 2. Basically, the amount of value that is locked in L1 bridges to L2s. It also includes native tokens such as ARB and OP. We take this value directly from L2Beat.&#x20;

### Fees paid by users

The amount of (gas) fees that users paid in order to use the chain. We think that this is one of the most important metrics for a Layer 2. If people are willing to pay more for a certain Layer 2 that means that this Layer 2 has more to offer in terms of applications or security. This metric is also often refered to as a Layer 2s revenue.

* **Ethereum**: Gas usage \* gas price \* eth price of all transactions.&#x20;
* **zkSync Era**: Gas usage \* effective gas price \* eth price
* **Arbitrum**: Gas usage \* gas price \* eth price of all transactions exclude transactions that are sent from `0x00000000000000000000000000000000000a4b05`(internal system transaction)
* **Optimism**: Gas usage \* gas price \* eth price of all transactions. `0x420000000000000000000000000000000000000f` (internal system transaction)
* **Polygon zkEVM**: Gas usage \* gas price \* eth price of all transactions.&#x20;
* **ImmutableX**: Users only pay fees to the protocol when the buy or sell NFTs. Usually 1% of buy and sell orders goes to the protocol. The sum of theses protocol fees is our fees paid metric (marketplace fees not included because they don't go to the protocol).

### Stablecoin market cap

The amount of stablecoins (USDT, USDC, DAI, etc.) that are locked on a Layer 2.&#x20;



###
