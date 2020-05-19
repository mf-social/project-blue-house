## Why does this repo exist?

Once upon a time I had a repo containing my Homeassistant configuration.  It was a big hit with people learning about homeassistant.  But it became difficult to manage as more and more parts of the configuration drifted out of files written in yaml.  I've been helping out in the Homeassistant community as much as I can, but I saw a need for a resource to help people build a stable homeassistant installation that is outide of 'the norm'.

Predicting where Homeassistant is heading is tricky as they don't have any kind of proper public roadmap, but [this thread](https://community.home-assistant.io/t/on-hold-deprecating-home-assistant-supervised-on-generic-linux/194310) on the community forum showed us that sometimes that direction will be incompatible with large numbers of people.  It also raises another interesting 'elephant in the room' that nobody else seems to be discussing: The homeassistant 'supervisor' is built and maintained by just one person!  Now, I have every respect for Pascal, but if he simply 'gives up' tomorrow (or gets ill, or has an accident...), then homeassistant as most people know it will be dead, and everyone will have to rely on a 'core' install.  Add-ons will be no more, you'll have to add the docker containers yourself etc.

Also, even if we assume that the 'supervisor' continues to be written long in to the future, it is clear that the direction homeassistant wants to take is that the 'supervisor' should only be available as a HassOS install on a dedicated computer.  They do (currently) offer VM images of this, there is currently a lot of uncertainty and to get lots of things to work you have to follow third party resources and there is no 'official' path.  I decided to create **Project: Blue House** - a specific list of unofficial instructions that anyone can refer to to get a homeassistant install that is definitely always going to be supported as it is based on core, and also to have some fun learning about homelabs and self-hosting along the way.


## What is it for?

The idea being that whilst this is an 'unofficial' resource, it can be a go to for people to get up and running with core in an easy-to-follow fashion, looking out for security and configuration options along the way.  In the event you have to ask for help with your configuration and someone says "what's your install method?" you can say "I followed the **Project: Blue House** instructions".

This will be the case regardless of whether you use this repo to set up a single computer just with homeassistant, or if you use this repo to set up a homelab with homeassistant as a virtual machine - all of which is covered in this repo.


## No guarantees

My plan with this repo is that if you follow it you will get a working install of homeassistant core that is 'future proof', but like many things there are no guarantees this will always be the case.  Espescially in the early days there may be some instructions that are incorrect, or if Homeassistant changes something major I may forget to update the instructions.  Hopefully this will become a wiki so visitors here can fix inaccuracies quickly, but if you want 'guarantees' you need to go with whatever the Homeassistant 'approved' methods are, although I wouldn't be writing this repo if Homeassistant offered guarantees :)


## Terms you will see

This guide assumes a few things.  If the assumptions aren't quite right for your personal circumstances you can probably still use it with a few minor adjustments.  I've tried to make it obvious what 'devices' I'm talking about in each section by using certain terms in bold, that you could potentially interchange to suit your use case.

 - **Laptop** - This is the computer that you use everyday, that you're going to use to remotely configure things, that you're going to use to view websites and check services etc.  The software recomendations for **laptop** assume that it is running windows 10 at this time, but there are MAC/Linux equivelants and I may expand the instructions later to cater for these variants too.
 - **Mobile** - Your smart phone, your 'cell phone', the thing that rings when you're in trouble with your mum.
 - **Host** - This is the computer you will be turning in to your smart home hub / home lab.
 - **VM** - A virtual machine - this is like a computer within a computer - more on this later.
 - \[Colour\] **house** - This is the names that are given to individual machines on the network.  More on the nomenclature later, but if you follow this guide all the way to the end and set up a Proxmox **host** with several VM's, you'll have a **grey house** (the **host** itself), a **blue house** (a **VM** running homeassistant - this is why the repo is called **Project: Blue House**!), a **red house** (a **VM** managing external access) etc.


## Software you'll need before you start

On your **laptop** you will need to download:

 - Software for creating bootable USB images - such as [BalenaEtcher](https://www.balena.io/etcher/)
 - Software for managing 2 Factor Authentication - such as [Authy](https://authy.com/download/)
 - Software for dealing with SSH/SCP - such as [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
 
 On your **mobile** you will need:
 
 - Software for scanning your network - such as [Fing](https://www.fing.com/products/fing-app)
 - Software for managing 2 factor Authentication - such as [Authy](https://authy.com/download/) (which then syncs with the desktop app)
 
 It doesn't hurt to have Authy (or equivelant) installed elsewhere too, just to be certain that you will never be locked out of your accounts.


Let's get started!
