---
description: Canonical chain coverage reference for growthepie origin_key values.
---

# Supported Chains And origin_key

The canonical live list of covered chains is `master.json.chains`. During this docs refresh on March 27, 2026, the live API exposed 31 chain entries, including aggregate entities such as `all_l2s` and `multiple`.

## Current Chain Entries

| origin_key | Name | chain_type |
| --- | --- | --- |
| `ethereum` | Ethereum Mainnet | `l1` |
| `all_l2s` | All L2s | `others` |
| `arbitrum` | Arbitrum One | `rollup` |
| `arbitrum_nova` | Arbitrum Nova | `others` |
| `base` | Base Chain | `rollup` |
| `celo` | Celo | `others` |
| `fraxtal` | Fraxtal | `others` |
| `gravity` | Gravity | `others` |
| `ink` | Ink | `rollup` |
| `linea` | Linea | `rollup` |
| `lisk` | Lisk | `others` |
| `loopring` | Loopring | `rollup` |
| `manta` | Manta Pacific | `others` |
| `mantle` | Mantle | `others` |
| `megaeth` | MegaETH | `others` |
| `metis` | Metis | `others` |
| `mode` | Mode Network | `others` |
| `optimism` | OP Mainnet | `rollup` |
| `plume` | Plume Network | `others` |
| `polygon_pos` | Polygon PoS | `others` |
| `ronin` | Ronin | `others` |
| `scroll` | Scroll | `rollup` |
| `soneium` | Soneium | `others` |
| `starknet` | Starknet | `rollup` |
| `taiko` | Taiko Alethia | `others` |
| `unichain` | Unichain | `rollup` |
| `worldchain` | World Chain | `others` |
| `zircuit` | Zircuit | `rollup` |
| `zksync_era` | ZKsync Era | `rollup` |

## Caveats

* Not every `origin_key` supports every metric.
* Aggregate entities such as `all_l2s` are useful for comparison but are not individual chains.

## Related Pages

* [What Is origin_key?](../core-concepts/what-is-origin-key.md)
* [Endpoint: master.json](../api-reference/master-json.md)
