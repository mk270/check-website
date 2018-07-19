Check-website
=============

This is a trivial script that checks which IP addresses behind a website
are actually responding to connection attempts.

Assumptions:

* the targeted website has one or more A records in the DNS
* the appropriate check for up-ness is whether a TCP connection to port 80
  returns within 4 seconds
* that the DNS is working at all
* that the machine doing the test isn't itself somehow at fault for
  not being able to connect to the target IP address(es)

Usage
-----

    $ ./check-website www.google.com

Example
-------

````
    mk270@savile ~/Src/check-website> ./check-website magic.mn
    {'202.131.0.10': ConnectionRefusedError(111, 'Connection refused'),
     '202.131.224.80': OSError(113, 'No route to host'),
     '202.72.241.5': OSError(113, 'No route to host'),
     '218.100.84.26': OSError(113, 'No route to host')}
    mk270@savile ~/Src/check-website> ./check-website news.bbc.co.uk
    {'212.58.244.56': 'OK', '212.58.246.81': 'OK'}
````
