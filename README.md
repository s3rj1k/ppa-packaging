Semi-automated script to create binary packages for (multiple version) of Ubuntu/Debian
==============================

Prerequisites
-------------

The following packages needs to be installed in order to build source .deb package:

    sudo apt-get install git build-essential devscripts debhelper dh-make cdbs

Build
-------------

Before build you should set environmental variables below:

    DEBFULLNAME
    DEBEMAIL

    For example:
        export DEBEMAIL="my@emailaddress.com"
        export DEBFULLNAME="Full Name"

To only build source packages only for Debian Jessie:

    make build DISTROS=jessie

To build binary package that can be installed with `dpkg -i <package>.deb`:

    make build DEBUILD=debuild DISTROS=jessie

The build package will be in `<package-folder>/work/<package-name>_<version>.deb`
