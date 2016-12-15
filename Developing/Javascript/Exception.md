# forEach async try catch

<pre>
<code>
function sleep(timeout) {
  //debug('media')(`sleep ${timeout} ms!`)
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, timeout);
  });
}

async function testAsyncTry(){
  const data = [1, 2, 3, 4]
  try {
    await data.forEach(async (d) => {
      try {
        await sleep(1000)
        console.log(d)
        throw new Error('lalala')
      } catch (err) {
        console.error('inner error', err)
        throw err
      }
    })
  } catch (err) {
    console.error('outer notification error', err)
  }
}

testAsyncTry()
</code>
</pre>

can never work because forEach do not deal with exception as Promise.then.catch

use map (await *) instead