# ZARO Transparency Summary

This document outlines the transparent and on-chain verified steps taken in the ZARO project launch.

---

## 🔑 Key Wallets
- **Treasury Wallet:** `0xb285dcc3A547e5649dfEa8E10134C322c67a63fC`
- **Token Contract:** `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7`
- **Uniswap V2 Pool Contract:** `0x53085839a2ee860e58108665825fc7ef5e061213`
- **UNCX Lock Transaction:** [View Final Lock on Etherscan](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)

---

## 🧱 Initial Deployment
- **Total Supply:** 1,000,000,000 ZARO (fixed)
- Contract created using **Thirdweb’s open-source**, audited ERC20 implementation
- Based on **OpenZeppelin** standards
- Ownership retained temporarily for LP setup, then **fully renounced**

---

## 🧑‍🚀 Founder Contribution
- Founder loaned **6 ETH** to the Treasury to seed the LP
- OTC Purchase: Founder paid **3.9 ETH** to Treasury for **195M ZARO** at the same public price (`0.00000002 ETH`)
- All transactions are **public and verifiable on-chain**
- Payment of 3.9 ETH from Founder to Treasury (195M ZARO @ 0.00000002 ETH OTC Deal): https://etherscan.io/tx/0x8bfec6c0fa1ebcf416bf1225bc55cef134b3190c38b2c6a79e94b7cb08d26e9d
- Received 195M ZARO from Treasury to Founder to complete the transaction: https://etherscan.io/tx/0x06a3c67288ef42e28fb4b0b6d7b56e6f80a09889f59e27dd78ecd26480681afd


---

## 💧 Liquidity Pool (Uniswap V2)
- LP created with **6 ETH** + **300M ZARO**
- **Initial price:** `0.00000002 ETH per ZARO`
- LP tokens are **permanently locked for 255 years** via UNCX
- 🔒 Lock Proof: [Final Lock Transaction on Etherscan](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)
- ⛓️ Status: Verified on UNCX dashboard

---

## 🔒 Initial Treasury Holdings (June 29, 2025)
- Tokens held in Treasury at launch: **505,000,000 ZARO**
- ❌ No presale
- ❌ No team allocation
- ❌ No VC allocation
- ❌ No vesting, no insider distribution

> **Post-December 2025 incident:** Treasury composition changed materially. The supply that was stolen on December 11, 2025 was reacquired through a buyback funded from personal capital (OTC settlements + open-market purchases through Uniswap). Outside the permanently locked 300M LP, every ZARO currently held by the company or the founder was paid for through capital deployed at market or original-buyer prices. Full record: [zarocoin.xyz/buyback](https://www.zarocoin.xyz/buyback). For current circulating-supply tracking: [CoinGecko](https://www.coingecko.com/en/coins/zaro-coin) · [CoinMarketCap](https://coinmarketcap.com/currencies/zaro-coin/).

---

## 🔍 Audit Reference
- Token contract is a minimal proxy of [Thirdweb ERC20 contract](https://github.com/thirdweb-dev/contracts)
- Thirdweb templates are audited by **OpenZeppelin**
- [Audit Report](https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf)

---

## 🚫 Ownership Renounced
- Ownership of the token contract was **permanently renounced**
- This ensures no further changes or upgrades can be made
- 🔗 [Renounce Transaction on Etherscan](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)

---


## 🟢 Cross-Chain Extension: BNB Smart Chain (via Wormhole)

**Overview**  
On **Nov 2, 2025 (UTC)**, ZARO expanded from Ethereum to **BNB Smart Chain (BSC)** via the **Wormhole Portal** bridge. Supply integrity is preserved: every ZARO on BSC is backed 1:1 by locked ERC-20 ZARO on Ethereum (no new supply minted outside the bridge).

---

### 🔹 Technical Summary

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

### 🔹 PancakeSwap Liquidity (BSC)

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

### 🔹 Public Verification Links

- **BSC Token (ZARO, via Wormhole):** `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc`  
- **Pancake v2 Pair (ZARO/WBNB):** `0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4`  
- **BSC Redeem/Mint Tx:** `0x9090d5…e44541e2`  
- **BSC Additional Bridge Tx:** `0x7e821e…24368e2`  
- **DEX Screener (BSC pair):** https://dexscreener.com/bsc/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4  

> **Note:** Wormhole contract addresses are documented here for reference: Ethereum core/token bridge and BNB token bridge are listed in Wormhole’s official contract reference.  

---

### 🔹 Verification Notes

- The BSC token is a Wormhole-wrapped twin of the Ethereum ERC-20 ZARO; no extra supply was created.  
- **1,025,000 ZARO** are locked on Ethereum with an equal amount minted on BSC.  
- Initial BSC pool was aligned within ~2% of the Uniswap price to enable natural cross-chain arbitrage.  
- All transactions are on-chain and linked above.

---
### 🔹 BSC Bridge Update — November 2025

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


## 🔵 Base Integration (OP Stack Standard Bridge)

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

## 🌐 Solana Integration (Wormhole)

**Date:** 9 Nov 2025  
**Bridge:** Wormhole (Mainnet)  
**Parent Token:** Ethereum 0xc311FD6DA9686507F33991543d8158EF5FaDd5E7  
**Wrapped Token (SPL Mint):** [AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W](https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W)  
**Treasury Wallet (ZaroVerse Ltd – Solana):** [GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ](https://solscan.io/account/GR2tgyBXv8gHxjuthCTtP5DPXzBuQJH9PBpixjW7mxzJ)  
**Bridge TX (Ethereum → Solana):** [0xac3641564d6d619575c0332969d90225ffb64ae2807992f4e862cd2720a4dd1f](https://wormholescan.io/#/tx/0xac3641564d6d619575c0332969d90225ffb64ae2807992f4e862cd2720a4dd1f?network=MAINNET)  
**Solana TX (Mint Redeem):** [5sj1b8NpoSvgbZrr1w9D6GYUC1FoiKTuRp2Luap67hnZyByr56m6aUBn2HkrK8EBYv2UeAiQVinggdy9YngCDUaF](https://solscan.io/tx/5sj1b8NpoSvgbZrr1w9D6GYUC1FoiKTuRp2Luap67hnZyByr56m6aUBn2HkrK8EBYv2UeAiQVinggdy9YngCDUaF)  
**Amount:** 1,010,000 ZARO (first mint)  
**Status:** ✅ Completed – confirmed via WormholeScan & SolScan  
**Bridge Custody:** 1:1 locked on Ethereum  
**Notes:** This marks the official expansion of ZARO to Solana via Wormhole. The wrapped SPL token inherits all transparency policies from the parent ERC-20.

### ✅ Solana Bridge Status

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

**Remarks:**
All bridged tokens correspond 1:1 with the locked ERC-20 supply on Ethereum.  
No new tokens were minted or issued outside the canonical 1,000,000,000 ZARO supply.  
This allocation (1%) is reserved for Solana-based liquidity, ecosystem growth, and multi-chain interoperability testing.
