---
DCP: 5
Title: NFT
Description: Number of NFTs and NFTs owned by an address.
Author: Quest3
Status: 
Type: 
Category: 
Created: 
---

## Abstract

DCP-5 is part of the fundamental framework for constructing Quest3 on-chain quest system. In order to validate if a Web3 user holds blue-chip NFTs, there is a minimum NFT holding threshold setup. And also can measure the current price of blue-chip NFTs.

## Motivation & rationales

This proposal provides reference data for the NFTs community, and a new NFTs project can provide a new channel for potential purchasers on the basis of blue-chip NFTs. The community of blue-chip NFTs can signal true partners.

## Specification

A proof-of-holding feature to tag an address currently holding NFTs’ contract and symbol with the number of holdings.

### Data source

Blockchain: Ethereum

### Data Schema
```
[
    {
        "symbol": string,                                                                          // NFT name
        "contract":string ,                                                                        // NFT contract address
        "count":   string                                                                          // Number of holdings
    }
]
 
Access path: https://credentials.knn3.xyz/nft/:address
Example: 
https://credentials.knn3.xyz/nft/0x04764f07542f8870168236da61d31c217c4cbc56

[
    {
        "symbol":"DW",                                                                             // NFT name
        "contract":"0x57f1887a8bf19b14fc0df6fd9b2acc9af147ea85",  // NFT contract address
        "count":"1"                                                                                // Number of holdings
    }
]
```
## Author & contributors

Quest3 is a revolutionary quest and event DApp, where users can earn tokens and NFT badges by participating in quests and events. Eventually, Quest3 will become a Web3 advertising platform, benefiting users continuously, flourishing the propagation ecosystem, and realizing Web3 native value delivery.

Website: https://quest3.xyz 

Wiki: https://notion.so/Quest3-WiKi-340c900c3e3542a7bfb6c6993017c8cc

One Page: https://docsend.com/view/wvxskbsyg356igm7

## References / Citations

More about [NFTs (ERC-721)](https://eips.ethereum.org/EIPS/eip-721).
