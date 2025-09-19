#### Location (when not in use): #2IT1 
>Model: 
>1. TP-Link 8-port POE Switch
>2. HP Prodesk 405 g4 mini

#### What is it?:


#### Interfaces:
The Ethernet port from the ProDesk, plugs into port 8 on the switch. While WAN is plugged into port 7.

**Switch port overview:**
1. LAN port w/POE
2. LAN port w/POE
3. LAN port w/POE
4. LAN port w/POE
5. LAN port
6. LAN port
7. WAN port (plug the upstream internet connection in here!)
8. Router port (only plug the ProDesk in here)

VLANS: WAN is vlan 1 while LAN is vlan 101. On the routers interface, WAN is the default port


#### How to use:
I have designed the travel router to be as easy as possible to use. Find a ethernet port thats open on any network, make sure that it has DHCP. Plug the router into this port, and plug your devices (or a switch) into the LAN port. After booting up the travel router will act like any other router and provide DHCP addresses on the LAN interface. BUT when traffic is directed to one of the IM-Nett Subnetts, the traffic will be routed through tailscale. When using normal internet services, tailscale will not be used. 
#### Important things to Note:
The network you are plugging into HAS to support UDP and have as few restrictions as possible. If you are on a heavily restrictive network, tailscale will fall back to DERP mode. This mode is VERY slow, and comes with a fair share of lag spikes, in addition this mode puts a LOT of strain on the tailscale servers (who provide this service for free) so theres is a chance that it will get you banned from tailscale.

#### Who's account is it on:
Currently the router and server are authenticated through one of Finn's google accounts. The google account in use is lite****bud@gmail.com In the future someone else will have to make their own tailscale account, and set it up themselves. 

### Login Info
Passwords for the router are documented elsewhere for safety. The username and password to login to the Switch's config are: admin/tplink