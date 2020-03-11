# vagrant_mulitmachine
This repo contains code for creating three vagrant virtual machines, two web servers and one database

# What is this repo for

This repo contains code that when executed will create three virtual box machines that will have a running web server on them.  How to do that you will see [below](#how-to-use-this-repo).


# Why use this repo

You might want to use this repo to gain a better understanding of how Vagrant can work for you. 
In this specific case we use a loop to create two similiar machines and another machine separately. 
This is accomplished by using `(1..2).each do |i|` and specifiying the names of the server as variables `vm_name="web#{i}"`.
Third machine is defined on its own.


# How to use this repo

* You need to have vagrant installed on you workstation
   *  for MacOS
   
    ```
    brew install vagrant
    ```
  
   *  for any other OS click [here](https://www.vagrantup.com/downloads.html).

* You also need to have virtualbox installed since this is the virtualization provider we are using in this example.

   * Download [Here](https://www.virtualbox.org/wiki/Downloads)
  
* This "How to" will cover macOS specifically, it may vary for other systems.

* Clone this repo locally to a folder of your choice
```
git clone git@github.com:yordanivh/vagrant-multimachine.git
```
* Go inside the newly created folder of the repo

```
cd vagrant-multimachine
```
* Give command to start the machines

```
vagrant up
```
* This is an expected output

```
Bringing machine 'web1' up with 'virtualbox' provider...
Bringing machine 'web2' up with 'virtualbox' provider...
Bringing machine 'mysql' up with 'virtualbox' provider...
==> web1: Importing base box 'yordan/box'...
==> web1: Matching MAC address for NAT networking...
==> web1: Checking if box 'yordan/box' version '1.0.0' is up to date...
==> web1: Setting the name of the VM: vagrant_mulitmachine_web1_1583925732466_96894
==> web1: Clearing any previously set network interfaces...
==> web1: Preparing network interfaces based on configuration...
    web1: Adapter 1: nat
==> web1: Forwarding ports...
    web1: 22 (guest) => 2222 (host) (adapter 1)
==> web1: Booting VM...
==> web1: Waiting for machine to boot. This may take a few minutes...
    web1: SSH address: 127.0.0.1:2222
    web1: SSH username: vagrant
    web1: SSH auth method: private key
    web1: 
    web1: Vagrant insecure key detected. Vagrant will automatically replace
    web1: this with a newly generated keypair for better security.
    web1: 
    web1: Inserting generated public key within guest...
    web1: Removing insecure key from the guest if it's present...
    web1: Key inserted! Disconnecting and reconnecting using new SSH key...
==> web1: Machine booted and ready!
==> web1: Checking for guest additions in VM...
==> web1: Setting hostname...
==> web1: Mounting shared folders...
    web1: /vagrant => /Users/yhalachev/repos/vagrant_mulitmachine
==> web2: Importing base box 'yordan/box'...
==> web2: Matching MAC address for NAT networking...
==> web2: Checking if box 'yordan/box' version '1.0.0' is up to date...
==> web2: Setting the name of the VM: vagrant_mulitmachine_web2_1583925763238_51910
==> web2: Fixed port collision for 22 => 2222. Now on port 2200.
==> web2: Clearing any previously set network interfaces...
==> web2: Preparing network interfaces based on configuration...
    web2: Adapter 1: nat
==> web2: Forwarding ports...
    web2: 22 (guest) => 2200 (host) (adapter 1)
==> web2: Booting VM...
==> web2: Waiting for machine to boot. This may take a few minutes...
    web2: SSH address: 127.0.0.1:2200
    web2: SSH username: vagrant
    web2: SSH auth method: private key
    web2: 
    web2: Vagrant insecure key detected. Vagrant will automatically replace
    web2: this with a newly generated keypair for better security.
    web2: 
    web2: Inserting generated public key within guest...
    web2: Removing insecure key from the guest if it's present...
    web2: Key inserted! Disconnecting and reconnecting using new SSH key...
==> web2: Machine booted and ready!
==> web2: Checking for guest additions in VM...
==> web2: Setting hostname...
==> web2: Mounting shared folders...
    web2: /vagrant => /Users/yhalachev/repos/vagrant_mulitmachine
==> mysql: Importing base box 'yordan/box'...
==> mysql: Matching MAC address for NAT networking...
==> mysql: Checking if box 'yordan/box' version '1.0.0' is up to date...
==> mysql: Setting the name of the VM: vagrant_mulitmachine_mysql_1583925796874_11783
==> mysql: Fixed port collision for 22 => 2222. Now on port 2201.
==> mysql: Clearing any previously set network interfaces...
==> mysql: Preparing network interfaces based on configuration...
    mysql: Adapter 1: nat
==> mysql: Forwarding ports...
    mysql: 22 (guest) => 2201 (host) (adapter 1)
==> mysql: Booting VM...
==> mysql: Waiting for machine to boot. This may take a few minutes...
    mysql: SSH address: 127.0.0.1:2201
    mysql: SSH username: vagrant
    mysql: SSH auth method: private key
    mysql: 
    mysql: Vagrant insecure key detected. Vagrant will automatically replace
    mysql: this with a newly generated keypair for better security.
    mysql: 
    mysql: Inserting generated public key within guest...
    mysql: Removing insecure key from the guest if it's present...
    mysql: Key inserted! Disconnecting and reconnecting using new SSH key...
==> mysql: Machine booted and ready!
==> mysql: Checking for guest additions in VM...
==> mysql: Setting hostname...
==> mysql: Mounting shared folders...
    mysql: /vagrant => /Users/yhalachev/repos/vagrant_mulitmachine
```

* After the above is finished you should have three virtual macines named web1, web2 and mysql. You can confirm this by running `vagrant status`

```
❯ vagrant status
Current machine states:

web1                      running (virtualbox)
web2                      running (virtualbox)
mysql                     running (virtualbox)

This environment represents multiple VMs. The VMs are all listed
above with their current state. For more information about a specific
VM, run `vagrant status NAME`.
```

* When you are done with this destroy the created environment to save resources

```
vagrant destroy
```
