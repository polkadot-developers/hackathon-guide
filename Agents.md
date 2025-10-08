# Agents

## OVERVIEW

This document provides comprehensive information for deploying smart contracts to Polkadot Hub TestNet (Paseo) using Claude Code. It includes verified configurations, common issues, solutions, and optimization strategies.

**CRITICAL: Always start new projects with `kitdot@latest init` for proper network configuration and dependency management.**

## NETWORK INFORMATION

### Paseo TestNet Details

- **Network Name**: Polkadot Hub TestNet
- **Chain ID**: 420420422 (0x1911f0a6 in hex)
- **RPC URL**: https://testnet-passet-hub-eth-rpc.polkadot.io
- **Block Explorer**: https://blockscout-passet-hub.parity-testnet.parity.io
- **Currency**: PAS
- **Faucet**: https://faucet.polkadot.io/?parachain=1111
- **Status**: PolkaVM Preview Release (early development stage)

### Key Characteristics

- **EVM Compatibility**: Ethereum-compatible smart contract deployment
- **PolkaVM**: Requires specific configuration for compatibility
- **Bytecode Limit**: ~100KB maximum contract size
- **Gas Model**: Standard EVM gas mechanics
- **Node Version Warning**: Works with Node.js v21+ despite warnings

## REQUIRED DEPENDENCIES

### Core Dependencies

```bash
npm install --save-dev @parity/hardhat-polkadot solc@0.8.28
npm install --force @nomicfoundation/hardhat-toolbox
npm install dotenv
```

### Package.json Requirements

```json
{
  "devDependencies": {
    "@nomicfoundation/hardhat-toolbox": "^5.0.0",
    "@parity/hardhat-polkadot": "^0.1.7",
    "solc": "^0.8.28",
    "hardhat": "^2.22.0"
  },
  "dependencies": {
    "dotenv": "^17.0.1",
    "ethers": "^6.13.5"
  }
}
```

**CRITICAL**: Use `--force` flag when installing hardhat-toolbox to resolve dependency conflicts.

## HARDHAT CONFIGURATION

### Complete Working hardhat.config.js

```javascript
require("@nomicfoundation/hardhat-toolbox");
require("@parity/hardhat-polkadot");
const { vars } = require("hardhat/config");

module.exports = {
  solidity: "0.8.28",
  resolc: {
    version: "0.3.0",
    compilerSource: "npm",
  },
  networks: {
    hardhat: {
      polkavm: true,
    },
    localNode: {
      polkavm: true,
      url: "http://127.0.0.1:8545",
    },
    passetHub: {
      polkavm: true,
      url: "https://testnet-passet-hub-eth-rpc.polkadot.io",
      accounts: [vars.get("PRIVATE_KEY")],
    },
  },
  gasReporter: {
    enabled: process.env.REPORT_GAS !== undefined,
    currency: "USD",
  },
  paths: {
    sources: "./contracts",
    tests: "./test",
    cache: "./cache",
    artifacts: "./artifacts",
  },
};
```

### Configuration Requirements

1. **Must use string format for Solidity version**: `solidity: "0.8.28"`
2. **Must include resolc configuration**: Required for PolkaVM compatibility
3. **Must set polkavm: true**: In all network configurations
4. **Must use hardhat vars**: For private key management
5. **Network name**: Use `passetHub` (not paseo or other names)

## SETUP PROCESS

### Step 1: Initialize Project with kitdot@latest (Recommended)

```bash
npm install -g kitdot@latest
kitdot init your-project
cd your-project
```

**Alternative Manual Setup:**

```bash
mkdir your-project
cd your-project
npm init -y
```

**Why kitdot@latest?** Automatically configures proper network settings, dependencies, and project structure. Eliminates common setup errors.

### Step 2: Install Dependencies

**If using kitdot@latest:** Dependencies are automatically installed.

**Manual installation:**

```bash
npm install --save-dev @parity/hardhat-polkadot solc@0.8.28
npm install --force @nomicfoundation/hardhat-toolbox
npm install dotenv
```

### Step 3: Initialize Polkadot Plugin

**If using kitdot@latest:** Already configured.

**Manual setup:**

