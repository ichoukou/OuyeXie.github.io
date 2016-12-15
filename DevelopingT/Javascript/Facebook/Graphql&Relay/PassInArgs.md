# Code

<pre>
<code>
 viewer: (Component, {color}) => Relay.QL`
      query {
        viewer {
          ${Component.getFragment('viewer', {color})}
        }
      }
    `
</code>
</pre>

<pre>
<code>
     path="widgets" component={WidgetList}
     queries={ViewerQueries}
     queryParams={['color', 'size']} stateParams={['limit']}
     prepareParams={prepareWidgetListParams}
     defaultLimit={10}
</code>
</pre>

<pre>
<code>
     stockComment (id: ${id})
</code>
</pre>
passing in `substituteVariables: true` as the second argument to `getBabelRelayPlugin()`

# Reference
 
 - https://github.com/facebook/relay/issues/99
 - https://github.com/relay-tools/react-router-relay
 - https://github.com/facebook/relay/commit/a57a7c86839f1d35f74e4329320ccf98ef49cf1c