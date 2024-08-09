# Token Swap and Aave Lending Integration

Welcome to the Token Swap and Aave Lending Integration project! This guide will help you set up, run, and interact with the DeFi script that performs token swaps using Uniswap and integrates with Aave for lending.

## Overview

This script performs a token swap using the Uniswap V3 protocol and then deposits the swapped tokens into the Aave Lending Pool. The overall workflow is as follows:

1. **Token Approval**: The script first approves the Uniswap SwapRouter to spend a specified amount of the input token (USDC).
2. **Token Swap**: It then swaps USDC for LINK using the Uniswap SwapRouter.
3. **Deposit into Aave**: Finally, the script deposits the swapped LINK tokens into the Aave Lending Pool to start earning interest.

## Diagram Illustration


<img width="900" alt="hello" src="https://www.globalxetfs.com/content/files/230222-AAVE-The-Basics_02-1.png">

## Code Explanation

### 1. **Setup and Configuration**

The script imports necessary dependencies, including the `ethers` library and ABI files for interacting with various smart contracts. It reads environment variables from a `.env` file for sensitive information such as the RPC URL and private key.

### 2. **Token Approval**

The `approveToken` function allows the SwapRouter to spend the specified amount of USDC tokens. This involves:

- Creating a contract instance for the USDC token.
- Generating and sending an approval transaction.

### 3. **Fetch Pool Information**

The `getPoolInfo` function retrieves information about the Uniswap pool that will be used for swapping tokens. It fetches the pool address from the Uniswap Factory contract and then queries the pool contract for details like token addresses and fee.

### 4. **Prepare Swap Parameters**

The `prepareSwapParams` function prepares the parameters needed for the Uniswap swap. It specifies the input and output tokens, the fee tier, and other parameters required for the swap.

### 5. **Execute Swap**

The `executeSwap` function executes the swap using the Uniswap SwapRouter. It generates a transaction for the swap and sends it using the wallet.

### 6. **Deposit into Aave**

The `depositToAave` function deposits the swapped LINK tokens into the Aave Lending Pool. This involves:

- Creating a contract instance for the Aave Lending Pool.
- Generating and sending a deposit transaction.

### 7. **Main Function**

The `main` function orchestrates the entire process, from token approval to swap execution and deposit into Aave. It handles exceptions and prints transaction details to the console.



## Project Setup

To get started with this project, follow these steps:

### 1. **Clone the Repository**

First, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/token_swap_gh.git
cd token_swap_gh
```

### 2. **Install Dependencies**

Ensure you have Node.js installed. Then, install the required dependencies:
```bash
npm install
This will install all the necessary packages specified in package.json.
```

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
This will execute the script, swap tokens using Uniswap, and deposit the swapped tokens into the Aave lending pool.
```

### 6. **Verify the Results**

Once the script is executed, verify the transactions using the transaction hashes printed in the console.


### 🛠 **Troubleshooting**

If you encounter any issues, consider the following troubleshooting steps:

Check .env File: Ensure your environment variables (RPC_URL and PRIVATE_KEY) are correctly set in the .env file. Incorrect values can lead to failed transactions or connection issues.

Verify ABI Files: Make sure the ABI files in the abis folder are up-to-date and correctly match the contracts you are interacting with. An outdated or incorrect ABI may cause contract interaction errors.

Consult Documentation: Refer to the Uniswap and Aave documentation for contract-specific details and to understand the parameters required for transactions.

Check Node Provider Status: Ensure your Ethereum node provider is operational and that you are not hitting any rate limits or service outages.
