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

"Any act that influence a person to take an action that may or may not be in
their best interest."

\- Set a frame (pretexting) for interaction/ prime for response

\- Reciprocity

\- Scarcity

\- Authority

\- Social Proof

\- Sympathy

Socal Engineering (Cont.)

\- Phone/email/In-person

\- Mental Buffer-Overflow: layering loop (stories/information) until the subject
tunes out/can't keep tract, inject bad stuff

\- Questions: Language structure that forces the execution of instructions.

Footprinting
============

Footprinting is also known as reconnaissance. This activity consists of
gathering information about computers, systems, networks, and the organizations
they belong to. This is generally the first step in a process used by attackers
to achieve their goals. An attacker may use various tools, techniques, and
technologies. Some of the utilities or tools used for Footprinting may include
(but is not limited to) the following:

World Wide Web Crawling
-----------------------

Web Robots (also known as Web Wanderers, Crawlers, or Spiders), are programs
that traverse the Web automatically. Legitimate search engines use them to index
web content however they can be abused by hackers or spammers to scan for email
addresses, or other information. These web robots use the robot.txt file for a
site to assume permission(s) to access content throughout the site.

DNS Basics
----------

A domain name is an easy to remember way for locating resources on the world
wide web. The domain names are related to computers or machines IP addresses.
The domain names are mapped to IP addresses through Domain Name Servers (DNS),
which are the Internet's equivalent of a phone book. These servers maintain a
directory of domain names and translate them when a query for a resource is
made.

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

-   DNS research quiz

    -   Simple Dig exercise

TCP/UDP Basics
--------------

<https://www.youtube.com/watch?v=ROuoU9qZSKQ>

Using Netstat
-------------

-   Report port status on local machine

-   Switches to filter by protocol

-   Display process name or PID that opened port

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
ZMap (software).

**TCP Flags**

-   Illegal flag combination can be used to determine Operating System

-   X-mas Tree scan is one popular example used in nmap w/OS detection
    (URG/PSH/FIN flag)

-   Linux Only sends RSTs if the port is open (no RST for closed ports)

-   Windows Mac ALWAYS send RSTs if the TCP segment isn't a part of an
    established communication

Port Scanning- Popular Scanning tools

-   Nmap/Zenmap, Netcat, Scapy, Hping3...

**Nmap/Zenmap is a highly popular scanning tool**

Nmap host discovery run with root privilege:

-   send raw ARP packet, nearly impossible to block or hide from this type of
    scan

Nmap Host discovery run without root privilege:

-   Cannot open raw sockets

-   Connects to the 2 TCP port (80 and 443)

-   Host considered "up" if the connection succeeds/reset

*ICMP: Nmap can do icmp ping sweeps however since OS'es & FW's often block/drop
ICMP this can be unreliable*

**Common Scanning Methods**

-   TCP Connect()Scan (IDS/logs catch this easily!)

-   SYN Scan (half-open)

-   ACK Scan (What is this for?)

-   Stealth Scans

-   NULL or FIN Scan (proper response - open-drop; closed-send an RST) \<br\>

-   UDP Scan (how does that work?!)

**What about IPV6?**

-   Host address space is enormous: scanning an entire prefix is out of the
    questions.

-   "\>(64 bit host space, with 1 probe/sec would take 5 billions years)

-   Identifying address become key

-   Scanning locally or remote (probe multicast all-node, link local

Additional Reading: RFC 7707;
https://www.cs.columbia.edu/\~smb/papers/v6worms.pdf

-   Network Enumeration quiz

-   Simple nmap exercise

Operating system and Service Identification
-------------------------------------------

Certain parameters within the TCP protocol definition are left up to the
implementation. Different operating systems, and different versions of the same
operating system, set different defaults for these values. By collecting and
examining these values, one may differentiate among various operating systems,
and implementations of TCP/IP.

Protection against the fingerprint doorway to attack is achieved by limiting the
type and amount of traffic a defensive system responds to. Examples include
blocking *address masks* and *timestamps* from outgoing ICMP control-message
traffic, and blocking ICMP echo replies. A security tool can alert to potential
fingerprinting: it can match another machine as having a fingerprinter
configuration by detecting *its* fingerprint.

Disallowing TCP/IP fingerprinting provides protection from vulnerability
scanners looking to target machines running a certain operating system.
Fingerprinting facilitates attacks. Blocking those ICMP messages is only one
defense required for full protection against attacks.

-   Operating System research quiz

-   Simple P0f exercise
