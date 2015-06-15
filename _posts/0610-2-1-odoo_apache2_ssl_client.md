## Odoo behind Apache2

### SSL client certificate authentication

{% highlight Bash %}
   SSLVerifyClient none
   SSLCACertificateFile /usr/share/ca-certificates/example/Example_CA_Root.crt

   <Location "/" >
      Order deny,allow
      Deny from all
      Allow from all
   </Location>

   <Location "/web/database/manager" >
      SSLVerifyClient require
      SSLVerifyDepth 10
      SSLRequireSSL
      SSLRequire %{SSL_CLIENT_S_DN_O} eq "Example Ltd." and
                 %{SSL_CLIENT_S_DN_OU} in {"Development"}
   </Location>

   <Location "/website/info" >
      SSLVerifyClient require
      SSLVerifyDepth 10
      SSLRequireSSL
      SSLRequire %{SSL_CLIENT_S_DN_O} eq "Example Ltd." and
                 %{SSL_CLIENT_S_DN_OU} in {"Development"}
   </Location>
{% endhighlight %}

