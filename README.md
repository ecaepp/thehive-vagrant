# thehive-vagrant
This project is for setting up an easy repeatable dev, test, and/or training environment for TheHive utilizing Vagrant and Ansible.
(Underdevelopment)


TheHive is a collaboration tool for incident response allowing network security team to be able to 
quickly find a share indicators in relation to the incident. It also provides built in automation for checking indicators
on common public tools such as VirusTotal and OTX, and uses Elasticsearch for the backend.

Rquierments

Vagrant:
This project requires Vagrant for provisioning and building the necessary VMs for the application to run on. You don't
need to know Vagrant at all, but having a basic understanding of the tool is helpful.

VirtualBox:
This is the Hypervisor that the Vagrant boxes are built for.

Ansible:
This is a configuration manager used to setup, install, and configure TheHive applications. In future releases Ansible will not be
needed as it will be prebuilt into the Vagrant boxes.


Settting up the Environment

NOTE: I primarily use Linux and OSX for this sort of work, but these instructions should work in Windows as well. If you
problems please open an issue so it can be troubleshot.

Installing Vagrant:
Vagrant supports multiple OS and installing is as simple as downloading the package and running it. The install in most 
cases the installer package will put the application in path for easy use.

Download packages can be found at 

Debian/Ubuntu:



