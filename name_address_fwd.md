# IP Addressing
## IPv4 structure and allocation
* IP = Internet Protocol
* 32-bit number formatted in dotted quad notation
* each quad consists of an 8-bit string

|  130   |  207   |   7    |  36    |
|:------:|:------:|:------:|:------:|
|10000010|11001111|00000111|00100100|

* there are 2<sup>32</sup> = 4 billion addresses

### Pre 1994: Classful Addressing
* Class A: 8-bits NetID, 2<sup>24</sup> Host ID
* Class B: 16-bits NetID, 2<sup>16</sup> Host ID
* Class C: 24-bits NetID, 8 for Host ID
* **Starting to run out of Class C addresses around 1994**

### IP Address Allocation
* Central
* ARIN
* Ripe NCC
* APNIC
* LACNIC
* AfriNIC
* Defined
* Multicast
* Experimental
* IANA
* **whois -h whois.ra.net ip address**

### CIDR - Classless Inter Domain Routing
