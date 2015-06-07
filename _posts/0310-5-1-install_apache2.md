## Install Apache 2.4 in Ubuntu 14.04

### Default page

{% highlight Bash %}
sudo mv /var/www/html/index.html /var/www/html/index-orig.html
sudo nano /var/www/html/index.html
{% endhighlight %}

{% highlight HTML linenos %}
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>Default</title>
    </head>
    <body>
        <p>Defaul page for server: proxy.example.com</p>
    </body>
</html>
{% endhighlight %}

Download this file: [index.html](files/index.html)
