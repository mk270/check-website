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

