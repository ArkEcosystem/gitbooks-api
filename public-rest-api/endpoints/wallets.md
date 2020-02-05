---
title: Wallets
---

# Wallets

Wallets are addresses containing, or previously having contained ARK. A wallet's public key may be unknown to the network, in that case, it is referred to as a `cold wallet`.

## List All Wallets

A paginated API is provided to obtain all wallets, including empty ones.

### Endpoint

```text
GET /api/wallets
```

### Example

```bash
curl http://dexplorer.ark.io/api/wallets
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |
| orderBy | string | Type by which it orders wallets. | No |
| address | string | ... | No |
| publicKey | string | ... | No |
| senderPublicKey | string | ... | No |
| vote | string | ... | No |
| username | string | ... | No |
| balance | int | ... | No |
| voteBalance | int | ... | No |
| producedBlocks | int | ... | No |

### Response

```javascript
{
    "meta": {
        "count": 100,
        "pageCount": 1968,
        "totalCount": 196789,
        "next": "/wallets?page=2&limit=100",
        "previous": null,
        "self": "/wallets?page=1&limit=100",
        "first": "/wallets?page=1&limit=100",
        "last": "/wallets?page=1968&limit=100"
    },
    "data": [
        {
            "address": "D6Z26L69gdk9qYmTv5uzk3uGepigtHY4ax",
            "publicKey": "03d3fdad9c5b25bf8880e6b519eb3611a5c0b31adebc8455f0e096175b28321aff",
            "nonce": "249",
            "balance": "8792440174231098",
            "attributes": {
                "delegate": {
                    "lastBlock": {
                        "id": "13114381566690093367",
                        "height": 1,
                        "timestamp": 0,
                        "generatorPublicKey": "03d3fdad9c5b25bf8880e6b519eb3611a5c0b31adebc8455f0e096175b28321aff"
                    }
                }
            },
            "isDelegate": false,
            "isResigned": false
        },
        {
            "address": "DEyaFhDuaoQyKbFH4gJtYZvKkB6umyrEUj",
            "publicKey": "033c59dcdc36944cc28f68c1e4b47ac370fe326e53f9adf5f07764d3e8b74b1838",
            "nonce": "2111",
            "balance": "2000044819999638",
            "attributes": {
                "secondPublicKey": "03820f214bd49a09c636fa366b4b3c1a0dbd2953d14aac7e68a596e0636e662dfb",
                "delegate": {
                    "username": "whalessio",
                    "voteBalance": "0",
                    "forgedFees": "0",
                    "forgedRewards": "0",
                    "producedBlocks": 0,
                    "rank": 291
                },
                "vote": "033a5474f68f92f254691e93c06a2f22efaf7d66b543a53efcece021819653a200"
            },
            "isDelegate": true,
            "isResigned": false,
            "vote": "033a5474f68f92f254691e93c06a2f22efaf7d66b543a53efcece021819653a200"
        },
        {
            "address": "DSyG9hK9CE8eyfddUoEvsga4kNVQLdw2ve",
            "publicKey": "033a5474f68f92f254691e93c06a2f22efaf7d66b543a53efcece021819653a200",
            "nonce": "21578",
            "balance": "150272074652148",
            "attributes": {
                "secondPublicKey": "026de1cd4321a7e78a7b4d8453d1b1ca210eaf991022c55a99e9b0b9ebddbbd502",
                "delegate": {
                    "username": "alessio",
                    "voteBalance": "2001209586209110",
                    "forgedFees": "468407250508",
                    "forgedRewards": "14120600000000",
                    "producedBlocks": 70801,
                    "rank": 1,
                    "lastBlock": {
                        "version": 0,
                        "timestamp": 90793640,
                        "height": 4138753,
                        "previousBlockHex": "274270f5d0e140f8b1c382c6b74afa4aa87256ecfc2cf26b5a597124b3e22b60",
                        "previousBlock": "274270f5d0e140f8b1c382c6b74afa4aa87256ecfc2cf26b5a597124b3e22b60",
                        "numberOfTransactions": 0,
                        "totalAmount": "0",
                        "totalFee": "0",
                        "reward": "200000000",
                        "payloadLength": 0,
                        "payloadHash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
                        "generatorPublicKey": "033a5474f68f92f254691e93c06a2f22efaf7d66b543a53efcece021819653a200",
                        "blockSignature": "3044022019b157d3bce0c8b7bcad4b3fb427af49e92a48e902172d0c17213ba0a6388db1022029bd561d91a36a835b0e6fc3e98a4b2050f5a42fae05c70e0076616fa2b5553e",
                        "idHex": "f1c2b78bcd7904dbfb6a240e3feaacf678e1de64c95fbdd0f6252268538e6f4d",
                        "id": "f1c2b78bcd7904dbfb6a240e3feaacf678e1de64c95fbdd0f6252268538e6f4d"
                    },
                    "round": 81153
                },
                "vote": "0215789ac26155b7a338708f595b97c453e08918d0630c896cbd31d83fe2ad1c33"
            },
            "isDelegate": true,
            "isResigned": false,
            "vote": "0215789ac26155b7a338708f595b97c453e08918d0630c896cbd31d83fe2ad1c33"
        },
    ...
    ]
}
```

## Retrieve a Wallet

Specific wallets can be obtained either by their `publicKey` or `address`.

### Endpoint

```text
GET /api/wallets/{id}
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the wallet to be retrieved. | Yes |

