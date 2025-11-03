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

## 🔒 Treasury Holdings
- Remaining tokens held in Treasury: **505,000,000 ZARO**
- ❌ No presale  
- ❌ No team wallet  
- ❌ No VC allocation  

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

## ✅ What’s Next
- [ ] Centralized Exchange Listings (underway)
- [ ] GitHub archive & badge verification




### 2025-07-20 – Founder Liquidity Addition (Uniswap V4)

**Wallet**: [0x984e23643acABDd447E8969ba08aaE6120A9bC8b](https://etherscan.io/address/0x984e23643acABDd447E8969ba08aaE6120A9bC8b)  
**ETH Added**: 5.0 ETH  
**ZARO Added**: 40,074,191.65 ZARO  
**Platform**: Uniswap V4  
**Transaction Hash**: [0xe6a5ef9c97eca67272769cfb44f4a2d1fb587c73b7fbcc3e50c8c6363ef2d4f3](https://etherscan.io/tx/0xe6a5ef9c97eca67272769cfb44f4a2d1fb587c73b7fbcc3e50c8c6363ef2d4f3)  
**NFT Position ID**: 38455  
**LP Token Holder**: 0x984e2364...bc8b  
**LP Lock Status**: Not locked — but publicly pledged: no withdrawal before $5M MC or without 30-day public notice  
**Statement**:  
> “I am very happy to own ZARO and ETH. The best of both worlds.”

---

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
| **Source Tx (Ethereum, Attestation)** | **(to be added)** → see “How to fetch the attestation tx” below |
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
