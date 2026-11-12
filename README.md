# Implement VLANs and Trunking Using IPv6

## Project Overview

This project demonstrates how to implement VLAN segmentation and trunking using IPv6 addressing in Cisco Packet Tracer.

The network consists of two Cisco switches (S1 and S2) connected through a trunk link. VLANs are configured to logically separate Staff and Management departments. A Native VLAN and Parking Lot VLAN are also implemented for network organization and basic switch security.

## Network Topology

**Devices Used:**
- 2 Cisco Layer 2 Switches (S1 and S2)
- 2 Staff PCs
- 2 Management PCs
- Copper Ethernet connections

## VLAN Configuration

The following VLANs are created on both switches:

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 15 | Staff | Staff department |
| 25 | Management | Network management |
| 88 | Parking_Lot | Unused switch ports |
| 888 | Native | Native VLAN for trunking |

## IPv6 Addressing Table

| Device | VLAN | IPv6 Address | Prefix |
|---|---|---|---|
| Staff-PC1 | 15 | 2001:DB8:ACAD:15::A | /64 |
| Staff-PC2 | 15 | 2001:DB8:ACAD:15::B | /64 |
| Management-PC1 | 25 | 2001:DB8:ACAD:25::A | /64 |
| Management-PC2 | 25 | 2001:DB8:ACAD:25::B | /64 |
| S1 Management SVI | 25 | 2001:DB8:ACAD:25::1 | /64 |
| S2 Management SVI | 25 | 2001:DB8:ACAD:25::2 | /64 |

## Switch Port Configuration

### Access Port Configuration

**VLAN 15 – Staff**
- Fa0/1–Fa0/6

**VLAN 25 – Management**
- Fa0/7–Fa0/12

**VLAN 88 – Parking Lot**
- Fa0/13–Fa0/24
- G0/2

Unused ports are assigned to VLAN 88 and administratively shut down.

### Trunk Port Configuration

The G0/1 interfaces of both switches are configured as trunk ports.

Trunk configuration includes:
- Switchport mode: Trunk
- Native VLAN: 888
- Allowed VLANs: 15, 25, 888

This allows Staff and Management VLAN traffic to pass between the switches.

## IPv6 Configuration

IPv6 addresses are configured on the Management VLAN SVI interfaces.

**Switch S1:**
- Interface: VLAN 25
- IPv6 Address: 2001:DB8:ACAD:25::1/64

**Switch S2:**
- Interface: VLAN 25
- IPv6 Address: 2001:DB8:ACAD:25::2/64

IPv6 addressing is also configured manually on all four end devices.

## Key Networking Concepts Implemented

1. VLAN creation and configuration.
2. IPv6 addressing and subnetting.
3. Access port configuration.
4. Trunk port configuration.
5. Native VLAN implementation.
6. Management SVI configuration.
7. Unused port security using a Parking Lot VLAN.
8. Switch SDM template configuration for dual IPv4 and IPv6 support.

## Verification Commands

The following Cisco IOS commands are used to verify the configuration:

```bash
show vlan brief
show interfaces trunk
show ipv6 interface brief
show running-config
show interfaces status
```

## Technologies and Tools

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv6 Addressing
- VLAN Configuration
- IEEE 802.1Q Trunking
- Layer 2 Switching

## Learning Outcomes

Through this project, I gained practical experience in configuring IPv6 addresses, creating VLANs, assigning switch ports, configuring trunk links, implementing native VLANs, and managing unused switch ports.

## Conclusion

This project helped strengthen my understanding of IPv6 networking and VLAN-based network segmentation. It also provided practical experience with Cisco switch configuration and basic network administration.

**Project Status:** Completed
