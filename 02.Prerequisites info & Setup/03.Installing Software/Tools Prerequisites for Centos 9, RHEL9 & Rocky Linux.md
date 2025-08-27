## Tools Prerequisites for Centos 9, RHEL9 & Rocky Linux


## Installing Virtualbox
Open Terminal and execute below commands

- ` sudo yum update `
- ` sudo yum install patch gcc kernel-headers kernel-devel make perl wget -y `
- ` sudo reboot `


Login, open terminal and execute below commands

- ` sudo wget http://download.virtualbox.org/virtualbox/rpm/el/virtualbox.repo -P /etc/yum.repos.d `
- ` sudo yum install VirtualBox-7.1 -y `


## Installing Vagrant
Open Terminal and execute below commands

- ` sudo dnf update -y `
- ` sudo dnf config-manager --add-repo=https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo `
- ` sudo dnf install vagrant -y `


## Install VScode
Open Terminal and execute below commands

- ` sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc `
 
- ` echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" | sudo tee /etc/yum.repos.d/vscode.repo > /dev/null `
 
- ` dnf check-update `
 
- ` sudo dnf install code -y `


## Install git
Open Terminal and execute below commands

 - ` dnf install git -y `



## Install JDK & Maven
Open Terminal and execute below commands

- ` dnf install java-17-openjdk java-17-openjdk-devel -y `
- ` dnf install maven-openjdk17 -y `




