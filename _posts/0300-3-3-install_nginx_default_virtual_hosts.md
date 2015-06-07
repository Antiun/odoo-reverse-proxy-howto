## Install Nginx 1.4 in Ubuntu 14.04

### Enable default virtual hosts

{% highlight Bash %}
cd /etc/nginx/sites-enabled
rm -rf *
ln -s ../sites-available/default default
ln -s ../sites-available/default-ssl default-ssl
service nginx restart
{% endhighlight %}
