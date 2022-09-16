---
DCP: 7
Title: Next.ID
Description: 
Author: Next.ID
Status: 
Type: DIDs
Category: 
Created: 
---

## Abstraction

DCP-7 is integrating Next.ID into KNN3 relational database. Next.ID is a Decentralized-Identity-as-a-Service (DIaaS) protocol that aggregates digital identities across Web2 and Web3, allowing users to create permissionless DID (decentralized identifiers) called Avatars.

Motivation & rationales

With the permissionless integration of Next.ID and the introduction of Next.ID’s Avatars, KNN3’s graphs are now offering:

An identity-first component to the data

Avatars provide off-chain web2-web3 identity data for more comprehensive profiles like associations of users’ Web2 (Twitter) and Web3 (blockchain wallets) accounts. Along with the cooperation, deeper and further user enabling can be realized across diverse platforms and facilitate the web3 ecosystem climate. Developers and users will have a more streamlined experience of Web3, as well as access to previously-unheard of usage scenarios like social relationship discovery/recommendation and a robust reputation system.


## Specification

Through the user's Avatar ID, you can query all bound EOA addresses, Twitter Handles, and assets owned by the addresses, such as NFTs, participating activities POAP, etc.

Data source

Next.ID Doc: [https://proof-service.next.id](https://proof-service.next.id)

Data Schema


```
query {
  avatars{
    Id               //avatar ID
    includeAddrs{
      Address        //EOA address bonded to corresponding avatar ID
      ens            //Resolved ENS address
    }
    includeTwitters{
      Id            //twitter handle bonded to corresponding avatar ID
    }
  }
}
```


Graphql Endpoint:[ https://mw.graphql.knn3.xyz/](https://mw.graphql.knn3.xyz/)


### Author & contributors

Next.ID is an decentralized-identity-as-a-service protocol created by Dimension, the team behind Mask Network. Next.ID is an open-source protocol for all self-governed digital identities across Web2 and Web3. 

Website:[ https://next.id/](https://quest3.xyz)


### Reference/Citation

More about [Avatar](https://docs.next.id/glossary#glossary-avatar).
