BEWARE THAT YOU SHOULD AT LEAST HAVE CONSOLE ACCESS TO YOUR SYSTEM BEFORE EXECUTING THE INSTRUCTIONS BELOW!!!

## Installing a firewall

To stay safe, it is mandatory to install a firewall. Here we are going to use ufw firewall.

Install ufw with the following command

```
sudo apt install ufw

sudo ufw status
```

### Configuring the firewall

We will initially set up the firewall that is only accepts ssh incoming sessions. There has to be an exception made in the firewall for each service we configure.

```
sudo ufw allow ssh/tcp
sudo ufw limit ssh/tcp
sudo ufw logging medium
sudo ufw enable
```

After configuring the firewall, you can check it with

```
sudo ufw status
```

Note that you can always disable the firewall with:

```
sudo ufw disable
```

### Adding exceptions for services for example VNC or other client software.

Each new service port has to be added with a command similar like this for VNC emergency login most VPS providers have when you lock yourself out:

```
ufw allow 63035/tcp # vnc port
ufw allow 51472/tcp # pivx masternode port
```
For security reasons, VNC service should be disabled all the time, most VPS hosters have a switch for turning VNC or any other remote service only when needed.


### Removing firewall rules

To remove rules from the firewall use:

```
sudo ufw status numbered
sudo ufw delete 2
```
Finally the install script 


