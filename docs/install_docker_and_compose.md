# Install docker and docker-compose

This is part 3 of 3 of creating your base Debain installation

## Install the dependencies

Login to your Debian machine by ssh and run the following commands in the terminal.  (You can copy and paste them, remember that pasting in ssh is the right mouse click)

```bash
sudo apt-get update

sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

## Install the repository

```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
    
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
```
   
## Install the Docker engine   

```bash
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io
``` 

## Install Docker-compose

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

## Add your user to the Docker group

```bash
sudo usermod -aG docker user
```

Replacing 'user' with your username
 
Then logout and login for the changes to your user group to take effect

Your Base system is now ready to create your docker stack.
