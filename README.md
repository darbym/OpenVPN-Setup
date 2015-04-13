OpenVPN-Setup
============

About
-----

Shell script to set up Raspberry Pi (TM) as a VPN server using the OpenVPN software.
Includes templates of the necessary configuration files for easy editing, as well as
a script for easily generating client .ovpn profiles after setting up the server.

This script has been tested on the Raspbian distribution on the Model B+, but should
also work in Raspbian on the Pi 2 Model B.

General Usage
-------------

You can download the OpenVPN setup script directly from the terminal or over SSH using
Git. If you don't already have it, update your APT repositories and install it:

```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
```

Then download the latest setup script with:

```shell
cd
git clone --depth=1 git://github.com/StarshipEngineer/OpenVPN-Setup.git
```

Execute the script with:

```shell
cd OpenVPN-Setup
chmod +x openvpnsetup.sh
sudo ./openvpnsetup.sh
```

The script will first update your APT repositories, upgrade packages, and install OpenVPN,
which will take some time. It will then prompt you for input in several identification fields as
it generates your certificate authority and server certificate; you can ignore most of these and
hit 'enter' to skip them if you don't care to fill them out. However, you will twice be asked to
confirm by pressing 'y', so do this when prompted. After this, the script will take a few minutes
to build the server's Diffie-Hellman key exchange, so be patient. When the script informs you
that it has finished configuring OpenVPN, reboot the system and the VPN server-side setup will
be complete!
