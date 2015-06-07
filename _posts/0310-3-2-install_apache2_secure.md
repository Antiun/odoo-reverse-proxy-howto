## Install Apache 2.4 in Ubuntu 14.04

### Secure Apache2

{% highlight Bash %}
sudo nano /etc/apache2/conf-enabled/security.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<Directory />
   Options None
   AllowOverride None
   Order Deny,Allow
   Deny from all
</Directory>
ServerTokens Prod
ServerSignature Off
TraceEnable Off
<DirectoryMatch "/(\.svn|\.git)">
   Deny from all
   Satisfy all
</DirectoryMatch>
{% endhighlight %}
