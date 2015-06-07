## Install Apache 2.4 in Ubuntu 14.04

### Default HTTPS virtual host

{% highlight Bash %}
sudo nano /etc/apache2/sites-available/default-ssl.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<VirtualHost *:443>
   ServerAdmin webmaster@example.com
   ServerName default.example.com

   SSLEngine on
   SSLProtocol           all -SSLv2 -SSLv3
   SSLCipherSuite        ALL:!ADH:!EXPORT:!SSLv2:RC4+RSA:+HIGH:+MEDIUM
   SSLCertificateFile    /etc/ssl/default.example.com/public.crt
   SSLCertificateKeyFile /etc/ssl/default.example.com/private.key

   DocumentRoot /var/www/html

   <Directory /var/www/html>
      Options None
      AllowOverride None

      # Access control by IP or IP range
      # Order deny,allow
      # Deny from all
      # Allow from 10.xx.0.0/16 127.0.0.0/255.0.0.0 ::1/128

      # Allow all
      Order allow,deny
      Allow from all
   </Directory>

   ErrorLog /var/log/apache2/default-ssl.error.log
   LogLevel warn

   CustomLog /var/log/apache2/default-ssl.access.log combined
</VirtualHost>
{% endhighlight %}

Download this file: [default-ssl.conf](files/default-ssl.conf)