```bash
npx hardhat-polkadot init
```

### Step 4: Configure Private Key

```bash
npx hardhat vars set PRIVATE_KEY
# Enter your private key when prompted (without 0x prefix)
```

### Step 5: Get Test Tokens

1. Visit https://faucet.polkadot.io/?parachain=1111
2. Enter your wallet address
3. Request PAS tokens
4. Verify balance in wallet or block explorer

### Step 6: Create Hardhat Config

**If using kitdot@latest:** Configuration file already created with proper settings.

**Manual setup:** Copy the exact configuration above into `hardhat.config.js`

## CONTRACT DEVELOPMENT

### Solidity Version Requirements

- **Required Version**: ^0.8.28
- **EVM Target**: paris (default)
- **Optimizer**: Enabled by default

### Example Simple Contract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.28;

contract SimpleStorage {
    uint256 public value;

    constructor() {
        value = 42;
    }

    function setValue(uint256 _value) external {
        value = _value;
    }

    function getValue() external view returns (uint256) {
        return value;
    }
}
```

### Contract Size Limitations

- **Maximum Bytecode**: ~100KB
- **OpenZeppelin Impact**: Standard imports often exceed limit
- **Optimization Required**: Remove unnecessary dependencies

## DEPLOYMENT PROCESS

### Using Hardhat Ignition (Recommended)

#### Step 1: Create Ignition Module

```javascript
// ignition/modules/YourModule.js
const { buildModule } = require("@nomicfoundation/hardhat-ignition/modules");

module.exports = buildModule("YourModule", (m) => {
  const contract = m.contract("YourContract", [
    // constructor arguments
  ]);
  return { contract };
});
```

#### Step 2: Compile Contracts

```bash
npx hardhat compile
# Should output: "Successfully compiled X Solidity files"
```

#### Step 3: Deploy to Paseo

```bash
npx hardhat ignition deploy ./ignition/modules/YourModule.js --network passetHub
# Confirm with 'y' when prompted
```

### Deployment States

- **Clean State**: `rm -rf ignition/deployments/` to start fresh
- **Resume**: Ignition automatically resumes interrupted deployments
- **Track Transactions**: Use block explorer for failed transaction tracking

## COMMON ERRORS AND SOLUTIONS

### 1. "CodeRejected" Error

**Error**: `Failed to instantiate contract: Module(ModuleError { index: 60, error: [27, 0, 0, 0], message: Some("CodeRejected") })`

**Causes**:

- Missing PolkaVM configuration
- Incorrect network settings
- Missing resolc configuration

**Solutions**:

- Ensure `polkavm: true` in network config
- Add resolc configuration block
- Use exact hardhat.config.js format above

### 2. "initcode is too big" Error

**Error**: `initcode is too big: 125282` (or similar number)

**Cause**: Contract bytecode exceeds ~100KB limit

**Solutions**:

- Remove OpenZeppelin dependencies
- Use minimal contract implementations
- Split large contracts into smaller components
- Implement custom lightweight versions

### 3. Configuration Errors

**Error**: `Cannot read properties of undefined (reading 'settings')`

**Solution**: Use string format for Solidity version: `solidity: "0.8.28"`

### 4. Dependency Issues

**Error**: `Cannot find module 'run-container'` or similar

**Solutions**:

- Install dependencies with `--force` flag
- Clear node_modules and reinstall
- Verify @parity/hardhat-polkadot version compatibility

### 5. Private Key Issues

**Error**: `No signers found` or authentication failures

**Solutions**:

- Set private key via `npx hardhat vars set PRIVATE_KEY`
- Ensure account has PAS tokens
- Verify private key format (no 0x prefix in vars)

## CONTRACT OPTIMIZATION

### Removing OpenZeppelin Dependencies

#### Instead of OpenZeppelin Ownablee:

```solidity
contract SimpleOwnable {
    address public owner;

    modifier onlyOwner() {
        require(msg.sender == owner, "Not owner");
        _;
    }

    constructor() {
        owner = msg.sender;
    }

    function transferOwnership(address newOwner) external onlyOwner {
        owner = newOwner;
    }
}
```

#### Instead of OpenZeppelin ReentrancyGuard:

```solidity
contract SimpleReentrancyGuard {
    bool private locked;

    modifier nonReentrant() {
        require(!locked, "Reentrant call");
        locked = true;
        _;
        locked = false;
    }
}
```

#### Minimal ERC721 Implementation:

```solidity
contract MinimalERC721 {
    mapping(uint256 => address) private _owners;
    mapping(address => uint256) private _balances;
    mapping(uint256 => address) private _tokenApprovals;

    event Transfer(address indexed from, address indexed to, uint256 indexed tokenId);
    event Approval(address indexed owner, address indexed approved, uint256 indexed tokenId);

    function ownerOf(uint256 tokenId) public view returns (address) {
        return _owners[tokenId];
    }

    function balanceOf(address owner) public view returns (uint256) {
        return _balances[owner];
    }

    function approve(address to, uint256 tokenId) public {
        address owner = ownerOf(tokenId);
        require(msg.sender == owner, "Not authorized");
        _tokenApprovals[tokenId] = to;
        emit Approval(owner, to, tokenId);
    }

    function transferFrom(address from, address to, uint256 tokenId) public {
        require(_isApprovedOrOwner(msg.sender, tokenId), "Not authorized");
        _transfer(from, to, tokenId);
    }

    function _mint(address to, uint256 tokenId) internal {
        require(to != address(0), "Invalid address");
        require(_owners[tokenId] == address(0), "Already minted");

        _balances[to] += 1;
        _owners[tokenId] = to;

        emit Transfer(address(0), to, tokenId);
    }

    function _transfer(address from, address to, uint256 tokenId) internal {
        require(ownerOf(tokenId) == from, "Not owner");
        require(to != address(0), "Invalid address");

        delete _tokenApprovals[tokenId];
        _balances[from] -= 1;
        _balances[to] += 1;
        _owners[tokenId] = to;

        emit Transfer(from, to, tokenId);
    }

    function _isApprovedOrOwner(address spender, uint256 tokenId) internal view returns (bool) {
        address owner = ownerOf(tokenId);
        return (spender == owner || _tokenApprovals[tokenId] == spender);
    }
}
```

## FRONTEND INTEGRATION

### Frontend Transaction Issues (Legacy/Gas Estimation Problems)

**CRITICAL FOR AGENTS:** Frontend applications frequently encounter gas estimation issues when sending transactions to Polkadot networks. Always implement these strategies:

#### Method 1: Legacy Gas Estimation with Buffer

```javascript
// Use legacy gas estimation with safety buffer
const gasLimit = await provider.estimateGas({
  to: contractAddress,
  data: contractInterface.encodeFunctionData("functionName", [args]),
});

