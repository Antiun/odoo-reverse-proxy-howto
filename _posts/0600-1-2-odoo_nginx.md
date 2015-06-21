## Odoo behind Nginx

### HTTPS virtual host (1/3)

{% highlight Bash %}
sudo nano /etc/nginx/sites-available/odoo-ssl
{% endhighlight %}

{% highlight Nginx linenos %}
upstream odoo {
    server localhost:8069 weight=1 fail_timeout=3000s;
}

server {
    listen 443;
    listen [::]:443 ipv6only=on;
    server_name odoo.example.com;

    ssl on;
    ssl_ciphers                 ALL:!ADH:!MD5:!EXPORT:!SSLv2:RC4+RSA:+HIGH:+MEDIUM;
    ssl_protocols               TLSv1 TLSv1.1 TLSv1.2;
    ssl_prefer_server_ciphers   on;
    ssl_certificate             /etc/ssl/wildcard.example.com/public.crt;
    ssl_certificate_key         /etc/ssl/wildcard.example.com/private.pem;

    # Specifies the maximum accepted body size of a client request,
    # as indicated by the request header Content-Length.
    client_max_body_size        200m;

    # add ssl specific settings
    keepalive_timeout           60;

    # increase proxy buffer to handle some OpenERP web requests
    proxy_buffers               16 64k;
    proxy_buffer_size           128k;
{% endhighlight %}

(...)

Download this file: [odoo-ssl](files/nginx/odoo-ssl)
