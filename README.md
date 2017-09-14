# Documentation

## Getting started

The goal of Dockerized Drupal initiative is to make Drupal development experience simpler, faster and more efficient than the conventional way of using the standard LAMP solution in a solo and a team environment.

To achieve that, we have built various tools and developed custom workflows around Docker ecosystem, so no matter what is your skill level and how complex your Drupal project is, you can focus on solving your particular problem at hand.

The initiative was started by two Drupal developers - [Jürgen Viljaste](https://www.drupal.org/u/viljaste) and [Mait Roosvalt](https://www.drupal.org/u/maitzzz) with the help of [Fenomen Agency](http://fenomen.ee/en).

If you are interested about the story why and how this project was born, please read or watch this [DrupalCamp Baltics](http://www.drupalcampbaltics.com/) 2015 presentation: [Using Docker to boost your development experience with Drupal](https://github.com/dockerizedrupal/drupalcamp-baltics-2015).

### Setting up a development environment

The goal of Dockerized Drupal initiative is to make Drupal development experience consistent on all major operating systems. In this section you can find the instructions on how to get started on different operating systems.

#### Windows

You may know or not know that Docker Engine only runs natively on Linux. For that reason we are currently working on making the workflows and the tools provided by the Dockerized Drupal initiative to work seamlessly on Windows operating system as well.

To accomplish that we have included Vagrant to our toolset as a wrapper for the Dockerized Drupal initiative tools to be able to run them on operating systems other than Linux.

**Comments**

> Tomáš Fülöpp • a year ago
>
> Docker for Windows (D4W) now runs nicely on Windows thanks to Hyper-V ( [https://beta.docker.com/doc...](https://docs.docker.com/docker-for-windows/) ). No VirtualBox or Vagrant needed.
>
> How can I run DockerizeDrupal environment under D4W? I am able to start individual sites using "docker-compose up -d" but then it is not clear on what IP they run etc., so I am clearly missing something.

> Tomáš Fülöpp • 2 years ago
>
> This is the best recipe to set up a fairly complete local Drupal development environment even on Windows. Great work guys! Looking forward to see the documentation to grow!

> viljaste • 2 years ago
>
> Hi Tomáš,
> Thanks! We will try our best to improve the documentation, as we think that this is the most important component to get right if we want to make this initiative and tools easily available to others.

##### Download and install VirtualBox

Since Docker Engine doesn't run natively on Windows, you need to download and install a hypervisor to your computer.

We are relying on VirtualBox to do that task in this example.

Go to the following URL <https://www.virtualbox.org/wiki/Downloads> and download VirtualBox for Windows.

![Windows 18](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_18.png "Windows 18")

Once you have downloaded VirtualBox to your computer you are ready to install it.

![Windows 19](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_19.png "Windows 19")

![Windows 20](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_20.png "Windows 20")

![Windows 21](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_21.png "Windows 21")

![Windows 22](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_22.png "Windows 22")

![Windows 23](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_23.png "Windows 23")

![Windows 24](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_24.png "Windows 24")

![Windows 25](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_25.png "Windows 25")

![Windows 26](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_26.png "Windows 26")

##### Download and install Vagrant

The second thing you would need to get started is to download and install Vagrant to your computer.

For that go to the following URL <https://www.vagrantup.com/downloads.html> and download Vagrant for Windows.

![Windows 1](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_1_0.png "Windows 1")

Once you have downloaded it you are ready to install it.

![Windows 2](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_2.png "Windows 2")

![Windows 3](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_3.png "Windows 3")

![Windows 4](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_4.png "Windows 4")

![Windows 5](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_5.png "Windows 5")

![Windows 6](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_6.png "Windows 6")

![Windows 7](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_7.png "Windows 7")

![Windows 8](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_8.png "Windows 8")

![Windows 9](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_9.png "Windows 9")

**Comments**

> Martin Ant • a year ago
>
> If you are experiencing problems with downloading the image on windows then make sure you have the 
> Microsoft Visual C++ Redistributable installed on your system or "vagrant up" will fail at downloading the box.
> 
> This is the error message I was receiving
> 
> "The box 'dockerizedrupal/base-ubuntu-trusty' could not be found or could not be accessed in the remote catalog. If this is a private box on HashiCorp's Atlas, please verify you're logged in via `vagrant login`. Also, please double-check the name. The expanded URL and error message are shown below:
> 
> URL: ["[https://atlas.hashicorp.com...](https://app.vagrantup.com/dockerizedrupal/boxes/base-ubuntu-trusty)"] "
> 
> Related issue on github
> [https://github.com/mitchell...](https://github.com/hashicorp/vagrant/issues/6754)

> Tomáš Fülöpp • 2 years ago
>
> In presentation [https://github.com/dockeriz...](https://github.com/dockerizedrupal/drupalcamp-baltics-2015) you say that Vagrant is only needed while drupal-compose does not work under Windows. Could you expand on that? Will Vagrant really be obsolete in the Windows setup soon?

> viljaste • 2 years ago
>
> Hi Tomáš,
> 
> If I'm honest with you then we have not yet decided, which way to go actually. Should we continue investing resources into Vagrant or Docker Toolbox based solution as of Docker Compose is now natively supported also on Windows. Both solutions have multiple drawbacks though.
> 
> I prefer Vagrant based solution myself as this currently gives us the most flexibility, but there are others who would like to use Docker Toolbox/Docker Machine based solution instead.
> 
> At the moment we have invested time into trying to use Vagrant to be able to use Dockerized Drupal toolset on Windows, which from a technical point of view works quite nicely, but from a UX point of view isn't ideal.

> Tomáš Fülöpp • 2 years ago
>
> Running Vagrant using "vagrant up" means having to open and type in the Windows command line interface, which is tedious. I suppose one could write a .bat file to automate that. Or is there a yet more efficient method?

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> Since we currently have invested time into trying to make Vagrant work for us on Windows, we are thinking to simply the interaction with it by developing a simple application that will run for example in the system tray, where you could easily stop/start the VM and SSH into it, maybe will have shortcuts to most used features etc., which means that you don't have to have a separate shell open and you can control the VM easily from global context.

> Tomáš Fülöpp • 2 years ago
> An intriguing plan plan!
>
> In the meantime I've solved it by creating a simple .bat file (dockerizedrupal.bat) containing the following lines:
>
> REM Run dockerizedrupal using Vagrant
> chdir /d "C:\path_to_my\dockerizedrupal\folder"
> vagrant up

##### Start the guest virtual machine with Vagrant

Now that you have sucessfully installed Vagrant to your computer, next you will need to download our latest Vagrantfile.

For that go to the following page <https://github.com/dockerizedrupal/vagrant-dockerizedrupal/releases> and download the latest source code to your computer.

![Windows 10](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_10.png "Windows 10")

Once you have done that, extract the contents of the Zip file.

![Windows 11](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_11.png "Windows 11")

![Windows 12](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_12.png "Windows 12")

![Windows 13](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_13.png "Windows 13")

![Windows 14](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_14.png "Windows 14")

The only required files at this time are Vagrantfile and config.yml, all the other files you can safely delete.

![Windows 15](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_15.png "Windows 15")

The extracted directory by default will be the place where you put your Drupal projects. Feel free to move it to the appropriate place and give it a proper name if needed.

In this example we have moved the extracted directory to user's (Container) home directory (C:\Users\Container) and renamed it to Projects (C:\Users\Container\Projects).

![Windows 16](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_16.png "Windows 16")

![Windows 17](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_17.png "Windows 17")

Now that everything is in place let's start the virtual machine with Vagrant, during which the Dockerized Drupal setup will be automatically provisioned for you.

**Comments**

> Martin Ant • a year ago
>
> Remember to run everything as admin or you might run into some "nasty" problems with VirtualBox network adapters.
 
> Tomáš Fülöpp • 2 years ago
>
> I have an existing installation with a number of local sites. I used Vargant and Virtualbox under Windows to install it.
>
> I see now that there is a newer version of dockerizedrupal at [https://github.com/dockeriz...](https://github.com/dockerizedrupal/vagrant-dockerizedrupal/releases)
> How can I safely upgrade? Can I just repeat the process described on this page?

##### Updating Dockerized Drupal tools inside the Vagrant VM

Latest version of Dockerized Drupal virtual machine includes a simple script that a user can execute anytime he/she wants to update the tools provided by the Dockerized Drupal project to latest version.

If you are using an older version of Vagrant VM where you don't have the Updater installe, then we recommend that instead of migrating all your current projects and any other custom configuration from the current VM to newer version, you install the Updater into your current VM and use that to update Dockerized Drupal tools in the future.

**Comments**

> Tomáš Fülöpp • a year ago
> 
> Despite running "updater" as root, after it completes and I shut down and start then start again the whole Vagrant VM, I see in http://dev/ that eg vhost is too old (1.1.7) instead having the latest version (1.1.8), etc. 
> Does it mean updater does not work for me?

#### Mac

We are currently working on making the workflows and the tools provided by the Dockerized Drupal initiative to work seamlessly on OS X operating system.

To accomplish that we have included Vagrant to our toolset as a wrapper for the Dockerized Drupal initiative tools to be able to run them on operating systems other than Linux.

**Comments**

> J3ll3nl • a year ago
>
> How are you guys doing on this?
  
> Alexis Saransig • 3 months ago
>
> hey guys, any update for Mac? 
> For Linux it works amazing. Thanks.

#### Linux

The goal is to develop an [Ansible playbook](http://docs.ansible.com/ansible/playbooks.html) to install all the tools to your Linux machine automatically, but this is still a work in progress. You can find more info about the project in [GitHub](https://github.com/dockerizedrupal/ansible-dockerizedrupal). 

In the meantime you can follow the manual process to install them to your machine.

##### Ubuntu

// TODO

###### Install Docker Engine

1) Install Docker Engine.

    ```bash
    $ wget -qO- https://get.docker.com/ | sh
    ```

2) Add current user to Docker group.

    ```bash
    $ sudo usermod -aG docker "$(whoami)"
    ```
    
3) Restart your machine.

    ```bash
    $ sudo reboot
    ```

**Comments**

> Bryden Arndt • 5 months ago
>
> Step 1, instead of...
>
> wget -qO- https://get.docker.com/ | sh
>
> ... it should be:
>
> wget -qO- https://get.docker.com/ | sudo sh

> Niklan • 9 months ago
>
> You don't need to reboot PC actually. You can just logout from current session and login again. Thats says info after installation of docker.

###### Install Docker Compose

1) Download Docker Compose binary.

    ```bash
    $ sudo sh -c "curl -L https://github.com/docker/compose/releases/download/1.7.1/docker-compose-Linux-x86_64 > /usr/local/bin/docker-compose"
    ```
  
2) Give the execute permission to Docker Compose binary.

    ```bash
    $ sudo chmod +x /usr/local/bin/docker-compose
    ```

**Comments**

> kovtunos • a year ago
>
> If you use Prelink in your Linux system add to the file /etc/prelink.conf next line:
> 
> ﻿-b /usr/local/bin/docker-compose

###### Install Drupal Compose

Repository: <https://github.com/dockerizedrupal/drupal-compose>

1) Install Drupal Compose.

    ```bash
    $ curl -sSL https://raw.githubusercontent.com/dockerizedrupal/drupal-compose/master/install.sh | sudo sh


###### Install Crush

Repository: <https://github.com/dockerizedrupal/crush>

1) Install Crush.

    ```bash
    $ curl -sSL https://raw.githubusercontent.com/dockerizedrupal/crush/master/install.sh | sudo sh
    ```

**Comments**

> Alexey Dyomin • 8 months ago
>
> Hi! How to use drush aliases?

> Simon Bonsor • a year ago
>
> Am I missing a trick somewhere? I've installed crush as above but when I try to use it the containers do not find drush on their PATH. I've tried various tweaks with .bashrc to try and get it included if it's non-interactive. This is on Ubuntu 14.04 (actually running under Vagrant).

> Tomáš Fülöpp • 2 years ago
>
> I see it's possible to use drush in each local site's directory. What is crush then for? Could you also make a section about it here in the documentation?

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> Drush is actually a symlink to Crush if you have followed the steps in this sections to set it up. You can use both "crush" or "drush" commands to interact with Drupal, the outcome is the same. If you are interacting with Drush, you are actually interacting with Crush behind the scenes.
>
> The reason why we created Crush is because Drush is actually located inside the PHP container. Normally when you would want to use any command in the containerized environment to interact with the application inside the container, you would need to first enter the container manually and the execute the command inside the container. This becomes very tedious very quickly if you have to use the command multiple times in a short period of time. For that reason we have created Crush, which enables you to execute Drush commands outside the container directly on your host (on Windows inside the Vagrant VM) and it will proxy the correct command to the container.
> 
> A brief explanation can also be found here [https://github.com/dockeriz...](https://github.com/dockerizedrupal/drupalcamp-baltics-2015) in section "Container + Drush = Crush".

> Tomáš Fülöpp • 2 years ago
>
> Makes sense, works great, to the degree I did not notice that I never noticed that what I use is not drush but crush. Well done!

## License

**MIT**
