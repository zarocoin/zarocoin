# ZARO on BNB Chain — Security Profile

**Role:** Bridged mirror of the Ethereum origin contract via the Wormhole Token Bridge.
**Contract:** [`0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc`](https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc)
**Standard:** BEP-20 · Wormhole Wrapped Token · BNB Smart Chain (chainId 56)
**Bridged:** 2025-11-02

---

## Position in the ZARO System

```
ETHEREUM (origin) ──── Wormhole locks ZARO ────→ BNB CHAIN (Wormhole mints mirror)
0xc311FD6DA9686507F33991543d8158EF5FaDd5E7      0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc
```

Every ZARO on BNB Chain represents ZARO locked in Wormhole custody on Ethereum. The BNB supply is a 1:1 mirror; no new supply is created. As of the last update, approximately 11M ZARO are bridged to BNB Chain, fully backed by an equal amount locked on Ethereum.

---

## Contract Architecture

- **Contract type:** Wormhole Wrapped Token — standard contract emitted by the Wormhole Token Bridge for every bridged asset. Audited by Halborn (Wormhole audit).
- **Wormhole Token Bridge (BNB):** [`0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7`](https://bscscan.com/address/0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7) — the **only** address that can call `mint()`. Verifiable: `chainId()` = 4 (BNB in Wormhole's chain numbering), `wormhole()` = `0x98f3c9e6E3fAce36bAAd05FE09d375Ef1464288B` (Wormhole Core on BNB).
- **Wormhole Token Bridge (ETH):** [`0x3ee18B2214AFF97000D974cf647E7C347E8fa585`](https://etherscan.io/address/0x3ee18B2214AFF97000D974cf647E7C347E8fa585) — holds the locked ZARO on Ethereum as backing.
- **Mint trigger:** A signed Validator Action Approval (VAA) from the Wormhole Guardian network — a decentralized set of 19 independent validators. No single party, including ZARO, can forge a VAA.

---

## Security Flags — Addressed

### 1. Proxy contract
The Wormhole wrapped token is **not an upgradeable proxy**. It is a standard ERC-20 deployed by the Wormhole bridge — same bytecode for every bridged asset. No admin key, no upgrade mechanism.

### 2. Ownership
`owner()` returns `0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7` — the **Wormhole Token Bridge contract on BNB Chain**, not a human wallet. This is a smart contract operated by the Wormhole protocol, verifiable on-chain. The ZARO team has no ownership role.

### 3. Hidden owner
The "owner" (`0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7`) is a public, audited Wormhole protocol contract. It is not hidden — it is the bridge itself. Any security scanner flagging it as a "hidden owner" is misidentifying a well-known bridge contract as a suspicious wallet.

### 4. Mintable
`mint()` can only be called by `owner()` — i.e., the Wormhole Token Bridge contract. Minting is only triggered by a verified VAA from the Wormhole Guardians, which itself requires an equal amount to have been locked on Ethereum first. No human — including the ZARO team — can call `mint()`. This is identical behavior to every other Wormhole-bridged token (WBTC, WETH variants, etc.).

### 5. Owner can change balance
The Wormhole bridge contract that holds "owner" can only mint/burn in response to verified Guardian VAAs. It cannot target arbitrary wallets or arbitrary amounts. It is a protocol-enforced relay, not an admin key.

---

## `is_proxy` Flag Explanation

GoPlus and similar scanners flag Wormhole wrapped tokens as `is_proxy = true`. This is a known false positive that affects **every Wormhole-bridged token identically** — USDC, USDT, ETH, and thousands of others on BNB Chain carry the same flag when viewed through the same lens. The Wormhole wrapped token contract delegates calls to the bridge for mint/burn only — this is not an upgradeable proxy pattern.

---

## Supply Proof

| Item | Value |
|---|---|
| Bridged supply on BNB Chain | ~11,025,000 ZARO |
| Locked on Ethereum (Wormhole escrow) | Equal amount, 1:1 |
| Backing ratio | 1:1 enforced by Wormhole protocol |
| Total across all chains | ≤ 1,000,000,000 ZARO |

---

## Key Links

| Resource | Link |
|---|---|
| BscScan token | https://bscscan.com/token/0xa9D72F6C1490647DF20E8Fad3C136cA6AC42c2fc |
| Wormhole Token Bridge (BNB) | https://bscscan.com/address/0xB6F6D86a8f9879A9c87f643768d9efc38c1Da6E7 |
| Wormhole Token Bridge (ETH) | https://etherscan.io/address/0x3ee18B2214AFF97000D974cf647E7C347E8fa585 |
| Wormhole audit (Halborn) | https://github.com/wormhole-foundation/wormhole/blob/main/audits/ |
| PancakeSwap pool (ZARO/WBNB) | https://pancakeswap.finance/info/pairs/0xAB900B7D4fb0cce879F1c3A831b1c172af6f72F4 |
| Bridge TX (original mint) | https://bscscan.com/tx/0x9090d5140b887c3efb5188b0f79b38bdbc9f2a15cdbd407b68ba6798e44541e2 |

---

_Parent document: [Security Overview](./readme.md) · Origin chain: [Ethereum](./ethereum.md) · Sibling chains: [Base](./base.md) · [Solana](./solana.md)_
