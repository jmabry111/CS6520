## Switching

### Switching and Bridging

* ARP allows query for an IP Address to map that address to a MAC Address
* Hosts build ARP tables to save MAC-IP Mapping
* Encapsulation:
  * source puts IP packet in ethernet frame with it's MAC address and the Destination MAC Address from ARP Table

### Hubs
* Broadcast medium - All packets go out all ports regardless of which MAC address they are destined for
* COLLISIONS and LATENCY occur

### Switches: Traffic Isolation
* Learn MAC addresses so that the packet only goes out ports where the destination is connected
* If destination MAC address is not known it floods packet out all ports until it gets a response, then will remember the port the response came in on
* Loops - most network contain for redundancy
  * Broadast packet is flooded out all ports
  * If there is a loop, the looped port is confused and doesnt know whether to remember the broadcast or flood out all ports again.

