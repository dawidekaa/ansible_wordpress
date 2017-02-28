# ansible_wordpress

This playbook allows to install clean version of Ubuntu Server 16.04 OS with Wordpress and other depedencies needed to run server with www website.

If you want to use that playbook, you need:

- Oracle Virtualbox - software, which gives an opportunity to create and run virtual machines on your PC and use another OS in window of Virtualbox.

Install commands for Linux:

$ sudo apt-get install virtualbox-5.1
$ sudo apt-get install dkms

- Vagrant - tool to automation of make and configuration of virtual environments (virtual machines) with use of VirtualBox, thanks to one file we can set up a virtual machine with specified OS, configure network connections, install required packets, configure services or set sharing directory with hosts.

Install commands for Linux:

$ sudo apt-get install vagrant

- Ansible - advanced platform which automate IT processes. Automation using Ansible can solve everyday problems associated with the administration of IT, due to the extent of infrastructure, the need for scalability, complex processes associated with the installation and configuration of your environment

Install commands for Linux:

$ sudo apt-get install ansible


After install all of these tools, you should run terminal in directory, where you downloaded files
and type:

$ vagrant up

Vagrant will check Vagrantfile updates and download files, if it will find new versions of OS's of other soft. After all it'll create a virtual machine with use of VirtualBox. If the creation of VM will complete successully, automatically will run the playbook.yml file, which contains set of Tasks, thanks to which install and set necessarily programs and other stuff.

After install the playbook, you can check the state of server by typing in browser in address textbox IP address: 192.168.88.8. If the website will open correctly, you'll see the site of Wordpress.

In file called playbook.yml you can find text with section called "tags:". These sections are used to run a specific part of the configuration without running the whole playbook. Adding “tags:” in any part of a play (including roles) adds those tags to the contained tasks. If you wanted to just run the “debs” and “wordpress” part of a very long playbook, you could do this:

ansible-playbook playbook.yml --tags "debs,wordpress".


In playbook.yml you can find too a task named: "Adjust OpCache memory setting". OpCache is a tool which improves PHP performance by storing precompiled script bytecode in shared memory, thereby removing the need for PHP to load and parse scripts on each request. 

Another tool is Composer. Composer allows to simple and fast management relationships in project. It allows to declare different relationships, which needs a project and install or update them automatically.

