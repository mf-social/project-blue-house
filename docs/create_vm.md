# Creating a Debian VM in proxmox

This page is to explain the process of generating the VM and getting to the point of installing and configuring Debian


## Get Debian

**Project: Blue House** uses Debian because it has good package management and is easy to set up as a headless server. It is a tried and tested method.

 - If this is your first **VM** Download the latest minimal Debian ISO from [here](https://www.debian.org/distrib/netinst) - get the AMD64 version.
 - If this is not your first **VM** you only need to check if the one you already have is up-to-date.
 
 
## Put the Debian ISO on to your Proxmox machine
 
Note: If this is not your first **VM** and you are happy you have the latest version already on your Proxmox you do not need to do this step again.

 - Navigate to your Proxmox webUI in your browser.
 - Expand the entry of your **grey house** node in the tree on the left (under 'Datacentre')
 - Press on the 'local' storage entry in the tree
 - Press on 'Content' in the menu
 - Press 'Upload' in the top bar
 - Press 'Select file'
 - Upload your Debian ISO
 
~~~ Screenshot ~~~
 

# Create a new VM

