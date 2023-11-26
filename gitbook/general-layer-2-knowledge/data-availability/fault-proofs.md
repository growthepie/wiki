# ❌ Fault Proofs

## What are fraud-proofs?

Imagine a full node spots some shady business going on in the network. It can quickly whip up a tiny piece of evidence 📜 showing that something's off with a proposed state change. This evidence gets shared with everyone.



Now, our light nodes can use these fraud proofs to ditch any bad block headers. This keeps them in sync with the honest full nodes, ensuring a clean and truthful chain.



But here's the catch 🎣: Full nodes need to see the full transaction details. If a sneaky attacker with a bad block header, doesn't share the transaction info, full nodes are in a bind. They might sense something's fishy 🐟, but without the full data, they can't prove it. It's like knowing there's a thief but not having the security footage to prove it!
