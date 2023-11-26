# 🧫 Data Availability Sampling

## What is Data Availability Sampling you ask?

It is one of the techniques to verify the availability of high volumes of data onchain without requiring any single node to personally download _all_ of the data.

Here each node (including light nodes that are not participating in staking) checks every blob, but instead of downloading the whole blob, they privately select N random indices in the blob and attempt to download the data at just those positions.

<figure><img src="../../../.gitbook/assets/F4TSJV1bQAAzeYH (1).png" alt=""><figcaption><p>Illustration from <a href="https://hackmd.io/@vbuterin/sharding_proposal">hackmd</a></p></figcaption></figure>

#### We want to achieve two goals here:

### 0-50%

First, we want to make sure that at least half of the data in each blob is available, and we reject any blob that doesn’t match this.

#### How?

If less than half of the data is available, then it is almost certain that at least one of the indices of any given client samples will not be available. Dankrad Feist, one of the brains from the Ethereum Foundation behind this tech, says the odds of messing this up after downloading 100 random bits is a tiny 10^-30!

### 51-99%

Now let’s say a bad blob that has 51% to 99% of the data available sneaks past the first step. Here is where Erasure Coding comes in handy.

#### Imagine this:&#x20;

If you've got two dots on a graph, you can figure out every other point on the line connecting them, right? Similarly, these blobs are encrypted in a way that if at least half of the data, anyone in the network can fill in the gaps and share the full picture! 🧩➡️🖼️”
