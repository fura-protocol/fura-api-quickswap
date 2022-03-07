# Quickswap History

Check it out live: [https://staging.fura.org/quickswap](https://staging.fura.org/quickswap)


### Fura - Quickswap GraphQL Endpoint
https://api.fura.org/subgraphs/name/quickswap  

Furadao endpoint will be offline by 31 March, 2022:
~~https://polygon.furadao.org/subgraphs/name/quickswap~~

### Code Configuration
change [src/apollo/client.js](https://github.com/Uniswap/uniswap-info/blob/v2/src/apollo/client.js) as follows:

```
export const client = new ApolloClient({
  link: new HttpLink({
    uri: 'https://api.fura.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})

export const healthClient = new ApolloClient({
  link: new HttpLink({
    uri: 'https://api.fura.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})

export const blockClient = new ApolloClient({
  link: new HttpLink({
    uri: 'https://api.fura.org/subgraphs/name/quickswap',
  }),
  cache: new InMemoryCache(),
})
```

### CORS Settings
https://api.fura.org/subgraphs/name/quickswap 

now supports:
```
localhost:3000
localhost:9528
127.0.0.1:3000
127.0.0.1:9528

info.quickswap.exchange
alpha.quickswap.exchange
beta.quickswap.exchange
dev.quickswap.exchange

paraswap.io
staging.paraswap.io

onx.finance
app.onx.finance
testnet.onx.finance

app.mai.finance
app.orion.money

telx.network
www.telx.network
```

### Full Schema
check [schema.graphql](https://github.com/fura-protocol/fura-api-quickswap/blob/main/schema.graphql)

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

https://github.com/graphql/graphiql 
