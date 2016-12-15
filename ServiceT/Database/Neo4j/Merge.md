It is quite dangerous to trigger multiple merge at the same time, E.g. if you do not have a node in the database and trigger the following commands several times SIMULTANEOUSLY.

```
MERGE
 (a:Entity {code:'80000475'}) ON CREATE SET a.id='5Lit5bu65oqV5L+h5omY5pyJ6ZmQ6LSj5Lu75YWs5Y+4', a.name='中建投信托有限责任公
司', a.alias=['中建投信托有限责任公司'], a.createdat='2016-08-03 16:52:35.172', a.updatedat='2016-08-03 16:52:35.172', a:Manag
er ON MATCH SET a.alias=filter(x IN a.alias WHERE NOT x='中建投信托有限责任公司')+'中建投信托有限责任公司', a.updatedat='2016-
08-03 16:52:35.172', a:Manager
```
                