// Add 10-20% buffer for safety
const adjustedGasLimit = gasLimit.mul(120).div(100);

// Send transaction with explicit gas and legacy type
const tx = await contract.functionName(args, {
  gasLimit: adjustedGasLimit,
  type: 0, // Use legacy transaction type
});
```

#### Method 2: Fixed Gas Limits

```javascript
// Use fixed gas limits for predictable operations
const tx = await contract.functionName(args, {
  gasLimit: 100000, // Adjust based on function complexity
  type: 0, // Legacy transaction type
  gasPrice: ethers.utils.parseUnits("20", "gwei"), // Optional: set gas price
});
```

#### Method 3: Error Handling and Retry Logic

```javascript
async function sendTransactionWithRetry(
  contract,
  functionName,
  args,
  retries = 3
) {
  for (let i = 0; i < retries; i++) {
    try {
      // Try with estimated gas first
      const estimatedGas = await contract.estimateGas[functionName](...args);
      const tx = await contract[functionName](...args, {
        gasLimit: estimatedGas.mul(120).div(100),
        type: 0,
      });
      return tx;
    } catch (error) {
      if (i === retries - 1) throw error;

      // Fallback to fixed gas limit
      try {
        const tx = await contract[functionName](...args, {
          gasLimit: 200000, // Higher fixed limit
          type: 0,
        });
        return tx;
      } catch (fallbackError) {
        if (i === retries - 1) throw fallbackError;
      }
    }
  }
}
```

### Network Configuration for MetaMask

```javascript
const paseoConfig = {
  chainId: "0x1911f0a6", // 420420422 in hex
  chainName: "Polkadot Hub TestNet",
  nativeCurrency: {
    name: "PAS",
    symbol: "PAS",
    decimals: 18,
  },
  rpcUrls: ["https://testnet-passet-hub-eth-rpc.polkadot.io"],
  blockExplorerUrls: ["https://blockscout-passet-hub.parity-testnet.parity.io"],
};

