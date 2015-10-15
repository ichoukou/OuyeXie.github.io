# How to use

## pooling

<pre>
<code>
const db = knex({
  client: 'mysql',
  connection: config.dbStock,
  pool: {
    min: 0,
    max: 1,
    acquireTimeout: 30 * 1000
  }
})
</code>
</pre>

# reference

 - http://knexjs.org/#Installation-pooling
 - https://github.com/myndzi/pool2