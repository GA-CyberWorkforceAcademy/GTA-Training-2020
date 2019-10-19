Footprinting
============

Footprinting is also known as reconnaissance. This activity consists of
gathering information about computers, systems, networks, and the organizations
they belong to. This is generally the first step in a process used by attackers
to achieve their goals. An attacker may use various tools, techniques, and
technologies. Some of the utilities or tools used for Footprinting may include
(but is not limited to) the following:

Domain Registar queries
-----------------------

A domain name registrar is a service that allows you to officially register your
desired website domain name so that it is unique to you, and no one else can own
it. Legitimate domain name registrars are accredited by the Internet Corporation
for Assigned Names and Numbers (ICANN). ICANN currently accredits domain name
registrars for the following top-level domains: .aero, .biz, .com, .coop, .info,
.museum, .name, .net, .org, .pro.

*(A "top-level domain" is the suffix that a domain name ends with, such as .com
or .org. Your domain name registrar will only allow you to register a domain
name that has not yet been registered to someone else.)*

-   Simple Whois exercise

Google Hacking

World Wide Web spidering
------------------------

-   Web crawler research quiz

-   Simple web crawler exerciss

DNS enumeration 
----------------

Provides information about the DNS servers and their corresponding records for
an organization. An organization may have both internal and external DNS servers
that can yield information such as usernames, computer names, and IP addresses
of potential target systems. There are tools and utilities useful for performing
DNS enumeration, as well as open sources of information. Some examples of these
include (but are not limited to), dig, nslookup, American Registry for Internet
Numbers (ARIN), and Whois. To enumerate DNS, you must have understanding about
DNS and how it works.

You must have knowledge about DNS records. The list of DNS record provides an
overview of types of resource records (database records) stored in the zone
files of the Domain Name System (DNS). The DNS implements a distributed,
hierarchical, and redundant database for information associated with Internet
domain names and addresses. In these domain servers, different record types are
used for different purposes. Some common DNS queries you should understand may
include: A, AAAA, MX, NS, CNAME, AXFR, and SOA. There are many more to learn,
but this short list should be a starting point for familiarity.

-   DNS research quiz

    -   Simple Dig exercise

Network enumeration/port scanning
---------------------------------

-   Network info research quiz

-   Simple nmap exercise

Operating system and Service Identification
-------------------------------------------

Certain parameters within the [TCP
protocol](https://en.wikipedia.org/wiki/TCP_protocol) definition are left up to
the implementation. Different operating systems, and different versions of the
same operating system, set different defaults for these values. By collecting
and examining these values, one may differentiate among various operating
systems, and implementations of TCP/IP.

Protection against the fingerprint doorway to attack is achieved by limiting the
type and amount of traffic a defensive system responds to. Examples include
blocking *address masks* and *timestamps* from
outgoing [ICMP](https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol) control-message
traffic, and blocking [ICMP echo
replies](https://en.wikipedia.org/wiki/ICMP_Echo_Reply). A security tool can
alert to potential fingerprinting: it can match another machine as having a
fingerprinter configuration by
detecting *its* fingerprint.[[3]](https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting#cite_note-3)

Disallowing TCP/IP fingerprinting provides protection from [vulnerability
scanners](https://en.wikipedia.org/wiki/Vulnerability_scanner) looking to target
machines running a certain operating system. Fingerprinting facilitates attacks.
Blocking those ICMP messages is only one of an array of defenses required for
full protection against
attacks.[[4]](https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting#cite_note-4)

-   Operating System research quiz

-   Simple P0f exercise