### Response

```javascript
{
  "data": {
    "address": "D9YiyRYMBS2ofzqkufjrkB9nHofWgJLM7f",
    "publicKey": "0306950dae7158103814e3828b1ab97a87dbb3680db1b4c6998b8208865b2f9db7",
    "username": "bongoninja",
    "secondPublicKey": null,
    "balance": 12534670000000,
    "isDelegate": true
  }
}
```

## List All Transactions of a Wallet

All transactions belonging to a wallet can be obtained using this API. Equivalent to `transactions/search` with parameters `senderId` and `recipientId`.

### Endpoint

```text
GET /api/wallets/{id}/transactions
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the wallet to be retrieved. | Yes |

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Response

```javascript
{
    "meta": {
        "count": 2,
        "pageCount": 127430,
        "totalCount": 254860,
        "next": "/v2/wallets/boldninja/transactions?page=2",
        "previous": null,
        "self": "/v2/wallets/boldninja/transactions?page=1",
        "first": "/v2/wallets/boldninja/transactions?page=1",
        "last": "/v2/wallets/boldninja/transactions?page=127430"
    },
    "data": [
        {
            "id": "261ec03a90e8c287fb2dcbb35bb8a842fe5ef1c7a6425319da7aa123c48dd929",
            "blockId": "15006101391552623930",
            "version": 1,
            "type": 0,
            "amount": 100000000,
            "fee": 10000000,
            "sender": "DHWBaG44rstymZjWFU4b7BiuTZjiKxfJpL",
            "recipient": "D9YiyRYMBS2ofzqkufjrkB9nHofWgJLM7f",
            "signature": "3045022100d7b59289b9576978fc0cbfea2f7f490409ef9455f2c4d28cc49f155c9ed69d6002206a32c4b668050f81b789b49fe5c29164872f9f1db63d7ba8604a6296f183a18a",
            "signSignature": "3045022100dae0598ff7dcab0184d36e3d8313da17401893b2b6b476276412f2682e66c34402205df085dae213c561e5db293cd5bc8930f6343783a99ce48c349e92abfd2e2fa1",
            "vendorField": ":bongocrazy"
            "confirmations": 347019,
            "timestamp": {
                "epoch": 51704908,
                "unix": 1541806108,
                "human": "2018-11-09T23:28:28.000Z"
            }
        }
    ]
}
```

## List All Received Transactions of a Wallet

Incoming transactions can be obtained as well, Equivalent to `transactions/search` with parameter `recipientId` set.

### Endpoint

```text
GET /api/wallets/{id}/transactions/received
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the wallet to be retrieved. | Yes |

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Response

