## Install Apache 2.4 in Ubuntu 14.04

### ModSecurity

Enable **headers** module

{% highlight Bash %}
sudo a2enmod headers
{% endhighlight %}

Install Apache 2 ModSecurity Rules

{% highlight Bash %}
sudo apt-get install -y libapache2-modsecurity modsecurity-crs
{% endhighlight %}

