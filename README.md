<img width="900" alt="30 Jul - Navigating the DeFi Ecosystem" src="https://github.com/user-attachments/assets/f4166974-50f5-400f-b084-5b95428f48ed">

# Token Swap and Aave Lending Integration

Welcome to the Token Swap and Aave Lending Integration project! This guide will help you set up, run, and interact with the DeFi script that performs token swaps using Uniswap and integrates with Aave for lending.

## 📦 Project Setup

To get started with this project, follow these steps:

### 1. **Clone the Repository**

First, clone the repository to your local machine:

```bash
git clone https://github.com/LikhithaO/token_swap_gh.git
cd token_swap_gh
```

### 2. **Install Dependencies**

Ensure you have Node.js installed. Then, install the required dependencies:
```bash
npm install --save
```
This will install all the necessary packages specified in package.json.


### 3. **Set Up Environment Variables**

Create a .env file in the root of the project directory. This file will hold your sensitive information, such as private keys and RPC URLs. Use the following template:

```bash
RPC_URL=https://your.rpc.url
PRIVATE_KEY=your_private_key_here
```

Replace https://your.rpc.url with your Ethereum node provider URL and your_private_key_here with your wallet's private key.

Note: Keep your .env file secure and never share it publicly.

### 4. **Verify ABI Files**

Ensure you have the ABI files for the contracts in the abis folder. The folder should contain:

factory.json - ABI for the Uniswap Factory contract.
swaprouter.json - ABI for the Uniswap SwapRouter contract.
pool.json - ABI for the pool contract.
token.json - ABI for the ERC20 token contract.
lendingpool.json - ABI for the Aave Lending Pool contract.
These ABIs are necessary for interacting with the respective contracts.

### 5. **Run the Script**

With everything set up, you can run the script to perform a token swap and interact with Aave. Use the following command:

```bash
node index.cjs
```
This will execute the script, swap tokens using Uniswap, and deposit the swapped tokens into the Aave lending pool.


### 6. **Verify the Results**

Once the script is executed, verify the transactions using the transaction hashes printed in the console.


### 🛠 **Troubleshooting**

If you encounter any issues, consider the following troubleshooting steps:

Check .env File: Ensure your environment variables (RPC_URL and PRIVATE_KEY) are correctly set in the .env file. Incorrect values can lead to failed transactions or connection issues.

Verify ABI Files: Make sure the ABI files in the abis folder are up-to-date and correctly match the contracts you are interacting with. An outdated or incorrect ABI may cause contract interaction errors.

Consult Documentation: Refer to the Uniswap and Aave documentation for contract-specific details and to understand the parameters required for transactions.

Check Node Provider Status: Ensure your Ethereum node provider is operational and that you are not hitting any rate limits or service outages.
