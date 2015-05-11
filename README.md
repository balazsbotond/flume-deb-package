Apache Flume Debian package
===========================

A Debian package for installing Apache Flume 1.5.2. Works on Ubuntu and Debian.

**Download the latest pre-built release here:**
https://github.com/balazsbotond/flume-deb-package/releases

Building the package
--------------------

Clone the repository:

    git clone https://github.com/balazsbotond/flume-deb-package.git

Build the package using `dpkg-deb`:

    cd flume-deb-package
    dpkg-deb --build flume_1.5.2-1

This will create a `flume_1.5.2-1.deb` file in the current directory.

Installing the package
----------------------

    dpkg -i flume_1.5.2-1.deb
    apt-get install -f

Using Flume
-----------

Use the file `/etc/flume/flume-conf.properties` to configure your agent. You can use the default settings (Sequence Generator Source and Logger Sink) to quickly test a new installation.

Start the service:

    service flume start

Use `tail -f /var/log/flume/flume.log` to check if everything works correctly. If something goes wrong, `/var/log/syslog` might also contain useful information.

You can stop it with:

    service flume stop
