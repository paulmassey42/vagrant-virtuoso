# Virtuoso Playground
This virtual environment creates a playground for exploring Linked Data tools. Today it enables the RDF Store Virtuoso.

*security usage warning*: The created virtual machine can be used to explore functional and deployment issues. 
It is, however, not intended to be made available online as such without taking the necessary security actions. 

# Before Starting
The two main components which have to be installed on the host machine are:

    VirtualBox - (https://www.virtualbox.org)
    Vagrant - (https://www.vagrantup.com/)

There is also a need for a command-line tool such as bash, shell, etc and that the paths are set correctly for ‘vagrant’ to be executable. These are the latest versions which have been tested (prior versions will not be tested). On Windows, cygwin or git bash could be installed which will provide bash along with an assortment of other GNU open-source tools.

# Building the VM

On the command line:

```
    git clone https://github.com/tenforce/vagrant-virtuoso
    cd vagrant-virtuoso
    vagrant plugin install vagrant-vbguest
    vagrant up Possibly select you network interface connection point This will take a long time the first time
```

Then to make sure the GUI interface is usable from the virtual machine

    vagrant halt
    vagrant up

Then it should be possible to use the virtual machine:

    Login password: vagrant
    Select the firefox web-browser


## Notes 

    Depending on the underlying system, it seems that the network connections settings sometimes cause problems (halt, wait a while and up again, normally clears the problem).
