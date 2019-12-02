Using Netstat
-------------

-   Report port status on local machine

-   Switches to filter by protocol

-   Display process name or PID that opened port

Scanning Deep Dive
------------------

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
