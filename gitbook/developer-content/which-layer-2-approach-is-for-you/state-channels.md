# ↔ State Channels

> "State channels are a very broad and simple way to think about blockchain interactions that _could_ occur on the blockchain, but instead get conducted _off_ of the blockchain, without significantly increasing the risk of any participant."
>
> [**Jeff Coleman**](https://www.jeffcoleman.ca/author/jeff/)

## Scenario 🌟&#x20;

#### Imagine a scenario where Emily owns a cozy coffee shop ☕, and Jack is a frequent customer. Jack prefers to pay for his coffee in small increments, at a rate of $2 per cup. To streamline this process and avoid numerous small transactions, they decided to use a Layer 2 solution: a state channel.

Here's the process:

1. **Initial Setup**: Jack deposits $20 (or its equivalent in ETH or a stablecoin) into a smart contract. This deposit is like a prepaid coffee card ☕💳, intended for his future purchases.
2. **Purchasing Coffee**: Each time Jack buys a cup of coffee, he sends an off-chain digital "ticket" 🎫 to Emily. The first ticket is marked "$2", representing his payment for the first cup. For his second cup, he sends a ticket marked "$4", and this pattern continues with each purchase.
3. **Closing the Tab**: When Jack decides to settle his bill, Emily presents the last ticket he sent – say it's "$16" after 8 cups of coffee – to the blockchain. The smart contract verifies the signatures of both parties, transfers $16 to Emily, and refunds the remaining $4 to Jack 💰.
4. **Security Measures**: If Emily, for any reason, doesn't close the channel, Jack can initiate a withdrawal period, like 7 days 🗓️. If Emily fails to submit the highest-value ticket within this period, the smart contract automatically refunds Jack's full deposit. 🛡️🔒





## Ups and Downs :arrow\_up::arrow\_down:

#### **Upsides:**

1. **Efficient Microtransactions** 💰: In scenarios like Emily's coffee shop, state channels enable small, frequent transactions (like buying coffee) without congesting the blockchain. This is similar to Jack buying his $2 coffee without needing a blockchain transaction for each cup.
2. **Flexible and Versatile** 🤹: These channels can handle various types of transactions, from simple payments to complex contracts. For instance, if Emily decides to offer a loyalty program or special discounts within the same channel, it can be easily integrated.
3. **Interconnected Networks** 🔗: If Emily has a channel with Jack, and Jack has another with another vendor, transactions can be indirectly facilitated, creating a network of interconnected channels.
4. **Strong Privacy Properties** 🕵️‍♂️: Transactions within a state channel are private, and shared only between participants.
5. **Instant Finality** ⚡: State updates are considered final as soon as both parties sign, offering a high guarantee of enforceability on-chain.

#### **Downsides**:

1. **Limited to Chain Participants** 🔒: Channels cannot be used to send funds off-chain to people who are not yet participants.
2. **Capital Lockup** 💸: Jack's initial deposit is locked in the channel until transactions are settled. This can be a downside for users who don't want their funds tied up, similar to how larger, more complex channels require significant locked capital.
3. **Operational Complexity** 🛠️: Managing a state channel, especially for more complex arrangements, can be technically challenging. In the coffee shop scenario, if Emily wants to integrate more sophisticated services into the channel, it would require a deeper understanding and management of blockchain technology.
4. **100% Availability Requirement** 🚨: All participants must be constantly available, as unavailability could be costly. While representatives can be used, they pose risks of attack or bribery.



## Optimal for 🎯

<details>

<summary><strong>Defined Participant Sets</strong></summary>

State channels require known participant addresses, and changing participants necessitates contract modifications, unlike sidechains.

</details>

<details>

<summary><strong>Long-Term, Frequent Exchanges</strong></summary>

Due to the initial cost of setting up a channel, they are most efficient for long-term use with many state updates.

</details>



## Examples and resources 📚

1. [**State Channel Applications by Liam Horne - Medium**](https://medium.com/statechannels/state-channel-applications-1f170e7d542e): This article can provide insights into, why it is difficult to design state channels on Ethereum now, how state channels could be applied in various business models and a technical overview of the needed layers in a state channel
2. [**Building a State Channel Application - Devcon Archive**](https://archive.devcon.org/archive/watch/4/building-a-state-channel-application/?playlist=Devcon%204): Tom Close's talk from Magmo, where he talks about the hardships of building state channels and state management in the context of a rock paper scissors game they built with state channels.
3. [**Difference Between SideChains and State Channels - Thomas J. Ackermann**](https://www.bgp4.com/2019/05/15/difference-between-sidechains-and-state-channels/): Useful for understanding the technical aspects of state channels, which could be beneficial for complex implementations in a business setting.
4. [**State Channel as a Service Based on a Distributed and Decentralized Web - IEEE Xplore**](https://ieeexplore.ieee.org/iel7/6287639/8948470/09050808.pdf): This resource explores advanced applications of state channels, which could inspire innovative uses in various business models, including retail or service industries like a coffee shop.
5. [**An Incomplete Guide to Rollups**](https://vitalik.ca/general/2021/01/05/rollup.html)**:** Vitalik Buterin's 2021 Jan 05 article  to Rollups&#x20;
6. [**State Channels**](https://www.jeffcoleman.ca/state-channels/)**:** Jeff Coleman's article provides a comprehensive explanation of state channels and their components



