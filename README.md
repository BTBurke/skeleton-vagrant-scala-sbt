Skeleton - Vagrant + Ansible + Scala + SBT
===

This is another installment in my multi-part series of project skeletons.  This one sets you up for a generic Vagrant + Ansible development environment for a Scala project.  It includes:

* An amazing Vagrantfile that will cue up Anisble for devops goodness and get you Scala and SBT installed for you
* An Ansible inventory file that works with a stock Vagrant set up
* A vagrant.yaml file that contains the tasks you want to execute on vagrant up

Notes:

1. This is set up for a basic Scala project on Ubuntu with a base box name "precise64"
2. If you clone this, you have to go in and make a lot of changes to build.sbt.  You can also use g8 with BTBurke/sbt.g8 to set up a new build.sbt with your info.
3. Technical Details:
 - Installs Oracle Java 7
   * You can use OpenJDK instead by making a small change to vagrant.yaml.  Instructions in the file.
 - Installs Scala 2.10.3 and SBT 0.13.0 
   * You can change this by specifying other version numbers in the vars section at the top of vagrant.yaml
