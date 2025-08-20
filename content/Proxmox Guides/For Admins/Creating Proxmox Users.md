### Active Directory:
Before you do anything in proxmox you simply need to add the user to active directory. Login to the IM-ID server at IM-ID.local, then create a user within the 2IT OU, & being a member of the 2IT-Students group.

### Activation in Proxmox:
Login to Proxmox with a admin user, and goto Datacenter > Permissions > Realms > Realm Sync Jobs. 

Select the IM-ID sync job, and click Run Now.

### Permissions Setup:
Now you need to make sure that the new users flooding in from Active Directory have the correct permissions.

With a Proxmox admin user, goto proxmox-server > Shell. 

Run the command `Python3 /root/scripts/create-userpools-fromAD.py`

By design this script will take a while to run, please wait until its done, and then all the users should be setup!