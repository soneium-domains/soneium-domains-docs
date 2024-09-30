# Get Subgraph Records

Get the records for a name from the subgraph

### Example

```ts
import { createPublicClient, http } from 'viem'
import { soneiumMinato } from 'viem/chains'
import { addEnsContracts } from '@soneium-domains/js'
import { getSubgraphRecords } from '@soneium-domains/js/subgraph'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getSubgraphRecords(client, { name: 'sns.son' })

// {
//   isMigrated: true,
//   createdAt: { date: 2019-08-26T05:09:01.000Z, value: 1566796141000 },
//   texts: [ 'snapshot', 'url', 'avatar', 'com.twitter', 'com.github' ],
//   coins: [ '60' ]
// }
```

### Parameters

| Parameter    | Type                           | Description                  |
| ------------ | ------------------------------ | ---------------------------- |
| `client`     | `ClientWithEns`                | ClientWithEns                |
| `parameters` | `GetSubgraphRecordsParameters` | GetSubgraphRecordsParameters |

### Returns

`Promise`< `GetSubgraphRecordsReturnType` >

Record object, or null if name was not found. GetSubgraphRecordsReturnType

### Source

[src/functions/subgraph/getSubgraphRecords.ts:154](https://github.com/soneium-domains/soneium-domains-js/tree/main/src/functions/subgraph/getSubgraphRecords.ts#L154)
