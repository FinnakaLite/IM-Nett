### Logging In:
To log in to Proxmox you'll need your IM-ID and a computer connected to the IM network. If you are using a laptop, make sure you are connected to the IM-Nett wifi.

In your web browser open https://172.20.0.10:8006/, this is the control panel for Proxmox, I suggest bookmarking this web address as you will use it a lot. Now login using your IM-ID username and password. If you have forgotten your password please look at **xxinsert herexx** or speak to a teacher if that doesnt work.

### Creating your Private Network:
Before starting please download the WireGuard client here: [Installation - WireGuard](https://www.wireguard.com/install/)

Just like any other network, you need a router to do NAT. For this we have the openwrt-router-wg template which you will copy. 

When logging in you will see the following in the corner of your screen:
![[Screenshot 2025-08-06 at 10.23.33.png]]
1. Right click on the "102 (openwrt-router-wg) template" and click clone.
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
## Creating the VPN server:
#### You need to edit the VPN server in a way that makes it possible for you and only you to VPN into the server.
1. First open the WAN IP address of your router in the browser, in my case 172.20.0.199
2. Log-in with the username and password "root"
3. Go to Network -> Interfaces
4. Find the WireGuard interface and click Edit.![[Pasted image 20251015180831.png]]
5. Under the Peers tab find "Peer 1" and click Edit
6. Click the generate new key pair button ![[Pasted image 20251015181358.png]]
7. Scroll down and click the green Save button
8. Press the Edit button AGAIN, and this time scroll down until you find the "Generate configuration" button
9. Copy the configuration text like so ![[Pasted image 20251015181550.png]]
10. Press the green save button, and then press the "Save and Apply" button at the bottom of the interfaces page.
11. Restart the WireGuard interface before continuing: ![[Pasted image 20251016091332.png]]
### Importing the VPN config:
1. Open the WireGuard application on your system
2. Press "Add Tunnel" and select "From empty file" ![[Pasted image 20251015181907.png]]
3. Highlight everything and paste what you have copied into the text box and click Save:  ![[Pasted image 20251016090942.png]]
4. You can now activate the VPN and connect to your virtual router. If this doesn't work then you need to try restarting your virtual router.

## Finishing up:
Please make sure to change the password for your router, in the routers config page you will have a huge yellow banner on top reminding you to do this. Please comply. 