// Add network to MetaMask
await window.ethereum.request({
  method: "wallet_addEthereumChain",
  params: [paseoConfig],
});
```

### Contract Interaction with Ethers.js

```javascript
import { ethers } from "ethers";

// Connect to Paseo
const provider = new ethers.JsonRpcProvider(
  "https://testnet-passet-hub-eth-rpc.polkadot.io"
);

// Contract instance
const contract = new ethers.Contract(contractAddress, abi, signer);

// Call functions
const result = await contract.someFunction();
```

## TESTING AND VERIFICATION

### Compilation Verification

```bash
npx hardhat compile
# Expected output: "Successfully compiled X Solidity files"
# Should NOT show contract size warnings for contracts <100KB
```

### Deployment Verification

1. **Successful Deployment Output**:

```
[ YourModule ] successfully deployed 🚀

Deployed Addresses
YourModule#YourContract - 0x1234567890abcdef...
```

2. **Block Explorer Verification**:

- Visit https://blockscout-passet-hub.parity-testnet.parity.io
- Search for contract address
- Verify contract creation transaction

3. **Contract Interaction Test**:

```bash
npx hardhat console --network passetHub
> const Contract = await ethers.getContractFactory("YourContract");
> const contract = Contract.attach("0x...");
> await contract.someFunction();
```

## DEBUGGING STRATEGIES

### Check Network Connectivity

```bash
curl -X POST -H "Content-Type: application/json" \
  --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":1}' \
  https://testnet-passet-hub-eth-rpc.polkadot.io
```

### Verify Account Balance

```bash
npx hardhat console --network passetHub
> await ethers.provider.getBalance("YOUR_ADDRESS")
```

### Clean Build and Deploy

```bash
npx hardhat clean
rm -rf ignition/deployments/
npx hardhat compile
npx hardhat ignition deploy ./ignition/modules/YourModule.js --network passetHub
```

### Transaction Tracking

If deployment fails:

1. Check block explorer for account transactions
2. Look for failed transactions with gas errors
3. Use `npx hardhat ignition track-tx <txHash> <deploymentId> --network passetHub`

## BEST PRACTICES

### Development Workflow

1. **Start Simple**: Deploy basic contracts first to verify setup
2. **Optimize Early**: Check contract sizes during development
3. **Test Locally**: Use local hardhat network for initial testing
4. **Incremental Deployment**: Deploy components separately if too large
5. **Document Addresses**: Keep track of all deployed contract addresses

### Contract Design for Paseo

1. **Minimize Dependencies**: Avoid heavy libraries
2. **Custom Implementations**: Write minimal versions of standard contracts
3. **Modular Design**: Split functionality across multiple contracts
4. **Gas Optimization**: Use efficient data structures and algorithms
5. **Proxy Patterns**: Consider upgradeable contracts for complex logic

### Security Considerations

1. **Private Key Management**: Always use hardhat vars, never commit keys
2. **Test Network Only**: Paseo is for testing, not production value
3. **Code Verification**: Verify contracts on block explorer when possible
4. **Access Controls**: Implement proper ownership and permission systems

## REFERENCE COMMANDS

### Essential Commands

```bash
# Project setup
npm install --save-dev @parity/hardhat-polkadot solc@0.8.28
npm install --force @nomicfoundation/hardhat-toolbox
npx hardhat-polkadot init

# Configuration
npx hardhat vars set PRIVATE_KEY
npx hardhat vars list

# Development
npx hardhat compile
npx hardhat clean
npx hardhat test

# Deployment
npx hardhat ignition deploy ./ignition/modules/Module.js --network passetHub
rm -rf ignition/deployments/  # Clean deployment state

