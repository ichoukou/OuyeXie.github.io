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