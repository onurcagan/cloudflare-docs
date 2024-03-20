---
pcx_content_type: concept
title: Nameservers
weight: 5
---

# Nameservers

As explained in [How DNS works](https://www.cloudflare.com/learning/dns/what-is-dns/), from the moment a user types an address (`www.example.com`) into their web browser, the resolution of a DNS query takes place. Also, the process behind DNS resolution involves different computers (or servers).

In the context of Cloudflare DNS, nameservers refer to authoritative nameservers, which are the last stop in the DNS query resolution. When a nameserver is authoritative for `example.com`, it means that DNS resolvers will consider responses from this nameserver when a user tries to access `example.com`.

## Authoritative nameservers offering

Within Cloudflare, and depending on your plan, you can choose between using Cloudflare-branded nameservers or setting up your own custom nameservers.

Regardless of the type you choose, for these nameservers to be authoritative for your domain, you need to [update your domain nameservers](/dns/nameservers/update-nameservers/). Updating your nameservers is required to activate your domain on Cloudflare and use most of our [application services](/fundamentals/concepts/how-cloudflare-works/#application-services).

### Standard nameservers

When you add a domain on a [primary (full)](/dns/zone-setups/full-setup/) DNS setup, Cloudflare automatically assigns two standard nameservers for your zone.

Standard nameservers are hosted on `ns.cloudflare.com` (Cloudflare-branded) and follow the pattern `<proper_name>.ns.cloudflare.com`.

### Advanced nameservers

If you are on a Enterprise plan, you have [Foundation DNS](/dns/foundation-dns/), which includes advanced nameservers.

[Advanced nameservers](/dns/foundation-dns/advanced-nameservers/) are hosted on `foundationdns.com`, `foundationdns.net` and `foundationdns.org` and each zone that uses advanced nameservers is assigned a set of three nameservers names: `<color>.foundationdns.com`, `<color>.foundationdns.net`, and `<color>.foundationdns.org`.

### Custom nameservers

With [custom nameservers](/dns/nameservers/custom-nameservers/), your nameservers are hosted on your own domain (or domains) and, in this sense, are not Cloudflare-branded.

You provide fully qualified domain names (`ns1.mydomain.com`) for your nameservers, and Cloudflare assigns one IPv4 and one IPv6 to each of your custom nameservers.