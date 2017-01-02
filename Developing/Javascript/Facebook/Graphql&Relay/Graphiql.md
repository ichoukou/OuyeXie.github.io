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

graphiql: process.env.NODE_ENV === 'development' || !!req.query.debug,
=>
http://shengupiao.com/graphql?debug=true

query {stock (symbol: "837602") {
  activities(first: 100) {
    edges {
      node {
        ... on PostActivity {
        post {
          sourceCreatedAt
          createdAt
          id
          title
        }
      }
    }
  }
}
}
}