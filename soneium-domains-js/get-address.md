# Get Address

Get an address record for a name and specified coin

### Example

```ts
import { createPublicClient, http } from 'viem'
import { soneiumMinato } from 'viem/chains'
import { addEnsContracts } from '@soneium-domains/js'
import { getAddressRecord } from '@soneium-domains/js/public'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getAddressRecord(client, { name: 'sns.son', coin: 'ETH' })
// { id: 60, name: 'ETH , value: '0x046fC1185e45224325f3191140fd236462574C07' }
```

### Parameters

<table><thead><tr><th width="287">Parameter</th><th width="179">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>client</code></td><td><code>ClientWithEns</code></td><td>ClientWithEns</td></tr><tr><td><code>parameters</code></td><td><code>object</code></td><td>GetAddressRecordParameters</td></tr><tr><td><code>parameters.bypassFormat</code>?</td><td><code>boolean</code></td><td>Optionally return raw bytes value of address record (default: false)</td></tr><tr><td><code>parameters.coin</code>?</td><td><code>string</code> | <code>number</code></td><td>Coin to get the address record for, can be either symbol (string) or coinId (number) (default: <code>60</code>)</td></tr><tr><td><code>parameters.name</code></td><td><code>string</code></td><td>Name to get the address record for</td></tr></tbody></table>

### Returns

`Promise`< `GetAddressRecordReturnType` >

Coin value object, or `null` if not found. GetAddressRecordReturnType

### Source

[src/functions/public/getAddressRecord.ts:61](https://github.com/soneium-domains/soneium-domains-js/tree/main/src/functions/public/getAddressRecord.ts#L61)
