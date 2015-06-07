## Install Apache 2.4 in Ubuntu 14.04

### Default ServerName

Define **ServerName** directive and ports where Apache2 will listen

* TCP/80: HTTP
* TCP/443: HTTPS

{% highlight Bash %}
sudo nano /etc/apache2/ports.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
ServerName proxy.example.com
Listen 80
<IfModule mod_ssl.c>
    Listen 443
</IfModule>
{% endhighlight %}

