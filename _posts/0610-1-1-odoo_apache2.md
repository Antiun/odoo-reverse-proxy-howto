---
label: odoo-apache2
---
## Odoo behind Apache2

### HTTP virtual host

{% highlight Bash %}
sudo nano /etc/apache2/sites-available/odoo.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<VirtualHost *:80>
   ServerAdmin webmaster@example.com
   ServerName odoo.example.com

   <IfModule mod_rewrite.c>
      RewriteEngine On

      # Permanent redirect (301 HTTP) if no canonical domain name
      RewriteCond %{HTTP_HOST} !^odoo.example.com
      RewriteRule ^/(.*)$ http://odoo.example.com/$1 [R=301,NE,L]

      # Redirect 301 to HTTPS
      RewriteCond %{HTTPS} !=on
      RewriteRule ^/?(.*) https://%{SERVER_NAME}/$1 [R=301,NE,L]
   </IfModule>

   <Location "/" >
      Order deny,allow
      Deny from all
      Allow from all
   </Location>

   ErrorLog /var/log/apache2/odoo.example.com.error.log
   LogLevel warn
   CustomLog /var/log/apache2/odoo.example.com.access.log combined

</VirtualHost>
{% endhighlight %}

Download this file: [odoo](files/apache2/odoo.conf)
