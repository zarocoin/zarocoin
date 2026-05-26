# ZARO — Project Overview
**Version 2.0 — May 2026**

This document describes what ZARO is, how the project is structured, and where to find verifiable evidence for every claim made on the public site.

For the chronological record of every event since incorporation, see [zarocoin.xyz/history](https://www.zarocoin.xyz/history). For every on-chain receipt and external transparency document, see [zarocoin.xyz/proof](https://www.zarocoin.xyz/proof).

---

## 1. What ZARO Is

ZARO is a fixed-supply ERC-20 collectible deployed on Ethereum, bridged 1:1 to Base, BNB Chain, and Solana via audited bridges. Total supply is 1,000,000,000 — mathematically fixed by a renounced contract. The contract owner is the zero address. Liquidity is permanently locked or burned on every chain.

ZARO is the on-chain artifact of the **ZaroVerse** fictional universe — a transmedia IP being developed by ZaroVerse Ltd.

---

## 2. What ZARO Is Not

- Not a yield product
- Not a utility token
- Not a governance token
- Not a security under applicable law (independent BVI legal opinion by Drew Barnholtz, Esq.)
- Not sold by the company — trading occurs only via third-party decentralized exchanges
- Has no intrinsic value; the company makes no financial claims about it

---

## 3. Launch Structure

The launch was structured to leave no administrative control over the token in the company's hands:

- No presale, no ICO, no private sale
- No team allocation, no advisor allocation, no VC round
- 0% transfer tax on every chain
- Initial liquidity (300M ZARO + 6 ETH) seeded by the company and locked at UNCX for 255 years
- Contract ownership renounced to the zero address (post-launch transaction)
- The founder acquired 195M ZARO from the company treasury at the public launch price via an on-chain OTC transaction — same price as anyone else paid on the open market

---

## 4. Multi-Chain Architecture

| Chain | Role | Bridge | LP status |
|---|---|---|---|
| Ethereum | Origin | — | Locked 255 years via UNCX |
| Base | OP Stack L2 | OP Stack Standard Bridge | LP burned to `0x…dEaD` (permanent) |
| BNB Chain | Wormhole wrapped | Wormhole Token Bridge | PancakeSwap V2 pool |
| Solana | Wormhole wrapped | Wormhole Token Bridge | Meteora DLMM positions, locked |

The Ethereum cap (1,000,000,000) is enforced at the origin layer. No bridge can create new supply.

Per-chain security profiles: [/docs/security](../security)

---

## 5. Company

**ZaroVerse Ltd.** — British Virgin Islands company (BVI No. 2183451), incorporated August 1, 2025. Operates from the UAE.

**Founder & CEO:** Shihab Khalil. 25+ years in technology innovation. MBA, New York Institute of Technology. LLM in International Law and Global Leadership, Aristotle University. Also Founder & CEO of [ZagTrader](https://zagtrader.com) (founded 2009), an institutional fintech platform serving 100+ institutions across 25+ regulated markets. ZagTrader and ZaroVerse Ltd are operationally and legally separate.

Full founder bio: [zarocoin.xyz/founder](https://www.zarocoin.xyz/founder).

---

## 6. Supply and Liquidity

ZARO has no allocations. No team, no VC, no presale, no vesting, no insider distribution. None has ever existed.

Every ZARO that exists is in one of two categories:

1. **Permanently locked liquidity (300,000,000 ZARO + 6 ETH)** — seeded into Uniswap V2 at launch and locked at UNCX for 255 years. Cross-chain DEX pools on Base (LP burned), BNB Chain, and Solana (Meteora positions locked) hold a portion of bridged supply with the same permanence model per chain.

2. **Acquired through market-price transactions (~700,000,000 ZARO)** — distributed across many wallets including the company and the founder. Every wallet in this category holds supply that was paid for at the same per-token price publicly available on the Uniswap pool.

**The entire non-locked supply of ZARO has been paid for, in some cases twice.** After the December 2025 incident, the company executed a buyback funded from personal capital — OTC settlements at original buyer USD prices, plus open-market purchases through Uniswap. The founder's original 195M OTC position (acquired July 2025) was already paid for once at launch and paid for again during the response. See [zarocoin.xyz/buyback](https://www.zarocoin.xyz/buyback) for the full record.

The company does not sell ZARO. Holdings are not deployed for market-making or price activity.

Live circulating-supply data: [CoinGecko](https://www.coingecko.com/en/coins/zaro-coin) · [CoinMarketCap](https://coinmarketcap.com/currencies/zaro-coin/).

---

## 7. December 2025 Incident

In December 2025, the founder's wallet and a portion of the company treasury were compromised through malware (detail at [zarocoin.xyz/buyback](https://www.zarocoin.xyz/buyback)). The renounced contract, the 255-year LP lock, and the bridge backing were not affected — the structural defenses were not the breach point. A third-party forensic investigation was conducted by [Collisionless Global Technology Services Inc.](https://www.collisionless.io) and is published in full. The company subsequently executed a buyback over December 2025 – February 2026, funded from personal capital. The stolen supply was reacquired.

The renounced contract did not allow a single new token to be minted during or after the incident.

---

## 8. Holder Equality

In the ZARO ecosystem:

- No wallet has special rights
- The founder, the treasury, and any other holder are equal at the contract level
- No privileged wallets, no mint function accessible to any human key
- No party — including the founder — can alter the contract, mint new tokens, or change balances

All structural facts above are independently verifiable on-chain.

---

## 9. Documentation

| Document | Location |
|---|---|
| Transparency report | [/docs/transparency](../transparency) |
| Security profiles (per chain) | [/docs/security](../security) |
| BVI legal opinion | [/docs/legal](../legal) |
| CMY (White) Paper | [/docs/whitepaper](../whitepaper) |
| Trademarks & USPTO filings | [/docs/trademarks](../trademarks) |
| Founder messages | [/docs/founder-message](../founder-message) |
| December 2025 incident record | [/docs/security/incidents/2025-12-11-malware-compromise](../security/incidents/2025-12-11-malware-compromise) |

---

## 10. Technical Reference (Ethereum origin)

| Field | Value |
|---|---|
| Network | Ethereum (ERC-20) |
| Contract | [`0xc311FD6DA9686507F33991543d8158EF5FaDd5E7`](https://etherscan.io/token/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7) |
| Decimals | 18 |
| Supply | 1,000,000,000 (fixed) |
| Tax | 0% |
| Ownership | Renounced (owner = zero address) |
| Upgradeable | No (EIP-1167 minimal proxy of audited Thirdweb `TokenERC20`; not an upgradeable proxy) |
| Audit reference | [Thirdweb audit report #12](https://github.com/thirdweb-dev/contracts/blob/main/audit-reports/audit-12.pdf) |

**LP lock TX:** [`0xbb17a0d0…`](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581)
**Ownership renounce TX:** [`0x15e47399…`](https://etherscan.io/tx/0x15e4739956e05a80d03cd258eb6a35d7ace2406b7c49a99bc8aa7f7c8fbb3b8a)

---

## 11. Disclaimers

ZARO is a digital collectible with no intrinsic value. The contract is fully renounced. The company does not sell ZARO. Trading occurs only on third-party decentralized exchanges. Nothing in this document constitutes financial, legal, or tax advice. Users are responsible for compliance with applicable law in their jurisdiction.

---

[zarocoin.xyz](https://www.zarocoin.xyz) · [zaroverse.com](https://www.zaroverse.com) · [GitHub](https://github.com/zarocoin/zarocoin)
