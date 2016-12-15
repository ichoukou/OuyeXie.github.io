 - [Json and String](http:blog.csdn.net/starrexstar/article/details/8083259)
 - [Validation](http:stackoverflow.com/questions/3710204/how-to-check-if-a-string-is-a-valid-json-string-in-javascript-without-using-try)
 
# Brace

<pre>
<code>
let obj = {a: 1234, b: 5678}

let {a, b: z} = obj

console.log(a)
console.log(z)

function test({a, b: z}) {
  console.log(a)
  console.log(z)

  a = 4321
  z = 8765

  console.log(a)
  console.log(z)
}

test(obj)

console.log(obj)
</code>
</pre>