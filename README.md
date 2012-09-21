# mod_geoip2_xff

**mod_geoip2 with fancy, new-fangled X-Forwarded-For handling**
---------------------

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

To enable this special mode you need to turn the **GeoIPUseLeftPublicXForwardedForIP**
flag **On** in your apache config.

An additional config option is also available: **GeoIPEnableHostnameLookups**, when
set to **On** mod_geoip2 will attempt to resolve the matched IP address and store
the result in the GEOIP_HOST environment variable. This is useful for logging or
other basic remote host based configuration.

Changes for this fork are being recorded in the
[Changes](https://github.com/rvagg/mod_geoip2_xff/blob/master/Changes) file.

Contributions more than welcome!

Thanks to Kevin Gaudin for his contributions to fall back to the RemoteIP
where we fail to find a public IP address match.

Original MaxMind README is
[here](https://github.com/rvagg/mod_geoip2_xff/blob/master/README).

Follow the same instructions found in the original
[INSTALL](https://github.com/rvagg/mod_geoip2_xff/blob/master/INSTALL).

**See [Downloads](https://github.com/rvagg/mod_geoip2_xff/downloads) for tarballs.**