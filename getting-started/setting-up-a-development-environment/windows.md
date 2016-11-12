# Windows

You may know or not know that Docker Engine only runs natively on Linux. For that reason we are currently working on making the workflows and the tools provided by the Dockerized Drupal initiative to work seamlessly on Windows operating system as well.

To accomplish that we have included [Vagrant](https://www.vagrantup.com/) to our toolset as a wrapper for the Dockerized Drupal initiative tools to be able to run them on operating systems other than Linux.

## Comments

`Tomáš Fülöpp • 5 months ago`

> Docker for Windows (D4W) now runs nicely on Windows thanks to Hyper-V ( [https://beta.docker.com/docs/w...](https://beta.docker.com/docs/windows/getting-started/) ). No VirtualBox or Vagrant needed.

> How can I run DockerizeDrupal environment under D4W? I am able to start individual sites using "docker-compose up -d" but then it is not clear on what IP they run etc., so I am clearly missing something.

***

`Tomáš Fülöpp • 8 months ago`

> This is the best recipe to set up a fairly complete local Drupal development environment even on Windows. Great work guys! Looking forward to see the documentation to grow!

***

`viljaste • 8 months ago`

> Hi Tomáš,

> Thanks! We will try our best to improve the documentation, as we think that this is the most important component to get right if we want to make this initiative and tools easily available to others.
