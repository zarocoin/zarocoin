# Token Metadata and Listing Kits

This folder includes metadata required for token listing services like CoinMarketCap, CoinGecko, TrustWallet, and Etherscan.

## Chain Hierarchy

> **ETH proves it. Base trades it.**

| Chain | Role | Address | Standard | Explorer |
|---|---|---|---|---|
| Ethereum | Canonical origin · Reference market | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` | ERC-20 | [Etherscan](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7) |
| Base | **Primary trading rail** (Uniswap v3 ZARO/USDC 0.01%) | `0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0` | ERC-20 (OptimismMintableERC20) | [BaseScan](https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0) |
| BNB Chain | Bridged representation (Wormhole) | `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc` | BEP-20 (Wormhole) | [BscScan](https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc) |
| Solana | Bridged representation (Wormhole) | `AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W` | SPL (Wormhole) | [Solscan](https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W) |

## Active Trading Pools

| Chain | Pool | Pair | Fee | Pool Address |
|---|---|---|---|---|
| Base | Uniswap v3 | ZARO/USDC | 0.01% | `0x768eafe02ae5845aef95546f3e086132dda254cf` |
| Ethereum | Uniswap V2 | ZARO/WETH | — | `0x53085839a2ee860e58108665825fc7ef5e061213` |
| BNB Chain | PancakeSwap V2 | ZARO/WBNB | — | `0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4` |

## Token Parameters

- **Name:** Zaro Coin
- **Symbol:** ZARO
- **Decimals:** 18 (all EVM chains) · 8 (Solana)
- **Total Supply:** 1,000,000,000 ZARO (fixed, origin on Ethereum)
- **Website:** https://www.zarocoin.xyz
- **Logo PNG:** https://raw.githubusercontent.com/zarocoin/zarocoin/main/media/logos/ZARO_logo_2D.png
- **Logo SVG:** https://raw.githubusercontent.com/zarocoin/zarocoin/main/media/logos/zarocoin-logo-2d.svg
- **CoinGecko ID:** zaro-coin

Listing instructions and JSON metadata files are updated here.
