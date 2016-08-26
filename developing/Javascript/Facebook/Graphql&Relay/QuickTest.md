test.js

<pre>
import fetch from 'node-fetch'

async function main() {
  const query = `
    {
      entity(id: "ODA1MDEzMTY=") {
        adjustments(first: 1) {
          edges {
            node {
              __typename
            }
          }
        }
      }
    }
  `
  const nQuotes = await fetch('http://localhost:3012/graphql', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/graphql'
    },
    body: query
  })
  let j = await nQuotes.json()
  console.log(j)
}

main().catch(err => console.log(err))
</pre>

index.js

<pre>
require('babel-register')
require('babel-polyfill')
require('./test')
</pre>