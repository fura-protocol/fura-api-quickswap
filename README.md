# Quickswap History

Check it out live: [https://demo.furadao.org/subgraph/polygon/quickswap](https://demo.furadao.org/subgraph/polygon/quickswap)


### Fura - Quickswap GraphQL Endpoint
https://polygon.furadao.org/subgraphs/name/quickswap

### Code Configuration
change [src/apollo/client.js](https://github.com/Uniswap/uniswap-info/blob/v2/src/apollo/client.js) as follows:

```
export const client = new ApolloClient({
  link: new HttpLink({
    uri: 'https://polygon.furadao.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})

export const healthClient = new ApolloClient({
  link: new HttpLink({
    uri: 'https://polygon.furadao.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})

export const blockClient = new ApolloClient({
  link: new HttpLink({
    uri: 'https://polygon.furadao.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
})
```

### CORS Settings
https://polygon.furadao.org/subgraphs/name/quickswap 

now supports:
```
localhost:3000
localhost:9528
127.0.0.1:3000
127.0.0.1:9528
info.quickswap.exchange
```

### Full Schema
check [schema.graphql](https://github.com/furaprotocol/quickswap-info/blob/main/schema.graphql)

```
It is the same as
https://github.com/QuickSwap/QuickSwap-subgraph/blob/master/schema.graphql

with the query which combines all sameepsi's subgraphs:

http://thegraph.com/legacy-explorer/subgraph/sameepsi/maticblocks
http://thegraph.com/legacy-explorer/subgraph/sameepsi/quickswap03
http://thegraph.com/legacy-explorer/subgraph/sameepsi/quickswap06
```

### Use Playground
https://github.com/graphql/graphql-playground

