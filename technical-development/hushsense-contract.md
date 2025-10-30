---
description: The contract which manages the $Hush token
icon: file-signature
---

# HushSense Contract

A smart contract project for the **HushSense ecosystem**, deployed on Hedera via Hardhat. It defines, deploys, and manages the **HushSense smart contract** with full support for mainnet deployment.

### 📌 Features

* Smart contract written in **Solidity** (`hushsense.sol`)
* Hardhat-based deployment scripts
* **npx-compatible execution** for smooth workflow
* Mainnet-ready with `--network hederamainnet` flag
* Script to mint tokens from the deployed contract

### 📂 Project Structure

hushsense-contract/\
├── contracts/\
│ └── HushSenseManager.sol                          # Core smart contract\
├── scripts/\
│ ├── deploy-hardhat.cjs                                 # Deployment script (mainnet/testnet ready)\
│ ├── fix-keys.js                                                 # Key fixing utility\
│ ├── initialise-contract.js                               # Contract initialization\
│ ├── mint.js                                                       # Minting script\
│ └── test.js                                                        # Test script\
├── test/                                                              # Test directory\
├── types/                                                           # Typechain output\
├── .env                                                               # Environment configuration\
├── hardhat.config.cjs                                    # Hardhat configuration\
└── README.md                                             # Documentation

### 🔗 Deployed Contracts

* HTS Fungible Token (HUSH): [0.0.10048362](https://hashscan.io/mainnet/token/0.0.10048362)
* &#x20;Smart Contract: [0.0.10047928](https://hashscan.io/mainnet/contract/0.0.10047928)

### ⚙️ Prerequisites

* **Node.js** v18 or later
* **npm** or **yarn**
* Hardhat installed (`npm install --save-dev hardhat`)
* Hedera account with sufficient HBAR for deployment

### 📥 Installation

Clone the repository and install dependencies:

<kbd>git clone https://github.com/your-username/hushsense-contract.git</kbd>\ <kbd>cd hushsense-contract</kbd>\ <kbd>npm install</kbd>&#x20;

### 🔑 Environment Setup

<kbd>MY\_ACCOUNT\_ID=0.0.xxxxx</kbd> \ <kbd>MY\_PRIVATE\_KEY=302e020100300506032b6570...</kbd> \ <kbd>HEDERA\_NETWORK=hederamainnet</kbd>

### 🚀 Usage

#### 1️⃣ Compile Contracts

<kbd>npx hardhat compile</kbd>

#### 2️⃣ Deploy Contract (Mainnet)

<kbd>npx hardhat run scripts/deploy-hardhat.cjs --network hederamainnet</kbd>&#x20;

#### 3️⃣ Mint via Contract

<kbd>npx hardhat run scripts/mint.js --network hederamainnet</kbd>&#x20;

### 📦 Deployment Notes

* Always double-check `.env` to ensure `hederamainnet` is set for production runs
* Maintain sufficient HBAR in the deployer account for gas fees
* Contracts can be upgraded or extended using standard Solidity patterns

### 🛠️ Scripts Details

#### **hushsense.sol**

Defines the core smart contract logic for HushSense.

#### **deploy-hardhat.cjs**

Deploys the contract to Hedera, with full support for mainnet deployment via `npx`.

#### **mint.js**

Mints tokens from the deployed smart contract.

### 📜 License

Copyright 2025 HushSense

Licensed under the Apache License, Version 2.0 (the "License");\
you may not use this file except in compliance with the License.\
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software\
distributed under the License is distributed on an "AS IS" BASIS,\
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.\
See the License for the specific language governing permissions and\
limitations under the License.
