---
id: access-node-nownodes
title: Access Node with NOWNodes
description: Make blockchain queries on Polygon without building a full node using the NOWNodes API
keywords:
  - docs
  - matic
  - polygon
  - node
  - nownodes
  - nownodes api
  - query 
  - full node
image: https://wiki.polygon.technology/img/polygon-wiki.png
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import useBaseUrl from '@docusaurus/useBaseUrl';

# Access a Full Node with NOWNodes

To speed up the working process it is highly suggested to use a node provider hosting for accessing the Polygon full node rather than managing your own node.

The majority of web 3 developers use a node provider, or a third-party external service that receives node requests and returns responses for you automatically. This is the fastest way to get developing on Polygon.

:::tip Recommended

New developers on the Polygon network can use the NOWNodes API key to access Polygon network for FREE. [Get FREE API key](https://account.nownodes.io/auth/signup).

:::

## Send Your First Blockchain Request

This guide assumes you already have an [NOWNodes account](https://account.nownodes.io/auth/signup) and access to the [NOWNodes Dashboard](https://account.nownodes.io/profile/dashboard).

**Step 1 &rarr;** Create an NOWNodes Key

First, you'll need an NOWNodes API key to authenticate your requests. You can [create API keys from the dashboard](https://account.nownodes.io/profile/dashboard). 
Navigate to the **ADD NEW KEY** button on the **DASHBOARD** page.

![img](https://files.readme.io/693457a-Getting_Started.png)

**Step 2 &rarr;** Make Your First CURL Request.

### Make Your First CURL Request

You can interact with NOWNodes's Polygon infrastructure provider using JSON-RPC and your [command line interface](https://www.computerhope.com/jargon/c/commandi.htm).

For manual requests, we recommend interacting with the `JSON-RPC` via `POST` requests. Simply pass in the `Content-Type: application/json` header and your query as the `POST` body with the following fields:

* `jsonrpc`: The JSON-RPC version—currently, only `2.0` is supported.
* `method`: The MATIC API method. 
* `params`: A list of parameters to pass to the method.
* `id`: The ID of your request. Will be returned by the response so you can keep track of which request a response belongs to.

Here is an example you can run from the Terminal/Windows/LINUX command line to retrieve the current gas price:

**Way 1 &rarr;**

```bash
curl https://matic.nownodes.io/ <your API key> \
-X POST \
-H "Content-Type: application/json" \
-d '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":73}'
```

**Way 2 &rarr;**

```bash
curl  https://matic.nownodes.io/ \
-X POST \
-H "Content-Type: application/json" \
-H "api-key: <your API key>"
-d '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":73}'
```

Check out [this article](https://nownodes.io/blog/polygon-how-to-build-a-dapp-on-polygon/) on how to build a dApp on Polygon.```