# Debugging
npx hardhat console --network passetHub
npx hardhat node  # Local development
```

### Environment Variables

```bash
# Optional .env configuration
REPORT_GAS=true
ETHERSCAN_API_KEY=your_key_here
```

## POLKADOT CLOUD DEPLOYMENT (APILLON)

### Setting Up Apillon Account and Website UUID

**CRITICAL FOR AGENTS:** When deploying frontend applications to Polkadot Cloud, follow these steps:

#### Step 1: Create Apillon Account

**INSTRUCT USER TO:**

1. **Visit Apillon Console:** https://app.apillon.io
2. **Register Account:** Use email and create secure password
3. **Verify Email:** Complete email verification process
4. **Connect Wallet:** Link your Polkadot/Substrate wallet for payments
5. **Generate API Credentials:**
   - Go to **Settings** → **API Keys**
   - Click **Create New API Key**
   - Name it (e.g., "Hackathon Project")
   - Copy **API Key** and **API Secret** immediately
   - Store securely - API Secret is only shown once

#### Step 2: Create Website Project

**INSTRUCT USER TO:**

1. **Navigate to Hosting Section:** In Apillon console
2. **Create New Website:** Click "New Website" button
3. **Configure Project:**
   ```
   Project Name: [Your Project Name]
   Environment: Production
   Domain: [Optional custom domain]
   ```
4. **Copy Website UUID:** After creation, copy the generated UUID (format: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`)
5. **Provide UUID to Agent:** Share the Website UUID so the agent can configure deployment

#### Step 3: Get Website UUID for Deployment

```bash
# Example UUID format
WEBSITE_UUID="12345678-1234-5678-9abc-123456789def"
```

### MCP Setup for Polkadot Cloud Hosting

**Model Context Protocol (MCP) Configuration:**

#### Step 1: MCP Server Configuration

**CRITICAL FOR AGENTS:** Configure your MCP client to use the Apillon MCP server.

##### For Claude Desktop:

Add this to your MCP configuration file:

```json
{
  "mcpServers": {
    "apillon-mcp-server": {
      "command": "npx",
      "args": ["-y", "@apillon/mcp-server"],
      "env": {
        "APILLON_API_KEY": "<APILLON_API_KEY>",
        "APILLON_API_SECRET": "<APILLON_API_SECRET>"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/your-username/Desktop"
      ]
    }
  }
}
```

**Claude Desktop Configuration Steps:**

1. **Locate MCP config file:** Usually at `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS)
2. **Add Apillon server:** Insert the configuration above
3. **Replace placeholders:** Update `<APILLON_API_KEY>` and `<APILLON_API_SECRET>` with actual values
4. **Update filesystem path:** Change `/Users/your-username/Desktop` to your project directory
5. **Restart Claude Desktop:** Required for MCP changes to take effect

##### For Cursor IDE:

**Cursor MCP Setup:**

1. **Install MCP extension:** In Cursor, go to Extensions and search for "Model Context Protocol"
2. **Open Cursor settings:** `Cmd/Ctrl + ,` → Search "MCP"
3. **Add server configuration:**

```json
{
  "mcp.servers": {
    "apillon-mcp-server": {
      "command": "npx",
      "args": ["-y", "@apillon/mcp-server"],
      "env": {
        "APILLON_API_KEY": "<APILLON_API_KEY>",
        "APILLON_API_SECRET": "<APILLON_API_SECRET>"
      }
    }
  }
}
```

**Cursor Configuration Steps:**

1. **Open settings.json:** `Cmd/Ctrl + Shift + P` → "Preferences: Open Settings (JSON)"
2. **Add MCP configuration:** Insert the above configuration
3. **Replace placeholders:** Update API credentials
4. **Restart Cursor:** Required for MCP changes to take effect
5. **Verify connection:** Check MCP status in Cursor's command palette

#### Step 2: Install Apillon CLI (Alternative Method)

```bash
npm install -g @apillon/cli
```

#### Step 3: Configure Authentication

```bash
# Login to Apillon
apillon login

