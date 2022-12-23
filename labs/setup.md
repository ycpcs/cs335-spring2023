---
layout: default
course_number: CS335
title: Lab Setup
---

Labs
-----------------------------------
- Hands-on [Labs](https://seedsecuritylabs.org/Labs_20.04/) for Security Education.

Lab Setup
-----------------------------------
- [Oracle® VM VirtualBox](https://www.virtualbox.org/wiki/Downloads) is a general-purpose full virtualizer for x86 hardware, targeted at server, desktop and embedded use. User Manual can be found [here](https://www.virtualbox.org/manual/).

- Pre-built Virtual Machine [SEED Ubuntu 20.04 VM](https://drive.google.com/file/d/138fqx0F8bThLm9ka8cnuxmrD6irtz_4m/view?usp=sharing).
  - Primary Account:
    - User ID: ```seed```
    - Password: ```dees```

Manual
-----------------------------------
- Follow [Run SEED VM on VirtualBox](vm-setup.html) to load the image into VirtualBox. This includes the account and password information, list of software and servers installed, and configuration.

Troubleshooting
-----------------------------------
- The first thing you should do after creating your SEED VM is to update your packages; to do that, run the following two commands from your VM:
  - ```sudo apt update``` - this commands downloads package information from all configured sources
  - ```sudo apt upgrade``` - will upgrade all installed packages to their latest versions
- If the guest screen is too small:
  - With VirtualBox 6.0.0 you need to go to the VirtualBox Preferences » Display » Scale Factor = 200%.
- When you clone your VM's, make sure the MAC Address Policy is set to _Generate new MAC addresses for all network adapters_.
