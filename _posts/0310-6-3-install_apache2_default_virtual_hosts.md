## Install Apache 2.4 in Ubuntu 14.04

### Enable default virtual hosts

{% highlight Bash %}
cd /etc/apache2/sites-enabled
rm -rf *
ln -s ../sites-available/default.conf 000-default.conf
ln -s ../sites-available/default-ssl.conf 000-default-ssl.conf
service apache2 restart
{% endhighlight %}

