# 🔀 Convenience

### Transaction Costs

This metric aims to show how much users have to pay for a transaction. We calculate the median transaction costs.

The detailed methodology for transaction costs on different chains can be found here: [Fees paid](https://docs.growthepie.xyz/\~/changes/pE2v7C4bY9yrcW3peCPJ/methodology/fundamentals/economics#fees-paid-by-users)

#### Why do we do that?&#x20;

Transaction costs depend on the gas used per transaction. Simple transactions (e.g. native transfers) use very little gas, while more complex transactions (e.g. a token swap) use more gas. By using the median transaction cost we are trying to report what the average transaction on this chain costs.

The methodology for all chains is the same: Take gas used, multiply it by gas price, and then take the daily median value over all transactions.