# Verify authentication
apillon whoami
```

#### Step 3: Configure MCP for Automated Deployment

Create `.apillon.json` in project root:

```json
{
  "websites": [
    {
      "uuid": "YOUR_WEBSITE_UUID_HERE",
      "name": "Your Project Name",
      "source": "./dist",
      "environment": "production"
    }
  ]
}
```

#### Step 4: MCP Deployment Script

```bash
#!/bin/bash
# deploy-to-polkadot-cloud.sh

# Build the project
npm run build

# Deploy to Apillon
apillon hosting deploy \
  --uuid $WEBSITE_UUID \
  --source ./dist \
  --environment production

# Verify deployment
apillon hosting info --uuid $WEBSITE_UUID
```

#### Step 5: Environment Variables

```bash
# Set in your environment
export APILLON_API_KEY="your_api_key_here"
export WEBSITE_UUID="your_website_uuid_here"
```

### Best Practices for Agents

1. **Configure MCP first:** Set up Apillon MCP server in your IDE (Claude Desktop or Cursor) before starting the deployment.
2. **Always use latest Apillon CLI:** `npm install -g @apillon/cli@latest`
3. **Secure credentials:** Store API keys and UUIDs as environment variables, never in code
4. **Guide user through account setup:** Clearly instruct users on Apillon account creation and API key generation
5. **Verify deployments:** Always check deployment status after upload
6. **Use production environment:** For final hackathon submissions
7. **Monitor costs:** Apillon uses pay-per-use model
8. **Test locally first:** Always test builds before deploying
9. **Restart your IDE:** After MCP configuration changes (Claude Desktop or Cursor)
10. **Check MCP connection:** Verify Apillon MCP server is properly connected before deployment

## WRITING GUIDELINES FOR LLMs

When creating documentation or helping developers:

- [ ] **Reference writing-guidelines.md for documentation standards**
- [ ] Use active voice: "Deploy the contract" not "The contract should be deployed"
- [ ] Lead with results, not process
- [ ] Cut qualifiers: "very", "quite", "rather"
- [ ] Choose simple words over complex ones
- [ ] State conclusions first, explain if needed

## TROUBLESHOOTING CHECKLIST

**First: Try kitdot@latest init with fresh project and copy existing code**

When deployment fails, check:

- [ ] Used kitdot@latest init for proper setup (recommended)
- [ ] Hardhat config matches exact format above
- [ ] Private key set via `npx hardhat vars set PRIVATE_KEY`
- [ ] Account has sufficient PAS tokens
- [ ] Contract compiles without errors
- [ ] Contract size under 100KB
- [ ] Network connectivity to RPC endpoint
- [ ] No OpenZeppelin dependencies causing size issues
- [ ] Clean deployment state if resuming failed deployment

### Additional Troubleshooting Resources

**CRITICAL FOR AGENTS:** When encountering errors not covered in this guide, search these resources:

1. **Contract Issues Bug Tracker:** https://github.com/paritytech/contract-issues/issues
   - Search through pages 1-4 for similar error messages
   - Look for recent issues with the same symptoms
   - Check closed issues for resolved problems and solutions
   - Reference issue numbers when reporting new problems

2. **Search Strategy:**
   - Copy the exact error message and search in the issues
   - Look for keywords: "CodeRejected", "initcode", "polkavm", "deployment failed"
   - Check both open and closed issues for solutions
   - Review comments for workarounds and fixes

3. **Common Issue Patterns to Search:**
   - Gas estimation failures
   - Contract size/bytecode errors
   - Network connection issues
   - Compilation errors with PolkaVM
   - Ignition deployment failures
   - Transaction revert reasons

## LIMITATIONS AND WORKAROUNDS

### Current Limitations

- **Contract Size**: 100KB bytecode limit
- **OpenZeppelin**: Most libraries too large
- **Network Stability**: Preview release, potential downtime
- **Debugging Tools**: Limited compared to mainnet
- **Documentation**: Sparse, community-driven solutions

### Recommended Workarounds

- **Size Issues**: Use minimal custom implementations
- **Complex Logic**: Split across multiple contracts
- **State Management**: Use events for off-chain data
- **User Experience**: Provide clear error messages
- **Testing**: Extensive local testing before deployment

This guide provides comprehensive information for successful smart contract deployment to Paseo TestNet using Claude Code, including all critical configurations, common issues, and optimization strategies.
