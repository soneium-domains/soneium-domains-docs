# Get Name

Get the primary name for an address

### Example

```ts
import { createPublicClient, http } from 'viem'
import { soneiumMinato } from 'viem/chains'
import { addEnsContracts } from '@soneium-domains/js'
import { getName } from '@soneium-domains/js/public'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getName(client, {
  address: '0x046fC1185e45224325f3191140fd236462574C07',
})
// { name: 'sns.son', match: true, reverseResolverAddress: '0xa2c122be93b0074270ebee7f6b7292c7deb45047', resolverAddress: '0x4976fb03c32e5b8cfe2b6ccb31c09ba78ebaba41' }
```

### Parameters

| Parameter    | Type                | Description       |
| ------------ | ------------------- | ----------------- |
| `client`     | `ClientWithEns`     | ClientWithEns     |
| `parameters` | `GetNameParameters` | GetNameParameters |

### Returns

`Promise`< `GetNameReturnType` >

Name data object, or `null` if no primary name is set. GetNameReturnType

### Source

[src/functions/public/getName.ts:123](https://github.com/soneium-domains/soneium-domains-js/tree/main/src/functions/public/getName.ts#L123)
