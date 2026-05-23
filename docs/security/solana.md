# ZARO on Solana — Security Profile

**Role:** Bridged mirror of the Ethereum origin contract via the Wormhole Token Bridge.
**Mint address:** [`AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W`](https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W)
**Standard:** SPL Token · Wormhole Wrapped · Solana Mainnet
**Bridged:** 2025-11-09

---

## Position in the ZARO System

```
ETHEREUM (origin) ──── Wormhole locks ZARO ────→ SOLANA (Wormhole mints SPL mirror)
0xc311FD6DA9686507F33991543d8158EF5FaDd5E7      AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W
```

Every ZARO on Solana represents ZARO locked in Wormhole custody on Ethereum. The Solana supply is a 1:1 mirror; no new supply is created. As of deployment, 10,000,000 ZARO are bridged to Solana (1% of total supply), fully backed by an equal amount locked on Ethereum.

---

## Contract Architecture

- **Token type:** Wormhole-wrapped SPL token — standard program emitted by the Wormhole Token Bridge for every bridged Solana asset.
- **Mint authority:** [`BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7`](https://solscan.io/account/BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7) — the Wormhole Token Bridge **Program Derived Address (PDA)**. A PDA has no private key — it is controlled exclusively by the Wormhole bridge program logic, not by any human.
- **Metadata update authority:** Same PDA (`BCD75...EYMV7`). This address appears as "update authority" in some scanners — it is the Wormhole program, not the ZARO team.
- **Wormhole Token Bridge (ETH):** [`0x3ee18B2214AFF97000D974cf647E7C347E8fa585`](https://etherscan.io/address/0x3ee18B2214AFF97000D974cf647E7C347E8fa585) — holds the locked ZARO on Ethereum as backing.
- **Wormhole audit:** Audited by Halborn — [Wormhole audit reports](https://github.com/wormhole-foundation/wormhole/blob/main/audits/).
- **Mint trigger:** A signed VAA from the Wormhole Guardian network (19 independent validators). No single party can forge a VAA.

---

## Security Flags — Addressed

### 1. Proxy contract
Not applicable. Solana SPL tokens are not contracts in the EVM sense. The Wormhole-wrapped SPL token is a standard mint account controlled by the Wormhole bridge program. No proxy pattern exists.

### 2. Ownership / mint authority
Mint authority is `BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7` — a **Program Derived Address**. PDAs are derived deterministically from a program's ID and have no corresponding private key. **No one can sign transactions from this address.** Minting is only possible via the Wormhole bridge program invoking the PDA through its internal logic.

### 3. Hidden owner
There is no hidden owner. The mint authority PDA is public and its derivation path is defined by the open-source Wormhole program. The ZARO team has no authority over this address.

### 4. Mintable
The SPL mint is technically mintable, but only via the Wormhole bridge PDA, which requires a verified Guardian VAA, which requires the equivalent ZARO to be locked on Ethereum first. Net supply remains bounded by the 1B Ethereum cap.

### 5. Owner can change balance
No owner exists. The Wormhole PDA can only mint/burn in response to verified cross-chain messages. Arbitrary balance changes are not possible.

---

## Metadata Re-attestation Note

In May 2026, a Wormhole re-attestation was performed to correct the on-chain metadata name from an incorrect string to the canonical **"Zaro Coin"**. This is a standard Wormhole operation that updates cosmetic metadata only — it does not affect supply, mint authority, or any security parameter. The re-attestation itself is signed by the Wormhole Guardians.

---

## LP Lock Status

- **Meteora DLMM Pool:** [`3voEHD9BvxKSPVFhhTGweuuexcLEqf1PKd1i2h2CS9JT`](https://dexscreener.com/solana/3voEHD9BvxKSPVFhhTGweuuexcLEqf1PKd1i2h2CS9JT)
- **LP Status:** Both LP positions permanently locked on Meteora — verifiable on-chain.

---

## Supply Proof

| Item | Value |
|---|---|
| Bridged supply on Solana | 10,000,000 ZARO |
| Locked on Ethereum (Wormhole escrow) | 10,000,000 ZARO |
| Backing ratio | 1:1 enforced by Wormhole protocol |
| Total across all chains | ≤ 1,000,000,000 ZARO |

---

## Key Links

| Resource | Link |
|---|---|
| Solscan token | https://solscan.io/token/AbzXS6NfGvCtg5B1rqZ1JSfoDHkwTAeEYJkWkHhCe38W |
| Wormhole bridge (ETH) | https://etherscan.io/address/0x3ee18B2214AFF97000D974cf647E7C347E8fa585 |
| Wormhole bridge PDA | https://solscan.io/account/BCD75RNBHrJJpW4dXVagL5mPjzRLnVZq4YirJdjEYMV7 |
| Bridge TX (ETH→SOL) | https://wormholescan.io/#/tx/0xac3641564d6d619575c0332969d90225ffb64ae2807992f4e862cd2720a4dd1f?network=MAINNET |
| Meteora DLMM pool | https://dexscreener.com/solana/3voEHD9BvxKSPVFhhTGweuuexcLEqf1PKd1i2h2CS9JT |
| Wormhole audit (Halborn) | https://github.com/wormhole-foundation/wormhole/blob/main/audits/ |

---

_Parent document: [Security Overview](./readme.md) · Origin chain: [Ethereum](./ethereum.md) · Sibling chains: [Base](./base.md) · [BNB Chain](./bnb-chain.md)_
