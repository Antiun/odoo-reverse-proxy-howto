---
label: install-nginx-default-virtual-hosts
---
## Install Nginx 1.4 in Ubuntu 14.04

### Default HTTP virtual host

{% highlight Bash %}
sudo nano /etc/nginx/sites-available/default
{% endhighlight %}

{% highlight Nginx linenos %}
server {
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;
    server_name default.example.com;

    root /var/www/html;
    index index.html index.htm;

    # Redirect 301 to HTTPS
    # return 301 https://$host$request_uri;

    location / {
        try_files $uri $uri/ =404;
    }

    access_log /var/log/nginx/default.access.log;
    error_log  /var/log/nginx/default.error.log;
}
{% endhighlight %}

Download this file: [default](files/nginx/default)
