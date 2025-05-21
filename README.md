![KURU - Indian mytho web4 battle card game-modified](https://github.com/user-attachments/assets/8f8a50aa-b373-469f-ae0f-03434ecadb24)

# 🐉 KURU: NFTCard Game on NERO Chain Testnet

KURU is an Indian and Japanese mythology-inspired strategy **NFT card game** hosted on the **NERO Chain Testnet**. Players battle using NFT cards, each with unique stats, and make strategic decisions — all powered by on-chain transactions. Gameplay is transparent, secure, and decentralized using blockchain technology.

---

## 🧩 Game Description

KURU is a blockchain-based **strategic card battler** where each action (attack or defend) is a signed blockchain transaction. Using **NERO**, the native token of NERO Chain's Testnet, players must manage their mana and choose their moves wisely to defeat their opponent.

---

## ✨ Features

- 🎴 **NFT Cards**  
  Each player owns unique NFT cards with different attack and defense stats.

- 🧠 **Strategic Gameplay**  
  Players choose to attack or defend. Success requires tactical decision-making.

- 🔗 **On-Chain Game Moves**  
  Every move is recorded as a signed transaction on the blockchain.

- ⚡ **Mana System**  
  - Attacks cost mana (3 mana points)
  - Defending regenerates mana (3 mana points)

- 💰 **NERO Native Token**  
  All game interactions use **NERO**, the native token of the **NERO Chain Testnet**.

---

## 📜 Game Rules

1. **Card Cancellation**:  
   If both players use cards with the same attack and defense values, they cancel each other out.

2. **Attack Impact**:  
   If a player attacks and the opponent does not defend, attack points directly reduce opponent’s health.

3. **Defense Calculation**:  
   If the opponent defends, defense points reduce the impact of the attack.

4. **Mana Mechanics**:  
   - Attacking costs 3 mana points  
   - Defending regenerates 3 mana points

5. **Victory Condition**:  
   The game ends when a player’s health reaches **zero**.

---

## 🕹️ How to Play

1.  Connect your wallet (MetaMask) to **NERO Chain Testnet**
    
2.  Obtain some **test NERO tokens** from a faucet (if available)
    
3.  Use your NFT card deck to:
    
    -   🛡️ **Defend** and gain mana
        
    -   ⚔️ **Attack** by spending mana
        
4.  Each move triggers a wallet transaction
    
5.  Win when opponent’s health drops to **0**

## 🔗 Network Configuration: NERO Chain Testnet

To play the game, you must connect to the **NERO Testnet** using a compatible crypto wallet (Metamask).

### ➕ Add NERO Chain Testnet to MetaMask

1. Open MetaMask → Click network dropdown → **Add Network**
2. Enter the following details:

| Field              | Value                             |
|-------------------|-----------------------------------|
| **Network Name**   | NERO Chain Testnet                |
| **RPC URL**        | `https://rpc-testnet.nerochain.io` |
| **Chain ID**       | `689`                             |
| **Symbol**         | `NERO`                            |
| **Decimals**       | `18`                              |
| **Explorer URL**   | `https://testnet.neroscan.io`     |

3. Click **Save** and switch to the NERO Testnet.

---

## 🧪 Getting Started

### 1. Install Dependencies

```
npm install
```
### 2. Compile Contracts

```
bash
npx hardhat compile
```

### 3. Deploy to NERO Chain Testnet

Update your `hardhat.config.ts`:

```

import { HardhatUserConfig } from  "hardhat/config"; 
import  "@nomiclabs/hardhat-ethers"; 
import dotenv from  "dotenv";

dotenv.config(); 
const  config: HardhatUserConfig = { 
	solidity: "0.8.16", 
	networks: { 
		neroTestnet: { 
			url: "https://rpc-testnet.nerochain.io", 
			chainId: 689, 
			accounts: [process.env.PRIVATE_KEY || ""],
    },
  },
}; export  default config;
```

Ensure `.env` file has:
```
PRIVATE_KEY=your_wallet_private_key_without_0x
``` 

Deploy:
```
npx hardhat run scripts/deploy.ts --network neroTestnet
```

## 🔮 Planned Upgrades (Future Updates)

### 🧠 Integrating Account Abstraction (AA)

We plan to upgrade the game to **support gasless transactions** via **NERO’s AA SDK** (EIP-4337 compliant), enhancing user experience:

#### ➕ Steps to Integrate:

1.  **Initialize the AA Client & Builder**
    
    -   Use `Presets.Builder.SimpleAccount.init(...)` from NERO SDK.
        
    -   Connect using either MetaMask or Web3Auth signer.
        
2.  **Build and Send UserOperations**
    
    -   Instead of `contract.method(...)`, construct `UserOperation` objects.
        
    -   Use SDK methods like `createUserOp`, `signUserOp`.
        
3.  **Enable Paymaster for Gas Sponsorship**
    
    -   Obtain an **API Key** from NERO's AA Platform.
        
    -   Integrate `Paymaster` module to handle sponsored gas.
        
    -   All signed moves will be executed **gas-free**.
        
4.  **Display Smart Contract Wallet Address**
    
    -   Retrieve and display AA wallet using `builder.getAddress()`.
        
5.  **Optional Social Login (Web3Auth)**
    
    -   Allow users to log in via Google or social accounts.
        
    -   Web3Auth signer can be passed to AA builder.
        
    -   Ensures even non-crypto users can onboard easily.
        

> 📚 For detailed implementation, visit: [docs.nerochain.io](https://docs.nerochain.io)

## 🚧 Roadmap

| Feature                            | Status       |
| ---------------------------------- | ------------ |
| NFT Card Game Engine               | ✅ Complete  |
| Metamask Integration               | ✅ Complete  |
| On-Chain Gameplay                  | ✅ Complete  |
| NERO Testnet Deployment            | ✅ Complete  |
| Account Abstraction Wallets        | 🔜 Planned   |
| Gasless Gameplay (Paymaster)       | 🔜 Planned   |
| Google OAuth Onboarding (Web3Auth) | 🔜 Planned   |
| Mobile-Optimized UI                | 🔜 Planned   |



## 👨‍💻 Tech Stack

-   **Frontend**: React + Ethers.js
    
-   **Smart Contracts**: Solidity on NERO Chain Testnet
    
-   **Wallets**: MetaMask
    
-   **Optional**: Web3Auth, NERO AA SDK


## ⚠️ Disclaimer

KURU is currently on **testnet** and experimental. This is a demo for educational/hackathon purposes only. Do not use real funds.
