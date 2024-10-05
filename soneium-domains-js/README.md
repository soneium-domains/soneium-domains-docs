---
description: Soneium Domains javascript library, with viem under the hood.
---

# Soneium Domains JS

### Getting Started

The simplest way to get started with **Soneium Domains** is by creating a public ENS client. This client will allow you to interact with the ENS-compatible read functions and subgraph functionalities for the supported chain, currently **Soneium Minato**.

To begin, you’ll need to install the [`@soneium-domains/js`](https://github.com/soneium-domains/soneium-domains-js/) package, which provides utilities for interacting with the Soneium Blockchain, including ENS-like functions. You will also need to import transport and chain utilities from **viem**, a library that allows you to interact with the Ethereum JSON-RPC interface.&#x20;

### Installation

#### First, install the required packages [@soneium-domains/js](https://github.com/soneium-domains/soneium-domains-js/), alongside [viem](https://github.com/wagmi-dev/viem).

```
npm install @soneium-domains/js viem
```

or

```
yarn add @soneium-domains/js viem
```

### Example Usage

Once the packages are installed, you can set up a **public client** for the Soneium Minato chain. The public client allows you to perform various **read operations** (like resolving address records) by using available subgraph functions.

Here’s how to create a public client and fetch an address record for a specific domain:

```javascript
// Import viem transport, viem chain, and @soneium-domains/js utilities
import { createPublicClient, http } from 'viem';
import { addEnsContracts } from '@soneium-domains/js';
import { getAddressRecord } from '@soneium-domains/js/public';

// Create the public client for the Soneium Minato testnet
const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),  
  // Adds Soneium ENS contracts to the chain
  transport: http(),                      
  // Use the HTTP transport to communicate with the chain
});

// Fetch an address record for the given domain name (e.g., 'sns.son')
const result = await getAddressRecord(client, { name: 'sns.son', coin: 'ETH' });

// Example output:
// { id: 60, name: 'ETH', value: '0x046fC1185e45224325f3191140fd236462574C07' }
console.log(result);

```



### Functions

[get-name.md](get-name.md "mention") - Get the primary name for an address

[get-address.md](get-address.md "mention") - Get an address record for a name and specified coin

[get-records.md](get-records.md "mention") - Get arbitrary records for a name

[get-names-for-address.md](get-names-for-address.md "mention") - Gets the names for an address from the subgraph.

[get-subgraph-records.md](get-subgraph-records.md "mention") - Get the records for a name from the subgraph

[get-profile.md](get-profile.md "mention") - Get a profile, meaning all associated records for a soneium domain.
