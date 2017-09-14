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

## License

**MIT**
