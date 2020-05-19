# Security

Understanding some of the many security considerations before we start actually building anything, let alone exposing things to the internet is really important.


## Setting up Authy and getting acquainted with 2FA

2FA is short for Two Factor Authentication.  It is decribed as "an extra layer of security used to make sure that people trying to gain access to an online account are who they say they are. First, a user will enter their username and a password. Then, instead of immediately gaining access, they will be required to provide another piece of information. This second factor could come from one of the following categories:

 - Something you know: This could be a personal identification number (PIN), a password, answers to “secret questions” or a specific keystroke pattern
 - Something you have: Typically, a user would have something in their possession, like a credit card, a smartphone, or a small hardware token
 - Something you are: This category is a little more advanced, and might include biometric pattern of a fingerprint, an iris scan, or a voice print

With 2FA, a potential compromise of just one of these factors won’t unlock the account. So, even if your password is stolen or your phone is lost, the chances of a someone else having your second-factor information is highly unlikely. Looking at it from another angle, if a consumer uses 2FA correctly, websites and apps can be more confident of the user’s identity, and unlock the account."

Source: [Authy, what is 2FA?](https://authy.com/what-is-2fa/)

The Authy app simply scans a QR code on a site/app for which you want to set up 2FA and then every 30 seconds it produces a code for that service.  When you login to a service it will ask you for a code.  Because both parties know what the QR code was that generates the codes, both know what the code should be every 30 seconds, but nobody else does.

Starting with your **mobile**, open Authy for the first time and input your email address and phone number.  When you then add these details to the desktop app the two will be synchronised together, meaning that if you add a 2FA key on your phone, you will be able to get login codes for the website on your **laptop** as well.  I personally also have Authy running on a tablet that I hardly ever use and always keep at home, so if my laptop and phone both get broken, stolen, whatever, I still have access.

Now have a play with it.  Set up 2FA on github and the Homeassistant forums, make sure you can generate codes on your **laptop** as well.  How many other services do you use that allow 2FA?  Now you're starting to think about your security online!  Keep that thought in your mind when building your **Project: Blue House**, espescially when we're setting up access from the internet.


## Understanding Strong Passwords

Passwords are the digital keys to our networks of friends, our work colleagues, and even our banking and payment services. We want to keep our passwords private to protect our personal lives, and that includes our financial information. While some cybercriminals may want to hack into our social networking or email accounts, most want the financial gain that hacking bank accounts can bring.

The most important two passwords are those for your email and social network accounts. If someone gains access to your email account, they could use the "forgot your password?" link on other websites you use, like online shopping or banking sites. If a hacker gets into your social network, they have the ability to scam your friends by sending out links to dangerous websites or posting fraudulent messages asking for money. The bottom line is that a good password is all that may stand between you and a cybercriminal.

A strong password is one that's easy for you to remember but difficult for others to guess. Let's take a look at some of the most important things to consider when creating a password.

 - Never use personal information such as your name, birthday, user name, or email address. This type of information is often publicly available, which makes it easier for someone to guess your password.
 - Use a longer password. Your password should be at least six characters long, although for extra security it should be even longer.
 - Don't use the same password for each account. If someone discovers your password for one account, all of your other accounts will be vulnerable.
 - Try to include numbers, symbols, and both uppercase and lowercase letters.
 - Avoid using words that can be found in the dictionary. For example, swimming1 would be a weak password.
 - Random passwords are the strongest. If you're having trouble creating one, you can use a password generator instead.
 
Source: [GCF Global - creating string passwords](https://edu.gcfglobal.org/en/internetsafety/creating-strong-passwords/1/)
 
 
## Understanding shared keys
 
Shared keys are a matching set of cryptographic keys which can be used for authentication. Each set contains a public and a private key. The public key can be shared freely without concern, while the private key must not be exposed to anyone.  These keys can then be used to encrypt and decrypt data, or used to authenticate the sender of a message.  In the case of a homelab the most common place for shared keys is in SSH.  When using Putty we will create a key on our **laptop** that we can use to authenticate when we log in to the other computers we want to speak to, meaning that only you have access.  There are some similarities with 2FA, where Authy and a website pre-share the QR code, and without the QR code nobody can generate the 6 digit numer and login.
 
 
## Understanding port forwarding
 
Port forwarding allows remote computers (for example, computers on the Internet) to connect to a specific computer or service within a private local-area network (LAN).[3]

In a typical residential network, nodes obtain Internet access through a DSL or cable modem connected to a router or network address translator (NAT/NAPT). Hosts on the private network are connected to an Ethernet switch or communicate via a wireless LAN. The NAT device's external interface is configured with a public IP address. The computers behind the router, on the other hand, are invisible to hosts on the Internet as they each communicate only with a private IP address.

When configuring port forwarding, the network administrator sets aside one port number on the gateway for the exclusive use of communicating with a service in the private network, located on a specific host. External hosts must know this port number and the address of the gateway to communicate with the network-internal service. Often, the port numbers of well-known Internet services, such as port number 80 for web services (HTTP), are used in port forwarding, so that common Internet services may be implemented on hosts within private networks

Source: [Wikipedia - Port forwarding](https://en.wikipedia.org/wiki/Port_forwarding)

## Understanding root and sudo

root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user and the superuser.

Source: [Linfo - root definition](http://www.linfo.org/root.html)

sudo is a program for Unix-like computer operating systems that allows users to run programs with the security privileges of another user, by default the superuser.[6] It originally stood for "superuser do"[7] as the older versions of sudo were designed to run commands only as the superuser. However, the later versions added support for running commands not only as the superuser but also as other (restricted) users, and thus it is also commonly expanded as "substitute user do".[8][9] Although the latter case reflects its current functionality more accurately, sudo is still often called "superuser do" since it is so often used for administrative tasks.

Source: [Wikipedia - sudo](https://en.wikipedia.org/wiki/Sudo)


## Understanding VLANs

A virtual local area network (VLAN) is a logical group of workstations, servers and network devices that appear to be on the same LAN despite their geographical distribution. A VLAN allows a network of computers and users to communicate in a simulated environment as if they exist in a single LAN and are sharing a single broadcast and multicast domain. VLANs are implemented to achieve scalability, security and ease of network management and can quickly adapt to changes in network requirements and relocation of workstations and server nodes.

Higher-end switches allow the functionality and implementation of VLANs. The purpose of implementing a VLAN is to improve the performance of a network or apply appropriate security features.

Setting up VLANs are currently out of the scope of **Project: Blue House**, but they work by seperating network traffic in your home.  They're like the VMs of networking.  I'm hoping to add VLAN configuration to the **Project: Blue House** repo in the future, but you may wish to investigate VLANs for extra security.





