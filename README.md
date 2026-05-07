# Polysors Protocol

**Permissionless On-Chain Lottery Platform on Polygon PoS**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Foundry](https://img.shields.io/badge/Built%20with-Foundry-orange.svg)](https://getfoundry.sh/)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.24-blue.svg)](https://soliditylang.org/)

---

## 🎰 What is Polysors?

Polysors is a fully decentralized, permissionless lottery protocol built on Polygon PoS. Anyone can stake SORS tokens, become an operator, and launch lottery rounds with custom rules. Winners are selected using **verifiable randomness** from the drand threshold beacon network combined with on-chain entropy — making outcomes impossible to predict or manipulate.

**No admins. No central control. Provably fair.**

---

## ✨ Key Features

- **Permissionless Deployment**: Anyone with 1,000 SORS can become an operator and launch lottery rounds
- **Dual-Source Randomness**: Combines drand BLS beacons with rolling on-chain hash accumulation
- **Elastic Tokenomics**: 1B SORS target supply with automatic mint/burn cycles for cashback sustainability
- **Operator Staking & Slashing**: Economic security through staked collateral; 5% penalty for missed deadlines
- **Pull-Payment Claims**: All payouts (prizes, cashback, commissions) are self-serve for maximum safety
- **Emergency Refund**: 60-day safety valve ensures players recover funds if rounds get stuck

---

## 🏗️ Architecture

The protocol consists of three core contracts:

| Contract | Purpose |
|---|---|
| **LotteryFactory** | Central hub for operator staking, EIP-1167 clone deployment, fee routing, and slashing |
| **PolysorsLottery** | Round template deployed as minimal proxies. Handles ticket sales, settlement, and claims |
| **SORSToken** | ERC-20 platform token with factory-only mint/burn for cashback shortfall cycles |

Supporting contracts: **RewardsPool** (cashback reservoir), **DrandVerifier** (BN254 BLS verification), **MarketingVesting**, **ReserveVesting**

---

## 🚀 Quick Start

### Prerequisites
- [Foundry](https://getfoundry.sh/) installed

### Installation
```bash
git clone https://github.com/polysors/Polysors.git
cd Polysors
forge install
```

### Build & Test
```bash
forge build
forge test
forge test --gas-report
```

---

## 📊 Tokenomics (SORS)

**Total Genesis Supply:** 1,000,000,000 SORS (1B)

| Allocation | Amount | Destination |
|---|---|---|
| RewardsPool | 200M | Cashback source |
| Treasury | 160M | Protocol operations |
| Reserve | 250M | 3-year vesting (1yr cliff + 2yr linear) |
| Team | 150M | PinkSale lock |
| Marketing/KOL | 80M | Vesting contract |
| Investor Presale | 60M | PinkSale |
| Operator Presale | 40M | PinkSale |
| DEX Liquidity | 60M | PinkSale LP |

---

## 🔐 Security Highlights

- **Unbiasable Randomness**: drand evmnet threshold signatures + rolling hash accumulation
- **Cherry-Pick Proof**: Target drand round set 250 rounds (~750s) ahead at close time
- **Slashing Mechanism**: 5% stake penalty for missing close (24h) or drand submission (48h) deadlines
- **Timelock Governance**: 48h proposal window for all sensitive parameter updates
- **Reentrancy Guards**: All critical functions protected
- **Emergency Refund**: Pull-payment refund after 60 days if round is stuck

---

## 🌐 Links

- **Website**: Coming Soon
- **Twitter/X**: [@polysors](https://x.com/polysors)
- **Telegram**: [t.me/polysors](https://t.me/polysors)
- **Documentation**: Coming Soon

---

## 📄 License

This project is licensed under the **MIT License**.

---

*Built with ❤️ on Polygon PoS • Powered by drand*
