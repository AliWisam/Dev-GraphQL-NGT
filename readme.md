https://dev.to/dabit3/building-graphql-apis-on-ethereum-4poa

GraphQL: https://thegraph.com/legacy-explorer/subgraph/aliwisam/zoranftsubgraph

 ## Querying for data 
Run the following query to get a list of tokens and their metadata:

```{
  tokens {
    id
    tokenID
    contentURI
    metadataURI
  }
}

 We can also configure the order direction:

{
  tokens(
    orderBy:id,
    orderDirection: desc
  ) {
    id
    tokenID
    contentURI
    metadataURI
  }
}



 Or choose to skip forward a certain number of results to implement some basic pagination:
{
  tokens(
    skip: 100,
    orderBy:id,cd 
    orderDirection: desc
  ) {
    id
    tokenID
    contentURI
    metadataURI
  }
}

 Or query for users and their associated content:
{
  users {
    id
    tokens {
      id
      contentURI
    }
  }
}



Once the subgraph has been redeployed, we can now query by timestamp to view the most recently created NFTS:

{
  tokens(
    orderBy:createdAtTimestamp,
    orderDirection: desc
  ) {
    id
    tokenID
    contentURI
    metadataURI
  }
}