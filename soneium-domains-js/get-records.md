# Get Records

Get arbitrary records for a name

### Example

```ts
import { createPublicClient, http } from 'viem'
import { soneiumMinato } from 'viem/chains'
import { addEnsContracts } from '@soneium-domains/js'
import { getRecords } from '@soneium-domains/js/public'

const client = createPublicClient({
  chain: addEnsContracts(soneiumMinato),
  transport: http(),
})
const result = await getRecords(client, {
  name: 'sns.son',
  records: {
    texts: ['com.twitter', 'com.github'],
    coins: ['ETH'],
    contentHash: true,
  },
})
// { texts: [{ key: 'com.twitter', value: 'ensdomains' }, { key: 'com.github', value: 'ensdomains' }], coins: [{ id: 60, name: 'ETH', value: '0xFe89cc7aBB2C4183683ab71653C4cdc9B02D44b7' }], contentHash: { protocolType: 'ipns', decoded: 'k51qzi5uqu5djdczd6zw0grmo23j2vkj9uzvujencg15s5rlkq0ss4ivll8wqw' } }
```

### Type parameters

| Parameter                                  |
| ------------------------------------------ |
| `TParams` _extends_ `GetRecordsParameters` |

### Parameters

| Parameter    | Type            | Description          |
| ------------ | --------------- | -------------------- |
| `client`     | `ClientWithEns` | ClientWithEns        |
| `parameters` | `TParams`       | GetRecordsParameters |

### Returns

`Promise`< `GetRecordsReturnType`< `TParams` > >

Records data object. GetRecordsReturnType

### Source

[src/functions/public/getRecords.ts:376](https://github.com/soneium-domains/soneium-domains-js/tree/main/src/functions/public/getRecords.ts#L376)
