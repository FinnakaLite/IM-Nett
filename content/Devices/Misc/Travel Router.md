#### Location (when not in use): #2IT1 
>Model: Unifi Security Gateway

#### What is it?:
The "Travel Router" is a Unifi Security Gateway that is flashed with custom OpenWRT firmware. It allows for connection to the IM-Nett no matter where the router is. It uses Tailscale to provide a PTP link to the IM-Server. 

#### Interfaces:
WAN (Port: WAN1): DHCP Client (plug it into any DHCP network)
LAN (Port: LAN1 & LAN2): 172.20.24.1/23 - Has a DHCP Server on this interface

#### How to use:
I have designed the travel router to be as easy as possible to use. Find a ethernet port thats open on any network, make sure that it has DHCP. Plug the router into this port, and plug your devices (or a switch) into the LAN port. After booting up the travel router will act like any other router and provide DHCP addresses on the LAN interface. BUT when traffic is directed to one of the IM-Nett Subnetts, the traffic will be routed through tailscale. When using normal internet services, tailscale will not be used. 

#### Important things to Note:
The network you are plugging into HAS to support UDP and have as few restrictions as possible. If you are on a heavily restrictive network, tailscale will fall back to DERP mode. This mode is VERY slow, and comes with a fair share of lag spikes, in addition this mode puts a LOT of strain on the tailscale servers (who provide this service for free) so theres is a chance that it will get you banned from tailscale.


#### Who's account is it on:
Currently the router and server are both logged in on Finn's Chamedia account. In the future someone else will have to make their own tailscale account, and set it up themselves. 