---
layout: post
title: "Blockchain with solidity 2"
date: 2021-07-14 11:54:49 +0530
categories: blockchain solidity truffle ganache
permalink: '/post/blockchain-with-solidity-2'
---

Using truffle framework and ganache-cli to create smart contract 🟥🟦.

Truffle is a framework for ethereum. It can be used to compile and migrate .sol files by `truffle compile` and `truffle migrate`. Running compile will create `build` folder where .json files of the compiled .sol files are stored. What is their function I don't know.

The truffle migrate command will start migrating or creating the blocks. At first migration is deployed, initial_migration.js which starts at block 0 and add 1 block to it. Then HelloBlockchain is deployed, deploy_contracts.js which adds 3 block. For each deplyment we get access to transaction hash, gas uses, balance, account and other informations.

But before migration a running blockchain client is needed. `ganache-cli` is such a tool. It creates a local blockchain client to migrate and test ethereum blockchain. To create a client `ganache-client` has to run in terminal. Both ganache and truffle can be installed as npm package globally. The ganache-cli command will create 10 accounts with 100 ETH with private key and a mnemonic. the blockchain client is hosted at address 127.0.0.1:8545. Once ganache is running we can easily run migration and also tests in test folder by the command `truffle test`.