This project contains two upgradable smart contracts used in LIR music creation. Developed with Filippo Andretta (https://github.com/Pelepo).
Init commands:

```shell

//Contract compilation
npx hardhat compile


//First contract deployments
npx hardhat run scripts/firstDeploy.js --network polygon_mumbai
npx hardhat run scripts/firstDeploy.js --network polygon_mainnet

//NFTMint Deployment
npx hardhat run scripts/deployNFTMint.js --network polygon_mumbai
npx hardhat run scripts/deployNFTMint.js --network polygon_mainnet

//NFTMarketplace Deployment
npx hardhat run scripts/deployNFTMarketplace.js --network polygon_mumbai
npx hardhat run scripts/deployNFTMarketplace.js --network polygon_mainnet

//Contract and the Implementation-Proxy verification
npx hardhat verify --contract "contracts/NFTMint.sol:NFTMintUpgradable" contract.address --network polygon_mumbai
npx hardhat verify --contract "contracts/NFTMint.sol:NFTMintUpgradable" contract.address --network polygon_mainnet

npx hardhat verify --contract "contracts/NFTMarketplace.sol:NFTMarketplaceUpgradable" contract.address --network polygon_mumbai
npx hardhat verify --contract "contracts/NFTMarketplace.sol:NFTMarketplaceUpgradable" contract.address --network polygon_mainnet

//Contract ownership transfer
npx hardhat run scripts/transferOwnership.js --network polygon_mainnet

//To update the contract that can interact with NFTMarketplace
npx hardhat run scripts/addNewContract.js --network polygon_mumbai "contractAddress"
npx hardhat run scripts/addNewContract.js --network polygon_mainnet "contractAddress"
