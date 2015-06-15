## Odoo configuration

### Example Apache2

{% highlight Ini %}
[options]
admin_passwd = admin

# Database configuration
db_host = localhost
db_port = False
db_user = odoo
db_password = odoo

# Ports to use
xmlrpc_port = 8069
longpolling_port = 8072

# Workers and timeouts
workers = 4
limit_time_real = 3600
limit_time_cpu = 3600

# Is it behind a HTTP reverse proxy?
proxy_mode = 1

# DB filtering for multi-site instances
dbfilter=^%h$

{% endhighlight %}
