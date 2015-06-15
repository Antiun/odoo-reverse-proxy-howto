## Odoo behind Nginx

### HTTPS virtual host (3/3)

(...)

{% highlight Nginx linenos %}
    # Cache some static data in memory for 60mins.
    # under heavy load this should relieve stress on the Odoo web interface a bit.
    location ~* /[0-9a-zA-Z_]*/static/ {
        proxy_cache_valid       200 60m;
        proxy_buffering         on;
        expires                 864000;
        proxy_pass              http://odoo;
    }

    access_log /var/log/nginx/odoo-ssl.access.log;
    error_log  /var/log/nginx/odoo-ssl.error.log;
}
{% endhighlight %}

Download this file: [odoo-ssl](files/nginx/odoo-ssl)
