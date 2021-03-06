# Vagrant

* Website: [http://vagrantup.com](http://vagrantup.com)
* Source: [https://github.com/mitchellh/vagrant](https://github.com/mitchellh/vagrant)
* IRC: `#vagrant` on Freenode
* Mailing list: [Google Groups](http://groups.google.com/group/vagrant-up)

Vagrant is a tool for building and distributing virtualized development environments.

By providing automated creation and provisioning of virtual machines using [Oracle’s VirtualBox](http://www.virtualbox.org),
Vagrant provides the tools to create and configure lightweight, reproducible, and portable
virtual environments. For more information, see the part of the getting started guide
on “[Why Vagrant?](http://vagrantup.com/docs/getting-started/why.html)”

## Quick Start

First, make sure your development machine has [VirtualBox](http://www.virtualbox.org) installed. 
After this, [download the appropriate Vagrant package for your OS](http://downloads.vagrantup.com) and install that. If you're not on Mac OS X or Windows, you'll need
to add `/opt/vagrant/bin` to your `PATH`. After this, you're ready to go!  Here are some common install steps these may need to be altered for your environment.
## Debian/Ubuntu
    apt-get install virtualbox vagrant
or 

    wget http://files.vagrantup.com/packages/eb590aa3d936ac71cbf9c64cf207f148ddfc000a/vagrant_1.0.3_x86_64.deb
    wget http://download.virtualbox.org/virtualbox/4.1.18/virtualbox-4.1_4.1.18-78361~Ubuntu~precise_amd64.deb
    dkpg -i virtualbox-4.1_4.1.18-78361~Ubuntu~precise_amd64.deb
    dpkg -i vagrant_1.0.3_x86_64.deb
## CentOS/Redhat
    wget http://download.virtualbox.org/virtualbox/rpm/el/virtualbox.repo -O /etc/yum.repos.d/virtualbox.repo
    yum install unzip VirtualBox-4.1 make automake gcc gcc-c++ kernel-devel -y
    export KERN_DIR=/usr/src/kernels/2.6.32-279.1.1.el6.x86_64
    /etc/init.d/vboxdrv setup
    wget http://files.vagrantup.com/packages/eb590aa3d936ac71cbf9c64cf207f148ddfc000a/vagrant_1.0.3_x86_64.rpm
    rpm -ivh vagrant_1.0.3_x86_64.rpm
## Mac OS X with [Homebrew](http://mxcl.github.com/homebrew/)
    LATEST_VBOX=$(curl http://download.virtualbox.org/virtualbox/LATEST.TXT)
    VBOX_FILE=$(curl -s http://download.virtualbox.org/virtualbox/${LATEST_VBOX}/ | grep -o -P 'VirtualBox-4.2.8-[0-9]+-OSX.dmg' index.html | head -n 1)
    wget http://download.virtualbox.org/virtualbox/${LATEST_VBOX}/${VBOX_FILE}
    brew install ruby
    sudo gem install vagrant

To build this vagrant cluster:

    git clone git://github.com/justhamade/vagrant-tutorial.git
    cd vagrant-tutorial/web-cluster
    vagrant up

Note: The above `vagrant up` command will also trigger Vagrant to download the
`centos56_64` box via the specified URL. Vagrant only does this if it detects that
the box doesn't already exist on your system.

Updated from demo of [S. Zachariah Sprackett](https://github.com/zsprackett/) found here [http://devops.me/2011/10/05/vagrant/](http://devops.me/2011/10/05/vagrant/)
