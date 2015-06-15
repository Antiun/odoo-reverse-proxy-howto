## Odoo behind Nginx

### Enable Odoo virtual hosts

{% highlight Bash %}
cd /etc/nginx/sites-enabled
rm -rf *
ln -s ../sites-available/odoo odoo
ln -s ../sites-available/odoo-ssl odoo-ssl
service nginx restart
{% endhighlight %}
