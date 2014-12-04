vagrant-frab
============

Project to spin up a frab conference system based with vagrant.

Vagrant provides a good environment for developing, testing or debugging [frab](http://frab.github.io/frab/).
It can also provide you an environment to migrate your configuration to newer versions or test new functionalities from feature branches and future versions.
The Vagrant box of frab requires the following:
- VirtualBox 4.2+ http://www.virtualbox.org
- Vagrant 1.5+ http://www.vagrantup.com
- Git http://www.git-scm.com
- *NIX based operating system

*Hint*: If you want to use Microsoft based operating system, please make sure you use Git under cygwin like http://msysgit.github.io.
You will have issues with different line break handling between *NIX and Windows.

By default the virtual machine uses a no-worry-NAT network interface. To give you access to the virtual machine there is some preconfigured port forwarding:
- TCP guest 3000 to your host 3000 for the frab WebUI
- TCP guest 22 to your host 2222 for SSH access you can also just run `vagrant ssh`

Usage
-----
1. Install VirtualBox and Vagrant on your computer
2. Checkout this repository with `git clone https://github.com/indigo423/vagrant-frab.git`
3. Change into vagrant-frab
4. Update cookbook dependencies with `git submodule init` and then `git submodule update --remote`
5. Run `vagrant up` to start the virtual machine
6. Connect in your browser to http://localhost:3000
7. Username is `vagrant` with password `vagrant` you can get root access with `sudo -i`
