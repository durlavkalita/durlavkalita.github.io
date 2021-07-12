---
layout: post
title: "Blockchain with solidity 1"
date: 2021-07-12 11:54:49 +0530
categories: blockchain solidity
permalink: '/post/blockchain-with-solidity-1'
---

Building basic smart contract with solidity 🟥🟦.

I finally ran my first etherium smart contract and deployed it locally. Continuing the microsoft course, I installed a vs-code extension called 'Blockchain Development Kit for Etherium'. It needs npm, git, python, truffle and ganache installed on the machine. The extension provides boilerplate code for new solidity project. There are two types of projects that can be created and I tried the basic project scaffold. It creates a boilerplate files and folders for solidity projects. There is a package.json file and truffle-config.js file. The main folder is contracts folder where there is already a sample HelloBlockchain.sol solidity file along with Migration.sol which links to the migration folder(I think). There is also a test folder in base directory where test code can be written in js.

When right clicking on HelloBlockchain.sol file there are two important options, build contracts which builds the contracts by running migrations and all kind of stuff. The second option deploy contracts is used to deploy the contract locally in development mode but I don't know much about how or what goes on during the process. Once deployed the output terminal spits out info about contract, gas used(gas is fees of conducting a transaction) and etherium balance which starts as 100 ETH.
