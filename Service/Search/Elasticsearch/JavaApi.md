# Alias

```
client.admin().indices().prepareAliases().addAlias("my_index", "my_alias").removeAlias("my_old_index", "my_alias").execute().actionGet();
```

```
get=getClient().admin().indices().prepareGetAliases(appid).execute().actionGet();
```

# References
 
 - https://www.elastic.co/guide/en/elasticsearch/client/java-api/index.html
 - http://elasticsearch-users.115913.n3.nabble.com/Working-with-aliases-using-Java-API-td3300648.html
 - http://www.programcreek.com/java-api-examples/index.php?api=org.elasticsearch.action.admin.indices.alias.get.GetAliasesResponse