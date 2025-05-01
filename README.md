# RebaseAI Token

RebaseAI is a dynamic ERC20 token with built-in rebase functionality that allows automatic adjustment of total supply based on market conditions. The contract is written in Solidity and deployable to any EVM-compatible blockchain (Ethereum, Arbitrum, Optimism, etc.).

## ✅ Features

- Compliant with ERC20 standard
- Supply can increase or decrease proportionally via `rebase()`
- Owner is anonymous at deployment (based on `msg.sender`)
- Ownership can be transferred after deployment
- Gas-efficient scaling using internal multipliers

## 🔁 How Rebase Works

The `rebase(int256 supplyDelta)` function allows the token supply to expand or contract. This adjusts all balances proportionally without affecting ownership percentages.

```solidity
function rebase(int256 supplyDelta) external onlyOwner
```

Supply changes:
- Positive `supplyDelta` → Inflation (e.g. +10%)
- Negative `supplyDelta` → Deflation (e.g. -5%)

## 🔐 Ownership

- The contract does **not** hardcode any owner address
- Ownership is initialized to `msg.sender`
- You may transfer ownership after deployment:

```solidity
transferOwnership("0xYourNewOwnerAddress")
```

## 🚀 Deployment (Hardhat Example)

```bash
npx hardhat run scripts/deploy.js --network mainnet
```

## 🛡 Security

- Only the owner can call `rebase()`
- No mint/burn fees or taxes included
- Transparent and open-source logic

## 📄 License

This project is open-source and released under the [MIT License](./LICENSE).
