# Alias

```
client.admin().indices().prepareAliases().addAlias("my_index", "my_alias").removeAlias("my_old_index", "my_alias").execute().actionGet();
```

# References

 - http://elasticsearch-users.115913.n3.nabble.com/Working-with-aliases-using-Java-API-td3300648.html