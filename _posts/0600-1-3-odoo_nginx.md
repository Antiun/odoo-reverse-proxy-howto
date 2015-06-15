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
}
{% endhighlight %}

(...)

Download this file: [odoo-ssl](files/nginx/odoo-ssl)
