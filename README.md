# Introduction
In this project I took a baseline installation of a Linux distribution (e.g. Ubuntu) on a virtual machine (AWS LightSail) and prepared it to host a web application I had previously developed. I also performed related maintainance tasks such as installing updates, securing it from a number of attack vectors and installing/configuring web and database servers.

## Details
IP address|SSH port
----------|--------
3.123.132.22|2200

## The complete URL to my hosted web application.
I used my own DNS name server for this project. This is the URL: [catalogapp.y0n1.xyz](https://catalogapp.y0n1.xyz).
I've also used [certbot](https://certbot.eff.org) in order to serve my app through `https`.

## Additional software installed
1. apache2
1. libapache2-mod-wsgi-py3
1. postgresql

## Configuration changes
1. *grader* user
    1. Created a new user called *grader*
    1. Added it to the sudoers list by creating the `etc/sudoers.d/grader` file with the following entry `grader ALL=(ALL) NOPASSWD:ALL`.
1. Firewall setup: 
    1. Block all incoming traffic
    1. Allow all outgoing trafic  
    1. Specific rules:
        1. `2200/tcp ALLOW Anywhere`
        1. `123/tcp ALLOW Anywhere`
        1. `80/tcp ALLOW Anywhere`
1. Created a database user called *catalog* with `CREATEDB` permissions only (remote connections are disabled by default).

## Third-party resources
1. [Flask's mod_wsgi deployment guide](https://flask.palletsprojects.com/en/1.1.x/deploying/mod_wsgi/?highlight=apache)
1. [Certbot's user guide](https://certbot.eff.org/lets-encrypt/ubuntuxenial-apache)
