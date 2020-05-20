# This page explains installing debian before logging in for the first time

This is the first part (1 of 3) of creating your base system.  After this we will secure the logins and install docker and docker-compose.

## Installing

Starting at the Installalation menu, graphical install should already be selected.  Press Enter.

![install debian 1](../images/install_debian_1.png)

Choose your language

![install debian 2](../images/install_debian_2.png)

...and location

![install debian 3](../images/install_debian_3.png)

... and keyboard layout

![install debian 4](../images/install_debian_4.png)

Type the name for this machine (eg bluehouse, redhouse, etc)

![install debian 5](../images/install_debian_5.png)

Leave the domain name blank

![install debian 6](../images/install_debian_6.png)

Set a password for the root user - do not worry about overcomplicating this one, we will be disabling root logins in the next section.

![install debian 7](../images/install_debian_7.png)

Type a name for you user, this is the name that you wil use to login to your system after we have completely set it up.  Use your own name, or whatever you want.  Then set a password for you user - this should be fairy strong, but also relatively easy to remember as you will need to type it whenever we use the 'sudo' command.

![install debian 8](../images/install_debian_8.png)

Leave the partition disks selection on "Guided - use entire disk" and press Continue.

![install debian 9](../images/install_debian_9.png)

If you have more than one hard disk, you can choose which one to install Debian on here.

![install debian 10](../images/install_debian_10.png)

Leave this setting as 'All files in one partition'

![install debian 11](../images/install_debian_11.png)

Finish partitioning and write changes to disks.

![install debian 12](../images/install_debian_12.png)

Press 'Yes' to confirm.

![install debian 13](../images/install_debian_13.png)

After a short while you will be asked if you want to scan another disk, we don't so press Continue.

![install debian 14](../images/install_debian_14.png)

Check that your correct country is selected.

![install debian 15](../images/install_debian_15.png)

...and choose a mirror to download packages from (you can leave this on the default one the installer selected if you don't have a preference)

![install debian 16](../images/install_debian_16.png)

Leave the proxy configuration blank

![install debian 17](../images/install_debian_17.png)

Decide whether or not you wish to participate in the anonymous package survey, press continue

![install debian 18](../images/install_debian_18.png)

Select SSH server and Standard System Utilities only

![install debian 19](../images/install_debian_19.png)

Yes to install the bootloader

![install debian 20](../images/install_debian_20.png)

Select the hard drive you installed to.

![install debian 21](../images/install_debian_21.png)

Installation is complete and your machine is ready to reboot.

 - If this is a 'single purpose install' remove the USB stick from the **host** and press continue to reboot.  As it reboots, catch it and go back in to your **host's** BIOS. Disable boot from USB, and move the UEFI entry for Debian to the primary boot device. Save and exit

 - If this is a **VM** just press continue and watch your VM reboot in your console window.

You can now continue to the 'Securing logins page'
