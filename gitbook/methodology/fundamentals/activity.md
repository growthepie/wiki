# 🕓 Activity

### Transaction Count

A transaction is an action that is triggered either by an EOA (Externally Owned Account) or smart contract, and it is stored on-chain. Some examples of transactions are transfers (ETH, ERC20, ERC721), swaps, etc. Our goal with this metric is to analyze how many actions are executed. We exclude known system transactions.

* **Arbitrum**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Base**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Ethereum**: All transactions that are stored onchain.
* **Linea:** All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Loopring:** All transactions that are stored onchain.
* **ImmutableX**: All actions that have a `transaction_id` assigned (deposits, withdrawals, mints, trades, transfers).
* **Mantle:** All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **OP Mainnet**: All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Polygon zkEVM**: All transactions that are stored on-chain.
* **Public Goods Network:** All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Scroll:** All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **zkSync Era**: All transactions that are stored onchain.
* **Zora:** All transactions but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).



### Daily Active Addresses

The number of daily active addresses is a simple heuristic for the number of active users on a chain. Some analytics sites count sender and receiver addresses but we only count unique sender addresses (because we see receiver addresses as passive addresses). This metric is far from being a perfect proxy for the number of users of a chain but it is still a good first step.

* **Arbitrum**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Base**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Ethereum**: All unique addresses that sent a transaction.
* **Linea:** All unique addresses that sent a transaction but we exclud transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Loopring:** All unique addresses that sent a transaction.
* **ImmutableX**: All unique addresses that actively interacted on ImmutableX (not mints, because they are not triggered by users themselves). We only consider unique sender addresses for deposits, withdrawals, orders, and transfers.
* **Mantle:** All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **OP Mainnet**: All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Polygon zkEVM**: All unique addresses that sent a transaction.
* **Public Goods Network:** All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **Scroll:** All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
* **zkSync Era**: All unique addresses that sent a transaction.
* **Zora:** All unique addresses that sent a transaction but we exclude transactions that have an L2 gas price of 0 (which are internal system transactions).
