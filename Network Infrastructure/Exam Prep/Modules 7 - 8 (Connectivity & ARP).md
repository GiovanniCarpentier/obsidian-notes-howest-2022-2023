#networking 
#icmp
#ARP

## Connectivity
Networking connectivity refers to the ability of devices on a network to communicate with each other and with devices on other networks. Here are some key points to understand about networking connectivity, with a focus on ICMP and ping/traceroute:
	- **ICMP**: ICMP (Internet Control Message Protocol) is a protocol that is used by devices on a network to communicate with each other and with routers. ICMP is a layer 3 (network layer) protocol in the OSI model and is often used in conjunction with IP (Internet Protocol).

ICMP provides a number of functions, including error reporting, diagnostic testing, and routing assistance. Some common uses of ICMP include:
	- **Echo request/response (ping)**: The ping utility uses ICMP echo request/response messages to test connectivity between two devices. When a device sends a ping request to another device, the destination device sends an echo reply message in response. This allows the sender to determine whether the destination device is reachable and to measure the round-trip time for the request/response.  
	- **Traceroute**: The traceroute utility uses ICMP echo request/response messages to trace the path that a packet takes from the source device to the destination device. Traceroute sends a series of ping requests with increasing time-to-live (TTL) values, and records the IP address of the device that responds to each request. This allows the user to see the path that the packet takes through the network and to identify any intermediate devices or routers

## ARP
**Address Resolution Protocol (ARP)** is a network protocol that is used to resolve the Internet Protocol (IP) address of a device to its Media Access Control (MAC) address. Here are some key points to understand about ARP:
- **IP and MAC**: IP addresses are used to uniquely identify devices on a network, while MAC addresses are unique identifiers assigned to the physical network interface of a device. IP and MAC addresses are used together to enable communication between devices on a network.  
- **ARP**: ARP is used to resolve the MAC address of a device when the IP address of that device is known. When a device wants to send data to another device on the same network, it uses ARP to determine the MAC address of the destination device based on its IP address.

The device sends an ARP request message containing the IP address of the destination device, and any device on the network that has that IP address will respond with its MAC address. The sender can then use the MAC address to send the data directly to the destination device.

- ARP issues: There are a number of issues that can arise with ARP, including:
	- **ARP spoofing**: ARP spoofing is a type of attack in which an attacker sends forged ARP request/response messages to trick devices on a network into believing that the attacker's device has a specific IP address. This can allow the attacker to intercept data intended for another device or to redirect traffic to the attacker's device.
	- **ARP cache poisoning**: ARP cache poisoning is a type of attack in which an attacker sends forged ARP request/response messages to update the ARP caches of other devices on the network with incorrect information. This can cause the devices to send data to the wrong MAC address, potentially allowing the attacker to intercept the data.
	- **ARP exhaustion**: In some cases, the number of unique IP-to-MAC address mappings that a device can store in its ARP cache may be limited. If the device receives too many ARP request messages for unique IP addresses