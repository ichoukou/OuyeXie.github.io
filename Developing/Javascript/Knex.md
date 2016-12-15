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

# Issues

Knex:Error Pool2 - Error: Handshake inactivity timeout

## track this

 - https://github.com/tgriesser/knex/issues/970

# reference

 - http://knexjs.org/#Installation-pooling
 - https://github.com/myndzi/pool2