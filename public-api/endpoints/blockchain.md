---
title: Blockchain
---

# Blockchain

Used to get the latest block and supply of the blockchain.

## Endpoint

```text
GET /api/blockchain
```

## Examples

```bash
curl https://api.ark.io/api/blockchain
```

```javascript
{
  "data": {
    "block": {
      "height": 8051250,
      "id": "16024042256653583473"
    },
    "supply": 14095130200000004
  }
}
```

