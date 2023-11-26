# 🕓 Activity

### Transaction Count

A transaction is an action that is triggered either by an EOA or smart contract and it is stored on-chain. Some examples of transactions are transfers (ETH, ERC20, ERC721), swaps, etc. Our goal with this metric is to analyze how many actions are executed. We exclude known system transactions.

* **Ethereum**: All transactions that are stored on-chain.
* **zkSync Era**: All transactions that are stored on-chain.
* **Arbitrum**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Optimism**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Base**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Polygon zkEVM**: All transactions that are stored on-chain
* **ImmutableX**: All actions that have a `transaction_id` assigned (deposits, withdrawals, mints, trades, transfers)

### Daily Active Addresses

The number of daily active addresses is a simple heuristic for the number of active users on a chain. Some analytics sites count sender and receiver addresses but we only count unique sender addresses (because we see receiver addresses as passive addresses). This metric is far from being a perfect proxy for the number of users of a chain but it is still a good first step.

* **Ethereum**: All unique addresses that sent a transaction.
* **zkSync Era**: All unique addresses that sent a transaction.
* **Arbitrum**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Optimism**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Base**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions)
* **Polygon zkEVM**: All unique addresses that sent a transaction
* **ImmutableX**: All unique addresses that actively interacted on ImmutableX (not mints, because they are not triggered by users themselves). We only consider unique sender addresses for deposits, withdrawals, orders, and transfers.
