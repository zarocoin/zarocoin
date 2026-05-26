# ZARO Chain Hierarchy

> **ETH proves it. Base trades it.**

This document defines the official chain hierarchy for the ZARO multi-chain deployment.

---

## The Three Tiers

### Tier 1 — Canonical Origin: Ethereum

| Field | Value |
|---|---|
| Role | Canonical origin. Reference market. Provenance chain. |
| Contract | `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` |
| Standard | ERC-20 (Thirdweb minimal proxy, OpenZeppelin-based, audited) |
| Supply enforcement | All 1,000,000,000 ZARO originate here. The hard cap is enforced at this layer and is immutable. |
| LP | 300,000,000 ZARO + 6 ETH in Uniswap V2, locked 255 years via UNCX — no unlock possible |
| Explorer | https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7 |
| DEX | https://app.uniswap.org/swap?outputCurrency=0xc311FD6DA9686507F33991543d8158EF5FaDd5E7&chain=mainnet |

**Why Ethereum is the canonical chain:** The 1,000,000,000 ZARO cap is enforced at the Ethereum layer. Contract ownership is permanently renounced — owner is the zero address. MINTER_ROLE and DEFAULT_ADMIN_ROLE have zero members. No entity can create new ZARO. All bridge-minted representations on other chains are 1:1 backed by locked supply here.

---

### Tier 2 — Primary Trading Rail: Base

| Field | Value |
|---|---|
| Role | Primary low-cost trading rail. Easy onramp for new holders. |
| Contract | `0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0` |
| Standard | OptimismMintableERC20 (canonical OP Stack bridge token, factory-deployed) |
| Bridge | OP Stack Standard Bridge (Coinbase / OP Labs) |
| Primary Pool | ZARO/USDC 0.01% Uniswap v3 — `0x768eafe02ae5845aef95546f3e086132dda254cf` |
| USDC Address | `0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913` (native USDC on Base) |
| Position NFT | #5191992 |
| Fallback Pool | Aerodrome ZARO/WETH (~0.3% volatile) — `0x55f0a6b67cae42f6a38f754ae7d814bcece1a80a` |
| Fallback LP | Permanently burned to `0x000…dEaD` — no unlock possible, ever |
| DexScreener | https://dexscreener.com/base/0x768eafe02ae5845aef95546f3e086132dda254cf |
| Explorer | https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0 |
| DEX | https://app.uniswap.org/swap?inputCurrency=0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913&outputCurrency=0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0&chain=base |

**Why Base is the primary trading rail:** Gas is a fraction of Ethereum mainnet. USDC pairing gives traders a stable denominator. The OP Stack bridge is audited Coinbase/OP Labs infrastructure. The `onlyBridge` modifier on `mint()` means only the canonical L2StandardBridge predeploy can mint — and only against locked supply on Ethereum. No human can call `mint()`.

**Note on BaseScan verification:** The contract was auto-verified via Similar Match (bytecode match). A support ticket has been filed with BaseScan to upgrade to Exact Match with constructor arguments, which will resolve the TokenSniffer "source code not verified" flag. The contract code and security properties are not affected by this metadata issue.

---

### Tier 3 — Maintained Bridged Representations: BNB Chain & Solana

Both chains are maintained for continuity. Existing liquidity is kept alive. Neither is promoted as a primary trading venue.

#### BNB Chain

| Field | Value |
|---|---|
| Role | Bridged representation (Wormhole) — maintained for existing holders |
| Contract | `0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc` |
| Bridge | Wormhole Token Bridge |
| DEX | PancakeSwap V2 |
| LP | Small pool (~hundreds USD) — maintained for price discovery / arbitrage candles |
| Explorer | https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc |

**Note:** `owner()` = Wormhole Token Bridge protocol contract, not the ZARO team. `mint()` is exclusively callable by the bridge with verified Guardian VAA messages. Wormhole architectural flags (proxy, ownership, mint authority) are inherent to the protocol — not project-specific risks.

#### Solana

| Field | Value |
|---|---|
| Role | Bridged representation (Wormhole) — maintained for existing holders |
| Mint | `AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W` |
| Bridge | Wormhole Token Bridge (Program-Derived Address mint authority) |
| DEX | Raydium |
| LP | Locked (Meteora DLMM, no expiry) |
| Explorer | https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W |

**Note:** Mint authority is a Wormhole PDA (`BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7`) — a program-derived address with no private key.

---

## Supply Accounting

```
Total Supply = 1,000,000,000 ZARO (Ethereum, immutable)

Ethereum  : canonical origin — all other chains draw from this
  └─ locked in Base bridge   : [variable] → minted on Base
  └─ locked in Wormhole      : [variable] → minted on BNB Chain
  └─ locked in Wormhole      : [variable] → minted on Solana
  └─ circulating on ETH      : remainder

SUM across all chains ≤ 1,000,000,000 ZARO. Always.
```

---

## Rationale

| Principle | Implementation |
|---|---|
| ETH is the only canonical chain | Supply, provenance, and immutability all enforced at the Ethereum layer |
| Base is the lowest-friction entry point | 0.01% fee, native USDC, near-zero gas, Coinbase infrastructure |
| BSC/Solana maintained, not promoted | Existing holders respected; not used for new-holder onboarding |
| Aerodrome Base pool | LP permanently burned to 0x000…dEaD — active as fallback pool; Uniswap v3 USDC is the primary |

---

_Last updated: 2026-05-26_  
_Full transparency record: [docs/transparency/readme.md](../transparency/readme.md)_  
_Per-chain security profiles: [docs/security/](../security/)_
