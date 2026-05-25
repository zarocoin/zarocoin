# ZARO on Ethereum — Security Profile

**Role:** Origin contract. Single source of truth for the entire 1,000,000,000 ZARO supply.
**Contract:** [`0xc311FD6DA9686507F33991543d8158EF5FaDd5E7`](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)
**Standard:** ERC-20 · Solidity 0.8.23 · Ethereum Mainnet

---

## Position in the ZARO System

```
ETHEREUM (origin) ─── locks ZARO ──→ BASE (OP Stack bridge mints mirror)
                  ─── locks ZARO ──→ BNB CHAIN (Wormhole mints mirror)
                  ─── locks ZARO ──→ SOLANA (Wormhole mints mirror)
```

All supply originates here. Tokens on other chains only exist because an equivalent amount is simultaneously locked in the bridge escrow on Ethereum. If the bridges unwound tomorrow, every token would return here. The 1,000,000,000 cap is enforced at this layer and is immutable.

---

## Contract Architecture

- **Framework:** [Thirdweb `TokenERC20`](https://github.com/thirdweb-dev/contracts/blob/main/contracts/prebuilts/token/TokenERC20.sol)
- **Base libraries:** OpenZeppelin (ERC20, AccessControl, Pausable)
- **Proxy pattern:** EIP-1167 Minimal Proxy (clone) — **not upgradeable**
- **Implementation:** [`0x071b36bce6a1e1693a864b933275fc3775fc7cc9`](https://etherscan.io/address/0x071b36bce6a1e1693a864b933275fc3775fc7cc9)
- **Audit:** Thirdweb Audit Report #12 — [PDF](https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf). No modifications to the audited implementation.

---

## Security Flags — Addressed

### 1. Proxy contract
ZARO uses an EIP-1167 minimal proxy (clone). This is a **deployment pattern for gas efficiency, not upgradeability**. There is no admin key, no upgrade mechanism, and no `upgradeTo()` function. The implementation address is fixed at creation and cannot be changed. This is categorically different from an upgradeable proxy (EIP-1967/UUPS/Transparent).

### 2. Ownership renounced
- `DEFAULT_ADMIN_ROLE` was revoked from the deployer wallet post-launch via `RoleRevoked` event.
- All roles (`MINTER_ROLE`, `DEFAULT_ADMIN_ROLE`) have zero members.
- **Renounce TX:** [`0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a`](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)
- Verify live: [Etherscan Read Contract → `hasRole`](https://etherscan.io/address/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7#readContract)

### 3. Hidden owner
No owner exists. `DEFAULT_ADMIN_ROLE` is permanently vacated. No wallet — including the deployer — can grant new roles, change supply, or pause the contract.

### 4. Mintable
The `mint()` function exists in the OpenZeppelin base code but is **permanently inaccessible**:
- `MINTER_ROLE` has zero members (on-chain verifiable)
- `DEFAULT_ADMIN_ROLE` has zero members — no one can assign `MINTER_ROLE`
- Ownership is renounced — roles cannot be granted post-deployment

The function exists in source; the access controls that gate it are irrevocably empty.

### 5. Owner can change balance
No owner exists. No wallet has any privileged role. No balance-altering function (`mint`, `burn`, `pause`) is accessible to any human key.

---

## Supply & Liquidity

| Item | Detail |
|---|---|
| Total supply | 1,000,000,000 ZARO (fixed, immutable) |
| Uniswap V2 LP | 300M ZARO + 6 ETH — locked 255 years via UNCX |
| Lock TX | [`0xbb17a0d0...`](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581) |
| Treasury wallet | [`0xb285dcc3A547e5649dfEa8E10134C322c67a63fC`](https://etherscan.io/address/0xb285dcc3A547e5649dfEa8E10134C322c67a63fC) |
| Bridge escrow (BSC + SOL) | ~11M ZARO locked in Wormhole custody |
| Bridge escrow (Base) | 10M ZARO locked in L1StandardBridge |

---

## Key Links

| Resource | Link |
|---|---|
| Etherscan token | https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7 |
| Thirdweb source | https://github.com/thirdweb-dev/contracts/blob/main/contracts/prebuilts/token/TokenERC20.sol |
| Audit report | https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf |
| Renounce TX | https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a |
| LP lock TX | https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581 |
| CoinGecko | https://www.coingecko.com/en/coins/zaro-coin |

---

_Parent document: [Security Overview](./readme.md) · Sibling chains: [Base](./base.md) · [BNB Chain](./bnb-chain.md) · [Solana](./solana.md)_
