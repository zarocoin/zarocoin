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
- **Ownership**: Fully renounced — owner = zero address (June 29, 2025)

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
- ✅ Ownership fully renounced — owner = zero address

---

## ⛓️ Deployment Timeline

| Step                            | Status     | Reference |
|---------------------------------|------------|-----------|
| Initial Mint (1B ZARO)          | ✅ Complete | [Etherscan Tx](https://etherscan.io/tx/0x65fba18a825da8c68e45ea1f21303de94693928bded39307d3f25152f2ab5bfb) |
| Loan from Founder to Treasury (6 ETH) | ✅ Complete | [Etherscan Tx](https://etherscan.io/tx/0x9387c6744b156f7d1e3fc98ddad3972e456fa4f4b3623fe1296389f619681233) |
| OTC Payment (3.9 ETH from Founder to Treasury) | ✅ Complete | [Etherscan Tx](https://etherscan.io/tx/0x8bfec6c0fa1ebcf416bf1225bc55cef134b3190c38b2c6a79e94b7cb08d26e9d) |
| OTC Token Transfer (195M ZARO from Treasury to Founder) | ✅ Complete | [Etherscan Tx](https://etherscan.io/tx/0x06a3c67288ef42e28fb4b0b6d7b56e6f80a09889f59e27dd78ecd26480681afd) |
| LP Setup (300M ZARO + 6 ETH on Uniswap V2) | ✅ Complete | [LP Lock TX](https://etherscan.io/tx/0xbb17a0d05a167047fb478c9769badaed00fa40e964a54d2917181420d26f4581) — locked 255 years via UNCX |
| Ownership Renounce              | ✅ Complete | Owner = zero address — verified on Etherscan |

---

This contract is the core of the ZARO token ecosystem. All changes will be visible on-chain and documented in the `docs/transparency/` folder.

