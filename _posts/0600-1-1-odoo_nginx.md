---
label: odoo-nginx
---
## Odoo behind Nginx

### HTTP virtual host

{% highlight Bash %}
sudo nano /etc/nginx/sites-available/odoo
{% endhighlight %}

{% highlight Nginx linenos %}
server {
    listen 80;
    listen [::]:80 ipv6only=on;
    server_name odoo.example.com;

    # Strict Transport Security
    add_header Strict-Transport-Security max-age=2592000;

    # Redirect 301 to HTTPS
    return 301 https://$host$request_uri;

    access_log /var/log/nginx/default.access.log;
    error_log  /var/log/nginx/default.error.log;
}
{% endhighlight %}

Download this file: [odoo](files/nginx/odoo)
