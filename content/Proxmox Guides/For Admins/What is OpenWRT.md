Each student will create a clone of the OpenWRT Router image. This router will act as a Virtual router, providing NAT and a firewall to the students virtual network. 

To be able to login to the network, and have their regular computer act like any other member of the virtual network they will need to login to the router using a VPN, you can think of the router as a gateway to the private network as its behind NAT. I have preinstalled a VPN server on the OpenWRT image. All you need to do, is find the IP address of the OpenWRT server, and then use the OpenConnect VPN client to connect to it with the credentials below. After this the student will also be able to access the routers configuration page at 192.168.1.1 with the default password (none).

VPN Connection OpenWRT: 
root/root
Port: 4443
Client: OpenConnect VPN Client

Setup process for OpenWRT Router:
1. Clone Template into your own Pool
2. Goto Hardware > Network Device (net1) > Edit, and replace the "VLAN Tag" with your Proxmox ID number and press OK.
3. Start VM
4. Goto Console > xterm.js
5. Enter terminal and run `nano /etc/config/network`
6. Scroll down and find `config interface 'wan'`
7. Under `option ipaddr '172.20.0.199'`, replace the last two digits with your Proxmox ID Number. For example if you are student 40 then replace the ip with 172.20.0.140
8. Press ctrl + x , press Y, then enter to save the file
9. Run the reboot command
10. You can now VPN into your OpenWRT server, use the OpenConnect client and connect to 172.20.0.XX:4443.