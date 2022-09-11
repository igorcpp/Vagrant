vagrant -h

vagrant init

vagrant init ubuntu/trusty64

vagrant up
- возобновить машину из паузы, можно и vagrant up
  vagrant resume
  
vagrant provision -- forces reprovisioning of the vagrant machine
vagrant reload -- restarts vagrant machine, loads new Vagrantfile configuration
vagrant reload --provision -- restart the virtual machine and force provisioning
Getting into a VM
vagrant ssh -- connects to machine via SSH
vagrant ssh <boxname> -- If you give your box a name in your Vagrantfile, you can ssh into it with boxname. Works from any directory.
Stopping a VM
vagrant halt -- stops the vagrant machine
vagrant suspend -- suspends a virtual machine (remembers state)
Cleaning Up a VM
vagrant destroy -- stops and deletes all traces of the vagrant machine
vagrant destroy -f -- same as above, without confirmation
Boxes
vagrant box list -- see a list of all installed boxes on your computer
vagrant box add <name> <url> -- download a box image to your computer
vagrant box outdated -- check for updates vagrant box update
vagrant box remove <name> -- deletes a box from the machine
vagrant package -- packages a running virtualbox env in a reusable box
Saving Progress
-vagrant snapshot save [options] [vm-name] <name> -- vm-name is often default. Allows us to save so that we can rollback at a later time

Tips
vagrant -v -- get the vagrant version
vagrant status -- outputs status of the vagrant machine
vagrant global-status -- outputs status of all vagrant machines
vagrant global-status --prune -- same as above, but prunes invalid entries
vagrant provision --debug -- use the debug flag to increase the verbosity of the output
vagrant push -- yes, vagrant can be configured to deploy code!
vagrant up --provision | tee provision.log -- Runs vagrant up, forces provisioning and logs all output to a file
Plugins
vagrant-hostsupdater : $ vagrant plugin install vagrant-hostsupdater to update your /etc/hosts file automatically each time you start/stop your vagrant box.
Notes
If you are using VVV, you can enable xdebug by running vagrant ssh and then xdebug_on from the virtual machine's CLI.
