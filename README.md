## Skeleton - Vagrant + Ansible + Scala + SBT


This is another installment in my multi-part series of project skeletons.  This one sets you up for a generic Scala development environment using Vagrant + Ansible.  It includes:

* An amazing Vagrantfile that will cue up Anisble for provisioning goodness
* An Ansible inventory file that works with a stock Vagrant set up
* A vagrant.yaml file that contains the tasks to install Scala and SBT (including Java)

Notes:

1. This is set up for a basic Scala project on Ubuntu with a base box name "precise64"

2. If you clone this, you have to go in and make a lot of changes to build.sbt.  You can also use g8 with BTBurke/sbt.g8 to set up a new build.sbt with your info.

3. Technical Details:
 - Installs Oracle Java 7
   * You can use OpenJDK instead by making a small change to vagrant.yaml.  Instructions in the file.
 - Installs Scala 2.10.3 and SBT 0.13.0 
   * You can change this by specifying other version numbers in the vars section at the top of vagrant.yaml
 - Ups the default VM memory from 384MB to 4GB.  You can change this in the Vagrantfile.


### Troubleshooting:

##### Ansible seems to be provisioning a new VM but scala isn't installed

This can happen when you have multiple VMs running.  Anisble identifies by IP address, so if you have multiple machines running on 127.0.0.1, it can't tell the difference.  You should destroy the other VMs if you don't need them.  Alternatively, you can run the new VM on a different IP address.
