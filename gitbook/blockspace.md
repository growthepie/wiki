# Blockspace

The blockspace analysis section works by initially examining each L2 separately and summing up the fees paid for each unique "to_address". 
Next, our contract mapping integrates this data, assigning the addresses to specific subcategories based on their activity. 
For example, executing a token swap on Uniswap V3 involves interacting with the V3 contract, which is automatically recognized by its "to_address" and then mapped to the "Decentralized Exchange" subcategory.


## Categories

### NFT

* **NFT Fi:**: Contracts that involve the financialization of NFTs, which includes lending NFTs.
* **NFT Marketplace:**: Platform contracts for the sale or minting of NFTs.
* **ERC721**: Contracts that adhere to the ERC721 token standard. This category does not include NFTs received as deposit receipts.
* **ERC1155**: Contracts that adhere to the ERC1155 token standard. This category does not include NFTs received as deposit receipts.

### Token Transfers

* **Native Transfers**: All native transfers (primarily ETH transfers, but the native token can vary depending on the L2), pre-filtered by assessing if the total gas used for a transaction is 21,000.
* **ERC20**: Contracts that adhere to the ERC20 token standard. This category does not include tokens received as deposit receipts or stablecoins.
* **Stablecoin**: ERC20 token contracts whose primary purpose is to maintain a value pegged to a fiat currency.

### DeFi

* **Decentralised Exchange**: Contracts whose primary focus is on routing token swaps through liquidity pools (LPs).
* **Derivative Exchange**: Contracts that facilitate the trading of derivatives, which are financial instruments deriving their value from an underlying asset or benchmark.
* **Lending**: Contracts that enable lending with the use of collateral.
* **Staking**: Contracts where the primary activity is staking tokens or LP positions. Additionally, LP pools are included here, as contributing tokens to an LP is considered a form of staking.

### Social

* **Community**: Contracts designed to support social interactions, networking or education.
* **Gambling**: Contracts that govern games of chance.
* **Gaming**: Contracts that are integrated into digital games, providing functionalities such as tokenized in-game assets, character progression, and digital ownership. Unlike gambling contracts, the outcomes in these games are influenced by the player's decisions, strategies or skill rather than by chance alone.

### CeFi

* **Trading**: Contracts whose primary objective is to trade tokens or NFTs based on arbitrage, MEV (Miner Extractable Value) or market-making strategies.
* **Centralized Exchange**: Contracts under the control of centralized exchanges.

### Utility

* **Oracle**: Contracts that feed external, real-world data onto the blockchain.
* **Developer Tool**: Contracts taht assist developers in creating, testing and deploying smart contracts.
* **Middleware**: Contracts that facilitate communication and interoperability between different blockchain protocols.
* **Identity**: Contracts that provide digital identification and verification services on the blockchain.
* **ERC4337**: Contracts that adhere to the ERC4337 standard for account abstraction, including all entry point contracts.
* **Smart Contract Deployment**: All fees paid towards publishing a smart contract onto the blockchain.
* **Airdrop**: Contracts that help to distribute tokens or NFTs to multiple wallet addresses.
* **Other**: Contracts that do not fall within any of the defined sub-categories.

### Cross-Chain

* **Cross-Chain Communication**: Contracts that facilitate the exchange of information or data between different blockchain networks. This sub-category does not include contracts that facilitate actual token or NFT transfers.
* **Bridge**: Contracts that facilitate cross-chain token or NFT transfers, enabling the movement of assets across various chains. This category includes cross-chain swap platforms, as users primarily utilize these DEXs to ensure better liquidity for their bridged assets.

### Unlabeled

This category encompasses all contracts that have not been assigned to a sub-category. We encourage you to utilize our front-end labeling mechanism to suggest appropriate labels for these unlabeled contracts.


## Chain Overview

This section provides an overview of each L2 and what its blockspace is primarily used for, based on the seven main categories. All numbers are expressed as a share of chain usage. This dashboard is perfect for gauging how the blockspace is utilized for each L2 and for analyzing shifts over time. Furthermore, it displays the most-used contracts for each main category across all L2s below.

## Category Comparison

This section delves deeper than the chain overview, allowing for an analysis all the way down to the sub-category level. It also displays the absolute fees paid and enables users to compare different L2s by offering the option to deselect chains. In the category comparison section, users can analyze chain activity on a much more granular level.
