## Incident Advisories
- [Incidents Index](./incidents/README.md)
- [2025-12-11 — Malware-Based Compromise (Green)](./incidents/2025-12-11-malware-compromise/README.md)
- 


# ZARO Smart Contract Security Profile & Transparency Report

_Last Updated: July 15, 2025_

This document provides a comprehensive technical overview of the ZARO token’s smart contract design, ownership status, supply configuration, minting logic, proxy behavior, and liquidity protections. It is intended as a verifiable, neutral reference for listing platforms, security aggregators, auditors, and blockchain data providers.

---

## ✅ Contract Overview

- **Token Name:** ZARO Coin (ZARO)
- **Network:** Ethereum (ERC-20)
- **Contract Address:** [0xc311FD6DA9686507F33991543d8158EF5FaDd5E7](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)
- **Total Supply:** 1,000,000,000 ZARO (fixed and immutable)
- **Decimals:** 18
- **Taxes:** None  
- **Team Wallet:** None  
- **VC Allocation:** None  

---

## 🔒 Ownership & Role Management

- **Ownership is Renounced**
  - `owner()` returns: `0x0000000000000000000000000000000000000000`
  - Renouncement confirmed via `RoleRevoked` event removing default admin from deployer wallet
  - **Renounce TX:** [0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)

- **No Roles Assigned**
  - All sensitive roles (`MINTER_ROLE`, `DEFAULT_ADMIN_ROLE`) return `0` members
  - No minting or admin functions are accessible

➡️ [Verify via Etherscan Read Contract Tab](https://etherscan.io/address/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7#readContract)

---

## 🧬 Contract Architecture & Audit Trail

- **Implementation Source:**  
  [`TokenERC20.sol`](https://github.com/thirdweb-dev/contracts/blob/main/contracts/prebuilts/token/TokenERC20.sol)

- **Framework:** Thirdweb  
- **Base Libraries:** OpenZeppelin (ERC20, AccessControl, Pausable)

- **Audit Coverage:**  
  - Thirdweb Audit Report #12 – [Audit PDF](https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf)  
  - No modifications were made to the audited implementation

---

## 🔄 Proxy Behavior

- **Proxy Type:** EIP-1167 Minimal Proxy (Clone)  
- **Upgradeability:** None (implementation is fixed)  
- **Implementation Address:** `0x071b36bce6a1e1693a864b933275fc3775fc7cc9`  
- **Confirmed on:** [Etherscan Code Tab](https://etherscan.io/address/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7#code)

> ZARO uses a gas-efficient, non-upgradeable proxy pattern with no admin, beacon, or upgrade mechanism.

---

## 🚫 Mint Functionality

- The inherited code includes a `mint()` function (from OpenZeppelin standards)
- However:
  - `MINTER_ROLE` is unassigned
  - Ownership is renounced
  - Roles cannot be granted post-deployment

**Conclusion:**  
> The mint function is **present in code but permanently disabled by design**. The token is effectively hard-capped.

---

## 🔐 Liquidity Lock & Treasury Transparency

- **Liquidity Lock:**  
  - 300M ZARO + $15K ETH paired on Uniswap V2  
  - Liquidity pool tokens permanently locked  
  - 🔒 [Lock TX Proof](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)

- **Treasury Wallet:**  
  [0xb285dcc3A547e5649dfEa8E10134C322c67a63fC](https://etherscan.io/address/0xb285dcc3A547e5649dfEa8E10134C322c67a63fC)  
  - Holds the remaining token supply  
  - Used for future CEX listings, rewards, and incentives  
  - Cannot alter token behavior in any way

- **Transparency Report:**  
  📂 [https://github.com/zarocoin/zarocoin/tree/main/docs/transparency](https://github.com/zarocoin/zarocoin/tree/main/docs/transparency)

---

## ✅ Final Summary

The ZARO smart contract is:

| Property               | Status           |
|------------------------|------------------|
| Mintable               | ❌ No             |
| Upgradeable            | ❌ No             |
| Owner Controlled       | ❌ No (Renounced) |
| Proxy Type             | ✅ EIP-1167 Clone |
| Liquidity Locked       | ✅ Yes (forever)  |
| Total Supply           | ✅ Fixed at 1B    |
| Audit Lineage          | ✅ Yes            |

> All facts are verifiable on-chain and supported by open-source code and public transactions.

---

## 📂 Additional Resources

- 🔎 [ZARO Contract on Etherscan](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)
- 📖 [Thirdweb ERC20 Contract](https://github.com/thirdweb-dev/contracts/blob/main/contracts/prebuilts/token/TokenERC20.sol)
- 🔐 [Renounce TX Proof](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)
- 🔐 [Liquidity Lock Proof](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)
- 📘 [Transparency Report](https://github.com/zarocoin/zarocoin/tree/main/docs/transparency)
