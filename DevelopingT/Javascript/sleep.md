<pre>
<code>
function sleep(timeout) {
  debug('media')(`sleep ${timeout} ms!`)
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, timeout);
  });
}
</code>
</pre>