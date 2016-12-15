# Explaination

 - The term query finds documents that contain the exact term specified in the inverted index
 - A family of match queries that accepts text/numerics/dates, analyzes them, and constructs a query
 
 The term query looks for the exact term in the field’s inverted index — it doesn’t know anything about the field’s analyzer. This makes it useful for looking up values in not_analyzed string fields, or in numeric or date fields. When querying full text fields, use the match query instead, which understands how the field has been analyzed.
 
# Reference

 - https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-term-query.html
 - https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html
 