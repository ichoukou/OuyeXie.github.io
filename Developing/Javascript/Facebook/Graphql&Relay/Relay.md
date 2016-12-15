 - https://facebook.github.io/relay/docs/tutorial.html#content
 - https://facebook.github.io/relay/docs/getting-started.html#content
 - [REQUIRED_CHILDREN](https://github.com/facebook/relay/issues/236)
 - [Could not find a type name for record](https://github.com/facebook/relay/issues/474)
 - [React can’t find the root component node - A lesson in server rendering](http://blog.j0.hn)
 
 <pre>
 React can’t find the root component node - A lesson in server rendering
 
 Warning: React can’t find the root component node for data-reactid value .261a1mvta80.0.0.0.0. If you’re seeing this message, it probably means that you’ve loaded two copies of React on the page. At this time, only a single copy of React can be loaded at a time.
 
 This warning and the subsequent exception:
 
 node_modules/react/lib/ReactMount.js:715
     firstChildren[0] = deepestAncestor.firstChild;
                                       ^
 
 TypeError: Cannot read property 'firstChild' of undefined
 Has plagued me many times on my current project.
 
 I’ve got a fancy isomorphic React+Flux environment that works beautifully when it works. Every now and then, I get stumped with the above warning and error when trying to render on the server.
 
 In fact, I do not have two copies of React on the page. Instead, this error occurs when I accidentally render my components multiple times on a single request.
 
 How does that even happen?
 
 The latest instance occurred when I visited /SomeProfile rather than /someprofile. This is because when we rendered the page, we did our initial Data Requirements fetch (which called to the api). Once the component was ready, React calls componentWillReceiveProps( props ). That lifecycle hook checks props.params.vendor_id vs this.state.vendor.username and noticed they were not equal. This caused another fetch call and another rendering for the same request.
 
 Conclusion
 
 If you’re seeing that warning + error on the server, find out if you’re rendering more than once per request. If so, it may be from your lifecycle methods.
 

 </pre>