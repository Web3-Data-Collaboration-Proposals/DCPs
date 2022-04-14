---
DCP: 3
Title: Impossible Finance Loyalty System
Description: 
Author: Impossible Finance
Status: Published
Type: #Proof-of-Action-credentials #Membership
Category: Data component
Created: 2022-04-12
---

## Abstract

DCP - 3 is the fundamental framework to construct Impossible Finance’s loyalty program. In order to validate if a web3 user is eligible for an Impossible community fan, there is a minimum $IF token holding threshold setup. In the future, these qualification criteria can be extended as the fans system requires more sophisticated conditions. The Impossible Friends group consist of power and loyal users in the Impossible community, launchpad users can enjoy various benefits and grow with the Impossible in a meaningful and symbiotic way. 

## Motivation

This application could bring membership system in a full Web3 structure, adapting on-chain data to power decentralized community in building the community infrastructure in Impossible Finance.  


Website: https://impossible.finance

Github: https://github.com/ImpossibleFinance

## Description

## Data feature specification

### IF_Token_Balance_Lt_625

**Definition**

A proof-of-holding feature to tag who currently holds $IF token >= 625. This is a threshold to be an eligible Impossible Finance fan.

**Data Source**

Contracts: 

- 0xB0e1fc65C1a741b4662B813eB787d369b8614Af1
    - Blockchain: Binance Smart Chain
    - Name: Impossible Finance

**Data Schema**

Get Transfer Event from contract 0xB0e1fc65C1a741b4662B813eB787d369b8614Af1.

```
Transfer (index_topic_1 address from, index_topic_2 address to, uint256 amount)
```

To calculate the real-time holding balance, reduce the balance of the “from” address as balance = balance - amount, and increase the balance of to address as balance = balance + amount.

*Notice: All data sum needs to be sorted by blockNumber.

## Author & contributors

Impossible Finance is the go-to crypto investment platform that empowers you with high-quality, fair and accessible crypto opportunities. 

Impossible Finance simplifies DeFi so you can enjoy fairer investing, cheaper trading and better yields through our accelerator, launchpad, and swap platform.

https://lintr.ee/impossiblefi

## References / Citations

More about Impossible Friends:
https://medium.com/impossiblefinance/the-impossible-friends-community-program-ffb4d8dc3e4d

Imposible Finance GitHub:
https://github.com/ImpossibleFinance
