# Businesses

## List all businesses

```text
GET api/businesses
```

### Example

```text
curl http://dexplorer.ark.io/api/businesses
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| page | int | The number of the page that will be returned. | false |
| limit | int | The number of resources per page. | false |
| orderBy | string | Type by which it orders businesses. | false |
| publicKey | string | The publicKey of a transaction which submitted the business. | false |
| isResigned | boolean | If business is resigned or not. | false |

### Response

```javascript
{
    "meta": {
        "count": 54,
        "pageCount": 1,
        "totalCount": 54,
        "next": null,
        "previous": null,
        "self": "/businesses?transform=true&page=1&limit=100",
        "first": "/businesses?transform=true&page=1&limit=100",
        "last": "/businesses?transform=true&page=1&limit=100"
    },
    "data": [
        {
            "address": "D991ZqskaGWMDu9kpfpJr5LRssV7ek981k",
            "publicKey": "02fbae320be2813c13406cea3b7680971c5d7fc3113b79b6d7547d98dde980fefc",
            "name": "Google2",
            "website": "http://www.google.com",
            "vat": "GB12345678",
            "repository": "https://github.com/arkecosystem/desktop-wallet.git",
            "isResigned": true
        },
        {
            "address": "D5taz6B4xDk1LD3jV4fYrUhaKC8DnTtziW",
            "publicKey": "0352ff2cbd609fdcfc032c18c6a667009044fdb3ed279ceca2092638ac8bd6d06c",
            "name": "business-29838468124",
            "website": "http://dexplorer.ark.io",
            "isResigned": false
        },
        {
            "address": "DMnY8QWLAmsb4wNEjRVvtQsNWF4SbXntxM",
            "publicKey": "03b88068bce125a3cbe86607d64c138c3c3ef79bf4c1589e7604a3a9bf6f3d5370",
            "name": "business-29838468124",
            "website": "http://dexplorer.ark.io",
            "isResigned": false
        },
        ...
    ]
}
```

## Return business by wallet address

```bash
GET /api/business/{walletAddress}
```

### Example

```bash
curl http://dexplorer.ark.io/api/businesses/D991ZqskaGWMDu9kpfpJr5LRssV7ek981k
```

### Response

```javascript
{
    "data": {
        "address": "D991ZqskaGWMDu9kpfpJr5LRssV7ek981k",
        "publicKey": "02fbae320be2813c13406cea3b7680971c5d7fc3113b79b6d7547d98dde980fefc",
        "name": "Google2",
        "website": "http://www.google.com",
        "vat": "GB12345678",
        "repository": "https://github.com/arkecosystem/desktop-wallet.git",
        "isResigned": true
    }
}
```

## Return bridgechains of a business

```bash
GET /businesses/{walletAddress}/bridgechains
```

### Example

```bash
curl http://dexplorer.ark.io/api/businesses/DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE/bridgechains
```

### Query Parameters <a id="query-parameters"></a>

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| page | int | The number of the page that will be returned. | false |
| limit | int | The number of resources per page. | false |
| orderBy | string | Type by which it orders business. | false |
| isResigned | boolean | If business is resigned or not. | false |

### Response

```javascript
{
    "meta": {
        "count": 8,
        "pageCount": 1,
        "totalCount": 8,
        "next": null,
        "previous": null,
        "self": "/businesses/DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE/bridgechains?page=1&limit=100",
        "first": "/businesses/DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE/bridgechains?page=1&limit=100",
        "last": "/businesses/DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE/bridgechains?page=1&limit=100"
    },
    "data": [
        {
            "publicKey": "02e7e9b33d19e5aa7ad092e8cdb5c973b44e2c761840c64a1abbe5571bb317d464",
            "address": "DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE",
            "name": "bchain-0.04206259029720094",
            "seedNodes": [
                "1.1.1.1",
                "1.2.3.4"
            ],
            "genesisHash": "a6f4b8ceb2299efba73f732dca52d871ce42c31af22eca1e7f8f16083daac6f6",
            "bridgechainRepository": "https://github.com/ArkEcosystem/core",
            "ports": {
                "@arkecosystem/core-api": 4003
            },
            "isResigned": false
        },
        {
            "publicKey": "02e7e9b33d19e5aa7ad092e8cdb5c973b44e2c761840c64a1abbe5571bb317d464",
            "address": "DEHyKHdtzHqTghfpwaBcvTzLpgPP5AAUgE",
            "name": "bchain-0.131270425116921",
            "seedNodes": [
                "1.1.1.1",
                "1.2.3.4"
            ],
            "genesisHash": "d910eb181ea3eb304e339e9632e14826ec6c9c074bbe01fb0743a32b471982d1",
            "bridgechainRepository": "https://github.com/ArkEcosystem/core",
            "ports": {
                "@arkecosystem/core-api": 4003
            },
            "isResigned": false
        },
        ...
    ]
}
```

## Search business

```bash
POST /api/businesses/search
```

### Query Parameters

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| page | int | The number of the page that will be returned. | false |
| limit | int | The number of resources per page. | false |
| orderBy | string | Type by which it orders business. | false |

### Body parameters

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| address | string | ... | false |
| publicKey | string | ... | false |
| name | string | ... | false |
| website | string | ... | false |
| vat | string | ... | false |
| repository | string | ... | false |
| isResigned | boolean | ... | false |

### Response

```javascript
{
    "meta": {
        "count": 1,
        "pageCount": 1,
        "totalCount": 1,
        "next": null,
        "previous": null,
        "self": "/businesses/search?page=1&limit=100",
        "first": "/businesses/search?page=1&limit=100",
        "last": "/businesses/search?page=1&limit=100"
    },
    "data": [
        {
            "address": "D991ZqskaGWMDu9kpfpJr5LRssV7ek981k",
            "publicKey": "02fbae320be2813c13406cea3b7680971c5d7fc3113b79b6d7547d98dde980fefc",
            "name": "Google2",
            "website": "http://www.google.com",
            "vat": "GB12345678",
            "repository": "https://github.com/arkecosystem/desktop-wallet.git",
            "isResigned": true
        }
    ]
}
```

