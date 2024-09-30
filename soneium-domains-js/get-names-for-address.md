# Get Names For Address

Gets the names for an address from the subgraph.

### Example

```ts
import { createPublicClient, http } from 'viem'
import { soneiumMinato } from 'viem/chains'
import { addEnsContracts } from '@soneium-domains/js'
import { getNamesForAddress } from '@soneium-domains/js/subgraph'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getNamesForAddress(client, {
  address: '0xFe89cc7aBB2C4183683ab71653C4cdc9B02D44b7',
})
```

### Parameters

| Parameter    | Type                           | Description                  |
| ------------ | ------------------------------ | ---------------------------- |
| `client`     | `ClientWithEns`                | ClientWithEns                |
| `parameters` | `GetNamesForAddressParameters` | GetNamesForAddressParameters |

### Returns

`Promise`< `GetNamesForAddressReturnType` >

Name array. GetNamesForAddressReturnType

### Source

[src/functions/subgraph/getNamesForAddress.ts:161](https://github.com/soneium-domains/soneium-domains-js/tree/main/src/functions/subgraph/getNamesForAddress.ts#L161)
