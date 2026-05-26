# ZARO Transparency Summary

Current state is at the top. The full chronological record is below.

---

## Current State

| Field | Value |
|---|---|
| Total supply | 1,000,000,000 ZARO — fixed, no mint function |
| Allocations | None — no presale, no team tokens, no VC round, no vesting schedule of any kind |
| Permanently locked LP | 300,000,000 ZARO in Uniswap V2 (UNCX, 255-year lock). Base LP burned to `0x000…dEaD`. Solana LP locked with no expiry (Meteora). |
| Non-locked supply | ~700,000,000 ZARO — every token acquired through market-price transactions |
| Pending unlock / vesting cliff | None |
| Contract ownership | Renounced — owner is the zero address |
| Mintable | No |

On-chain reference: [Etherscan token page](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)

---

## Supply: Two Categories

There are **no allocations**. Every ZARO falls into one of two categories.

| Category | Amount | Notes |
|---|---|---|
| Permanently locked LP (Uniswap V2, UNCX 255-year lock) | 300,000,000 | Cannot be withdrawn by anyone — including the company or the founder. [Lock TX →](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581) |
| Market-acquired | ~700,000,000 | Held across many wallets. Every token was purchased at the same per-token price publicly available on Uniswap. No free distribution has ever occurred. |
| Team / VC / presale allocation | 0 | None has ever existed. |
| **Total supply** | **1,000,000,000** | Fixed. No mint function. |

