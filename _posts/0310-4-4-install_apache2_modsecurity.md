## Install Apache 2.4 in Ubuntu 14.04

### ModSecurity

Enable all **base** and **optional** rules

{% highlight Bash %}
cd /usr/share/modsecurity-crs
for f in `ls --color=never base_rules/ | grep modsecurity`; do sudo ln -s /usr/share/modsecurity-crs/base_rules/$f activated_rules/$f; done
for f in `ls --color=never optional_rules/ | grep modsecurity`; do sudo ln -s /usr/share/modsecurity-crs/optional_rules/$f activated_rules/$f; done
{% endhighlight %}

