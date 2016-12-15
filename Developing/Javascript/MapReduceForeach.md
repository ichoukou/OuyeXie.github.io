# Trick

<pre>
<code>
const users = await records.reduce(async (results, record) => {
    results = await results
    let user = await getUserById(record.user_id)
    results.push(user)
    return results
  }, []);
</code>
</pre>

# test try catch 

## code

<pre>
function testTry() {
  const data = [1, 2, 3, 4]
  let a = 0
  try {
    data.forEach((d) => {
      try {
        a = d
        console.log(d)
        a += 10
        throw new Error('hahaha: ' + d)
      } catch (err) {
        console.error('inner error', err)
        throw err // comment me out and see difference
      }
    })
    console.log(a)
    console.log('finished')
  } catch (err) {
    console.log(a)
    console.error('outer notification error', err)
  }
}

//testTry()

function sleep(timeout) {
  //debug('media')(`sleep ${timeout} ms!`)
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, timeout);
  });
}

async function testAsyncTryFor() {
  const data = [1, 2, 3, 4]
  try {
    for (let i = 0; i < data.length; i++) {
      const d = data[i]
      try {
        await sleep(1000)
        console.log(d)
        throw new Error('lalala: ' + d)
      } catch (err) {
        console.error('inner error', err)
//        break // uncomment me out and see difference
        throw err // comment me out and see difference
      }
    }
    console.log('finished')
  } catch (err) {
    console.error('outer notification error', err)
  }
}

//testAsyncTryFor()


async function testAsyncTryForIn() {
  const data = [1, 2, 3, 4]
  try {
    for (let d in data) {
      if (true) {
        try {
          await sleep(1000)
          console.log(d)
          throw new Error('lalala: ' + d)
        } catch (err) {
          console.error('inner error', err)
//        break // uncomment me out and see difference
          throw err // comment me out and see difference
        }
      }
    }
    console.log('finished')
  } catch (err) {
    console.error('outer notification error', err)
  }
}

//testAsyncTryForIn()

async function testAsyncTryForEach() {
  const data = [1, 2, 3, 4]
  let a = 0
  try {
    const r = await data.forEach(async (d) => {
      try {
        a = d
        await sleep(2000)
        console.log(d)
        a += 10
        throw new Error('lalala: ' + d)
      } catch (err) {
        console.error('inner error', err)
        throw err // comment me out and see difference
      }
    })
    console.log(r)
    console.log('finished: ' + a)
  } catch (err) {
    console.error('outer notification error', err)
  }
}

//testAsyncTryForEach()

async function testAsyncTryMap() {
  const data = [1, 2, 3, 4]
  try {
    await* data.map(async (d) => {
      try {
        await sleep(1000)
        console.log(d)
        throw new Error('lalala: ' + d)
      } catch (err) {
        console.error('inner error', err)
        throw err // comment me out and see difference
      }
    })
    console.log('finished')
  } catch (err) {
    console.error('outer notification error', err)
  }
}

//testAsyncTryMap()

async function testAsyncTryReduce() {
  const data = [1, 2, 3, 4]
  try {
    await data.reduce(async (r, d) => {
      r = await r
      console.log(r)
      try {
        await sleep(1000)
        console.log(d)
        throw new Error('lalala: ' + d)
      } catch (err) {
        console.error('inner error', err)
        throw err // comment me out and see difference
      }
      r.push(`result[${d}]`)
      return r
    }, [])
    console.log('finished')
  } catch (err) {
    console.error('outer notification error', err)
  }
}

//testAsyncTryReduce()
</pre>

## conclusion

 - sync
    - foreach: data is accessed at the same time (parallel), error can be thrown and caught from outside

 - async
    - for: data is accessed one by one (series), error can be thrown and caught from outside, break can work
    - forin: data is accessed one by one (series), error can be thrown and caught from outside, break can work
    - foreach: data is accessed at the same time (parallel), error cannot be thrown and caught from outside, forEach itself does not return anything (not even promise) so it cannot be decorated with await. We want to dig deeper here 
        - forEach() executes the provided callback once for each element present in the array in ascending order (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
    - map: data is accessed at the same time (parallel), error can be thrown and caught from outside
    - reduce: data is accessed one by one (series), error can be thrown and caught from outside

# Reference

 - [如何形象地解释 JavaScript 中 map、foreach、reduce 间的区别？](http://www.zhihu.com/question/24927450)
 - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach
 