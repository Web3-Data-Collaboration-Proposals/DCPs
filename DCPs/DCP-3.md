# DCP-3

### Summary

Name: Impossible Finance Loyalty System

Website:

Github:

### Description

### Data feature specification

#### IF\_FANS\_TOKEN\_THRESHOLD

**Description**

Find the addresses whose IF token balance larger than 650, and then record them into pg database.

**Data Source**

Contracts:

* 0xB0e1fc65C1a741b4662B813eB787d369b8614Af1
  * Blockchain: Binance Smart Chain
  * Name: Impossible Finance

**Data Decoding**

Get Transfer Event from contract 0xB0e1fc65C1a741b4662B813eB787d369b8614Af1.

```
Transfer (index_topic_1 address from, index_topic_2 address to, uint256 amount)
```

After catching each Transfer Event, reduce balance of from address as balance = balance - amount, and increase balance of to address as balance = balance + amount.

If balance of to address larger than 650, add it into pg.

If from address is already in pg, and after this transfer its balance becomes less than 650, delete it from pg.

\*Notice: All data analysis needs to be ordered by blockNumber.

### Reference

### Contributor
