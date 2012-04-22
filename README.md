A fork of [MaxMind](http://www.maxmind.com)'s
[mod_geoip2](http://www.maxmind.com/app/mod_geoip) with more intelligent
X-Forwarded-For handling, as per
[this post](http://rod.vagg.org/2011/07/wrangling-the-x-forwarded-for-header/).

Currently based on mod_geoip2_1.2.7

**Summary**: The client-IP address in the list of addresses potentially
in the X-Forwarded-For HTTP header is normally the left-most header but
clients with private IP addresses using a forwarding proxy mean that
you'll often get the wrong address, usually a private IP address. This
module follows the rule:

**Always use the leftmost non-private address.**

You can compare with the current MaxMind release
[here](https://github.com/rvagg/mod_geoip2_xff/compare/maxmind...master).

*Note: There is a GeoIPEnableHostnameLookups flag, don't use it, it can
lead to lengthy blocking lookups, I'll be removing it at some point
unless someone wants to contribute a lookup that can timeout after a
very short period.*

Contributions more than welcome! I haven't done any serious C for a long
time so it's not a natural language for me any more and this module
isn't a high priority for me.

Original MaxMind README is
[here](https://github.com/rvagg/mod_geoip2_xff/blob/master/README).

Follow the same instructions found in the original
[INSTALL](https://github.com/rvagg/mod_geoip2_xff/blob/master/INSTALL).
