---
label: pki-with-xca-import-proxy
---
## Creating a PKI with XCA

### Import certificates in proxy server

* Create a folder for our CA Root ```/usr/share/ca-certificates/example```
    * Copy CA Root ```Example_CA_Root.crt``` to ```/usr/share/ca-certificates/example```
* Create a folder for our Wildcard ```/etc/ssl/wildcard.example.com```
    * Copy Wildcard certificate ```Wildcard_Example.crt``` to ```/etc/ssl/wildcard.example.com```
    * Copy Wildcard private key ```Wildcard_Example.pem``` to ```/etc/ssl/wildcard.example.com```

Protect private key

{% highlight Bash %}
sudo chmod 444 /usr/share/ca-certificates/example/Example_CA_Root.crt
sudo chmod 444 /etc/ssl/wildcard.example.com/Wildcard_Example.crt
sudo chmod 400 /etc/ssl/wildcard.example.com/Wildcard_Example.pem
{% endhighlight %}

