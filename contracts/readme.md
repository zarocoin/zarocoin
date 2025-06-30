# ZARO Token Smart Contract

This folder documents the official smart contract for the $ZARO ERC-20 token. It was deployed using [Thirdweb](https://thirdweb.com), utilizing their audited `TokenERC20` implementation, without any custom modifications.

---

## 🔗 Contract Links

- **Etherscan Contract Address**  
  [`0xc311FD6DA9686507F33991543d8158EF5FaDd5E7`](https://etherscan.io/address/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)

- **Thirdweb Deployment View**  
  [`thirdweb.com/team/zaroverse/ZARO-Coin-663217`](https://thirdweb.com/team/zaroverse/ZARO-Coin-663217)

- **Underlying Proxy Implementation**  
  [`0x071b36bce6a1e1693a864b933275fc3775fc7cc9`](https://etherscan.io/address/0x071b36bce6a1e1693a864b933275fc3775fc7cc9)

---

## ✅ Token Parameters

- **Token Name**: ZARO Coin  
- **Token Symbol**: ZARO  
- **Network**: Ethereum Mainnet  
- **Standard**: ERC-20  
- **Decimals**: 18  
- **Total Supply**: 1,000,000,000 ZARO  
- **Treasury Wallet**: [`0xb285dcc3A547e5649dfEa8E10134C322c67a63fC`](https://etherscan.io/address/0xb285dcc3A547e5649dfEa8E10134C322c67a63fC)  
- **Ownership**: Admin rights held by Treasury until renouncement

---

## 🧾 Source Details

- **Compiler**: Solidity v0.8.23  
- **EVM Version**: London  
- **Optimization**: Enabled (20 runs)  
- **License**: Apache 2.0  
- **Verification**: ✅ Verified & published on Etherscan

This contract is a minimal proxy that inherits all logic from a Thirdweb-audited base, making it secure and immutable once ownership is renounced.

---

## 🔒 Security & Admin

- ✅ No minting allowed post-deployment  
- ✅ No burn function  
- ✅ No transfer tax or blacklist logic  
- ✅ Transferability is unrestricted  
- 🔜 Ownership to be renounced post-launch and liquidity lock

---

## ⛓️ Deployment Timeline

| Step                  | Status | Reference |
|-----------------------|--------|-----------|
| Initial Mint (1B ZARO) | ✅ Complete | [Tx](https://etherscan.io/tx/…) |
| OTC Transfer (195M)    | ✅ Complete | [Tx](https://etherscan.io/tx/…) |
| LP Setup (300M + 6 ETH) | 🔜 Pending |  |
| Ownership Renounce     | 🔜 After LP Lock |  |

---

This contract is the core of the ZARO token ecosystem. All changes will be visible on-chain and documented in the `docs/transparency/` folder.

