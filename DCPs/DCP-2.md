# DCP-2

### Summary

Name: Ice Melting Protocol

Website: [https://www.knn3.xyz/](https://www.knn3.xyz/)

Github: [https://github.com/Treasury-research/ETHDenver\_Pigeon](https://github.com/Treasury-research/ETHDenver\_Pigeon)

### Description

### Data feature specification

#### Ice\_Melting\_Status

**Description**

The data of dcp2 traces the tasks finished status, and there are 3 tasks in Ice Melting Protocol:

* Task 1: Follow KNN3 on RSS3
* Task 2: Visit KNN3 Website
* Task 3: Join Pod’s Discord

**Data Source**

Contracts:

* 0x95125adA1BdF707c869E567175b9DDD3AC52A6d0
  * Blockchain: Polygon
  * Name: Ice Melting
* 0x3592304e2b3B8d37B0FFB23aA56C7CFF1a2f30C4
  * Blockchain: Polygon
  * Name: Pod Tag

**Data Decoding**

Get Transfer Event from contract 0x95125adA1BdF707c869E567175b9DDD3AC52A6d0.

```
Transfer (index_topic_1 address from, index_topic_2 address to, uint256 tokenId)
```

from = address(0) means mint an task nft to the to address, and its nft token id is tokenId.

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

Filter data by tagClassId = 0xaf5c7b89abee0f2305ae02fb0b4f1244491f, if object.address in tag match a to address above, this address has finished the task1.

At the same time filter data by tagClassId = 0xae8140bec4c47f83ef148fe0bec5fd770c35, object.address is an address has task1 finished, then resolve the data field in tag, it must be an array. If array is \[1], this address has finished task2 but not finished task3, or if array is \[1, 2], address has both finished task2 and task3.

\*Notice: All data analysis needs to be ordered by blockNumber.

### Reference

### Contributor
