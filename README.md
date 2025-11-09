# 💾 PROTOCOL INTERFACE // SEPOLIA TESTNET

## Project Overview

This project is a fully functional, single-page **Decentralized Application (dApp)** acting as a public message board and funding mechanism deployed on the **Sepolia Testnet**.

### Built with:
- **Solidity** — Smart contract logic
- **HTML / CSS / JavaScript** — Front-end interface
- **Ethers.js** — Front-end blockchain interactions

The dApp demonstrates core Web3 development concepts:
- Handling payable transactions
- Updating blockchain state
- Reading live contract data in real time

---

## ✨ Design Philosophy: Neon Synthwave Interface

The interface features a **Neon Synthwave / Retro-Tech** aesthetic, giving a bold and visually dynamic experience.

| Element | Description | Why it Works |
|---------|-------------|--------------|
| **Color Scheme** | Deep purples/blacks with Neon Pink (#FF0099) and Neon Cyan (#00FFFF) | High contrast & futuristic look |
| **Font** | Space Mono (monospace) | Reinforces console / protocol theme |
| **Layout** | Fully responsive grid | Desktop two-column dashboard, collapses for mobile |
| **UX Feedback** | Glowing buttons, hover effects, neon-green success indicators | Immediate visual feedback on user actions |

---

## 🚀 Getting Started

### Prerequisites
- **Node.js & npm** — Install development dependencies (Hardhat/Foundry if needed)
- **MetaMask** (or compatible wallet) — Wallet must have Sepolia ETH

### 1. Smart Contract Deployment

#### Primary functions:

| Function | Type | Description |
|----------|------|-------------|
| `setMessage(string newMessage)` | Non-payable | Updates the public message stored on-chain |
| `contribute()` / `likeMessage()` | Payable | Sends ETH to contract and increments like counter |

#### Steps:
1. Compile & deploy contract to Sepolia Testnet
2. Save the contract address and ABI for the front-end

### 2. Front-End Setup

The entire dApp runs from `index.html`.

#### Configure the Contract

Inside the `<script>` section, update:
```javascript
const CONTRACT_ADDRESS = "0x0e7770f45c15c9562362d9F8302c64D0f8AD8B1F"; 
const CONTRACT_ABI = [
{
        "inputs": [
            {
                "internalType": "string",
                "name": "initialMessage",
                "type": "string"
            }
        ],
        "stateMutability": "nonpayable",
        "type": "constructor"
    },
    {
        "inputs": [],
        "name": "currentMessage",
        "outputs": [
            {
                "internalType": "string",
                "name": "",
                "type": "string"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "getLastUpdater",
        "outputs": [
            {
                "internalType": "address",
                "name": "",
                "type": "address"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "getLikeCount",
        "outputs": [
            {
                "internalType": "uint256",
                "name": "",
                "type": "uint256"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "getMessage",
        "outputs": [
            {
                "internalType": "string",
                "name": "",
                "type": "string"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "lastUpdater",
        "outputs": [
            {
                "internalType": "address",
                "name": "",
                "type": "address"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "likeCount",
        "outputs": [
            {
                "internalType": "uint256",
                "name": "",
                "type": "uint256"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "likeMessage",
        "outputs": [],
        "stateMutability": "payable",
        "type": "function"
    },
    {
        "inputs": [
            {
                "internalType": "string",
                "name": "_newMessage",
                "type": "string"
            }
        ],
        "name": "setMessage",
        "outputs": [],
        "stateMutability": "nonpayable",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "totalLikesBalance",
        "outputs": [
            {
                "internalType": "uint256",
                "name": "",
                "type": "uint256"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    }

   ];


### 3. Running the dApp

1. Save the file
2. Open `index.html` in a browser
3. Click **INITIATE CONNECTION** to connect MetaMask

#### Dashboard Buttons

| Button | Action |
|--------|--------|
| **PULL LATEST DATA** | Fetch blockchain data (message, like count, wallet address) |
| **TRANSMIT MESSAGE** | Sends a state-changing transaction to update message |
| **CONTRIBUTE** | Calls payable function and sends 0.0001 ETH |

---

##⚙️ Key Technical Features

| Feature | Description |
|---------|-------------|
| **Ethers.js Integration** | Direct interaction with MetaMask for reading/writing contract data |
| **Payable Transactions** | Single-click ETH contributions via CONTRIBUTE |
| **Real-Time Feedback** | Event log with transaction results, status, hashes |
| **Sepolia Compatibility** | Fully configured for Sepolia Testnet |

---

