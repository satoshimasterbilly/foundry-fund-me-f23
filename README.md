This is a section of the Cyfrin Solidity Course.

⭐️ (0:00:00) | Lesson 7: Foundry Fund Me

Foundry Fund Me
Getting Started
Requirements
Quickstart
Optional Gitpod
Usage
Testing
Test Coverage
Deployment to a testnet or mainnet
Scripts
Withdraw
Estimate gas
Formatting
Thank you!




## Getting Started

## Requirements

## Git 
git --version
and you see a response like git version x.x.x

## foundry
You'll know you did it right if you can run forge --version and you see a response like forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)

## Foundry forge --version

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

## Quickstart
git clone https://github.com/Cyfrin/foundry-fund-me-f23
cd foundry-fund-me-f23
forge build

## Optional Gitpod
https://gitpod.io/#github.com/PatrickAlphaC/foundry-fund-me-f23

## Deploy 
forge script script/DeployFundMe.s.sol

## Testing
Discussion and topic of learning
1. Unit
2. Integration
3. Forked
4. Staging 
   
## This repo covered #1 and #3
forge test
or

// Only run test functions matching the specified regex pattern.

"forge test -m testFunctionName" is deprecated. Please use 

forge test --match-test testFunctionName

or
forge test --fork-url $SEPOLIA_RPC_URL[https://eth-mainnet.g.alchemy.com/v2/UI7q89gx7vDJZ48oL0d_kax3ya52rA6.....] use https as substitute for $SEPOLIA_RPC_URL

## Test Coverage
forge coverage

## Deployment to a testnet or mainnet

Setup environment variables
You'll want to set your SEPOLIA_RPC_URL and PRIVATE_KEY as environment variables. You can add them to a .env file, similar to what you see in .env.example.

PRIVATE_KEY: The private key of your account (like from metamask). NOTE: FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
You can learn how to export it here.
SEPOLIA_RPC_URL: This is url of the sepolia testnet node you're working with. You can get setup with one for free from Alchemy
Optionally, add your ETHERSCAN_API_KEY if you want to verify your contract on Etherscan.

Get testnet ETH
Head over to faucets.chain.link and get some testnet ETH. You should see the ETH show up in your metamask.

## Deploy
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY

## Scripts
After deploying to a testnet or local net, you can run the scripts.

Using cast deployed locally example:

cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
or
## Withdraw
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY>

## Estimate Gas
forge snapshot
And you'll see an output file called .gas-snapshot

## Formatting
forge fmt

Thank you!


---------------------------------------------------------------------------


