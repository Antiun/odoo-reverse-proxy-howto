## Odoo behind Apache2

### HTTPS virtual host (2/3)

(...)

{% highlight ApacheConf linenos %}
   <Location "/" >
      Order deny,allow
      Deny from all
      Allow from all
   </Location>

   <Location "/web/database/manager" >
      Order deny,allow
      Deny from all
      Allow from 192.168.122.0/24 127.0.0.0/255.0.0.0 ::1/128
   </Location>

   <Location "/website/info" >
      Order deny,allow
      Deny from all
      Allow from 192.168.122.0/24 127.0.0.0/255.0.0.0 ::1/128
   </Location>
{% endhighlight %}

(...)

Download this file: [odoo-ssl.conf](files/apache2/odoo-ssl.conf)
