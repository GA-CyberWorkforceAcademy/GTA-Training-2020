**What to look for**

You must inventory and assess your environment in the same way an adversary
would do reconnaissance, both from an internal and an external perspective. This
includes identifying all of the following:

-   Technologies

-   IP Addresses and Sub-domains

-   People

-   Content of Interest/Importance

-   Vulnerabilities

"All the business of war, and indeed all the business of life, is to endeavor to
find out what you don't know by what you do: that's what I called 'guessing what
was at the other side of the hill"

\~Duke of Wellington

**From the Outside: An Attacker's Perspective**

The attacker will be doing an inventory and assessment of you environment and
looking for information and vulnerabilities that may help them in establishing
an avenue of approach.\</font\>\</p\>

Open Source Intelligence

Externally Facing Systems

People

**Open Source Intelligence (OSINT)**

Reconnaissance g begins with establishing a base of information via OSINT.
Without visiting the website, collect all the information you can about a
company of your choice. \</font\>\</p\>

Try some of these resources to start off with:

http://www.iana.org

https://newgtlds.icann.org/en

https://ww.dnsstuf.com/tools

https://www.whois.net

https://www.shodan.io

Interactions with protocols/resources

You may find yourself needing to obtain information from websites, FTP sites etc
however you only have CLI access. Try practicing some methods for interacting
with services from the command line.

**Social Engineering**

"Any act that influence a person to take an action that may or may not be in
their best interest."

\- Set a frame (pretexting) for interaction/ prime for response

\- Reciprocity

\- Scarcity

\- Authority

\- Social Proof

\- Sympathy

\<a href="https://www.youtube.com/watch?v=opRMrEfAIiI"
style="color:\#0000fe"\>\<font size="5"\>\<b\>Video - Social Engineering for a
password

Socal Engineering (Cont.)

\- Phone/email/In-person

\- Mental Buffer-Overflow: layering loop (stories/information) until the subject
tunes out/can't keep tract, inject bad stuff

\- Questions: Language structure that forces the execution of instructions.

\<a
href="https://www.youtube.com/watch?v=lc7scxvKQOo"style="color:\#0000fe"\>\<font
size="5"\>\<b\>Another Social Engineering Example - think about which techniques
were used\</b\>\</font\>\</a\>\<br\>

TCP Flags

\- Illegal flag combination can be used to determine Operating System \</font\>
\</p\>

\- X-mas Tree scan is one popular example used in nmap w/OS detection
(URG/PSH/FIN flag)\</font\> \</p\>

\- Linux Only sends RSTs if the port is open (no RST for closed ports)\</font\>
\</p\>

\- Windows Mac ALWAYS send RSTs if the TCP segment isn't a part of an
established communication

Port Scanning

Popular Scanning tools

\- Nmap, Netcat, Scapy, Hping3...

Common Scanning Methods

TCP Connect()Scan (IDS/logs catch this easily!)

\- SYN Scan (half-open)

\- ACK Scan (What is this for?)

\- Stealth Scans

\- NULL or FIN Scan (proper response - open-drop; closed-send an RST) \<br\>

\- UDP Scan (how does that work?!)

What about IPV6?

Host address space is enormous: scanning an entire prefix is out of the
questions.

"\>(64 bit host space, with 1 probe/sec would take 5 billions years)

Identifying address become key

Scanning locally or remote (probe multicast all-node, link local

Additional Reading: RFC 7707;
https://www.cs.columbia.edu/\~smb/papers/v6worms.pdf

Scanning

Nmap is a highly popular scanning tool

Nmap host discovery run with root privilege:

\- send raw ARP packet, nearly impossible to block or hide from this type of
scan

Nmap Host discovery run without root privilege:

\- Cannot open raw sockets

\- Connects to the 2 TCP port (80 and (443)

\- Host considered "up" if the connection succeeds/reset

ICMP: Nmap can do icmp ping sweeps however since OS'es & FW's often block/drop
ICMP this can be unreliable

P0f for Fingerprinting

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