Live distribution: [Etherscan holders](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7#balances) · [CoinGecko](https://www.coingecko.com/en/coins/zaro-coin) · [CoinMarketCap](https://coinmarketcap.com/currencies/zaro-coin/)

---

## Key Addresses

| | Address |
|---|---|
| Token contract | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` |
| Uniswap V2 pool (locked LP) | `0x53085839a2ee860e58108665825fc7ef5e061213` |

---

## Contract and LP Verification

| Event | Proof |
|---|---|
| Ownership renounced | [TX on Etherscan](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a) |
| LP locked 255 years (UNCX) | [TX on Etherscan](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581) |
| Audit (Thirdweb ERC-20, OpenZeppelin) | [Audit report PDF](https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf) |

---

---

## Chronological Record

The sections below document the full project history. If you only needed the current state, you already have it above.

---

### Deployment — June 29, 2025

- 1,000,000,000 ZARO minted to the treasury wallet at contract creation
- Contract template: Thirdweb ERC-20 (OpenZeppelin-based, audited)
- Ownership temporarily retained for LP setup, then permanently renounced
- No presale, no ICO, no private sale, no team allocation of any kind

### Liquidity Pool — June 29, 2025

- 300,000,000 ZARO + 6 ETH deployed to Uniswap V2 at launch
- Initial price: 0.00000002 ETH per ZARO
- LP tokens locked for 255 years via UNCX on the same day
- [Lock TX on Etherscan](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)

### Ownership Renounced — June 29, 2025

Contract ownership permanently renounced immediately after LP setup. Owner is now the zero address. No further changes can be made by any party.

[TX on Etherscan](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)

### Founder Market-Price Acquisition — July 2025

The founder of ZaroVerse Ltd (Shihab Khalil) purchased 195,000,000 ZARO from the company at 0.00000002 ETH per token — the same price publicly available on the Uniswap pool at that date. Payment was 3.9 ETH directly to the company wallet. No tokens were granted or allocated for free.

- 3.9 ETH payment (founder → company): [TX on Etherscan](https://etherscan.io/tx/0x8bfec6c0fa1ebcf416bf1225bc55cef134b3190c38b2c6a79e94b7cb08d26e9d)
- 195M ZARO received (company → founder): [TX on Etherscan](https://etherscan.io/tx/0x06a3c67288ef42e28fb4b0b6d7b56e6f80a09889f59e27dd78ecd26480681afd)

### Cross-Chain Expansion — November 2025

ZARO expanded to BNB Smart Chain (November 2, 2025) and Solana (November 9, 2025) via Wormhole. Full technical details in the cross-chain sections below.

### Post-Launch Market Activity — December 2025 and February 2026

A portion of the non-locked supply changed hands through open-market activity. The company subsequently reacquired the equivalent supply through direct on-chain purchases from the Uniswap pool and direct settlements with original buyers at their original acquisition prices, funded entirely from personal capital. Total supply remained 1,000,000,000 throughout — no tokens were created or destroyed.

Full record: [zarocoin.xyz/buyback](https://www.zarocoin.xyz/buyback) · [zarocoin.xyz/history](https://www.zarocoin.xyz/history)

### Base Expansion — May 2026

ZARO expanded to Base via OP Stack Standard Bridge (May 23, 2026). Full technical details in the Base section below.

---

---

## Cross-Chain Extension: BNB Smart Chain (via Wormhole)

**Overview**  
On **Nov 2, 2025 (UTC)**, ZARO expanded from Ethereum to **BNB Smart Chain (BSC)** via the **Wormhole Portal** bridge. Supply integrity is preserved: every ZARO on BSC is backed 1:1 by locked ERC-20 ZARO on Ethereum (no new supply minted outside the bridge).

---

### Technical Summary

| Item | Detail |
|---|---|
| **Bridge Protocol** | Wormhole (Portal) |
| **Bridge Wallet** | `0x485e2305E953558a2ef959ce9C4FFa317e502BAB` (ZARO Wormhole Bridge Wallet) |
| **Origin Token (Ethereum)** | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` (Etherscan) |
| **Destination Token (BSC)** | `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc` (BscScan) |
| **Wormhole Token Bridge (BSC)** | `0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7` |
| **Redeem/Mint Tx (BSC)** | `0x9090d5140b887c3efb5188b0f79b38bdbc9f2a15cdbd407b68ba6798e44541e2` |
| **Additional Bridge Tx (BSC)** | `0x7e821ed5f9fe2ee0d2d3e3b9d03937ea16879ea729aa649734db29b7324368e2` |
| **Total Bridged to BSC (to date)** | **1,025,000 ZARO** (25k test + 1,000,000 main) |
| **Date/Time (UTC)** | 2025-11-02 |

---

### PancakeSwap Liquidity (BSC)

| Item | Detail |
|---|---|
| **Exchange** | PancakeSwap V2 |
| **Pair** | **ZARO / WBNB** |
| **Pair Address** | `0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4` |
| **Liquidity Creation Tx** | `0x22863fc0d2fadc81518e87dee15461e58623ec55870ff968d665d54453f9e4c7` |
| **Amounts Added** | 1,025,000 ZARO + 0.959376 BNB |
| **Reference Price (ETH Uniswap)** | $0.0009861 per ZARO |
| **Implied Pool Price (BSC at init)** | ~$0.001008 per ZARO |
| **LP Holder** | ZARO Wormhole Bridge Wallet |

---

### Public Verification Links

- **BSC Token (ZARO, via Wormhole):** `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc`  
- **Pancake v2 Pair (ZARO/WBNB):** `0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4`  
- **BSC Redeem/Mint Tx:** `0x9090d5…e44541e2`  
- **BSC Additional Bridge Tx:** `0x7e821e…24368e2`  
- **DEX Screener (BSC pair):** https://dexscreener.com/bsc/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4  

> **Note:** Wormhole contract addresses are documented here for reference: Ethereum core/token bridge and BNB token bridge are listed in Wormhole's official contract reference.  

---

### Verification Notes

- The BSC token is a Wormhole-wrapped twin of the Ethereum ERC-20 ZARO; no extra supply was created.  
- **1,025,000 ZARO** are locked on Ethereum with an equal amount minted on BSC.  
- Initial BSC pool was aligned within ~2% of the Uniswap price to enable natural cross-chain arbitrage.  
- All transactions are on-chain and linked above.

---

### BSC Bridge Update — November 2025

As of Nov-03-2025, the ZARO Wormhole Bridge Wallet  
`0x485e2305E953558a2ef959ce9C4FFa317e502BAB`  
holds a cumulative **4,048,008.816 ZARO (BEP-20)** on BNB Smart Chain.  

Distribution snapshot (BscScan verified):  
- **Bridge Wallet:** 79.86 % (4,048,008 ZARO)  
- **PancakeSwap V2 ZARO/WBNB Pool:** 19.96 % (1,011,778 ZARO)  
- **Other wallets:** 0.18 % combined  

Total unique holders: **5**  
Explorer link:  
https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc#balances  

This confirms a total of **~5.06 M ZARO bridged and circulating on BSC**, fully backed by locked ERC-20 ZARO on Ethereum.  
No new minting or supply inflation has occurred.


**Liquidity Update — Nov 3, 2025**

Additional liquidity was added to the PancakeSwap V2 ZARO/WBNB pool by the official Wormhole Bridge Wallet:

- Wallet: 0x485e2305E953558a2ef959ce9C4FFa317e502BAB  
- Pool: 0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4  
- Exchange: PancakeSwap V2  
- Add Liquidity Link: https://pancakeswap.finance/add/BNB/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc  
- Transaction log: https://bscscan.com/address/0x485e2305E953558a2ef959ce9C4FFa317e502BAB  

This transaction brings total BSC liquidity to approximately $2,000 (combined ZARO and BNB value).  
All actions were executed by the official ZARO Wormhole Bridge Wallet, with LP tokens held securely by the same wallet pending future lock.


---

## Cross-Chain Extension: Base (OP Stack Standard Bridge)

**Date:** 2026-05-23  
**Bridge:** OP Stack Standard Bridge (Coinbase / OP Labs)  
**Parent Token:** Ethereum `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7`  
**Base Contract (OptimismMintableERC20):** [`0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0`](https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0)

### Technical Summary

| Item | Detail |
|---|---|
| Bridge Protocol | OP Stack Standard Bridge (Coinbase / OP Labs) |
| Factory | `0x4200000000000000000000000000000000000012` (predeploy, audited) |
| L1StandardBridge (ETH) | `0x3154Cf16ccdb4C6d922629664174b904d80F2C35` |
| L2StandardBridge (Base) | `0x4200000000000000000000000000000000000010` |
| `REMOTE_TOKEN()` | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` (immutable — points to ETH origin) |
| Total Bridged | 10,000,000 ZARO (1% of total supply) |
| Deployer Wallet | `0x4B7a5e5a0119B011c5Ba112A84A3FB47C7c18802` (gas-only, now empty) |
| Contract auto-verified | ✅ via bytecode match on BaseScan |

### Bridge Transactions

| Step | TX |
|---|---|
| Test bridge (1,000 ZARO) | [`0x72b96e27...`](https://etherscan.io/tx/0x72b96e279ad1ecfe718c5caa005a70ae6efe3136bb015de8349d697a1337169f) |
| Main bridge (9,999,000 ZARO) | [`0x34974128...`](https://etherscan.io/tx/0x34974128cfb0465e3454dfa4f7bad4a0e589dff475f400dfb0d5310a0930bb2e) |

### Aerodrome Liquidity (Base)

| Item | Detail |
|---|---|
| Exchange | Aerodrome Finance |
| Pair | ZARO / WETH (volatile) |
| Pool Address | `0x55f0a6b67cae42f6a38f754ae7d814bcece1a80a` |
| BaseScan | https://basescan.org/address/0x55f0a6b67cae42f6a38f754ae7d814bcece1a80a |
| LP Status | **Burned** — LP tokens sent to `0x000000000000000000000000000000000000dEaD` (permanent, no unlock possible) |
| LP Burn TX | [`0x2033eda6...`](https://basescan.org/tx/0x2033eda615044458b723fb9b7a2141ddcd6cc60d5bf9c7cde933c8d2e33da332) |

All bridged tokens correspond 1:1 with locked ERC-20 supply on Ethereum. No new tokens were minted or issued outside the canonical 1,000,000,000 ZARO supply.

---

## Cross-Chain Extension: Solana (Wormhole)

**Date:** 9 Nov 2025  
**Bridge:** Wormhole (Mainnet)  
**Parent Token:** Ethereum 0xc311FD6DA9686507F33991543d8158EF5FaDd5E7  
**Wrapped Token (SPL Mint):** [AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W](https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W)  
**Bridge destination wallet (Solana):** [GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ](https://solscan.io/account/GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ)  
**Bridge TX (Ethereum → Solana):** [0xac3641564d6d619575c0332969d90225ffb64ae2807992f4e862cd2720a4dd1f](https://wormholescan.io/#/tx/0xac3641564d6d619575c0332969d90225ffb64ae2807992f4e862cd2720a4dd1f?network=MAINNET)  
**Solana TX (Mint Redeem):** [5sj1b8NpoSvgbZrr1w9D6GYUC1FoiKTuRp2Luap67hnZyByr56m6aUBn2HkrK8EBYv2UeAiQVinggdy9YngCDUaF](https://solscan.io/tx/5sj1b8NpoSvgbZrr1w9D6GYUC1FoiKTuRp2Luap67hnZyByr56m6aUBn2HkrK8EBYv2UeAiQVinggdy9YngCDUaF)  
**Amount:** 1,010,000 ZARO (first mint)  
**Status:** ✅ Completed – confirmed via WormholeScan & SolScan  
**Bridge Custody:** 1:1 locked on Ethereum  

### Solana Bridge Status

**Total Bridged Supply:** 10,000,000 ZARO  
**Percentage of Total Supply:** 1% (out of 1,000,000,000 ZARO)

**Bridge Details:**
- **Bridge Used:** Wormhole v2  
- **Canonical Token (Ethereum):** 0xc311FD6DA9686507F33991543d8158EF5FaDd5E7  
- **Solana Mint:** AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W  
- **Destination Wallet:** Phantom Bridge Wallet  
  `GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ`

**Bridge Wallets:**
- ETH ↔ BNB: `0x485e2305E953558a2ef959ce9C4FFa317e502BAB`
- ETH ↔ Solana: `GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ`

**Transaction Summary:**
- 1,000,000 ZARO bridged on November 10, 2025  
- 9,000,000 ZARO bridged on November 11, 2025  
- Verified on Solscan:  
  https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W  

All bridged tokens correspond 1:1 with the locked ERC-20 supply on Ethereum.  
No new tokens were minted or issued outside the canonical 1,000,000,000 ZARO supply.
