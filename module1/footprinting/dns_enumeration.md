Dig
===

“Dig” is a command line tool used for domain name server functions; it is a
component of the software suite BIND. This tool supersedes older tools, such
as “nslookup” and the program “host” however, these older tools remain popular
for use in many of the same ways you can use “dig”.

Dig is especially useful in DNS enumeration. Attackers may perform these types
of operations as a first step in reconnaissance of a target, so it is important
that defenders take the time to perform these types of enumeration exercises
against their own assets.

Try the following from your Analyst VM:

1.  Perform a simple domain lookup to fetch A records for “gacybercenter.org”:

>   hostname\@gta.internal: \~\$ dig gacybercenter.org +short

>   Output:

|   |
|---|


1.  Now let’s grab some mail server information for “Augusta.edu” by adding -t
    mx parameters:

hostname\@gta.internal: \~\$ dig augusta.edu -t mx +short

Output:

|   |
|---|


1.  The process can be used for finding NS, CNAME and other records. Try finding
    the authoritative nameserver(s) for “augusta.edu”:

hostname\@gta.internal: \~\$ dig augusta.edu -t ns +short

>   Output:

|   |
|---|


Great! With this last command we now have the authoritative name servers. This
information is readily available but can be abused by attackers. One type of DNS
transaction used in reconnaissance is a zone transfer.

Usually a zone transfer is a normal operation between primary and secondary DNS
servers in order to synchronize the records for a domain. This is typically not
something you want to be externally accessible, nor available to any device
except the authorized DNS servers that are synchronizing. If an attacker can
gather all your organization’s DNS records, they can use those to more precisely
select targets for exploitation.

While a name server may be configured to reject AXFR requests, that isn’t always
the case. This is why we suggest you use AXFR queries against all the
authoritative NS in use to ensure proper configuration.

Try a zone transfer against your own organization or a randomly selected domain:

hostname\@gta.internal: \~\$ dig axfr \@“ns” “domain”

*Example: dig axfr \@ns.domains.com mydomainname.net*

>   Output:

|   |
|---|


>   Hopefully the attempt failed/was rejected because the DNS server was well
>   secured!

In the case of a successful DNS transfer, you would receive the full DNS zone
for the given domain name. Try testing the vulnerable site zonetransfer.me.

1.  Gather the NS and attempt a zone transfer request against the domain
    “zonetransfer.me”. In the results, you will find a variety of records.
    Locate an AAAA record, and an interesting TXT record. Record their domain
    and details:

>   Output:

| AAAA |   |
|------|---|
| TXT  |   |