```javascript
{
    "meta": {
        "count": 2,
        "pageCount": 4,
        "totalCount": 8,
        "next": "/v2/wallets/boldninja/transactions/received?page=2",
        "previous": null,
        "self": "/v2/wallets/boldninja/transactions/received?page=1",
        "first": "/v2/wallets/boldninja/transactions/received?page=1",
        "last": "/v2/wallets/boldninja/transactions/received?page=4"
    },
    "data": [
        {
            "id": "261ec03a90e8c287fb2dcbb35bb8a842fe5ef1c7a6425319da7aa123c48dd929",
            "blockId": "15006101391552623930",
            "version": 1,
            "type": 0,
            "amount": 100000000,
            "fee": 10000000,
            "sender": "DHWBaG44rstymZjWFU4b7BiuTZjiKxfJpL",
            "recipient": "D9YiyRYMBS2ofzqkufjrkB9nHofWgJLM7f",
            "signature": "3045022100d7b59289b9576978fc0cbfea2f7f490409ef9455f2c4d28cc49f155c9ed69d6002206a32c4b668050f81b789b49fe5c29164872f9f1db63d7ba8604a6296f183a18a",
            "signSignature": "3045022100dae0598ff7dcab0184d36e3d8313da17401893b2b6b476276412f2682e66c34402205df085dae213c561e5db293cd5bc8930f6343783a99ce48c349e92abfd2e2fa1",
            "vendorField": ":bongocrazy"
            "confirmations": 347019,
            "timestamp": {
                "epoch": 51704908,
                "unix": 1541806108,
                "human": "2018-11-09T23:28:28.000Z"
            }
        }
    ]
}
```

## List All Sent Transactions of a Wallet

The inverse of `transactions/received`.

> Note that the balance of a wallet does not equal `totalIncoming - totalOutgoing` if the wallet is a Delegate. You must then also add the total reward from transaction fees and forged blocks to their balance.

### Endpoint

```text
GET /api/wallets/{id}/transactions/sent
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the wallet to be retrieved. | Yes |

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Response

```javascript
{
  "meta": {
    "count": 2,
    "pageCount": 2,
    "totalCount": 4,
    "next": "/v2/wallets/boldninja/transactions/sent?page=2",
    "previous": null,
    "self": "/v2/wallets/boldninja/transactions/sent?page=1",
    "first": "/v2/wallets/boldninja/transactions/sent?page=1",
    "last": "/v2/wallets/boldninja/transactions/sent?page=2"
  },
  "data": [
    {
      "id": "686b989f56ede8141289691d166b8158f0b2c3b272112fdf77198e394fa4b59a",
      "blockId": "16409699706603010399",
      "version": 1,
      "type": 3,
      "amount": 0,
      "fee": 100000000,
      "sender": "D9YiyRYMBS2ofzqkufjrkB9nHofWgJLM7f",
      "recipient": "D9YiyRYMBS2ofzqkufjrkB9nHofWgJLM7f",
      "signature": "304402202ad26e82b6b9c96babfb7fba4389d17e868cc802ada3a7d263848a8b7baa144402205e5571afdba7b1c0cad698620c5306e320f3dadcb9a82df6ebbd3af7df757904",
      "signSignature": null,
      "asset": {
        "votes": [
          "+0306950dae7158103814e3828b1ab97a87dbb3680db1b4c6998b8208865b2f9db7"
        ]
      },
      "confirmations": 526006,
      "timestamp": {
        "epoch": 49663543,
        "unix": 1539764743,
        "human": "2018-10-17T08:25:43.000Z"
      }
    }
  ]
}
```

## List All Votes of a Wallet

Returns all votes made by the wallet. Often users create a new wallet instead of recasting their vote, as the former was historically cheaper.

### Endpoint

```text
GET /api/wallets/{id}/votes
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the wallet to be retrieved. | Yes |

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Response

