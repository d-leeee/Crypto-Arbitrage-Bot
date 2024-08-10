1. Setup Node.js Project
Make sure you are in your project directory:

bash
Copy code
mkdir arbitrage-bot
cd arbitrage-bot
npm init -y
2. Install Hardhat and Dependencies
Install Hardhat and its related plugins, as well as TypeScript and the necessary type definitions:

bash
Copy code
npm install --save-dev hardhat @nomicfoundation/hardhat-toolbox typescript ts-node @types/node
3. Install Ethers
Install the ethers library, which is required for interacting with Ethereum:

bash
Copy code
npm install ethers
4. Install Uniswap and SushiSwap Interfaces
If you need Uniswap and SushiSwap interfaces for interacting with their contracts, you might need to add specific packages. You can use @uniswap and @sushiswap packages if available:

bash
Copy code
npm install @uniswap/v3-core @uniswap/v3-periphery @sushiswap/sdk
5. Install OpenZeppelin Contracts
For common contracts and utilities like SafeMath, install OpenZeppelin Contracts:

bash
Copy code
npm install @openzeppelin/contracts
6. Install Flashloan Provider
If you are using a specific flash loan provider, like Aave, you need to install its contract interfaces. For Aave, you can use:

bash
Copy code
npm install @aave/protocol-v2
7. Install TypeChain for TypeScript Support
TypeChain provides TypeScript bindings for Ethereum smart contracts:

bash
Copy code
npm install --save-dev typechain @typechain/hardhat
8. Update TypeScript Configuration
Generate or update the tsconfig.json:

bash
Copy code
npx tsc --init
Modify tsconfig.json to include Hardhat and TypeScript settings:

json
Copy code
{
  "compilerOptions": {
    "target": "ESNext",
    "module": "CommonJS",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": ["scripts", "test", "typechain"],
  "files": ["hardhat.config.ts"]
}
9. Update Hardhat Configuration
Ensure hardhat.config.ts includes the necessary plugins and settings:

typescript
Copy code
import { HardhatUserConfig } from "hardhat/config";
import "@nomicfoundation/hardhat-toolbox";
import "@typechain/hardhat";

const config: HardhatUserConfig = {
  solidity: "0.8.19", // or your desired version
  typechain: {
    outDir: "typechain",
    target: "ethers-v5",
  },
};

export default config;
