## Install Apache 2.4 in Ubuntu 14.04

### ModSecurity

Enable Secure Rules Engine

{% highlight Bash %}
sudo nano /etc/modsecurity/modsecurity.conf-recommended
{% endhighlight %}

{% highlight ApacheConf linenos %}
# SecRuleEngine DetectionOnly
SecRuleEngine On
{% endhighlight %}

