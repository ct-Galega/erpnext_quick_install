# Unattended Install Script for Fraqppe / ERPNext
Unattended script for ERPNext installation (Supports Versions 13, 14, 15 and develop).

This is a no-interactive script for installing ERPNext Versions 13, 14, 15 and develop. You can set up either development or production with very minimal interaction.

# How To:
To use this script, follow these steps:

# Before Installation

Make sure you install the latest package versions by updating system packages if you are running this script on a fresh Ubuntu machine.

```
sudo apt update && sudo apt -y upgrade
```
and then reboot your machine 

# Important!
Do not run this script as root as it will fail when setting up the site. If your VPS default user is root, create a non-root user by following these steps:

1. Create a new user (you can change frappeuser to your preferred user name):
```
sudo adduser frappe
Full Name []: frappe
Room Number []:
Work Phone []:
Home Phone []:
Other []:
Is the information correct? [Y]
```
2. Add the user to sudoers:
```
sudo usermod -aG sudo frappe
```
3. Switch to created user:
```
su frappe
```
4. Ensure you're on created user's home directory:
```
cd /home/frappe
```
5. Continue with the next steps below.

# Installation:

1. Clone the Repo:
```
git clone https://github.com/ct-Galega/frappe_quick_install.git
```
2. navigate to the folder:
```
cd frappe_quick_install
```
3. Make the script executable
```
chmod +x frappe_install.sh
```
4. Run the script:
```
source frappe_install.sh
```
# Compatibility

Ubuntu 24.04 LTS,
Ubuntu 23.04 LTS,
Ubuntu 22.04 LTS,
Ubuntu 20.04 LTS

Debian 10 (Buster),
Debian 11 (Bulls Eye)
Debian 12 (Bookworm)

# NOTE:

Version 15 Compatibility is set to Ubuntu 22.04 LTS and above and Debian 12 only. Lower versions are not supported for version 15 installation due to dependency issues.
Visit https://github.com/gavindsouza/awesome-frappe to learn about other apps you can install.

If you encounter spawn error on socketio when running bench restart, run the following commands:

```
bench setup socketio
bench setup supervisor
bench setup redis
sudo supervisorctl reload
```
This will fix the spawn error and all services will restart successfully.
