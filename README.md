# CCNA Mega Lab – Enterprise Network (HSRP + OSPF + NAT + DHCP + VLANs + IPv6)

## Overview

This project simulates a full enterprise network with redundancy, dynamic routing, VLAN segmentation, DHCP services, NAT, and Internet connectivity. High availability is implemented using HSRP, and OSPF is used for dynamic routing between routers.

Built and tested using Cisco Packet Tracer.

---

## Network Features

* VLAN segmentation (Sales, HR, IT, Servers)
* Inter-VLAN Routing
* HSRP gateway redundancy
* OSPF dynamic routing (IPv4 and IPv6)
* NAT overload for Internet access
* DHCP server for automatic IP assignment
* IPv4 and IPv6 dual-stack configuration
* ISP simulation with external network access

---

## VLAN and Subnet Design

| VLAN | Department | Network         | Gateway      |
| ---- | ---------- | --------------- | ------------ |
| 10   | Sales      | 192.168.10.0/24 | 192.168.10.1 |
| 20   | HR         | 192.168.20.0/24 | 192.168.20.1 |
| 30   | IT         | 192.168.30.0/24 | 192.168.30.1 |
| 99   | Servers    | 192.168.99.0/24 | 192.168.99.1 |

Gateways provided using HSRP virtual IP addresses.

---

## Routing Configuration

Dynamic routing protocol:

* OSPF Area 0
* IPv4 and IPv6 routing enabled

Example:

```id="ospfmega1"
router ospf 1
network 10.0.0.0 0.0.0.255 area 0
```

---

## NAT Configuration

NAT overload configured for Internet access:

```id="natmega1"
ip nat inside source list 1 interface g0/0 overload
```

Allows internal users to access ISP network.

---

## DHCP Services

DHCP Server provides automatic IP assignment to all VLAN clients.

Services provided:

* IP address
* Default gateway
* DNS server

---

## Redundancy (HSRP)

HSRP provides gateway failover protection:

* Virtual gateway for each VLAN
* Automatic failover
* High availability

---

## Internet Connectivity

ISP router simulated with public network.

Connectivity verified using ping to:

```id="pingmega"
8.8.8.8
```

---

## Skills Demonstrated

* Enterprise network design
* VLAN configuration
* Inter-VLAN routing
* HSRP redundancy
* OSPF dynamic routing
* NAT overload (PAT)
* DHCP configuration
* IPv6 configuration
* Network troubleshooting

---

## Lab File

CCNA Mega Lab – Enterprise Network (.pkt)

---

## Author

Amir Samandi
CCNA Certified
Network+ Certified
