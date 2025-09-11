### Logging In:
To log in to Proxmox you'll need your IM-ID and a computer connected to the IM network. If you are using a laptop, make sure you are connected to the IM-Nett wifi.

In your web browser open https://172.20.0.10:8006/, this is the control panel for Proxmox, I suggest bookmarking this web address as you will use it a lot. Now login using your IM-ID username and password. If you have forgotten your password please look at **xxinsert herexx** or speak to a teacher if that doesnt work.

### Creating your Private Network:
Before we get started download and install the OpenConnect client here: [Download OpenConnect VPN for Windows](https://gui.openconnect-vpn.net/download/)

Just like any other network, you need a router to do NAT. For this we have the openwrt-vpn template which you will copy. 

When logging in you will see the following in the corner of your screen:
![[Screenshot 2025-08-06 at 10.23.33.png]]
1. Right click on the "102 (openwrt-vpn) template" and click clone.
2. You will be given a random and unique VM ID, write this down, as this will now be the ID for your private network. Fill out the rest of the options like below, and make sure you assign it to your resource pool.![[Screenshot 2025-08-06 at 10.25.55.png]]
3. Click Clone
4. Click on the new VM on the side bar (you can remove the "template" tag from the VM if you'd like)
5. Goto Hardware and find "Network Device (net1)" and double click on it.
6. Under "VLAN Tag" change it to the VM ID you were told to write down earlier in the guide.
7. Start the VM, then click on the "Console" button next to the start button. This will open a console window
8. Click Enter in the Console to activate it
9. Run the command `nano /etc/config/network` and use your arrow keys to scroll down until you find `config interface 'wan'`
10. Find the line `option ipaddr '172.20.0.199'`, replace the last three digits with the VM ID you were told to write down earlier. 
11. Press ctrl + x , press Y, then enter to save the file
12. Run the `reboot` command.
#### Connecting to your Private Network:
1. Open the OpenConnect client that you downloaded earlier, and connect to 172.20.0.xxx:4443 (replace the last digits with your VM ID)
2. When asked for credentials, the username is root and the password is root
3. You should then be connected to your private network!
How does it work?: Basically, when you have the VPN on, you are inside your private network, if you create for example a windows server machine, you will only be able to remote into it when the OpenConnect VPN is connected. This way you have a completely safe and isolated network that you only connect to when it needs to be used. 