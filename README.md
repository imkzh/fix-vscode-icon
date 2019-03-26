# Fix vscode icon
Fix vscode icon for Debain-like systems.

Vscode uses "code" as its name for desktop icon, and it is a "too-general" name for most icon packages(like numix-circle). 
This package simply add a post installation trigger for "code.desktop" located at "/usr/share/applications", to automatically 
change the icon name to "vscode" every time the file is updated (which means this package installs no file to your system, 
but a dpkg trigger). 

## Install

Use prebuilt dpkg package: [download](https://github.com/imkzh/fix-vscode-icon/releases/tag/1.3.2-1) the `vscode-icon-fix.deb` and:

    sudo dpkg -i vscode-icon-fix.deb

or build your own .deb:

    git clone https://github.com/imkzh/fix-vscode-icon
    cd fix-vscode-icon
    dpkg -b ./vscode-icon-fix
    sudo dpkg -i ./vscode-icon-fix.deb
 
## Unisntall

to uninstall this package:
    
    sudo apt purge vscode-icon-fix
    
The changes this script made is not reverted after purge.
To revert the changes:

    git clone https://github.com/imkzh/fix-vscode-icon
    cd fix-vscode-icon
    sudo vscode-icon-fix/DEBIAN/postinst revert


