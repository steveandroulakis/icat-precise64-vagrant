ICAT 4.2 Ubuntu Precise 12.04 Vagrant Virtual Machine
===============================

_Runs a pre-configured blank [ICAT](https://icatproject.googlecode.com/) server with Derby database (in the Glassfish server environment). Can be used for development, testing or upgrading to a production environment. Admin port 4848 and web service port 8080 are exported to the host machine by default (you can change this in the Vagrantfile)._

Requires Vagrant, a small ruby program (that in turn requires Oracle's VirtualBox VM software).

## Todo
 - Put example data in

## Requirements
 - Vagrant (and in turn, Virtualbox) see [Getting Started](http://docs-v1.vagrantup.com/v1/docs/getting-started/index.html)

## Installation and running

 - Install Vagrant (guide linked above)

Git clone this repository:
    
    git clone https://github.com/steveandroulakis/icat-precise64-vagrant.git icat_precise64_v1

Add the the VM box:

```
vagrant box add icat_precise64_v1 https://dl.dropbox.com/u/172498/icat_precise64_v1.box
```

The VM will be downloaded and registered with Vagrant.

cd to the cloned git repository and start the virtual server:

```
vagrant up
```

Once it's ready, connect to the server with:

```
vagrant ssh
```

Start the server and test with:

```
sudo su --
service glassfish start

glassfish3/test.sh
```

If all goes well you will receive the following output:

```
Run 'service glassfish start' as root first before running this
Login, search, create, delete and logout operations were all successful.
```

Access the admin and WSDL endpoint with:

```
localhost:4848

localhost:8080/ICATService/ICAT?wsdl
```

The admin username and password is admin / adminadmin

Shut down the VM with `vagrant halt` and restart it with `vagrant up` in the same directory.
