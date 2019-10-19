Dig
===

“Dig” is a command line tool used for domain name server functions; it is a
component of the software suite BIND. This tool supersedes older tools, such
as “nslookup” and the program “host” however, these older tools remain popular
for use in many of the same ways you can use “dig”.

Dig is especially useful in DNS enumeration. Attackers may perform these types
of operations as a first setup on footprinting a target, so it is important that
defenders take the time to perform these types of enumeration exercises against
their own assets.

To perform a simple domain lookup to fetch A records:

dig securitytrails.com +short

Expected output:

[research\@securitytrails.com \~]\$ dig securitytrails.com +short

151.139.243.5

[research\@securitytrails.com \~]\$

Now let’s grab some mail server information adding -t mx parameters:

[research\@securitytrails.com \~]\$ dig securitytrails.com -t mx +short

10 aspmx2.googlemail.com.

1 aspmx.l.google.com.

5 alt2.aspmx.l.google.com.

5 alt1.aspmx.l.google.com.

10 aspmx3.googlemail.com.

[research\@securitytrails.com \~]\$

That’s right, securitytrails.com uses Google Apps for the email services.

The same goes for NS, CNAME and other records:

dig securitytrails.com -t ns +short

Output:

[research\@securitytrails.com \~]\$ dig securitytrails.com -t ns +short

ns07.domaincontrol.com.

ns08.domaincontrol.com.

[research\@securitytrails.com \~]\$

Great! With this last command we now have the authoritative name servers.

Of course, dig allows DNS transfers and this leads us to use the AXFR argument
against the ns08.domaincontrol.com NS, as you see below:

[researcg\@securitytrails.com \~]\$ dig axfr securitytrails.com
ns08.domaincontrol.com

; \<\<\>\> DiG 9.11.10-RedHat-9.11.10-1.fc30 \<\<\>\> axfr securitytrails.com
ns08.domaincontrol.com

;; global options: +cmd

; Transfer failed.

[research\@securitytrails.com \~]\$

And the transfer failed, because our DNS servers are well secured.

Recon tip: sometimes a particular name server may be configured to reject AXFR
requests. However, some others may not—that’s why we suggest you launch AXFR
queries against all the authoritative NS.

Host

Host is a command used to resolve the IP address of any given domain name.

As an example, we’ll use it to get all the public DNS records from
securitytrails.com. See below:

host securitytrails.com

Expected output:

[research\@securitytrails.com \~]\$ host securitytrails.com

securitytrails.com has address 151.139.243.5

securitytrails.com mail is handled by 5 alt2.aspmx.l.google.com.

securitytrails.com mail is handled by 5 alt1.aspmx.l.google.com.

securitytrails.com mail is handled by 10 aspmx3.googlemail.com.

securitytrails.com mail is handled by 1 aspmx.l.google.com.

securitytrails.com mail is handled by 10 aspmx2.googlemail.com.

The default host command retrieves A, AAAA and MX records.

If you want to specify any specific type of DNS record, you can use the -t
option. For example:

host -t ns securitytrails.com

Expected output:

[research\@securitytrails.com \~]\$ host -t ns securitytrails.com

securitytrails.com name server ns08.domaincontrol.com.

securitytrails.com name server ns07.domaincontrol.com.

What if you want to grab MX records? Just use -t mx, as shown here:

[research\@securitytrails.com \~]\$ host -t mx securitytrails.com

securitytrails.com mail is handled by 10 aspmx3.googlemail.com.

securitytrails.com mail is handled by 5 alt2.aspmx.l.google.com.

securitytrails.com mail is handled by 10 aspmx2.googlemail.com.

securitytrails.com mail is handled by 1 aspmx.l.google.com.

securitytrails.com mail is handled by 5 alt1.aspmx.l.google.com.

The -t option can be used to request any recognized query type such as: CNAME,
NS, SOA, TXT, DNSKEY, AXFR, etc. If no query type is specified, host by default
will look for A, AAAA and MX records.

Having said that, let’s try to perform a full DNS transfer:

[research\@securitytrails.com \~]\$ host -t axfr securitytrails.com
ns08.domaincontrol.com

Trying "securitytrails.com"

Host securitytrails.com not found: 9(NOTAUTH)

; Transfer failed.

[research\@securitytrails.com \~]\$

No luck :), our DNS server doesn’t allow AXFR transfers by default.

In the case of a successful DNS transfer, you should be able to get the full DNS
zone for the given domain name, as you see below—notice this time we are using
-l option, which is another way to list all DNS records from a domain name—while
testing the vulnerable site zonetransfer.me:

DNS Recon
---------

[DNSRecon](https://github.com/darkoperator/dnsrecon) is another great script
that can help you discover DNS data from any given domain name.

It allows you to enumerate all types of DNS records, including A, AAAA, SPF,
TXT, SOA, NS and MX, and also includes a brute force technique for grabbing
subdomain and host A and AAAA records based on a wordlist.

A cool thing we noticed is that it supports checking for cached A and AAAA DNS
records on the DNS servers, as well as local DNS enumeration capabilities.

How can I perform DNS exploration with DNSRecon?

The easiest way is by using the -d parameter, as you see below:

dnsrecon -d domain.com

Here we performed this dns enumeration against linkedin.com, and this was the
result:
