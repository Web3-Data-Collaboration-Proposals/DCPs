---
DCP: 6
Title: Snapshot
Description: Number of votes in snapshot
Author: Quest
Status: 
Type: 
Category: 
Created: 
---

## Abstract

DCP-6 is part of the fundamental framework for constructing Quest3 on-chain quest system. In order to validate if a Web3 user voting on Snapshot, there is a minimum voting times threshold setup. The number of votes can even be limited to a specific proposal.

## Motivation & rationales

This proposal will greatly promote the on-chain governance of Snapshot, retrieve on-chain data, and provide motivation for more Web3 users to participate in community governance. Addresses participating in community governance will be rewarded by the community.

## Specification

A proof-of-vote feature marks who(address) voted on which project(spaceID) and how many votes were made in total by this address.

### Data source

Thegraph: https://hub.snapshot.org/graphql

### Data Schema
```
{
     "totalCount": number,                         // Total votes
     "updatedAt":number,                           // Last update time
      "balancer.eth": number                       // “spaceID”: number of votes
}

Access path: https://credentials.knn3.xyz/snapshot/:address
Example: 
https://credentials.knn3.xyz/snapshot/0x28143659f4500411D9E49513B88E66CDF81F9002
{
     "totalCount": 1,                              // Total votes
     "updatedAt":1655095727,                       // Last update time
      "balancer.eth": 1                            // “spaceID”: number of votes
}
```
## Author & contributors

Quest3 is a revolutionary quest and event DApp, where users can earn tokens and NFT badges by participating in quests and events. Eventually, Quest3 will become a Web3 advertising platform, benefiting users continuously, flourishing the propagation ecosystem, and realizing Web3 native value delivery.

Website: https://quest3.xyz 

Wiki: https://notion.so/Quest3-WiKi-340c900c3e3542a7bfb6c6993017c8cc

One Page: https://docsend.com/view/wvxskbsyg356igm7

## References / Citations

More about [Snapshot](https://snapshot.org/).
