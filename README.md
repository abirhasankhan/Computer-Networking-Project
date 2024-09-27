# University Network Design Project

<img src="./network design.PNG" alt="University Network Design" width="1000" height="800">

## Project Overview

This project involves designing a network infrastructure for the **"University of Professionals"** complex using Cisco Packet Tracer. The university has six campuses, each connected by routers, allowing seamless communication between devices across campuses. The network supports various devices such as PCs, laptops, tablets, smartphones, and servers, utilizing a combination of copper wire, wireless, and serial DTE transmission media.

## Tools Used
- **Cisco Packet Tracer**: For network simulation and design.
- **Snipping Tool**: For taking screenshots of the network setup.
- **Microsoft Word**: For documentation.

## Network Components

### Hardware
- PCs, Laptops, Tablets, Smartphones
- Servers
- Switches
- WiFi Routers
- Routers

### Transmission Media
- Copper Wire
- Wireless
- Serial DTE

### Protocols
- **Routing**: RIP (Routing Information Protocol)
- **TCP/IP**: HTTP, HTTPS, DHCP, DNS

### Topology
All devices are connected through six main routers representing the six university campuses.

## Network Configuration

The network is divided into six campuses, each with its own set of devices connected through routers and switches. All devices can communicate with each other and access the university web server using DNS configured for each switch. Wireless connections are provided for smartphones.

### IP Addressing
Here is the list of IP addresses used for the network:

| Device       | IP Address     | Default Gateway   | Description             |
|--------------|----------------|-------------------|-------------------------|
| DHCP1        | 140.168.10.10  | 140.168.10.1      | DHCP server for Campus 1|
| DNS          | 140.168.10.5   | 140.168.10.1      | DNS server for Campus 1 |
| WEB          | 140.168.10.7   | 140.168.10.1      | University Web Server   |
| DHCP2        | 192.168.10.10  | 192.168.10.1      | DHCP server for Campus 2|
| DNS          | 192.168.10.5   | 192.168.10.1      | DNS server for Campus 2 |
| ...          | ...            | ...               | ...                     |

*Note: Similar configuration for other campuses.*

### Router Configuration
```bash
# Configuration for connecting switches to router1
en
config t
interface fa0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
exit

# RIP Configuration for router to router communication
en
config t
router rip
version 2
no auto-summary
exit
```

## Limitations

High Maintenance Costs: Due to the use of multiple DHCP and DNS servers across campuses.
Management Complexity: Managing multiple servers can be challenging and requires additional resources.

## Suggested Improvements
Centralized Servers: Using a single DNS and DHCP server for the entire university network would simplify maintenance and reduce operational costs.
Enhanced Security Measures: Implementing network security measures like firewalls and VPNs can protect sensitive data and prevent unauthorized access.
Scalability Considerations: Optimizing the network design for scalability will make future expansions and upgrades easier.

## Conclusion
The network design successfully integrates multiple devices and subnets across six campuses. The project demonstrates the setup of servers, Wi-Fi connections, and device configurations. The implementation of RIP made routing easier compared to static settings. Future enhancements can focus on optimizing server usage and reducing complexity.
