# Command

<pre>
use admin
db.createUser(
   {
     user: "root",
     pwd: "root",
     roles: ["root"]
   }
)

mongo admin -u root -p root1234

db.createUser( { "user" : "shengupiao",
                 "pwd": "####",
                 "customData" : { "privilege": "readWrite" },
                 "roles" : [ "readWrite" ] },
               { w: "majority" , wtimeout: 5000 } )
               
mongo infinity -u shengupiao -p ####
</pre>

# Reference

 - [built-in roles](https://docs.mongodb.org/manual/reference/built-in-roles/#built-in-roles)
 - [create](https://docs.mongodb.org/manual/reference/method/db.createUser/#db.createUser)
 - [roles](http://www.jb51.net/article/53830.htm)
 - [js module](http://cnodejs.org/topic/53ad10aca087f45620c4cf5d)