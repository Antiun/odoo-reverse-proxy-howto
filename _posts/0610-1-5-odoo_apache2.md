## Odoo behind Apache2

### Enable Odoo virtual hosts

{% highlight Bash %}
cd /etc/apache2/sites-enabled
rm -rf *
ln -s ../sites-available/odoo.conf 010-odoo.conf
ln -s ../sites-available/odoo-ssl.conf 010-odoo-ssl.conf
service apache2 restart
{% endhighlight %}

