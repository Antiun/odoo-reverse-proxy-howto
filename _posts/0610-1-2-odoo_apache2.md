## Odoo behind Apache2

### HTTPS virtual host (1/3)

{% highlight Bash %}
sudo nano /etc/apache2/sites-available/default-ssl.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<VirtualHost *:443>
   ServerAdmin webmaster@example.com
   ServerName odoo.example.com

   SSLEngine on
   SSLProtocol           all -SSLv2 -SSLv3
   SSLCipherSuite        ALL:!ADH:!EXPORT:!SSLv2:RC4+RSA:+HIGH:+MEDIUM
   SSLCertificateFile    /etc/ssl/wildcard.example.com/public.crt
   SSLCertificateKeyFile /etc/ssl/wildcard.example.com/private.pem

   RequestHeader set X-Forwarded-Proto "https"

   <IfModule mod_rewrite.c>
      RewriteEngine On

      # Permanent redirect (301 HTTP) if no canonical domain name
      RewriteCond %{HTTP_HOST} !^odoo.example.com
      RewriteRule ^/(.*)$ https://odoo.example.com/$1 [R=301,NE,L]
   </IfModule>

{% endhighlight %}

(...)

Download this file: [odoo-ssl.conf](files/apache2/odoo-ssl.conf)
