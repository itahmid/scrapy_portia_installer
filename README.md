# scrapy_portia_installer
--------------------------

Bash script to automate remote deployment of Portia Web Crawler. Tested on Ubuntu Server 14.04 / 16.04. 
Testing and using web scrapers/crawlers can be done easily from a remote VPS and keep home ip address from any initial jeopardy that ensues from learning how to scrape without overwhelming the host. 
Easily ssh and setup automation allowing access to a gui web frontend and dns routing to one of your domains.

EndUser: 

"This script has only been tested to work on Ubuntu Server 14.04 / 16.04 - 64 bit"

So, here's the process...

Step 1.
Check your VPS / VM IP address with username and password...

Login to your server

Linux users open terminal and type

    ssh root@(your_vps_ip_address) without the () Parentheses


-------------------------------------------------------------------
The authenticity of host '.......... ' can't be established.
ECDSA key fingerprint is ......................
Are you sure you want to continue connecting (yes/no)? 
-------------------------------------------------------------------

    Type YES and press enter.. this is normal for first connect..
    Enter your password
    Enter it again
    Put in a new password (remember your password)

Step 2. If you made it this far good job, now let's setup a user so we don't use root for everything..
copy / paste the following one line at a time into the terminal and press enter..

    Please note: in order for this script to work you must use the username portia you can change the password to whatever you like
        useradd -d /home/portia -s /bin/bash -m portia 
        passwd portia 
    
(or make one up.)

    enter a password for the user portia (remember your password)

Copy paste these commands one line at a time.

    echo "portia ALL=(ALL) ALL" >> /etc/sudoers
    sudo aptitude install git
    exit

Then reconnect but this time using the name "portia" instead of root.

    ssh portia@(ip.address.of.vps)

and type the password you remembered


Step 3. You've successfully setup a user named portia with a password and you are logged in as that user, you know this because it says

    portia@(hostname_you_used_when_setting_up_the_droplet):~# 

We are going to setup the script...
copy / paste these commands..

    nano install_portia.sh

copy / paste this script of git clone it from this repo found at this link:

    https://github.com/tytek2012/Portia_Installer_Script.git
    
After pasting into nano on the vps you can save it by:

    hit control + o then hit enter to save 
    hit control + x to exit

verify you copied the script by typing

    ls
    
Make the script executable then run it.

    chmod +x install_portia.sh
    sudo ./install_portia.sh


hit ENTER or press Y when asked if you want to update etc... This is pretty fast so just chill or grab a brewsky, I've been messing with this to pull jobs off local jobs boards and classifieds. If you build an interesting scraper please consider sharing it.
