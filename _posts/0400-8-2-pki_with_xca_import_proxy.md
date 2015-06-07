## Creating a PKI with XCA

### Import certificates in proxy server

Add Example CA Root as a trusted CA certificate

{% highlight Bash %}
sudo nano /etc/ca-certificates.conf
{% endhighlight %}

{% highlight Bash linenos %}
# (...)
example/Example_CA_Root.crt
{% endhighlight %}

Update trusted CA certificates

{% highlight Bash %}
sudo update-ca-certificates
{% endhighlight %}

