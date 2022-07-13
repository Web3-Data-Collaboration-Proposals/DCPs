---
DCP: 4
Title: ENS
Description: Get the Numbers of ENS held by an address.
Author: Quest3
Status: Published
Type: Proof-of-Status
Category: 
Created: 
---

## Abstract

DCP - 4 is part of the fundamental framework for constructing Quest3 on-chain quest ·system. In order to validate if a Web3 user is eligible to complete the ENS domain task, there is a minimum ENS domain holding threshold setup.

## Motivation & rationales

This proposal will help the ENS community to screen the real ENS domain holders, proof the holder's on-chain identification. Enables ENS community members to identify with each other.

## Specification

A proof-of-holding feature to tag addresses currently holds how many ENS and how many ENS names resolving to this address. 

### Data source

Blockchain: Ethereum

### Data Schema
```
{
     "holdCount": number,                        // # of ENS holdings
     "count": number                             // # of ENS resolvers
}

Example:
https://credentials.knn3.xyz/ens/0x04764f07542f8870168236da61d31c217c4cbc56

{
     "holdCount": 1                           // number of ENS NFT holdings
     "count": 1,                              // number of ENS resolvers
     "updatedAt":1655095727                   // Last update time.
}
```
## Author & contributors

Quest3 is a revolutionary quest and event DApp, where users can earn tokens and NFT badges by participating in quests and events. Eventually, Quest3 will become a Web3 advertising platform, benefiting users continuously, flourishing the propagation ecosystem, and realizing Web3 native value delivery.

Website: https://quest3.xyz 

Wiki: https://notion.so/Quest3-WiKi-340c900c3e3542a7bfb6c6993017c8cc

One Page: https://docsend.com/view/wvxskbsyg356igm7

## References / Citations

More about [ENS](https://docs.ens.domains/).
