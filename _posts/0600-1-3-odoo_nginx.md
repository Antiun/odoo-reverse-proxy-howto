## Odoo behind Nginx

### HTTPS virtual host (2/2)

(...)

{% highlight Nginx linenos %}
    location / {
        proxy_pass              http://odoo;

        # Force timeouts if the backend dies
        proxy_next_upstream error timeout invalid_header http_500 http_502 http_503;

        # Set headers
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forward-For $proxy_add_x_forwarded_for;
        # Let the Odoo web service know that we're using HTTPS, otherwise
        # it will generate URL using http:// and not https://
        proxy_set_header X-Forwarded-Proto https;

        # Set timeouts
        proxy_connect_timeout   3600;
        proxy_send_timeout      3600;
        proxy_read_timeout      3600;
        send_timeout            3600;

        # By default, do not forward anything
        proxy_redirect          off;
    }

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
