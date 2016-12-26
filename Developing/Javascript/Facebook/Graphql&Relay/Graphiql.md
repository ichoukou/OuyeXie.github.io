query{
  viewer {
    searchManagerResults(q:"吴非"){
      id,
      cname,
      age,
      actdutyname,
      dutylength,
      stock{
        symbol,
        name
      }
    }
  }
}


query{
  node(id:"UG9zdDoxNjAy"){
    ... on Post {
      id,
			title
    }
  }
}

mutation UpdateContributorUsername {
  subscribeStockMutation(input: {clientMutationId:"a", stockId: "U3RvY2s6NDMwNDg4", subscribed: false}) {
    stock {
      id
      viewerDoesSubscribe
    }
  }
}