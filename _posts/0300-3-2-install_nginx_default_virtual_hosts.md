## Install Nginx 1.4 in Ubuntu 14.04

### Default HTTPS virtual host

{% highlight Bash %}
sudo nano /etc/nginx/sites-available/default-ssl
{% endhighlight %}

{% highlight Nginx linenos %}
server {
    listen 443 default_server;
    listen [::]:443 default_server ipv6only=on;
    server_name default.example.com;

    root /var/www/html;
    index index.html index.htm;

    ssl on;
    ssl_ciphers                 ALL:!ADH:!MD5:!EXPORT:!SSLv2:RC4+RSA:+HIGH:+MEDIUM;
    ssl_protocols               TLSv1 TLSv1.1 TLSv1.2;
    ssl_prefer_server_ciphers   on;
    ssl_certificate             /etc/ssl/wildcard.example.com/public.crt;
    ssl_certificate_key         /etc/ssl/wildcard.example.com/private.pem;

    location / {
        try_files $uri $uri/ =404;
    }

    access_log /var/log/nginx/default-ssl.access.log;
    error_log  /var/log/nginx/default-ssl.error.log;
}
{% endhighlight %}

Download this file: [default-ssl](files/nginx/default-ssl)
