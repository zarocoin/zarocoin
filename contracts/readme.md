# ZARO Token Smart Contract

This folder contains the verified implementation details of the $ZARO ERC-20 token smart contract. The contract was deployed using [Thirdweb](https://thirdweb.com), utilizing their audited `TokenERC20` module.

---

## 🔗 Contract Links

- **Etherscan Contract Page**  
  [0xc311FD6DA9686507F33991543d8158EF5FaDd5E7](https://etherscan.io/address/0xc311FD6DA9686507F33991543d8158EF5FaDd5E7)

- **Thirdweb Deployment Page**  
  [thirdweb.com/team/zaroverse/ZARO-Coin-663217](https://thirdweb.com/team/zaroverse/ZARO-Coin-663217)

- **Minimal Proxy Source**  
  Linked to audited implementation:  
  [`0x071b36bce6a1e1693a864b933275fc3775fc7cc9`](https://etherscan.io/address/0x071b36bce6a1e1693a864b933275fc3775fc7cc9)

---

## ✅ Contract Details

- **Standard**: ERC-20  
- **Token Name**: Zaro Coin  
- **Token Symbol**: ZARO  
- **Decimals**: 18  
- **Max Supply**: 1,000,000,000 ZARO  
- **Deployer Address**: [Zaro Treasury Wallet](https://etherscan.io/address/0xb285d8a3207D44a77444A333bdf02c7922A0a63F)  
- **Ownership Status**: Not renounced (to be updated post-launch)

---

## 🧾 Verified Source

The contract uses the audited `TokenERC20` template by Thirdweb, compiled with:

- **Compiler**: Solidity v0.8.23+commit.f704f362  
- **EVM Version**: London  
- **Optimization**: Enabled, 20 runs  
- **License**: Apache 2.0

ASCII logo and attribution clearly indicate Thirdweb provenance in the source.

---

## 🛡️ Security

The contract code inherits directly from an audited implementation verified by OpenZeppelin through Thirdweb. The deployment includes no custom logic, no privileged backdoors, and no transfer taxes.  

Ownership will be **renounced** after liquidity lock and OTC execution are complete.

---

## 📦 Deployment Events

| Event | Description | Link |
|-------|-------------|------|
| Token Mint | Minted 1B ZARO to treasury | [Tx Hash](https://etherscan.io/tx/…) |
| Liquidity Pool | Coming soon | - |
| Contract Renounce | Coming soon | - |

---

