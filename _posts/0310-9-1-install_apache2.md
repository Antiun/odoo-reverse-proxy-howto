## Install Apache 2.4 in Ubuntu 14.04

### HTTP Proxy

Enable HTTP Proxy module

{% highlight Bash %}
a2enmod proxy_http
{% endhighlight %}

### Protect configuration files

Only Root (and Root group) can access configuration files

{% highlight Bash %}
sudo chown -R root:root /etc/apache2
sudo chmod -R o-rwx /etc/apache2
{% endhighlight %}

Restart Apache 2 service

{% highlight Bash %}
sudo service apache2 restart
{% endhighlight %}

