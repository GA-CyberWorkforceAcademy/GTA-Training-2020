Footprinting
============

Footprinting is also known as reconnaissance. This activity consists of
gathering information about computers, systems, networks, and the organizations
they belong to. This is generally the first step in a process used by attackers
to achieve their goals. An attacker may use various tools, techniques, and
technologies. Some of the utilities or tools used for footprinting may include
(but is not limited to) the following:

Open Source Intelligence (OSINT)
--------------------------------

Reconnaissance g begins with establishing a base of information via OSINT. This
may include:

-   Passive reconnaissance

-   Locating information that the target may not regard as exploitable or even
    know they have disclosed

-   Performing searches covertly through anonymized proxies / VPNs

-   Using compromised accounts or web servers to gain further access

To begin to understand what type on information is available through open source
intelligence, try collecting all the information you can about a company of your
choice.

Try some of these resources to start off with:

-   <https://www.shodan.io> (you can perform limited searches with a free
    account)

-   https://Indeed.com (You can find information about technology and their
    personnel needs in job postings)

-   <https://ww.dnsstuf.com/tools>

Social Engineering
------------------

*"Any act that influence a person to take an action that may or may not be in
their best interest."*

![Image result for social engineering](media/6a685c9ec5e6e1d10ccb43dd6a9b37be.jpg)

Image result for social engineering

Image result for social engineering

This is often the starting point for an attacker. Getting information from
people within an organization can allow attackers a fast, cheap, and potentially
low-risk way to develop their strategy. If social engineering is used to gain
access to an organization either physically, or through the network, this is
even more valuable to the attacker.

When using social engineering as a method in reconnaissance, the attacker will
generally look at framing the exchange, and potentially priming a victim for
responses. Some tricks/tactics to successful social engineering include using
(but are not limited too): reciprocity, scarcity, authority, and sympathy.

**Social engineering can be done in-person, over the phone, or online (email or
other methods) with varying degrees of risk to the attacker.**

World Wide Web Crawling
-----------------------

Web Robots (also known as Web Wanderers, Crawlers, or Spiders), are programs
that traverse the Web automatically. Legitimate search engines use them to index
web content however they can be abused by hackers or spammers to scan for email
addresses, or other information. These web robots use the robot.txt file for a
site to assume permission(s) to access content throughout the site.

\---

DNS Basics
----------

A domain name is an easy to remember way for locating resources on the world
wide web. The domain names are related to computers or machines IP addresses.
The domain names are mapped to IP addresses through Domain Name Servers (DNS),
which are the Internet's equivalent of a phone book. These servers maintain a
directory of domain names and translate them when a query for a resource is
made.

\---

Domain Registar Queries
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

Whois can be accesses in your browser from a number of sites. Try using
<https://whois.net> or <https://lookup.icann.org/> to lookup domain names for a
few sites you use commonly.

DNS enumeration 
----------------

DNS enumeration provides information about the DNS servers and their
corresponding records for an organization. An organization may have both
internal and external DNS servers that can yield information such as usernames,
computer names, and IP addresses of potential target systems. There are tools
and utilities useful for performing DNS enumeration, as well as open sources of
information. Some examples of these include (but are not limited to), dig,
nslookup, American Registry for Internet Numbers (ARIN), and Whois. To enumerate
DNS, you must have understanding about DNS and how it works.

You must have knowledge about DNS records. The list of DNS record provides an
overview of types of resource records (database records) stored in the zone
files of the Domain Name System (DNS). The DNS implements a distributed,
hierarchical, and redundant database for information associated with Internet
domain names and addresses. In these domain servers, different record types are
used for different purposes. Some common DNS queries you should understand may
include: A, AAAA, MX, NS, CNAME, AXFR, and SOA. There are many more to learn,
but this short list should be a starting point for familiarity.

Frameworks
----------

Like most aspects of cybersecurity or cyberattack, there are a number of
frameworks available for automating work! **Recon-ng** is a full-featured
reconnaissance framework designed with the goal of providing a powerful
environment to conduct open source web-based reconnaissance quickly and
thoroughly.

Using Netstat
-------------

The netstat  command (network statistics) is a utility that displays network
connections for Transmission Control Protocol (both incoming and outgoing), UDP
ports that are open and listening for communications, routing tables, and a
number of network interface and protocol statistics. It can be used on
linux/unix or windows type operating systems. This command is useful for
troubleshooting issues, but also may be used by an adversary that has access to
a compromised host to gain more information about what the system is running,
the types of connections it can make or the networks it connects to.

The command can be very important for defenders to identify network connections
on hosts. Malware often either connects out to an adversary to establish a
connection the attacker can use to access the victim/network, or opens a port to
be connected to by an attacker.

Network enumeration/port scanning
---------------------------------

Network Enumeration is the process of gathering information about a target
network(s). There are several methods that attackers can enumerate a network
during which attackers may gather information such as: Usernames, Group names,
Hostnames, Network shares and services, IP tables and routing tables, Service
settings and Audit configurations, Application and banners, SNMP and DNS
Details. While there are a number of methods and tools available to gather this
information, port scanning and vulnerability scanning are generally at the top
of the list. Port scanning is often used by an attacker to establish an active
connection with the target(s) and try to discover as much data as possible to
help them to deliver a payload that can exploit the systems further. Enumeration
tools scan ports to gather information about services that may be listening and
available on a target. For example, an attacker that finds a host with TCP based
SMB protocol open to the internet could use that knowledge to target this host
via this protocol. (SMB protocol should only be accessible internally as is has
many security vulnerabilities that can be remotely exploited.) A vulnerability
scan may look at ports/services but will also look at things such as
software/application version. Outdated or unpatched software/applications
provides another way that attackers may look to deliver a payload or exploit a
target.

The following are commonly used tools in network enumeration: Nmap, Nessus,
OpenVAS, SAINT (software), Security Administrator Tool for Analyzing Networks,
ZMap (software). Port Scanning will be discussed in further depth in following
lessons.
