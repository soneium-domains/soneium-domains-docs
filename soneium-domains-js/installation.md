---
description: >-
  This guide assumes you have a basic understanding of react or node.js, viem
  and web3.
---

# Installation

### Installation

Install [@soneium-domains/js](https://github.com/soneium-domains/soneium-domains-js/), alongside [viem](https://github.com/wagmi-dev/viem).

```
npm install @soneium-domains/js viem
```

or

```
yarn add @soneium-domains/js viem
```

### Getting Started

The most simple way to get started is to create a public ENS client, with a supported chain (currently **soneiumMinato**) and transport imported from viem.&#x20;

The public client has all the read functions available on it, as well as all subgraph functions.

```javascript
// Import viem transport, viem chain, and @soneium-domains/js
import { createPublicClient, http } from 'viem'
import { addEnsContracts } from '@soneium-domains/js'
import { getAddressRecord } from '@soneium-domains/js/public'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getAddressRecord(client, { name: 'sns.son', coin: 'ETH' })
// { id: 60, name: 'ETH , value: '0x046fC1185e45224325f3191140fd236462574C07' }
```
