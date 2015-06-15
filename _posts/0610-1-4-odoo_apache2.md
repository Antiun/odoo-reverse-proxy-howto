## Odoo behind Apache2

### HTTPS virtual host (3/3)

(...)

{% highlight ApacheConf linenos %}

   # Comment to disable proxy
   ProxyRequests Off
   ProxyPreserveHost On
   ProxyPass /longpolling/        http://localhost:8072/longpolling/ retry=0
   ProxyPassReverse /longpolling/ http://localhost:8072/longpolling/ retry=0
   ProxyPass /                    http://localhost:8069/ retry=0
   ProxyPassReverse /             http://localhost:8069/ retry=0

   ErrorLog /var/log/apache2/odoo.example.com-ssl.error.log
   LogLevel warn
   CustomLog /var/log/apache2/odoo.example.com-ssl.access.log combined

</VirtualHost>
</IfModule>
{% endhighlight %}

Download this file: [odoo-ssl.conf](files/apache2/odoo-ssl.conf)
