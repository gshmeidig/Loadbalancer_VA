[Main M_KB](/README.md)
[Cisco](/Cisco/README.md)
# Cisco Labs

## Briefly summarized
### IPv6
IPv6 Categories:
- Unicast – Unicast uniquely identifies an interface on an IPv6-enabled device.
- Multicast – Multicast is used to send a single IPv6 packet to multiple destinations.
- Anycast – This is any IPv6 unicast address that can be assigned to multiple devices.

Types of IPv6 Unicast Addresses:
- Global UNicast Address (GUA)
    - Similar to Public IPv4
    - Global Unique
    - internet-routable addresses
    - IPv6 Structure and available Range form ISP (only 1/8 of available address space)
    ![IPv6 Struccture](/Cisco/Labs/Bilder/IPv6_structure.png)
        - Global Routing Prefix assigned by ISP
        - Subnet ID used to identify subnets within sites
        - Interface ID equivalent to host portion (recommended /64 subnets)
    - obtained dynamically through Internet Control Message Protocol version 6 (ICMPv6)
    - 

- Link-local Address (LLA)
    - Required for every IPv6-enabled Device
    - not routable and only Single Link
    - Every IPv6-enabled network interface must have LLA
    - if not manually configured, device automatically create one.

IPv6 Unique Local Address(ULA) used for:
- range fc00::/7 to fdff::/7
- used for local addressung within a site or between a limited number of sites
- not gloablly-routed or translated to global IPv6
- is used for secure or hide network

### STP
Switch (ports)
Roles:
- Root Port; The best port to reach the Root Bridge
- Designated Port; Port with the best route to the Root Bridge on a link
- Non.Designated Port; All other ports that are on a blocking state

States:
- Disabled; A port that is shutdown
- Blocking; A port that is blocking traffic
- Listening; Not forwarding traffic and not learning MAC addresses
- Learning; Not forwarding traggic but leraning MAC addresses
- Forwarding; Sending and receiving traffic like normal

Bsp.:
![STP](/Cisco/Labs/Bilder/STP.png)

## Labs
-  [Implement a Subnetted IPv6 Addressing](#implement-a-subnetted-ipv6-addressing)


## Implement a Subnetted IPv6 Addressing
