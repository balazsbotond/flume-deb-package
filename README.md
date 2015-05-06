Apache Flume Debian package
===========================

A Debian package for installing Apache Flume 1.5.2. Works on Ubuntu and Debian.

Building the package
--------------------

Clone the repository:

    git clone https://github.com/balazsbotond/flume-deb-package.git

Build the package using `dpkg-deb`:

    cd flume-deb-package
    dpkg-deb flume_1.5.2-1

This will create a `flume_1.5.2-1.deb` file in the current directory.

Installing the package
----------------------

    dpkg -i flume_1.5.2-1.deb
    apt-get install -f

Using Flume
-----------

Use the file `/etc/flume/flume-conf.properties` to configure your agent

Start the service:

    service flume start

You can stop it with:

    service flume stop

If something goes wrong, inspect the log at `/var/log/flume/flume.log`. `/var/log/syslog` might also contain useful information.