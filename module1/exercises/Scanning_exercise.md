Part 1 – Getting familiar with the nmap
=======================================

NMAP (network mapper) is a console-based utility for network exploration and
conducting security audits. It is used for host discovery, port scanning, OS and
application identification and general vulnerability scanning.

References:

<https://linux.die.net/man/1/nmap>

<https://nmap.org/book/man.html>

Host Discovery
--------------

One of the very first steps in any network reconnaissance mission is to reduce a
(sometimes huge) set of IP ranges into a list of active or interesting hosts.

1.  When performing host discovery, If no host discovery options are given, Nmap
    sends the following:

| 1a) |
|-----|
| 1b) |
| 1c) |
| 1d) |

2.  There are six port states recognized by Nmap. Provide a SHORT (1-2 sentence)
    description of each. This information can be found at:
    <https://nmap.org/book/man-port-scanning-basics.html>

| 2a) Open:             |
|-----------------------|
|                       |
|                       |
|                       |
|                       |
| 2b) Closed:           |
|                       |
|                       |
|                       |
|                       |
| 2c) Filtered:         |
|                       |
|                       |
|                       |
|                       |
| 2d) Unfiltered:       |
|                       |
|                       |
|                       |
|                       |
| 2e) Open\|filtered:   |
|                       |
|                       |
|                       |
|                       |
| 2f) Closed\|filtered: |
|                       |
|                       |
|                       |
|                       |

3.  What do the following switches do?

| \-sn: |
|-------|
| \-PO: |
| \-PS: |
| \-PU: |
| \-sN: |
| \-sX: |
| \-sV: |
| \-O:  |

Part 2 - Using nmap to conduct reconnaissance
---------------------------------------------

1.  Open a terminal window in your analyst VM.

2.  Use a broad ping scan to determine the hosts that are "up" on the LAN
    portion of your network. This should be the 10.X.X.X/24 network.

3.  Record the results.

>   *Investigate how to restrict the application scans to specific sets of port
>   numbers, otherwise your scans may take a long time to complete.*

1.  Use the same nmap command to start a ping scan on the entire /16 common
    network for 10.X.X.X/16. Terminate this scan after a couple minutes
    with Ctrl-C.

2.  How many hosts would this scan look for? Justify your answer.

3.  Conduct a scan of the server at 10.X.X.X to discover the Operating System,
    open ports and version of any services running. Record your results.

>   6a) What operating system does nmap think your Server VM is running?

>   6b) What is its MAC address? 

>   6c) What services (ports) are running and what is their version?

1.  Now that you have a list of services and versions, research a few and record
    any known vulnerabilities based on those services.