```javascript
{
  "meta": {
    "count": 2,
    "pageCount": 2,
    "totalCount": 3,
    "next": "/v2/wallets/boldninja/votes?page=2",
    "previous": null,
    "self": "/v2/wallets/boldninja/votes?page=1",
    "first": "/v2/wallets/boldninja/votes?page=1",
    "last": "/v2/wallets/boldninja/votes?page=2"
  },
  "data": [
    {
      "id": "08c6b23f9edd97b613f17153fb97a316a4fb83136e9842655dafc8262f363e0e",
      "blockId": "14847399772737279404",
      "version": 1,
      "type": 3,
      "amount": 0,
      "fee": 100000000,
      "sender": "DARiJqhogp2Lu6bxufUFQQMuMyZbxjCydN",
      "recipient": "DARiJqhogp2Lu6bxufUFQQMuMyZbxjCydN",
      "signature": "304402207ba0e8aaee93695360081b7ce713f13d62b544038ac440bd46357398af86cae6022059ac74586738be1ef622e0baba992d0e417d9aed7ab980f374eb0c9d53e25f8e",
      "asset": {
        "votes": [
          "+0257b7724e97cd832e0c28533a86da5220656f9b5122141daab20e8526decce01f"
        ]
      },
      "confirmations": 1636029,
      "timestamp": {
        "epoch": 17094358,
        "unix": 1507195558,
        "human": "2017-10-05T09:25:58Z"
      }
    }
  ]
}
```

## List All Top Wallets

Sort the wallets by their balance. Most top wallets belong to exchanges and the frozen remainder from the ARK ICO.

### Endpoint

```text
GET /api/wallets/top
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Response

```javascript
{
  "meta": {
    "count": 100,
    "pageCount": 1859,
    "totalCount": 185829,
    "next": "/api/v2/wallets/top?page=2&limit=100",
    "previous": null,
    "self": "/api/v2/wallets/top?page=1&limit=100",
    "first": "/api/v2/wallets/top?page=1&limit=100",
    "last": "/api/v2/wallets/top?page=1859&limit=100"
  },
  "data": [
    {
      "address": "DGihocTkwDygiFvmg6aG8jThYTic47GzU9",
      "publicKey": "024c8247388a02ecd1de2a3e3fd5b7c61ecc2797fa3776599d558333ef1802d231",
      "username": null,
      "secondPublicKey": null,
      "balance": 11499593462120632,
      "isDelegate": false
    },
    {
      "address": "DRac35wghMcmUSe5jDMLBDLWkVVjyKZFxK",
      "publicKey": "0374e9a97611540a9ce4812b0980e62d3c5141ea964c2cab051f14a78284570dcd",
      "username": null,
      "secondPublicKey": null,
      "balance": 554107676293547,
      "isDelegate": false
    }
    //... 98 more wallets
  ]
}
```

## Search All Wallets

Searching for specific wallets is possible as well. A direct database query usually is more performant when the query expression becomes complicated.

### Endpoint

```text
POST /api/wallets/search
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Body Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| address | string | ... | No |
| publicKey | string | ... | No |
| secondPublicKey | string | ... | No |
| vote | string | ... | No |
| username | string | ... | No |
| balance | object | ... | No |
| balance.from | int | ... | No |
| balance.to | int | ... | No |
| votebalance | object | ... | No |
| votebalance.from | int | ... | No |
| votebalance.to | int | ... | No |

### Response

```javascript
{
  "meta": {
    "count": 2,
    "pageCount": 2,
    "totalCount": 3,
    "next": "/v2/wallets/search?page=2",
    "previous": null,
    "self": "/v2/wallets/search?page=1",
    "first": "/v2/wallets/search?page=1",
    "last": "/v2/wallets/search?page=2"
  },
  "data": [
    {
      "address": "DGihocTkwDygiFvmg6aG8jThYTic47GzU9",
      "publicKey": "024c8247388a02ecd1de2a3e3fd5b7c61ecc2797fa3776599d558333ef1802d231",
      "username": null,
      "secondPublicKey": null,
      "balance": 351774803773,
      "isDelegate": false
    }
  ]
}
```

