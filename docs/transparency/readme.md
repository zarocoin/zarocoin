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

**Overview:**  
On November 2 2025, ZARO officially expanded from Ethereum to **BNB Smart Chain (BSC)** through the verified **Wormhole Portal Bridge**.  
This extension maintains ZARO’s single, immutable supply of 1 billion tokens across all networks.  
Every ZARO bridged to BSC is fully backed 1:1 by locked ERC-20 ZARO on Ethereum, ensuring total transparency and supply integrity.

---

### 🔹 Technical Summary

| Item | Detail |
|------|---------|
| **Bridge Protocol** | Wormhole (Portal) |
| **Bridge Wallet** | `0x485e2305E953558a2ef959ce9C4FFa317e502BAB` |
| **Origin Token (Ethereum)** | [ZARO ERC-20 – 0xc311FD6DA9686507F33991543d8158EF5FaDd5E7](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7) |
| **Destination Token (BSC)** | [Wrapped ZARO (via Wormhole) – 0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc](https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc) |
| **Bridge Contract (BSC)** | [Wormhole Token Bridge – 0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7](https://bscscan.com/address/0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7) |
| **Attestation Tx (Ethereum)** | [0xdcb16067695a0a99329c41377113c9e45e6ed0225ec1f91387a015c6c25c1805](https://etherscan.io/tx/0xdcb16067695a0a99329c41377113c9e45e6ed0225ec1f91387a015c6c25c1805) |
| **Redeem Tx (BSC)** | [0x9090d5140b887c3efb5188b0f79b38bdbc9f2a15cdbd407b68ba6798e44541e2](https://bscscan.com/tx/0x9090d5140b887c3efb5188b0f79b38bdbc9f2a15cdbd407b68ba6798e44541e2) |
| **Additional Bridge Tx (BSC)** | [0x7e821ed5f9fe2ee0d2d3e3b9d03937ea16879ea729aa649734db29b7324368e2](https://bscscan.com/tx/0x7e821ed5f9fe2ee0d2d3e3b9d03937ea16879ea729aa649734db29b7324368e2) |
| **Amount Bridged** | 1 025 000 ZARO (25 000 test + 1 000 000 main) |
| **BNB Gas Used** | ≈ 0.000028 BNB (≈ $0.04) |
| **Date & Time (UTC)** | 2025-11-02 21:55 UTC |

---

### 🔹 PancakeSwap Liquidity Creation

| Item | Detail |
|------|---------|
| **Exchange** | PancakeSwap V2 |
| **Pair** | [ZARO / WBNB](https://pancakeswap.finance/info/v2/pair/0x53085839A2Ee860E58108665825Fc7Ef5e061213) |
| **Pair Contract** | [0x53085839A2Ee860E58108665825Fc7Ef5e061213](https://bscscan.com/address/0x53085839A2Ee860E58108665825Fc7Ef5e061213) |
| **Liquidity Tx** | [0x22863fc0d2fadc81518e87dee15461e58623ec55870ff968d665d54453f9e4c7](https://bscscan.com/tx/0x22863fc0d2fadc81518e87dee15461e58623ec55870ff968d665d54453f9e4c7) |
| **Amount Added** | 1 025 000 ZARO + 0.959376 BNB |
| **Reference Price (ETH Uniswap)** | $0.0009861 per ZARO |
| **Implied Pool Price (BSC)** | $0.001008 per ZARO |
| **Total Pool Value** | ≈ $2 075 |
| **LP Tokens Holder** | ZARO Wormhole Bridge Wallet |
| **DEX Screener Link** | [https://dexscreener.com/bsc/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4](https://dexscreener.com/bsc/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4) |

---

### 🔹 Verification Notes
- ZARO’s BNB Chain token is an official Wormhole-wrapped twin of the Ethereum ERC-20 ZARO.  
- 1 025 000 ZARO have been locked on Ethereum and an equal amount minted on BSC.  
- No additional tokens were created; the global supply remains exactly **1 000 000 000 ZARO**.  
- All transactions are verifiable on-chain through Etherscan and BscScan.  
- The BNB Chain pair was initialized to match the Ethereum Uniswap price within 2 %.  
- Future liquidity additions will be announced with Tx links and timestamps in this report.  

---

### 🔹 Cross-Chain Market Dynamics
ZARO liquidity is now active on **Ethereum (Uniswap V2)** and **BNB Chain (PancakeSwap V2)**.  
Prices between chains remain aligned through open-market arbitrage facilitated by the Wormhole bridge.  
No manual team rebalancing occurs; supply and liquidity are fully on-chain and verifiable.

---

### 🔹 Public Verification Links
- [ZARO on BscScan](https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc)  
- [Wormhole Bridge Contract (BSC)](https://bscscan.com/address/0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7)  
- [BNB Chain DEX Screener Pair](https://dexscreener.com/bsc/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4)  
- [Transparency Report Repository](https://github.com/zarocoin/zarocoin/tree/main/docs/transparency)

---

**Result:**  
ZARO is now verified and tradable on BNB Smart Chain through PancakeSwap, bridged via Wormhole, and fully documented on-chain.  
The project maintains its “one supply / one truth” principle across networks as part of its long-term cross-chain architecture.

---
