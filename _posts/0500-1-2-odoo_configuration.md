## Odoo configuration

### Featured settings related to proxing

* **proxy_mode**: Enables the use of ```X-Forwarded-*``` headers through Werkzeug's
proxy support.
* **workers**: Enables multiprocessing and sets up the specified number of
HTTP workers
* **limit_time_real**: Prevents the worker from taking longer than <limit>
seconds to process a request
* **xmlrpc_port**: (TCP/8069) Port on which the HTTP server listens.
* **longpolling_port**: (TCP/8072) port for long-polling connections in
multiprocessing or gevent mode. **Not used in default (threaded) mode**.
* **dbfilter**: Hides databases that do not match <filter>. The filter is a
regular expression, with the additions that:
    * ```%h``` is replaced by the whole hostname the request is made on.
    * ```%d``` is replaced by the subdomain the request is made on, with the
    exception of www (so domain odoo.com and www.odoo.com both match the
    database odoo)

More options at [Odoo Command-line interface](https://www.odoo.com/documentation/8.0/reference/cmdline.html)
