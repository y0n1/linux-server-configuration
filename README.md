# Introduction
In this project I took a baseline installation of a Linux distribution (e.g. Ubuntu) on a virtual machine (AWS LightSail) and prepared it to host a web application I had previously developed. I also performed related maintainance tasks such as installing updates, securing it from a number of attack vectors and installing/configuring web and database servers.

## Details
IP address|SSH port
----------|--------
3.123.132.22|2200

## The complete URL to my hosted web application.
[Click here](http://3.123.132.22) to see the web-app in action.

## Additional software installed
1. apache2
1. libapache2-mod-wsgi-py3
1. postgresql

## Configuration changes
1. `grader` user
    1. Created a new user called `grader`
    1. Added it to the sudoers list by creating the `etc/sudoers.d/grader` file with the following entry `grader ALL=(ALL) NOPASSWD:ALL`.
1. Firewall setup: 
    1. Block all incoming traffic
    1. Allow all outgoing trafic  
    1. Specific rules:
        1. `2200/tcp ALLOW Anywhere`
        1. `123/tcp ALLOW Anywhere`
        1. `80/tcp ALLOW Anywhere`

## Third-party resources
