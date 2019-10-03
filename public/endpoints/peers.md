---
title: "Peers"
---

The `peers` resource is much like the [node](/public/endpoints/node) resource, but only exposes the IPs and ports of connected peers. Recursively traversing this API and its responses allow you to inspect the entire network.

## List All Peers

Returns all peers known by the Node. These are not necessarily all peers; only public Nodes appear here.

### Endpoint

```
GET /api/peers
```

### Query Parameters

| Name    |  Type  | Description                                                   | Required |
| :------ | :----: | :------------------------------------------------------------ | :------: |
| page    |  int   | The number of the page that will be returned.                 |    No    |
| limit   |  int   | The number of resources per page.                             |    No    |
| port    |  int   | The port by which the resources will be filtered.             |    No    |
| status  | string | The status by which the resources will be filtered.           |    No    |
| os      | string | The operating system by which the resources will be filtered. |    No    |
| version | string | The node version by which the resources will be filtered.     |    No    |
| orderBy | string | The column by which the resources will be sorted.             |    No    |

### Response

```json
{
  "meta": {
    "count": 2,
    "pageCount": 1,
    "totalCount": 2,
    "next": null,
    "previous": null,
    "self": "/v2/peers?page=1",
    "first": "/v2/peers?page=1",
    "last": "/v2/peers?page=1"
  },
  "data": [
    {
      "ip": "167.114.29.53",
      "port": 4001,
      "version": "2.0.16",
      "height": 6881793,
      "status": 200,
      "os": "linux",
      "latency": 1390
    }
  ]
}
```

## Retrieve a Peer

Specific peers can be found by IP address. Note that a peer may have their Public API disabled, and thus they are only reachable by the internal `p2p` API.

### Endpoint

```
GET /api/peers/{ip}
```

### Query Parameters

| Name |  Type  | Description                                 | Required |
| :--- | :----: | :------------------------------------------ | :------: |
| ip   | string | The IP address of the peer to be retrieved. |   Yes    |

### Response

```json
{
  "data": {
    "ip": "167.114.29.55",
    "port": 4001,
    "version": "2.0.16",
    "height": 6881793,
    "status": 200,
    "os": "linux",
    "latency": 355
  }
}
```
