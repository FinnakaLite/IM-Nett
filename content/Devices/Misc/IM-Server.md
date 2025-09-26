#### Location: #Fordelingskap 
>Model: Dell PowerEdge R740xd

#### Description:
This server runs proxmox, and runs all the associated VMS on the IM network. The Proxmox control panel can be accessed through the web browser by going to 172.20.0.10:8006

In the event of a catastrophic failure, the server control panel can be accessed through iDRAC through the IP 172.16.1.10 on the management network. For the username and password for this interface, check the handoff document.

#### Network ports:

**eno1 SFP+:** Connected to [[SW-02]] via 10G Fibre
**eno2 SFP+:** Not in use
**eno3 Ethernet 1G:** Not in use
**eno4 Ethernet 1G:** Not in use

**iDRAC Port:** Connected to [[SW-07]] on Management network.