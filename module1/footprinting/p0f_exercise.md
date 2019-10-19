**P0f for Fingerprinting and Operating System**

P0f is a tool that utilizes an array of sophisticated, purely passive traffic
fingerprinting mechanisms to identify the players behind any incidental TCP/IP
communications (often as little as a single normal SYN) without interfering in
any way. Version 3 is a complete rewrite of the original codebase, incorporating
a significant number of improvements to network-level fingerprinting, and
introducing the ability to reason about application-level payloads (e.g., HTTP).

Some of p0f's capabilities include:

-   Highly scalable and extremely fast identification of the operating system
    and software on both endpoints of a vanilla TCP connection - especially in
    settings where NMap probes are blocked, too slow, unreliable, or would
    simply set off alarms.

-   Measurement of system uptime and network hookup, distance (including
    topology behind NAT or packet filters), user language preferences, and so
    on.

-   Automated detection of connection sharing / NAT, load balancing, and
    application-level proxying setups.

-   Detection of clients and servers that forge declarative statements such
    as *X-Mailer* or *User-Agent*.

Primarily looks at TCP/IP Header attributes to make a determination (packaged
and custom signatures)

1: IP version

2: Initial TTL

3: IP Options

4: MSS

5: Windows size (value or multiple of value)

6: Window Scale

7: TCP Options (in the orders listed in the field)

8: Quirks (DF-Flag or IP ID)

9: Payload Class
