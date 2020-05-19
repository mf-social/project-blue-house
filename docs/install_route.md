# Deciding your installation route

Understanding which route you will take to create your **Project: Blue House** is important, you can either make your install a single purpose machine or you can use **VMs** to separate out the features and create a nice Homeassistant centred homelab.


## Understanding Virtualisation (and the coloured house nomenclature)

A virtual machine is defined as a computer file, typically called an image, that behaves like an actual computer.  If you had 3 **VMs** running on one physical computer then ran a network scan, you would see 4 computers.  They are, quite literally, a computer within a computer.  They get their own IP address, they have there own (allocated) processing power and memory.

As you install computers on your network, many people name them.  You can come up with any naming scheme you like.  Some people use planets or characters from film franchises.  I like to use random references from sci-fi, for example the computer I used to spin up a proxmox installation procedure so I could take some photos of the screens is called 'The Lifeboat' after the time machine from Timeless.

For the purpose of knowing which machine is which throughout this repo I decided to name the computers/**VMs** in this guide after colours.  So in the guide, a **host** or **VM** with homeassistant on it will be called **blue house**.  If you go the virtualisation route and build a whole homelab you will have a **grey house** (proxmox) on your **host**, and then VMs for **blue house** (home assistant), **red house** (nginx), etc...

You can either name your **host** and **VMs** the same, or simply substitute the coloured house for the name of your 'machine'.


## The HassOS way

The concept of HassOS is to create an 'appliance' that runs homeassistant in a self contained Operating System that you manage entirely via the UI.  If you're planning on running only a **blue house** and have a supported **host**, then this is actually a really good way of doing things, and whilst you can use this repo for reference you should consider using the [official installation instrucions](https://www.home-assistant.io/getting-started/) for homeassistant to acheive this.  If you want more flexibility than HassOS offers, and want more control of your system then you're in the right place.  At the time of writing the decision to deprecate the 'Supervised' install on Linux has been suspended.  This means that you can still 'get the best of both worlds' and have a supervised install with add-ons etc, but that is not what you will get from this repo.  Later in the repo I will list like for like docker containers so that you can manage your own 'add-ons'.  You WILL NOT lose out on any functionality of homeassistant by following **Project: Blue House**, but you may lose some minor conveniences.


## Docker and docker-compose explained

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package.  This means that you do not have to worry about managing dependencies for things that run in docker containers, you just fire them up and they work.

**Project: Blue House** relies on docker-compose to create docker containers for homeassistant and any supporting containers.  If you go the virtualisation route, then we will also be using docker-compose to create a docker stack in the **red house** to configure external access.  Docker-compose is a yaml file that lists the containers you want to run with some configuration options.  The aim of **Project: Blue House** is to provide copy-and-paste examples of containers that will work for 99% of end users without causing any complications.  Simply copy/paste the container configuration in to your docker-compose.yaml, follow any additional instructions (like creating a folder for the container to store its data in, nothing complicated), and press a button.  I'm trying to strike a balance between the slickest experience and the fullest control.


## A single purpose installation

If you choose to dedicate your whole **host** to homeassistant and you are happy that you will not ever want to use it for anything else, you can move straight on to the **blue house** setup and install Debian directly on to the host instead of a VM.  There is no need to add an extra VM just for external access as the nginx/vpn container(s) can be addded to your **blue house's** docker-compose.  There is no need to add the extra layer of proxmox to this setup.

## A Homelab installation

If you have a decent spec **host** (like a NUC) and/or you just don't want to dedicate all that computing to just one thing, even if you're not sure what else you might do with it, then go for the virtualised install.  You will simply end up with your **blue house** on a **VM** on your **host**, rather than directly on it.  As far as the rest of your network (or even the rest of the world!) is concerned your **blue house** is on its own computer regardless.  There is NO DIFFERENCE in the end productt of homeassistant that you will get from either install method.

Of course this is better, because:

 - You'll learn about proxmox and virtualisation along the way
 - Once you've got the bug you'll find you want to host other things at home, and you can add further **VMs** as and when you need to
 - You will earn major geek points
 - As a bonus we'll also set up a **yellow house** with a self-hosted version of [Bitwarden]() so you can securely host your own password manager!


