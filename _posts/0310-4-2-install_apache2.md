## Install Apache 2.4 in Ubuntu 14.04

### ModSecurity

Include ModSecurity rules

{% highlight Bash %}
sudo nano /etc/modsecurity/rules.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<IfModule security2_module>
    Include "/usr/share/modsecurity-crs/*.conf"
    Include "/usr/share/modsecurity-crs/activated_rules/*.conf"
</IfModule>
{% endhighlight %}

