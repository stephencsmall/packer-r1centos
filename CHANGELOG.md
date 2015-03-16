# Creating a Centos Minimal Vagrant box with Packer
## For REZ-1

----

### *16-MAR-2015*

I left off on Friday having created a skeleton CentOS packer file that had the basics to kick off the build, but no further boot commands or instructions.  Today I will create instructions and a kickstart file for my perfect image.

Initial goals

- Create boot command to launch Anaconda into my kickstart file
- Create my kickstart file

#### *9:45 AM*

I've found a usable example [here](http://digitalsandwich.com/packer-built-centos-vagrant-base-box-automated-build/) that I'm basing my build off of.  I've removed his bit about setting up a private key, I want to revisit this later and set up our own for REZ.

#### *4:48 PM*

After a day of bashing this around, I've managed to create a configuration that will produce a viable Vagrant box for REZ-1 use.  I still want to accomplish the following:

- 8 out of 10 times, the build fails after detecting an SSH server is alive.  If I run this with `-debug` on, I can step through this part sometimes, but not always. I need to figure out why.

        Error uploading VirtualBox version: Process exited with: 1. Reason was:  ()

- Clean up naming of outputted box files
- Get a list of small utils that we want to have in here.
    - tmux
    - htop
    - vim

----
