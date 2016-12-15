# Proxy example

<pre>
server {
    listen     9288;
    server_name  0.0.0.0;

    charset utf-8;

    access_log /var/log/nginx/search.access.log;
    error_log /var/log/nginx/search.error.log;

    location / {
        proxy_pass_header Server;
        proxy_set_header Host $http_host;
        proxy_redirect off;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Scheme $scheme;
        proxy_pass http://182.92.242.58:9288;
    }
}
</pre>