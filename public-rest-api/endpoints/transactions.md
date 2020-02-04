---
title: Transactions
---

# Transactions

Transactions are signed, serialized payloads; batched together to form a block.

## Create a Transaction

Creating the correct payload for a transaction is non-trivial, as it requires cryptographic functions and a specific serialization protocol. Our [crypto SDKs](https://sdk.ark.dev) provide the functionality needed in most major programming languages. You can read more about it in the send transaction section.

### Endpoint

```text
POST /api/transactions
```

### Body Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| transactions | array | The list of transactions to create. | Yes |

### Response

```javascript
{
  "data": {
    "accept": [
      "15d4b3e933b79e5172bbf14c2bd3f92d927394cd8ebd102f18dcc2203af363ca",
      "c48862c4df75a8b0859b559658c757c1c289088488630494fe51613db0747e57",
      "bd10b25444363252e0787e46f5cac90797d08a0c34d507a10d064c94cccf6226"
    ],
    "broadcast": [
      "15d4b3e933b79e5172bbf14c2bd3f92d927394cd8ebd102f18dcc2203af363ca",
      "c48862c4df75a8b0859b559658c757c1c289088488630494fe51613db0747e57",
      "bd10b25444363252e0787e46f5cac90797d08a0c34d507a10d064c94cccf6226"
    ],
    "excess": [],
    "invalid": []
  },
  "errors": null
}
```

## Retrieve a Transaction

Obtaining a transaction by ID does not require advanced logic; as the API does not return a serialized transaction, but a nicer [DTO](https://en.wikipedia.org/wiki/Data_transfer_object).

### Endpoint

```text
GET /api/transactions/{id}
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the transaction to be retrieved. | Yes |

### Response

```javascript
{
  "data": {
    "id": "5c6ce775447a5acd22050d72e2615392494953bb1fb6287e9ffb3c33eaeb79aa",
    "blockId": "4271682877946294396",
    "type": 0,
    "amount": 32106400000,
    "fee": 10000000,
    "sender": "DDiTHZ4RETZhGxcyAi1VruCXZKxBFqXMeh",
    "recipient": "DQnQNoJuNCvpjYhxL7fsnGepHBqrumgsyP",
    "signature": "3044022047c39f6f45a46a87f91ca867f9551dbebf0035adcfcbdc1370222c7a1517fc0002206fb5ecc10460e0352a8b626a508e2fcc76e39e490b0a2581dd772ebc8079696e",
    "confirmations": 1928,
    "timestamp": {
      "epoch": 32794053,
      "unix": 1522895253,
      "human": "2018-04-05T02:27:33Z"
    }
  }
}
```

## List All Transactions

The paginated API is used to query for multiple transactions. You can apply _filters_ through the query parameter to search for specific transactions.

### Endpoint

```text
GET /api/transactions
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |
| type | int | The transaction type to be retrieved. | No |
| blockId | int | The block id to be retrieved. | No |
| id | int | The transaction id to be retrieved. | No |

### Response

```javascript
{
  "meta": {
    "count": 2,
    "pageCount": 127430,
    "totalCount": 254860,
    "next": "/v2/transactions?page=2",
    "previous": null,
    "self": "/v2/transactions?page=1",
    "first": "/v2/transactions?page=1",
    "last": "/v2/transactions?page=127430"
  },
  "data": [
    {
      "id": "5c6ce775447a5acd22050d72e2615392494953bb1fb6287e9ffb3c33eaeb79aa",
      "blockId": "4271682877946294396",
      "version": 1,
      "type": 0,
      "amount": 32106400000,
      "fee": 10000000,
      "sender": "DDiTHZ4RETZhGxcyAi1VruCXZKxBFqXMeh",
      "recipient": "DQnQNoJuNCvpjYhxL7fsnGepHBqrumgsyP",
      "signature": "3044022047c39f6f45a46a87f91ca867f9551dbebf0035adcfcbdc1370222c7a1517fc0002206fb5ecc10460e0352a8b626a508e2fcc76e39e490b0a2581dd772ebc8079696e",
      "asset": {},
      "confirmations": 1924,
      "timestamp": {
        "epoch": 32794053,
        "unix": 1522895253,
        "human": "2018-04-05T02:27:33Z"
      }
    }
  ]
}
```

## List All Unconfirmed Transaction

Unconfirmed transactions have not been incorporated in the blockchain, but reside in the mempool. Although usually the mempool is cleared within minutes, during high network load a transaction with a low fee will live here for a considerable time. If you have set the transaction with a fee of near zero, it might not be picked up by a Delegate and will time out.

### Endpoint

```text
GET /api/transactions/unconfirmed/
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
    "count": 5,
    "pageCount": 8,
    "totalCount": 40,
    "next": "/api/v2/transactions/unconfirmed?limit=5&page=2",
    "previous": null,
    "self": "/api/v2/transactions/unconfirmed?limit=5&page=1",
    "first": "/api/v2/transactions/unconfirmed?limit=5&page=1",
    "last": "/api/v2/transactions/unconfirmed?limit=5&page=8"
  },
  "data": [
    {
      "id": "c94504293d23e3be535a049fdfacba95147f2a87a4ef6682c56801da96befce0",
      "version": 1,
      "type": 0,
      "amount": 70866123,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "signature": "30450221008adeff8eb2a780168704d9e210368d81edff79b81aa7b995e43486f3b1e0096502205caef345584319a6294b1f5283c0d17b478b8a9bcdc10570e5a58681b0eae332",
      "vendorField": "Yooooooloooooo",
      "confirmations": 0,
      "timestamp": {
        "epoch": 56388424,
        "unix": 1546489624,
        "human": "2019-01-03T04:27:04.000Z"
      }
    },
    {
      "id": "db2e54211c352217eee0313a01f6258ac1634e201f04f89b0561d34f7d598066",
      "version": 1,
      "type": 0,
      "amount": 17130719,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DKahhVFVJfqCcCmaQHuYzAVFKcWjBu5i6Z",
      "signature": "30440220069f25d555157f3216b6725e1f66f37b126dcc039f2a4eb12fe74d9e93595d7b02202980215c9375d43f24ebd26a32d6db49f260ad55199c3a137b7dce61e324c970",
      "vendorField": "Yooooooloooooo",
      "confirmations": 0,
      "timestamp": {
        "epoch": 56388424,
        "unix": 1546489624,
        "human": "2019-01-03T04:27:04.000Z"
      }
    },
    {
      "id": "825ab53b50fa99d339486ab780c6a187c7f4fbccfa1098f38be7f57226b144bd",
      "version": 1,
      "type": 0,
      "amount": 11266113,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DG92jj4vUW7SyxzM1VzkmQWMmgBGZVhrjb",
      "signature": "3045022100918864cc6e5ae22010820f1d2a3d4677472d20d7a151597f3f6c705028f28dcf02203518b755fb860b40edfcde5107909d043e7a2cc38d66f5ca52710a0be7e6d710",
      "vendorField": "Yooooooloooooo",
      "confirmations": 0,
      "timestamp": {
        "epoch": 56388425,
        "unix": 1546489625,
        "human": "2019-01-03T04:27:05.000Z"
      }
    },
    {
      "id": "26146b25cde21ab72ecd49a0ac582372314625d854154cfd705dc841a4765ac8",
      "version": 1,
      "type": 0,
      "amount": 737042,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DN8nGwcNbE3YcnZYFp8uvvc9z4WWDbytWK",
      "signature": "3044022067abb680cd6699cf5dac9194c576949dce4b29fe3e4d108724829e8aa34d8a3c02205a3bb91bb46a0182c1dc393c05538e0b673702c75ff39ad0acbf6b879082d911",
      "vendorField": "Yooooooloooooo",
      "confirmations": 0,
      "timestamp": {
        "epoch": 56388425,
        "unix": 1546489625,
        "human": "2019-01-03T04:27:05.000Z"
      }
    },
    {
      "id": "7f54d415750361b3f15bdd4c85d73cbc6ea43efbee6e7725048c223cadd9a4b2",
      "version": 1,
      "type": 0,
      "amount": 70866123,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "signature": "304402207a2f0ce904148dfa1aa0ffc685bdf0614b2e98de98f32b108dd205174d6b767102201566d703296801057e8f94c396fc5be208e6bddde20f5d70be3f46fbcf640bbd",
      "vendorField": "Yooooooloooooo",
      "confirmations": 0,
      "timestamp": {
        "epoch": 56388425,
        "unix": 1546489625,
        "human": "2019-01-03T04:27:05.000Z"
      }
    }
  ]
}
```

## Get an Unconfirmed Transaction

As with confirmed transactions, you may query for unconfirmed transactions directly.

### Endpoint

```text
GET /api/transactions/unconfirmed/{id}
```

### Path Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| id | string | The identifier of the transaction to be retrieved. | Yes |

### Response

```javascript
{
  "data": {
    "id": "c94504293d23e3be535a049fdfacba95147f2a87a4ef6682c56801da96befce0",
    "version": 1,
    "type": 0,
    "amount": 70866123,
    "fee": 344000,
    "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
    "recipient": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
    "signature": "30450221008adeff8eb2a780168704d9e210368d81edff79b81aa7b995e43486f3b1e0096502205caef345584319a6294b1f5283c0d17b478b8a9bcdc10570e5a58681b0eae332",
    "vendorField": "Yooooooloooooo",
    "confirmations": 0,
    "timestamp": {
      "epoch": 56388424,
      "unix": 1546489624,
      "human": "2019-01-03T04:27:04.000Z"
    }
  }
}
```

## Search for Transactions

For fine-grained searches, use the `search` endpoint. Note that unless you use specific body parameters, the response might contain a large number of transactions \(hundreds of thousands\). It is best to filter as many transactions node side, instead of dissecting the response client side.

### Endpoint

```text
POST /api/transactions/search
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| page | int | The number of the page that will be returned. | No |
| limit | int | The number of resources per page. | No |

### Body Parameters

| Name | Type | Description | Required |
| :--- | :---: | :--- | :---: |
| orderBy | string | ... | No |
| id | string | ... | No |
| blockId | string | ... | No |
| type | int | ... | No |
| version | int | ... | No |
| senderPublicKey | string | ... | No |
| senderId | string | ... | No |
| recipientId | string | ... | No |
| ownerId | string | ... | No |
| vendorFieldHex | string | ... | No |
| timestamp | object | ... | No |
| timestamp.from | int | ... | No |
| timestamp.to | int | ... | No |
| amount | object | ... | No |
| amount.from | int | ... | No |
| amount.to | int | ... | No |
| fee | object | ... | No |
| fee.from | int | ... | No |
| fee.to | int | ... | No |

### Response

```javascript
{
  "meta": {
    "Count": 1,
    "PageCount": 79382,
    "totalCount": 79382,
    "next": "/api/v2/transactions/search?limit=1&page=2",
    "previous": null,
    "self": "/api/v2/transactions/search?limit=1&page=1",
    "first": "/api/v2/transactions/search?limit=1&page=1",
    "last": "/api/v2/transactions/search?limit=1&page=79382"
  },
  "data": [
    {
      "id": "026fbc15cf630e8fc2a3e963d2c436c744d880611a468b34b85145e181b80dc0",
      "blockId": "14085724014999449555",
      "version": 1,
      "type": 0,
      "amount": 737042,
      "fee": 344000,
      "sender": "DMzBk3g7ThVQPYmpYDTHBHiqYuTtZ9WdM3",
      "recipient": "DN8nGwcNbE3YcnZYFp8uvvc9z4WWDbytWK",
      "signature": "3045022100cb2c2d9086188f4b09c97b99374da91579d15c99206bbb04512053922cb0209f022026a4676483d1162eaafd64d2acfa43413e02f587922cf55f3205bbf509bd118b",
      "vendorField": "Yooooooloooooo",
      "confirmations": 103,
      "timestamp": {
        "epoch": 56388434,
        "unix": 1546489634,
        "human": "2019-01-03T04:27:14.000Z"
      }
    }
  ]
}
```

## Get Transaction Types

The transaction types are network specific. ARK currently supports eight different types, but BridgeChains may define more or less if needed for their business purpose.

### Endpoint

```text
GET /api/transactions/types
```

### Response

```javascript
{
  "data": {
    "Transfer": 0,
    "SecondSignature": 1,
    "DelegateRegistration": 2,
    "Vote": 3,
    "MultiSignature": 4,
    "Ipfs": 5,
    "TimelockTransfer": 6,
    "MultiPayment": 7,
    "DelegateResignation": 8
  }
}
```

## Get Transaction Fees \(Non-Dynamic\)

The static transaction fees are significantly higher than the dynamic transaction fees. Use the [node resource](https://github.com/ArkEcosystem/gitbooks-api/tree/9815499ca52e615b8de858160da915cd960e6ea3/api/public/v2/node.html#retrieve-the-configuration) to find dynamic fees, and prefer using these.

### Endpoint

```text
GET /api/transactions/fees
```

### Response

```javascript
{
  "data": {
    "transfer": 10000000,
    "secondSignature": 500000000,
    "delegateRegistration": 2500000000,
    "vote": 100000000,
    "multiSignature": 500000000,
    "ipfs": 0,
    "timelockTransfer": 0,
    "multiPayment": 0,
    "delegateResignation": 0
  }
}
```

## Get transaction schemas

### Endpoint

```bash
/api/transactions/schemas
```

### Response

```bash
{
    "data": {
        "1": {
            "0": {
                "id": {
                    "anyOf": [
                        {
                            "$ref": "transactionId"
                        },
                        {
                            "type": "null"
                        }
                    ]
                },
                "version": {
                    "enum": [
                        1,
                        2
                    ]
                },
                "network": {
                    "$ref": "networkByte"
                },
                "timestamp": {
                    "type": "integer",
                    "minimum": 0
                },
                "nonce": {
                    "bignumber": {
                        "minimum": 0
                    }
                },
                "typeGroup": {
                    "type": "integer",
                    "minimum": 0
                },
                "amount": {
                    "bignumber": {
                        "minimum": 1,
                        "bypassGenesis": true
                    }
                },
                "fee": {
                    "bignumber": {
                        "minimum": 1,
                        "bypassGenesis": true
                    }
                },
                "senderPublicKey": {
                    "$ref": "publicKey"
                },
                "signature": {
                    "$ref": "alphanumeric"
                },
                "secondSignature": {
                    "$ref": "alphanumeric"
                },
                "signSignature": {
                    "$ref": "alphanumeric"
                },
                "signatures": {
                    "type": "array",
                    "minItems": 1,
                    "maxItems": 16,
                    "additionalItems": false,
                    "uniqueItems": true,
                    "items": {
                        "allOf": [
                            {
                                "minLength": 130,
                                "maxLength": 130
                            },
                            {
                                "$ref": "alphanumeric"
                            }
                        ]
                    }
                },
                "type": {
                    "transactionType": 0
                },
                "vendorField": {
                    "anyOf": [
                        {
                            "type": "null"
                        },
                        {
                            "type": "string",
                            "format": "vendorField"
                        }
                    ]
                },
                "recipientId": {
                    "$ref": "address"
                },
                "expiration": {
                    "type": "integer",
                    "minimum": 0
                }
            },
        ...
```

