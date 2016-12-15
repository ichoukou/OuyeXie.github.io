 - [react的refs和event](https://segmentfault.com/q/1010000004993919/a-1020000005045455)
    - 不过 React 的 event 不是真正的 DOM event，它有一个特点即在下一个 event loop 里就会被释放掉，换句话说如果你有这样的处理方法：
      那么这里的 event.target 是获取不到的，同时 React 会提示你这个问题，解决的方法是持久化这个 event 对象，即先 event.persist()。这一点尤其要在对 event handler 进行二次包装时（比如 lodash.debounce 它）注意。