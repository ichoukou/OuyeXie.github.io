# Options.proxy

In my understanding, proxy only works when there is nothing we can find out from dev-server's resources.

This is why I think so:

In lib/server.js

<pre>
<code>
if (options.proxy) {
		if (!Array.isArray(options.proxy)) {
			options.proxy = Object.keys(options.proxy).map(function (path) {
				var proxyOptions;
				if (typeof options.proxy[path] === 'string') {
					proxyOptions = {path: path, target: options.proxy[path]};
				} else {
					proxyOptions = options.proxy[path];
					proxyOptions.path = path;
				}
				return proxyOptions;
			});
		}
		options.proxy.forEach(function (proxyOptions) {
			proxyOptions.ws = proxyOptions.hasOwnProperty('ws') ? proxyOptions.ws : true;
			<b>app.all(proxyOptions.path, function (req, res) {</b>
				if(typeof proxyOptions.rewrite === 'function') proxyOptions.rewrite(req, proxyOptions);
				if (proxyOptions.host) {
					req.headers.host = proxyOptions.host;
				}
				proxy.web(req, res, proxyOptions, function(err){
					var msg = "cannot proxy to " + proxyOptions.target + " (" + err.message + ")";
					this.io.sockets.emit("proxy-error", [msg]);
					res.statusCode = 502;
					res.end();
				}.bind(this));
				if (proxyOptions.configure) {
					proxyOptions.configure(proxy);
				}
			}.bind(this));
		}.bind(this));
	}
</code>
</pre>

and before this, we have:

<pre>
<code>
	// serve webpack bundle
	app.use(this.middleware = webpackDevMiddleware(compiler, options));

	app.get("/__webpack_dev_server__/live.bundle.js", function(req, res) {
		res.setHeader("Content-Type", "application/javascript");
		liveJs.pipe(res);
	});

	app.get("/webpack-dev-server.js", function(req, res) {
		res.setHeader("Content-Type", "application/javascript");
		inlinedJs.pipe(res);
	});

	app.get("/webpack-dev-server/*", function(req, res) {
		res.setHeader("Content-Type", "text/html");
		this.livePage.pipe(res);
	}.bind(this));

	app.get("/webpack-dev-server", function(req, res) {
</code>
</pre>

Notice the sequence:)