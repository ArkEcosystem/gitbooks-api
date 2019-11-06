---
id: getting-started
title: Getting Started
description: Exchange JSON-RPC Getting Started Guide
---

# Getting Started

**THIS RPC IS BUILD SPECIFICALLY FOR THE NEEDS OF AN** [**EXCHANGE**](https://exchange.ark.dev)**.** The JSON-RPC was created to aid organizations with the integration of ARK in their existing RPC based infrastructure. If you do not have any restrictions in your IT architecture, we recommend using the [Public API](https://github.com/ArkEcosystem/gitbooks-api/tree/9815499ca52e615b8de858160da915cd960e6ea3/public/getting-started/README.md) over the JSON-RPC. All operations provided by the JSON-RPC can be performed using the public API.

{% hint style="danger" %}
All HTTP requests have to be sent with the `Content-Type: application/json` header. If the header is not present, it will result in malformed responses or request rejections.
{% endhint %}

