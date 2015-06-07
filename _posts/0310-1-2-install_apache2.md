## Install Apache 2.4 in Ubuntu 14.04

### Apache 2

Install Apache 2 in prefork mode using Debian Package system

{% highlight Bash %}
sudo apt-get install -y apache2 apache2-utils apache2-mpm-prefork
{% endhighlight %}

Enable **rewrite** and **SSL** modules

{% highlight Bash %}
sudo a2enmod rewrite
sudo a2enmod ssl
{% endhighlight %}
