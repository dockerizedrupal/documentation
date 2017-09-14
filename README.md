# Documentation

## Table of Content

* [Getting started](https://github.com/dockerizedrupal/documentation#getting-started)
  * [Setting up a development environment](https://github.com/dockerizedrupal/documentation#setting-up-a-development-environment)
    * [Windows](https://github.com/dockerizedrupal/documentation#windows)
      * [Download and install VirtualBox](https://github.com/dockerizedrupal/documentation#download-and-install-virtualbox)
      * [Download and install Vagrant](https://github.com/dockerizedrupal/documentation#download-and-install-vagrant)
      * [Start the guest virtual machine with Vagrant](https://github.com/dockerizedrupal/documentation#start-the-guest-virtual-machine-with-vagrant)
      * [Updating Dockerized Drupal tools inside the Vagrant VM](https://github.com/dockerizedrupal/documentation#updating-dockerized-drupal-tools-inside-the-vagrant-vm)
    * [Mac](https://github.com/dockerizedrupal/documentation#mac)
    * [Linux](https://github.com/dockerizedrupal/documentation#linux)
      * [Ubuntu](https://github.com/dockerizedrupal/documentation#ubuntu)
        * [Install Docker Engine](https://github.com/dockerizedrupal/documentation#install-docker-engine)
        * [Install Docker Compose](https://github.com/dockerizedrupal/documentation#install-docker-compose)
        * [Install Drupal Compose](https://github.com/dockerizedrupal/documentation#install-drupal-compose)
        * [Install Crush](https://github.com/dockerizedrupal/documentation#install-crush)
        * [Install vhost](https://github.com/dockerizedrupal/documentation#install-vhost)
  * [Tutorials](https://github.com/dockerizedrupal/documentation#tutorials)
    * [Starting a new project](https://github.com/dockerizedrupal/documentation#starting-a-new-project)
    * [Deleting an existing project permanently](https://github.com/dockerizedrupal/documentation#deleting-an-existing-project-permanently)
    * [Switching to a different PHP version](https://github.com/dockerizedrupal/documentation#switching-to-a-different-php-version)
    * [Increasing or decreasing the PHP memory limit](https://github.com/dockerizedrupal/documentation#increasing-or-decreasing-the-php-memory-limit)
    * [Debugging a project with Xdebug](https://github.com/dockerizedrupal/documentation#debugging-a-project-with-xdebug)
    * [Profiling a project with Blackfire](https://github.com/dockerizedrupal/documentation#profiling-a-project-with-blackfire)
    * [Working in a multi-site environment](https://github.com/dockerizedrupal/documentation#working-in-a-multi-site-environment)
    * [Connecting to MySQL database with an external tool](https://github.com/dockerizedrupal/documentation#connecting-to-mysql-database-with-an-external-tool)
  * [Frequently asked questions](https://github.com/dockerizedrupal/documentation#frequently-asked-questions)
    * [Where to get help?](https://github.com/dockerizedrupal/documentation#where-to-get-help)
  * [Tips & Tricks](https://github.com/dockerizedrupal/documentation#tips--tricks)
    * [Removing orphaned Docker volumes](https://github.com/dockerizedrupal/documentation#removing-orphaned-docker-volumes)
* [Documentation](https://github.com/dockerizedrupal/documentation#documentation-1)
  * [Building Docker images](https://github.com/dockerizedrupal/documentation#building-docker-images)
  * [Logging](https://github.com/dockerizedrupal/documentation#logging)
  * [Tools](https://github.com/dockerizedrupal/documentation#tools)
    * [Docker Registry](https://github.com/dockerizedrupal/documentation#docker-registry)
    * [Docker images](https://github.com/dockerizedrupal/documentation#docker-images)
    * [vhost](https://github.com/dockerizedrupal/documentation#vhost)
      * [Environment variables available to Docker containers](https://github.com/dockerizedrupal/documentation#environment-variables-available-to-docker-containers)
        * [VHOST_PROJECT_NAME](https://github.com/dockerizedrupal/documentation#vhost_project_name)
        * [VHOST_PRIMARY_SERVICE](https://github.com/dockerizedrupal/documentation#vhost_primary_service)
        * [VHOST_SERVICE_NAME](https://github.com/dockerizedrupal/documentation#vhost_service_name)
        * [VHOST_VERSION_FILE_URL](https://github.com/dockerizedrupal/documentation#vhost_version_file_url)
        * [VHOST_REPOSITORY_URL](https://github.com/dockerizedrupal/documentation#vhost_repository_url)
        * [VHOST_DOMAIN_ALIASES](https://github.com/dockerizedrupal/documentation#vhost_domain_aliases)
      * [HTTP Basic Authentication](https://github.com/dockerizedrupal/documentation#http-basic-authentication)
* [Community](https://github.com/dockerizedrupal/documentation#community)
  * [Contributing to Dockerized Drupal initiative](https://github.com/dockerizedrupal/documentation#contributing-to-dockerized-drupal-initiative)
  * [Chat (IRC)](https://github.com/dockerizedrupal/documentation#chat-irc)

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

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_18.png "Image")

Once you have downloaded VirtualBox to your computer you are ready to install it.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_19.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_20.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_21.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_22.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_23.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_24.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_25.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_26.png "Image")

##### Download and install Vagrant

The second thing you would need to get started is to download and install Vagrant to your computer.

For that go to the following URL <https://www.vagrantup.com/downloads.html> and download Vagrant for Windows.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_1_0.png "Image")

Once you have downloaded it you are ready to install it.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_2.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_3.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_4.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_5.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_6.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_7.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_8.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_9.png "Image")

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

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_10.png "Image")

Once you have done that, extract the contents of the Zip file.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_11.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_12.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_13.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_14.png "Image")

The only required files at this time are Vagrantfile and config.yml, all the other files you can safely delete.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_15.png "Image")

The extracted directory by default will be the place where you put your Drupal projects. Feel free to move it to the appropriate place and give it a proper name if needed.

In this example we have moved the extracted directory to user's (Container) home directory (C:\Users\Container) and renamed it to Projects (C:\Users\Container\Projects).

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_16.png "Image")

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Windows_17.png "Image")

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

###### Install vhost

```bash
$ SERVER_NAME="dev"
```

```bash
$ TMP="$(mktemp -d)"
```

```bash
$ git clone https://github.com/dockerizedrupal/vhost.git "${TMP}"
```

```bash
$ cd "${TMP}"
```

```bash
$ git checkout 1.1.9
```

```bash
$ sudo cp ./docker-compose.yml /opt/vhost.yml
```

```bash
$ sudo sed -i "s/SERVER_NAME=localhost/SERVER_NAME=${SERVER_NAME}/" /opt/vhost.yml
```

```bash
$ docker-compose -f /opt/vhost.yml up -d
```

Watch the following video to see it in action:

[![Getting started on Linux: Install vhost](http://img.youtube.com/vi/WV3HPaJxeuM/0.jpg)](http://www.youtube.com/watch?v=WV3HPaJxeuM)

**Comments**

> Derek • a year ago
>
> Is installing vhost going to destroy all my local vhost files or is this safe to use on a machine that is already a devbox? For instance, the previous procedure kills Drush for all non-containerized sites. I can get around it by setting up a new alias to use the "old drush" but there should be a warning about these things.

> Derek • a year ago
>
> Found out the answer is no. Nice docker integration so far! Thanks!

> Bryden Arndt • a year ago
>
> On the final step:
>
> docker-compose -f /opt/vhost.yml up -d
>
> I get the following error:
>
> Invalid service name "vhost-data" - only [a-zA-Z0-9] are allowed
>
> I'm on Ubuntu 15.10

> viljaste • a year ago
>
> Hi Bryden,
>
> I haven't seen this error message in a long time :). I think you have an older version of Docker Compose installed, which doesn't support newer naming conventions. So I suggest that you upgrade your Docker Compose to latest version.

### Tutorials

Here you can find tutorials for various topics on how to solve a specific use case using the Dockerized Drupal initiative tools and workflows.

#### Starting a new project

Prerequisites: Setting up a development environment

To Dockerize a new Drupal project you simply have to follow these steps:

1) Download Drupal source code to your machine.

    ```bash
    $ wget http://ftp.drupal.org/files/projects/drupal-8.0.2.tar.gz
    ```

2) Untar the package.

    ```bash
    $ tar xzf drupal-8.0.2.tar.gz
    ```

3) Move to newly extracted directory.

    ```bash
    $ cd drupal-8.0.2
    ```

4) Generate general purpose configuration file for your Drupal project.

    ```bash
    $ drupal-compose
    ```

5) Start the containers.

    ```bash
    $ docker-compose up -d
    ```

6) Create the services.yml file.

    ```bash
    $ cp sites/default/default.services.yml sites/default/services.yml
    ```

7) Install Drupal.

    ```bash
    $ drush -y site-install --db-url=mysqli://container:container@mysql/drupal --account-name=admin --account-pass=admin
    ```

Watch the following video to see it in action:

[![Tutorials: Starting a new project](http://img.youtube.com/vi/zqRYWIXmv04/0.jpg)](http://www.youtube.com/watch?v=zqRYWIXmv04)

**Comments**

> kovtunos • 8 months ago
>
> Hello viljaste. Is there a way to use Dockerized Drupal with the Drupal Composer project? 
> [https://github.com/drupal-c...](https://github.com/drupal-composer/drupal-project) 
> It provides drupal installation in the *web* folder like this:
>
> ![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/a5b37a33cb9c1c137ae764c93fd0b5bf5fd37c44ecc5aa0bdc6262b084d69923.png "Image")

> Villorente Gerald • 4 months ago
>
> I keep getting this error
>
> $ drush -y site-install --db-url=mysqli://container:container@mysql/bud --account-name=root --account-pass=root
> You are about to CREATE the 'bud' database. Do you want to continue? (y/n): y
> Failed to create database: ERROR 2005 (HY000): Unknown MySQL server host 'mysql' (0)
>
> Any idea?

> Villorente Gerald • 4 months ago
>
> So here is the output.
>
> $ drush -y site-install --db-url=mysqli://container:container@0.0.0.0:32775/bud --account-name=root --account-pass=root
> You are about to CREATE the 'bud' database. Do you want to continue? (y/n): y
> Starting Drupal installation. This takes a while. Consider using the --notify global option. [ok]
> Installation complete. User name: root User password: root [ok]
> Congratulations, you installed Drupal!
>
> After refreshing the page http://dev I still dont see the new site I setup. Any idea?

> Villorente Gerald • 4 months ago
>
> After running docker ps. I resorted to running like this and it works.
>
> $ drush -y site-install --db-url=mysqli://container:container@0.0.0.0:32775/bud --account-name=root --account-pass=root

> Omar SALLAH • a year ago
>
> Hi , I have followed all those steps, but when i had finished , i have got 502 bad gateway nginx/1.10.1
>
> can anyone help me ? thanks

> Tomáš Fülöpp • 2 years ago
>
> How to go about installing local multisites? Database can be easily added via phpMyAdmin, but how about the necessary vhost entry that needs to point to the same Drupal site installation.

> viljaste • 2 years ago
>
> Hi Tomáš,
> 
>There is an environment variable called VHOST_DOMAIN_ALIASES that you can use to specify additional DNS entries for your project.
>
> ```
> apache:
>   extends:
>     file: host.yml
>     service: apache
>   image: dockerizedrupal/apache-2.4:1.2.2
>   hostname: apache
>   volumes_from:
>     - apache-data
>   links:
>     - php
>   environment:
>     - VHOST_PROJECT_NAME=my-project
>     - VHOST_PRIMARY_SERVICE=True
>     - VHOST_SERVICE_NAME=apache
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-apache-2.4/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/apache-2.4/
>     - VHOST_DOMAIN_ALIASES=my-multisite-1,my-multisite-2,my-multisite-3
> ```

> Tomáš Fülöpp • 2 years ago
>
> Works like a charm! Please document that as well on this site so that others can find it.

> Tomáš Fülöpp • 2 years ago
>
> Another problem I've ran into. In the folder that holds all Drupal sites I run a .sh script containing mysqldump to backup databases of running containers. I am happy to manually list the db names etc. But host name "mysql" or "localhost" or "127.0.0.1" do not work there. The only thing that works is looking up each db IP address via their phpMyAdmin and setting it into the .sh script. That I cannot do because the IP addresses are not fixed.
>
> Do you see any way how to alias or extract IP address from each running MySQL for a script like this?

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> The following shell script will give you the list of IP addresses for all your MySQL containers:
>
> ```
> #!/usr/bin/env bash
>
> shopt -s nullglob
>
> mysql_containers() {
>   echo "$(docker ps -a | grep _mysql_ | awk '{ print $1 }')"
> }
>
> CONTAINERS="$(mysql_containers)"
>
> if [ -n "${CONTAINERS}" ]; then
>   for CONTAINER in ${CONTAINERS}; do
>     CONTAINER_NAME="$(docker inspect --format='{{.Name}}' ${CONTAINER} | cut -c 2-)"
>     CONTAINER_IP="$(docker inspect --format='{{.NetworkSettings.IPAddress}}' ${CONTAINER})"
>
>     echo "${CONTAINER_NAME}" "${CONTAINER_IP}"
>   done
> fi
> ```
>
> Using mysqldump however requires that the MySQL server you are 

> Tomáš Fülöpp • 2 years ago
>
> Thanks, Jürgen, that helped a lot. Eventually I used "docker start ${CONTAINER_NAME}" followed by "sleep 10" to make sure the mysql container is running, and then I used mysqldump with ${CONTAINER_IP} for their IP addresses.
> Not so elegant but simple and perfectly satisfactory for regular backups of all databases!

> Tomáš Fülöpp • 2 years ago
>
> Problem: quite often when I want to start up existing local sites (using "docker-compose up -d"), they just show an error because they cannot connect to their database. What happens is that while their database is intact and running, its IP address is every time different. 
> Is there some standard alias that we can use for each local site without regards to its IP address?

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> There are two ways how you could approach this:
> 
> 1) You can either use "127.0.0.1" or "localhost" as a hostname in your settings.php file to connect to your MySQL instance with Drupal.
> 2) Or you can use "mysql" as a hostname, which is an automatically generated alias to your MySQL instance IP address when you start your project containers.
> 
> I suggest using option 2, because the convenience of option 1 comes at the expense of small performance loss, which you can read more about here [https://github.com/dockeriz...](https://github.com/dockerizedrupal/drupalcamp-baltics-2015) in the "Networking made easy" section.
>
> If you are interested in how Docker networking itself works in more detail, then I recommend reading this article [https://docs.docker.com/eng...](https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/)

> Tomáš Fülöpp • 2 years ago
>
> Excellent, "mysql" as hostname in settings.php works like a charm! Please put it into this documentation!

> Lenivetz • 2 years ago
>
> docker-compose up -f in site directory doesn't start containers. In help message there's no such argument as -f. 
> Maybe it should be -d (detached)?

> viljaste • 2 years ago
>
> Hey Lenivetz, you are absolutely correct, this is a typo. Thank you for bringing this up!

#### Deleting an existing project permanently

To delete an existing Drupal project permanently you simply have to follow these steps:

1) Go to your project directory.

    ```bash
    $ cd /var/www/drupal
    ```
    
2) Delete Docker containers and volumes associated with the project.

    ```bash
    $ docker-compose rm -vf
    ```
    
3) Delete project files.

    ```bash
    $ rm -rf /var/www/drupal
    ```

**Comments**

> Simon Bonsor • a year ago
> 
> You might need to stop the docker containers before doing steps 2 and 3: otherwise you will not be allowed to delete the project files. Also you might need to chmod 777 the .htaccess files and settings.php to delete them (tested with drupal 8.1.1)

#### Switching to a different PHP version

To change the PHP version, simply execute the following command in your project directory:

```bash
$ drupal-compose service php set version <VERSION>
```

Supported PHP versions:

```
5.2
5.3
5.4
5.5
5.6
```

Watch the following video to see it in action:

[![Tutorials: Switching to a different PHP version](http://img.youtube.com/vi/aUfJOrj5p6w/0.jpg)](http://www.youtube.com/watch?v=aUfJOrj5p6w)

**Comments**

> Dezső BICZÓ • a year ago
>
> What is the reason of missing PHP 7 support? Is the a scheduled date for a release or not yet?

> viljaste • a year ago
>
> Hey Dezső BICZÓ
>
> There now is PHP 7 Docker image available, only extensions that aren't currently supported are MSSQL, APCU and APD. Everything else that works in PHP 5.6 image works also for PHP 7.
>
> The latest stable version for PHP 7 Docker image is dockerizedrupal/php-7.0:1.1.0
>
> If you would like to switch your PHP version with Drupal Compose, please update it to version 1.4.1 first.

> Dezső BICZÓ • a year ago
>
> Thank you viljaste , I'll try it out soon.

> viljaste • a year ago
>
> PHP 7 support will be coming soon (exact date is not specified), the reason why it's still delayed is because some of the essential extensions are not fully tested with PHP 7 yet.

> Alex • a year ago
>
> Hi! How can I install php extensions to current php version?

> viljaste • a year ago
>
> Hi Alex,
>
> Since the project is still young in terms of how many people are using it, there actually hasn't been any requests before using different extensions that are already supported. In addition to that the idea allowing to use different extensions and being able to configure them conflicts with the main idea about this project, that every configuration option has to be in Docker Compose file and not external.
>
> But in which extension are you interested in?

#### Increasing or decreasing the PHP memory limit

[![Tutorials: Increasing or decreasing the PHP memory limit](http://img.youtube.com/vi/q9Gn_4h0i08/0.jpg)](http://www.youtube.com/watch?v=q9Gn_4h0i08)

**Comments**

> kovtunos • 4 months ago
>
> How this can be done to mysql? 
> For example: max_allowed_packet = 64M
> Adding: MAX_ALLOWED_PACKET="64M" to hosts.yml or docker-compose.yml doesn't work.

#### Debugging a project with Xdebug

[![Tutorials: Debugging a project with Xdebug](http://img.youtube.com/vi/nKngjFA6J70/0.jpg)](http://www.youtube.com/watch?v=nKngjFA6J70)

**Comments**

> Niklan • a year ago
>
> ```
> - PHP_INI_XDEBUG=On
> - PHP_INI_XDEBUG_REMOTE_CONNTECT_BACK=On
> - PHP_INI_XDEBUG_IDEKEY=PHPSTORM
> ```

> Niklan • a year ago
>
> How to set xdebug.profiler_output_dir ?
> I tried to set - PHP_INI_XDEBUG_PROFILER_OUTPUT_DIR=/apache/data bu no any result

> Dezső BICZÓ • a year ago
>
> Debugging Drush commands is working by default?

> Tomáš Fülöpp • 2 years ago
>
> Looking forward to read about Xdebug integration!

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> I've put together a short video that shows how to use Xdebug with the Dockerized Drupal setup.

#### Profiling a project with Blackfire

[![Tutorials: Profiling a project with Blackfire](http://img.youtube.com/vi/L130npoZRG8/0.jpg)](http://www.youtube.com/watch?v=L130npoZRG8)

**Comments**

> @iamuser2 • 3 months ago
>
> viljaste 
> Could you please share a detailed video or document for using blackfire.io docker image to profile a page from CLI. I am struggling a lot You can share resource to my email also.
> Thanx.

> Tomáš Fülöpp • 2 years ago
> 
> Looking forward to read about Blackfire integration!

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> I've put together a short video that shows how to profile Drupal with Blackfire in the Dockerized Drupal setup.

#### Working in a multi-site environment

**Comments**

> Derek • a year ago
>
> There is no content about this topic on this page, so I am copying over some content from a comment I found on this site:
>
> Q: How to go about installing local multisites? Database can be easily added via phpMyAdmin, but how about the necessary vhost entry that needs to point to the same Drupal site installation.
>
> A: There is an environment variable called VHOST_DOMAIN_ALIASES that you can use to specify additional DNS entries for your project.
>
> ```
> apache:
> extends:
> file: host.yml
> service: apache
> image: dockerizedrupal/apache-2.4:1.2.2
> hostname: apache
> volumes_from:
> - apache-data
> links:
> - php
> environment:
> - VHOST_PROJECT_NAME=my-project
> - VHOST_PRIMARY_SERVICE=True
> - VHOST_SERVICE_NAME=apache
> - VHOST_VERSION_FILE_URL=https://raw.githubuserconte...
> - VHOST_REPOSITORY_URL=https://hub.docker.com/r/do...
> - VHOST_DOMAIN_ALIASES=my-multisite-1,my-multisite-2,my-multisite-3
> 

#### Connecting to MySQL database with an external tool

To get a project MySQL container IP address, which you can use to connect with any external tool, simply execute the following command:

```bash
$ docker inspect --format '{{ .NetworkSettings.IPAddress }}' myproject_mysql_1
```

**Comments**

> Morten Trøjborg Willadsen • a year ago
>
> Hello and thanks for making Dockerized Drupal ;)
>
> Is there any way to initialize a new database with the same name as the project itself upon creating the containers?
>
> Kind regards

> viljaste • a year ago
>
> Hey Morten,
>
> Unfortunately this specific functionality is not currently supported. I've created a new ticket in GitHub [https://github.com/dockeriz...](https://github.com/dockerizedrupal/mysql-for-docker/issues/9) for that. If we'll come up with any solution or conclusion we'll keep you updated there.

> Bryden Arndt • a year ago
>
> This tutorial is amazing. One thing lacking is an explanation of how to use drush with dockerizedrupal. Is there any easy way to do this? Right now I'm running drush on my dockerizedrupal projects like this:
>
> docker run -v $(pwd):/app drush/drush 'en' '-y' 'xmlsitemap'
>
> That gets a bit cumbersome, and it fails if I run it in sub folders of the drupal project. Do you have any tricks to make that command a bit more compact?

> viljaste • a year ago
>
> Hey Bryden Arndt,
>
> We actually have created Crush for that exact purpose. It's a wrapper for Drush that tries to proxy your Drush command from your host to inside the container. Keep in mind that most of the functionality that Drush provides works, but not all of them, but we are working on that issue.
>
> You can find the installation instructions here [https://dockerizedrupal.com...](https://dockerizedrupal.com), if you already have Drush installed on your host, then skip the last instruction and use Crush instead, because the last command creates an alias to Crush with the same name as Drush.
>
> If you need more information regarding Crush, then you can read more about it here [https://github.com/dockeriz...](https://github.com/dockerizedrupal/drupalcamp-baltics-2015).

### Frequently asked questions

Here we have listed all the common questions and answers from various people that we thought are useful to document and share with others.

**Comments**

> Niklan • a year ago
>
> Hi.
>
> I tried to use Drupal Console, all works fine, but only one thing confusing me. All files created by drupal console in container has root owner and group. How can i change it. In host.yml all values is 1000 as my `echo $UID`

> viljaste • a year ago
>
> Hi Niklan,
>
> To have the right permissions generated by Drupal Console for your project inside the PHP container you can simply switch to user called container which have the same user and group ID as your host user by executing the following command:

> Niklan • a year ago
>
> Where i can find Apache error logs? I found how to connect into container
>
> ```
> sudo docker exec -i -t CONTAINER_ID /bin/bash
> ```
>
> but for apache container /var/log/apache2/ is not contain any of error.log and access.log

> Martin Ant • a year ago
>
> Hey,
>
> Have you tried docker logs command ? You can specify apache container if that's all you want to see.
>
> [https://docs.docker.com/eng...](https://docs.docker.com/engine/reference/commandline/logs/)

> Niklan • a year ago
>
> Hello, thank you, this is good command, i didn't know about it. But for apache container i get only access.log, for php container some info about memcached running, but i have problem on project, and trying to working one add typo to the code, and logs shows nothing. I checked phpinfo() and log_erros is on, how to access error.log information?

> viljaste • a year ago
>
> Hey Niklan,
>
> Could you please provide your docker-compose.yml file so we could also debug it? And which Drupal version you are using currently?

> Niklan • a year ago
>
> Hi,
>
> I still need help with this problem. I using docker logs -f CONTAINER_php_1 and last logs contains this, but there is not php errors :(
> 
> ```
> ...
> 2016-09-27 08:05:26,008 INFO supervisord started with pid 354
> 2016-09-27 08:05:27,010 INFO spawned: 'mysql-2' with pid 357
> 2016-09-27 08:05:27,011 INFO spawned: 'mysql-3' with pid 358
> 2016-09-27 08:05:27,012 INFO spawned: 'mysql-1' with pid 359
> 2016-09-27 08:05:27,195 INFO spawned: 'postfix' with pid 360
> 2016-09-27 08:05:27,196 INFO spawned: 'cron' with pid 361
> 2016-09-27 08:05:27,197 INFO spawned: 'logs_cron' with pid 362
> 2016-09-27 08:05:27,197 INFO spawned: 'php' with pid 363
> 2016-09-27 08:05:27,198 INFO spawned: 'memcached' with pid 364
> 2016-09-27 08:05:27,199 INFO success: postfix entered RUNNING state, process has stayed up for > than 0 seconds (startsecs)
> Starting Postfix Mail Transport Agent: postfix2016-09-27 08:05:28,334 INFO success: mysql-2 entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: mysql-3 entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: mysql-1 entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: cron entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: logs_cron entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: php entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> 2016-09-27 08:05:28,334 INFO success: memcached entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
> . 
> 2016-09-27 08:05:28,852 INFO exited: postfix (exit status 0; expected)
> [27-Sep-2016 08:05:28] WARNING: Nothing matches the include pattern '/usr/local/src/phpfarm/inst/php-5.4.45/etc/fpm.d/*.conf' from /usr/local/src/phpfarm/inst/php-5.4.45/etc/php-fpm.conf at line 15.
> ```

> Niklan • a year ago
>
> Hi viljaste,
>
> I use Drupal 7 and this is my docker-compose.yml
> 
> ```
> # Configuration generated with Drupal Compose version 1.3.2
> apache:
>   extends:
>     file: host.yml
>     service: apache
>   image: dockerizedrupal/apache-2.4:1.2.3
>   hostname: apache
>   volumes_from:
>     - apache-data
>   links:
>     - php
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_PRIMARY_SERVICE=True
>     - VHOST_SERVICE_NAME=apache
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-apache-2.4/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/apache-2.4:1.2.3
> apache-data:
>   image: dockerizedrupal/apache-2.4:1.2.3
>   hostname: apache-data
>   entrypoint: ["/bin/echo", "Data-only container for Apache."]
>   volumes:
>     - .:/apache/data
> mysql:
>   image: dockerizedrupal/mysql:1.2.2
>   hostname: mysql
>   volumes_from:
>     - mysql-data
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=mysql
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-mysql/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/mysql/
> mysql-data:
>   image: dockerizedrupal/mysql:1.2.2
>   hostname: mysql-data
>   entrypoint: ["/bin/echo", "Data-only container for MySQL."]
>   volumes:
>     - /mysql
> php:
>   extends:
>     file: host.yml
>     service: php
>   image: dockerizedrupal/php-5.6:1.2.9
>   hostname: php
>   volumes:
>     - ~/.ssh:/home/container/.ssh
>   volumes_from:
>     - apache-data
>   links:
>     - mysql
>     - mailcatcher:smtp
>     - memcached
>   environment:
>     - DRUPAL_VERSION=7
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=php
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-php-5.6/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/php-5.6:1.2.9
> mailcatcher:
>   image: dockerizedrupal/mailcatcher:1.1.1
>   hostname: mailcatcher
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=mailcatcher
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-mailcatcher/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/mailcatcher/
> phpmyadmin:
>   image: dockerizedrupal/php-5.6:1.2.9
>   hostname: phpmyadmin
>   links:
>     - mysql
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=phpmyadmin
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-phpmyadmin/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/php-5.6:1.2.9
> adminer:
>   image: dockerizedrupal/adminer:1.1.1
>   hostname: adminer
>   links:
>     - mysql
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=adminer
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-adminer/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/adminer/
> memcached:
>   image: dockerizedrupal/memcached:1.1.0
>   hostname: memcached
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=memcached
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-memcached/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/memcached/
> memcachephp:
>   image: dockerizedrupal/memcachephp:1.1.1
>   hostname: memcachephp
>   links:
>     - memcached
>   environment:
>     - VHOST_PROJECT_NAME=dving
>     - VHOST_SERVICE_NAME=memcachephp
>     - VHOST_VERSION_FILE_URL=https://raw.githubusercontent.com/dockerizedrupal/docker-memcachephp/master/VERSION.md
>     - VHOST_REPOSITORY_URL=https://hub.docker.com/r/dockerizedrupal/memcachephp/
> ```

> Niklan • a year ago
>
> I'am dropped in issue. vhsot stopped working. I do not know what happens, but drupal-compose and docker-compose work correctly, but http://dev/ and project url not working at all. When i tried to access any page i get ERR_CONNECTION_REFUSED. This happens after i changed php version from default to 5.3. I tried to change to any other PHP version 5.4, 5.5, 5.6 - same story.

> Martin Ant • a year ago
>
> Hi,
>
> There is a know bug with vhost container. The vhost service won't automatically start and you have to start it manually by navigating into the vhost container.

> Niklan • a year ago
>
> Hi, Martin. Thank you for answer. How can i do it on Ubuntu?
>
> I tried docker-compose -f /opt/vhost.yml up -d and get this.
>
> ```
> docker-compose -f /opt/vhost.yml up -d
> Starting opt_vhost-data_1
> Starting opt_vhost_1
> 
> ERROR: for vhost  rpc error: code = 6 desc = "mkdir /run/containerd/39935dd30d8e6807d8adaad3f8a73b6f30b0cd705e7ee3662e214480ebac472a: file exists"
> Traceback (most recent call last):
>   File "<string>", line 3, in <module>
>   File "compose/cli/main.py", line 63, in main
> AttributeError: 'ProjectError' object has no attribute 'msg'
> docker-compose returned -1
> ```
>
> But then i tried
> 
> ```
> docker-compose -f /opt/vhost.yml up -d --force-recreate
> ```
>
> and container starts well. But if i do the same with currently existing container with data, I loose it or it's safe command?
> 
> P.s. doing this code seems works on all docker containers, not currently working on. So all containers starts working without losing data.

> Martin Ant • a year ago
>
> Sorry I didn't specify, my answer was regarding vagrant vhost. I guess your problem is solved for now ?

> Niklan • a year ago
>
> Yes, my problem is sloved by
>
> ```
> docker-compose -f /opt/vhost.yml up -d --force-recreate
> ```

> Martin Ant • a year ago
>
> According to this
> [https://docs.docker.com/com...](https://docs.docker.com/compose/reference/up/)
>
> I would say that '--force-recreate' flag should be safe as it would just enforce the default 'docker-compose up -d' behavior. And if that solves your issue then I would go with that for now.
>
> "If there are existing containers for a service, and the service’s configuration or image was changed after the container’s creation, docker-compose up picks up the changes by stopping and recreating the containers (preserving mounted volumes)."
>
> note the "preserving mounted volumes" part.

> Derek • a year ago
>
> I guess I am the only person with questions. I am wondering if I'm in the Twilight Zone.

#### Where to get help?

The fastest way to get support is to join our [IRC channel](http://webchat.freenode.net/?channels=dockerizedrupal) where other people in the community can help you solve your particular problem at hand.

**Comments**

> Derek • a year ago
>
> I take it there is no "Second fastest" way?

### Tips & Tricks

> Niklan • a year ago
>
> If you want to use Drupal Console.
>
> ```
> docker exec -it PROJECTNAME_php_1 bash -l
> su -l container
> cd /apache/data
> ```

> Niklan • a year ago
>
> If you have separated disk partition for kernel and home directory, you can be affected by issue i dropped in. On install process i reserve only 30GB for kernel, and it's enough, but docker installs and stores all container data on this partition, and this very fast will be full and cause some problem. Better to move docker container data immediately after installation process. I write all variants here: [https://github.com/Niklan/T...](https://github.com/Niklan/Trash/blob/master/VMs/docker/move_docker_container_data.md) Hope it's help someone.

#### Removing orphaned Docker volumes

Some of you may not know that Docker by default doesn't remove the volumes when you delete a container which is the intentional behavior of Docker to avoid accidental data loss.

Docker version 1.9 and up supports removing orphaned volumes natively:

```bash
$ docker volume rm $(docker volume ls -qf dangling=true)
```

In earlier versions the go to method to remove orphaned volumes was [docker-cleanup-volumes](https://github.com/chadoe/docker-cleanup-volumes).

## Documentation

The place to be if you are interested to know in depth details how to use various tools and workflows.

### Building Docker images

Our philosophy building Docker images is to include every dependency in the source code along side with the Dockerfile.

The primary reason for that is because in practice relying on dependencies that in otherwise would be pulled over the network from a third party server when building a Docker image is prone to errors.

Our experience has shown that on critical times the source may not be available at the time or can be completely gone in other words deleted, which isn't a good thing if you want to have a reliable system.

### Logging

Logging is still unfortunately a work in progress, but much effort has been put into it already so some of the more useful services logs are piped directly to standard output, which means that you can use standard Docker features to access services logs running inside the container.

The goal is to streamline logging and make it more reliable in the future for all services.

### Tools

// TODO

#### Docker Registry

The primary reason why we have built a separate Docker image for Docker Registry is to have a simple solution where we can host our Docker images freely and privately on-premise.

#### Docker images

List of Docker images that are maintained by Dockerized Drupal initiative.

#### vhost

The purpose of vhost is to constantly monitor your development environment and generate a list from all your running containers which are displayed on a single web page that you can access with your web browser on port 80 or 443.

Under the hood inside the container runs Nginx that dynamically generates its configuration from the events that are emitted by the Docker Engine. So if a container dies it will be removed from the Nginx configuration and if a new container is launched a new entry will be added to the configuration.

So by using this tool all your multi-container Drupal projects running on your development machine are easily accessible through DNS.

**Comments**

> Jowan Parker • 5 months ago
>
> How do I use this without vhost ?
>
> I have developed my docker and want to spin up the docker-compose with vhost on localhost ?

> Tomáš Fülöpp • a year ago
>
> Still the same problem, now with vhost:1.1.7.
> I always have to run "docker-compose -f /opt/vhost.yml up -d" after starting Vagrant.
>
> After starting Vagrant, this is what I get when I run your command:
>
> vagrant@dev:~$ ps -A |grep docker
> 957 ? 00:00:25 docker

> Frederick Henderson • a year ago
> @Tomáš Fülöpp Hi! That all looks good and the vhost.yml has the line:
> restart: always
> so it should try and start when Docker starts. So, I guess the question is, does Docker start automatically when your vagrant box starts?
>
> Run
> ```
> ps -A |grep docker
> ```
> in a terminal on the virtual machine to see if it is running after startup.

> Tomáš Fülöpp • a year ago
> In v0.4.8 we have a problem with vhost -- it does not run after vagrant up. The system is accessible via SSH, pings get responses, but there is no web interface.
>
> At [https://dockerizedrupal.com...](https://dockerizedrupal.com) I've seen that it can be started by:
> docker-compose -f /opt/vhost.yml up -d
> So this is what I do every time I boot up vagrant, but obviously it's a problem.
>
> Any idea why does vhost not start automatically?

##### Environment variables available to Docker containers

A list of environment variables available to Docker containers to configure vhost behaviour.

###### VHOST_PROJECT_NAME

The **VHOST_PROJECT_NAME** environment variable is there to group different Docker containers together that are displayed in vhost as single group.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_PROJECT_NAME.png "Image")

**Comments**

> Віктор Щербак • a year ago
>
> sorry? after installation drupal I have error 502 Bad Gateway nginx/1.8.1
> what is a problem&

> umarzaffer • a year ago
>
> Hopefully you should have figured it out till now. If not, then here is my experience with the same issue. I basically faced the same issue because of improper permissions. Make sure that the project files that you have created are NOT created as a ROOT user. Hope that helps.

###### VHOST_PRIMARY_SERVICE

If you want to specify a primary service/container that is displayed on the top of the page within the context of a project group, you can set the **VHOST_PRIMARY_SERVICE** variable to **True** on that container.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_PRIMARY_SERVICE.png "Image")

###### VHOST_SERVICE_NAME

The **VHOST_SERVER_NAME** environment variable is just there to give you an option to properly label your services by their purpose or a like.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_SERVICE_NAME.png "Image")

###### VHOST_VERSION_FILE_URL

The **VHOST_VERSION_FILE_URL** environment variable helps vhost determine if a particular service has an update available and if so, displays it to the user.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_VERSION_FILE_URL.png "Image")

**Comments**

> Tomáš Fülöpp • 2 years ago
>
> I see that an update is available to both mysql and php. Should I apply it and how? Will it have impact on already installed local websites?

> viljaste • 2 years ago
>
> Hi Tomáš,
>
> The idea is to only update project images if you need any particular feature or functionality that isn't provided by the older/current image.
> 
> One of the reasons why I personally like Docker so much is that you can very easily give a version number to your "configuration" which at the same time is still fairly manageable.
> 
> In a sense this allows you to create a snapshot in the form of a docker-compose.yml file from your environment configuration for your Drupal project which you can commit to VCS alongside with your project source code. So if for whatever reason you have to continue developing your project in the future, you can be sure that the configuration you used originally is still there and the project behaves exactly the same. It also helps you to almost completely eliminate the waste you would normally have when setting up a development environment for your project.
> 
> But if you want to change the image version for a particular service, then in the near future we will be adding that functionality to Drupal Compose, which will do most of the work automatically in the background, but in the meantime you have to do it manually as follows:
> 
> 1) Click on the "New version is available!" link, it will take you to the Docker image "Repo Info" page on Docker Hub;
> 2) Navigate to "Tags" page, where you see all the available versions/tags for that image;
> 3) Open docker-compose.yml file and change the image version/tag to a version that suits your needs, for example if you see lines like this:
> 
>   ```
>   mysql:
>     image: dockerizedrupal/mysql:1.2.1
>     hostname: mysql
>     volumes_from:
>     - mysql-data
>   ```
>
>   Change the image tag from 1.2.1 to 1.2.2 (which is currently the latest MySQL image version) so the changed configuration would look like this:
> 
>   ```
>   mysql:
>     image: dockerizedrupal/mysql:1.2.2
>     hostname: mysql
>     volumes_from:
>     - mysql-data
>   ```
>
> 4) Once you have happy with the changes, you will need to restart your project containers with Docker Compose which will recreate the environment according to the configuration specified in the docker-compose.yml file.
> 
> NB! According to the Docker Support there currently is a known issue with the tags page which doesn't display recently added tags on Docker Hub. So until they will come up with a fix for that, to get the latest image version, you can navigate from Docker image "Repo Info" page to project “Source Repository” on GitHub, and from there go to “Releases” page, where you can see all the releases for that image which you can use to specific your Docker image version in your docker-compose.yml file.

###### VHOST_REPOSITORY_URL

The **VHOST_REPOSITORY_URL** environment variable only exists for a convenience, so a user can quickly go a service's home page where he could find more info about that particular service.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_REPOSITORY_URL.png "Image")

###### VHOST_DOMAIN_ALIASES

The **VHOST_DOMAIN_ALIASES** environment variable enables you to define custom domains for your service.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/VHOST_DOMAIN_ALIASES.png "Image")

##### HTTP Basic Authentication

If you need to restrict the access to vhost or to services running on your host you can enable HTTP Basic Authentication for that.

There are multiple ways how you control the authentication behaviour using vhost.

Firstly you can enable HTTP Basic Authentication globally, which means you have a single username and password protecting access to vhost itself and all the services running on your host.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Authentication_1_0.png "Image")

Secondly you can enable HTTP Basic Authentication globally and override the username and password for a specific service.

![Image](https://raw.githubusercontent.com/dockerizedrupal/documentation/master/images/Authentication_2.png "Image")

Thirdly you can enable HTTP Basic Authentication globally and disable HTTP Basic Authentication for a specific service.

// TODO - Indicator in the interface and once that done, add the screenshot to the documentation

There is also an option to set a random password for all the services, which still gives you an option to override or disable the authentication per service. In this mode the default username for a service will be the value of its service name specified by the **VHOST_SERVICE_NAME** environment variable

## Community

Our strong belief is that a project without a strong community is doomed to fail, so our goal in addition to developing awesome tools to make Drupal development experience better is to create a strong and supportive community around it.

### Contributing to Dockerized Drupal initiative

Since Dockerized Drupal initiative is still quite young in terms of being open to public, the best place to start contributing to this project at this stage is to be active in our IRC channel by providing support for others or by asking help for a particular issue at hand yourself.

You could also create a feature request or report a bug directly in [GitHub](https://github.com/dockerizedrupal).

### Chat (IRC)

The quickest way to contact us and with the rest of the community members to get help is through [IRC (Internet Relay Chat)](https://en.wikipedia.org/wiki/Internet_Relay_Chat).

If you don't have an IRC client already installed on your computer then you can use a web based IRC client to quickly join our IRC channel [#dockerizedrupal](http://webchat.freenode.net/?channels=dockerizedrupal) on [freenode](http://freenode.net/).

## License

**MIT**
