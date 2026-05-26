# ZARO on Base — Security Profile

**Role:** Primary low-cost trading rail. Bridged mirror of the Ethereum origin contract via the OP Stack Standard Bridge (Coinbase/OP Labs infrastructure). Uniswap v3 ZARO/USDC 0.01% pool is the active trading pool.
**Contract:** [`0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0`](https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0)
**Standard:** ERC-20 · OptimismMintableERC20 · Base Mainnet (chainId 8453)
**Deployed:** 2026-05-23
**Primary Pool:** ZARO/USDC 0.01% Uniswap v3 — `0x768eafe02ae5845aef95546f3e086132dda254cf`
**Fallback Pool:** Aerodrome ZARO/WETH (~0.3% volatile) — LP permanently burned to `0x000…dEaD`

---

## Position in the ZARO System

```
ETHEREUM (origin) ──── L1StandardBridge locks ZARO ────→ BASE (L2StandardBridge mints mirror)
0xc311FD6DA9686507F33991543d8158EF5FaDd5E7              0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0
```

Every ZARO on Base represents ZARO locked on Ethereum in the L1StandardBridge (`0x3154Cf16ccdb4C6d922629664174b904d80F2C35`). The Base supply cannot exceed what has been locked on Ethereum. Any amount may be bridged at any time — the circulating Base supply is always verifiable on BaseScan and is always backed 1:1 on Ethereum.

---

## Contract Architecture

- **Contract type:** `OptimismMintableERC20` — the canonical bridged token standard used by every officially bridged token on Base, deployed via the OP Stack factory.
- **Factory:** [`0x4200000000000000000000000000000000000012`](https://basescan.org/address/0x4200000000000000000000000000000000000012) — predeploy, same address on every OP Stack chain. Audited by OP Labs / Coinbase.
- **Bridge:** [`0x4200000000000000000000000000000000000010`](https://basescan.org/address/0x4200000000000000000000000000000000000010) — L2StandardBridge predeploy. The **only** address that can call `mint()` or `burn()`.
- **`REMOTE_TOKEN()`:** `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` — hardcoded at deploy, immutable. Points directly to the ZARO Ethereum origin contract.
- **Auto-verified on BaseScan** via bytecode exact match (no manual verification needed — the factory produces a known, audited bytecode).

---

## Security Flags — Addressed

### 1. Proxy contract
This contract is **not an upgradeable proxy**. `OptimismMintableERC20` is a standalone ERC-20 implementation deployed directly by the factory — no implementation slot, no admin key, no `upgradeTo()`. The bytecode is fixed at deployment.

### 2. Ownership / no owner
`owner()` — this function does **not exist** in the contract. There is no Ownable pattern. The only privileged address is the L2StandardBridge (`0x4200...0010`), which is a network predeploy operated by Coinbase/OP Labs, not by the ZARO team.

### 3. Hidden owner
There is no owner — hidden or otherwise. The privileged bridge address (`0x4200...0010`) is a public, immutable, hardcoded network contract, verifiable by calling `BRIDGE()` on-chain.
- `BRIDGE()` → `0x4200000000000000000000000000000000000010` ✅
- `REMOTE_TOKEN()` → `0xc311FD6DA9686507F33991543d8158EF5FaDd5E7` ✅

### 4. Mintable
`mint()` exists and **can only be called by the L2StandardBridge** (`0x4200...0010`). This is enforced by the contract:

```solidity
modifier onlyBridge() {
    require(msg.sender == BRIDGE, "OptimismMintableERC20: only bridge can mint and burn");
    _;
}
```

Minting is only triggered by the bridge relaying a verified deposit from Ethereum L1. Every mint corresponds to an equal lock on Ethereum — net supply across all chains stays within the 1B hard cap. No human wallet — including the ZARO team — can call `mint()` directly.

### 5. Owner can change balance
No owner exists. The bridge can only mint or burn in direct response to a verified cross-chain message. It cannot target arbitrary wallets or amounts. There is no mechanism for any human to arbitrarily alter any address's balance.

---

## Supply Proof

| Item | Value |
|---|---|
| Current supply on Base | Verifiable live on [BaseScan](https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0) |
| Locked on Ethereum L1 | Equal amount in L1StandardBridge `0x3154Cf16ccdb4C6d922629664174b904d80F2C35` |
| Backing ratio | 1:1 enforced by bridge protocol |
| Total across all chains | ≤ 1,000,000,000 ZARO |

---

## Key Links

| Resource | Link |
|---|---|
| BaseScan token | https://basescan.org/token/0x1d4CeA73e212829d06B9a774d2e06be9DEe5AAB0 |
| Factory contract | https://basescan.org/address/0x4200000000000000000000000000000000000012 |
| L2StandardBridge | https://basescan.org/address/0x4200000000000000000000000000000000000010 |
| L1StandardBridge (ETH) | https://etherscan.io/address/0x3154Cf16ccdb4C6d922629664174b904d80F2C35 |
| OP Stack bridge docs | https://docs.optimism.io/builders/app-developers/bridging/standard-bridge |
| Uniswap v3 pool (ZARO/USDC 0.01%) | https://basescan.org/address/0x768eafe02ae5845aef95546f3e086132dda254cf |
| DexScreener (Base pool) | https://dexscreener.com/base/0x768eafe02ae5845aef95546f3e086132dda254cf |
| Uniswap position NFT #5191992 | https://app.uniswap.org/positions/v3/base/5191992 |
| Aerodrome fallback pool (ZARO/WETH ~0.3%, LP burned) | https://basescan.org/address/0x55f0a6b67cae42f6a38f754ae7d814bcece1a80a |
| Aerodrome LP burn TX | https://basescan.org/tx/0x2033eda615044458b723fb9b7a2141ddcd6cc60d5bf9c7cde933c8d2e33da332 |

---

_Parent document: [Security Overview](./readme.md) · Origin chain: [Ethereum](./ethereum.md) · Sibling chains: [BNB Chain](./bnb-chain.md) · [Solana](./solana.md)_
