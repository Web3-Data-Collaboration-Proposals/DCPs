---
dcp: 1
title: Pigeon Envelope
description: 
author: 
status: Published
created: 2022-3-15
---

## Summary

Name: Pigeon Envelope

Website: [https://www.knn3.xyz/](https://www.knn3.xyz/)

Github:  [https://github.com/Treasury-research/ETHDenver_Pigeon](https://github.com/Treasury-research/ETHDenver_Pigeon)

## Description

## Data feature specification

### Pigeon_Envelope_Status

**Description**

The data of dcp1 traces the real-time envelope status info, there are two status about an envelope:

- **status = 0** envelope has not been opened;
- **status = 1** envelope has been opened.

**Data Source**

Contracts: 

- 0x6D0471b04988bAF6B50B2cdcFe6929636a68FE86
    - Blockchain: Polygon
    - Name: Pigeon Envelope
- 0x3592304e2b3B8d37B0FFB23aA56C7CFF1a2f30C4
    - Blockchain: Polygon
    - Name: Pod Tag

**Data Decoding**

Get Transfer Event from contract 0x6D0471b04988bAF6B50B2cdcFe6929636a68FE86.

```
Transfer (index_topic_1 address from, index_topic_2 address to, uint256 tokenId)
```

from = address(0) means mint an envelope nft to to address, and initially state = 0.

Code reference:

```
const inputs = [
  {
    indexed: true,
    internalType: "address",
    name: "from",
    type: "address",
  },
  {
    indexed: true,
    internalType: "address",
    name: "to",
    type: "address",
  },
  {
    indexed: true,
    internalType: "uint256",
    name: "tokenId",
    type: "uint256",
  },
];

const hexString = "0x";

const topics = [
  "0x0000000000000000000000000000000000000000000000000000000000000000",
  "0x00000000000000000000000063d5bdee0d0d427e76eb36cff39d188fxxxxxxxx",
  "0x0000000000000000000000000000000000000000000000000000000000002259",
];

const result = web3.eth.abi.decodeLog(inputs, hexString, topics);
console.log(result);

// result 
from: '0x0000000000000000000000000000000000000000',
to: '0x63d5BDee0d0D427E76EB36CFF39D188Ffxxxxxxxx',
tokenId: 'xxxx'
```

Then get SetTag Event from contract 0x3592304e2b3B8d37B0FFB23aA56C7CFF1a2f30C4.

```
SetTag (
        bytes20 indexed id,
        bytes18 indexed tagClassId,
        IPodCore.TagObject object,
        bytes data,
        address issuer,
        uint32 expiredAt
	    );
```

Filter needed data by tagClassId = 0xa4fdd682161c7902ee44fe7ee6a982e79ffe, update the envelope status of to address from above if the status of matching object.Address = to turns to 1.

Code reference:

```
const inputs = [
  {
    indexed: true,
    internalType: "bytes20",
    name: "id",
    type: "bytes20",
  },
  {
    indexed: true,
    internalType: "bytes18",
    name: "tagClassId",
    type: "bytes18",
  },
  {
    components: [
      {
        internalType: "enum IPodCore.ObjectType",
        name: "Type",
        type: "uint8",
      },
      {
        internalType: "bytes20",
        name: "Address",
        type: "bytes20",
      },
      {
        internalType: "uint256",
        name: "TokenId",
        type: "uint256",
      },
    ],
    indexed: false,
    internalType: "struct IPodCore.TagObject",
    name: "object",
    type: "tuple",
  },
  {
    indexed: false,
    internalType: "bytes",
    name: "data",
    type: "bytes",
  },
  {
    indexed: false,
    internalType: "address",
    name: "issuer",
    type: "address",
  },
  {
    indexed: false,
    internalType: "uint32",
    name: "expiredAt",
    type: "uint32",
  },
];

const hexString =
  "0x0000000000000000000000000000000000000000000000000000000000000000b9f8a99d8d8e57b34eef60dfe9b95325320e9988000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000c0000000000000000000000000b9f8a99d8d8e57b34eef60dfe9b95325320e998800000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000";

const topics = [
  "0x616e4345324e4ef22306363cac2d564db9380e11000000000000000000000000",
  "0xa4fdd682161c7902ee44fe7ee6a982e79ffe0000000000000000000000000000",
];

const result = web3.eth.abi.decodeLog(inputs, hexString, topics);
console.log(result);

// result
id: '0x616e4345324e4ef22306363cac2d564db9380e11000000000000000000000000',
tagClassId: '0xa4fdd682161c7902ee44fe7ee6a982e79ffe0000000000000000000000000000',
object: [
  Type: '0',
  Address: '0xb9f8a99d8d8e57b34eef60dfe9b95325320exxxx',
  TokenId: '0'
],
data: null,
issuer: '0xb9f8A99D8d8e57B34eEF60dFE9B95325320exxxx',
expiredAt: '0'
```

## Reference

## Contributor
