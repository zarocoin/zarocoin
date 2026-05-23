# ZARO — Security Overview

_Last updated: 2026-05-23_

This document is the canonical security reference for the ZARO token across all chains. It is intended for security aggregators, listing platforms, auditors, and blockchain data providers. All claims are verifiable on-chain.

**Short version for security companies:** [Jump to summary →](#summary-for-security-reviewers)

---

## The One-Billion Rule

ZARO has a fixed, immutable supply of **1,000,000,000 tokens**, minted once on Ethereum. Every token on Base, BNB Chain, and Solana is a 1:1 bridge mirror — it exists only because an equal amount is simultaneously locked in bridge custody on Ethereum. The bridges cannot create new supply; they can only move supply across chains. The 1B cap is enforced at the Ethereum layer and is permanent.

```
Total Supply = 1,000,000,000 ZARO (Ethereum, immutable)

Ethereum  : 1,000,000,000  (origin — all other chains draw from this)
  └─ locked in Base bridge  : 10,000,000  →  minted on Base
  └─ locked in Wormhole     : ~11,000,000 →  minted on BNB Chain
  └─ locked in Wormhole     : 10,000,000  →  minted on Solana
  └─ circulating on ETH     : remainder

SUM across all chains ≤ 1,000,000,000 ZARO. Always.
```

---

## Contracts — Quick Reference

| Chain | Address | Bridge | Explorer |
|---|---|---|---|
| **Ethereum** (origin) | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` | None | [Etherscan](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7) |
| **Base** | `0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0` | OP Stack Standard Bridge | [BaseScan](https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0) |
| **BNB Chain** | `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc` | Wormhole Token Bridge | [BscScan](https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc) |
| **Solana** | `AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W` | Wormhole Token Bridge | [Solscan](https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W) |

---

## Per-Chain Security Profiles

Full on-chain proof, architecture details, and flag-by-flag responses:

- 🔗 [Ethereum — Origin Contract](./ethereum.md)
- 🔗 [Base — OP Stack Bridge Mirror](./base.md)
- 🔗 [BNB Chain — Wormhole Bridge Mirror](./bnb-chain.md)
- 🔗 [Solana — Wormhole Bridge Mirror](./solana.md)

---

## Summary for Security Reviewers

The five most common flags — addressed at the system level:

### 1. Proxy contract
- **Ethereum:** EIP-1167 minimal proxy (clone) — gas-efficient deployment pattern, **not upgradeable**. No admin key, no upgrade mechanism.
- **Base:** `OptimismMintableERC20` — standalone contract from OP Stack factory, **not upgradeable**.
- **BNB Chain / Solana:** Standard Wormhole wrapped token — **not an upgradeable proxy**. Bridge-ownership pattern ≠ proxy pattern.

### 2. Ownership renounced / no owner
- **Ethereum:** All roles (`MINTER_ROLE`, `DEFAULT_ADMIN_ROLE`) have zero members. Renounced via [`0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a`](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a).
- **Base:** No `owner()` function. No Ownable pattern.
- **BNB Chain:** `owner()` = Wormhole Token Bridge contract `0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7` — a smart contract, not a human wallet. Verifiable: `chainId()` = 4, `wormhole()` = `0x98f3c9e6E3fAce36bAAd05FE09d375Ef1464288B`.
- **Solana:** Mint authority = Wormhole PDA `BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7`. PDAs have no private key.

### 3. Hidden owner
No hidden owner on any chain. Every privileged address is a public, audited bridge contract — verifiable on-chain. The ZARO team holds zero privileged roles post-renouncement.

### 4. Mintable
Mint functions exist on bridged contracts but are **exclusively gated to bridge protocols**:
- **Ethereum:** `MINTER_ROLE` unassigned, `DEFAULT_ADMIN_ROLE` vacated — mint permanently inaccessible.
- **Base:** `mint()` only callable by L2StandardBridge `0x4200000000000000000000000000000000000010` (Coinbase/OP Labs predeploy). Verified via `BRIDGE()` on-chain.
- **BNB Chain:** `mint()` only callable by Wormhole Token Bridge `0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7`.
- **Solana:** SPL mint only via Wormhole PDA — requires verified Guardian VAA.

In all cases, minting requires equal supply to be locked on Ethereum first. Net supply across all chains remains ≤ 1,000,000,000.

### 5. Owner can change balance
No wallet can arbitrarily alter any balance. Bridge contracts that hold technical "owner" roles only mint/burn in response to verified, atomic cross-chain messages. There is no function on any chain that allows a human to target an arbitrary address and change its balance.

---

## Audit & Verification References

| Item | Link |
|---|---|
| Ethereum contract (Etherscan) | https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7 |
| Ownership renounce TX | https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a |
| Thirdweb audit report #12 | https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf |
| Base contract (BaseScan) | https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0 |
| OP Stack Standard Bridge docs | https://docs.optimism.io/builders/app-developers/bridging/standard-bridge |
| Wormhole audit (Halborn) | https://github.com/wormhole-foundation/wormhole/blob/main/audits/ |
| CoinGecko listing | https://www.coingecko.com/en/coins/zaro-coin |
| Blockaid confirmation | Available on request — shihab@zaroverse.com |

---

## Incident Advisories

- [Incidents Index](./incidents/readme.md)
- [2025-12-11 — Malware-Based Compromise (Green)](./incidents/2025-12-11-malware-compromise/readme.md)
