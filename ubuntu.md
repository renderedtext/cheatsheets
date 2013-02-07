# Ubuntu

Add a new user:

    sudo adduser <username>

Add user to sudoers list:

    sudo usermod -a -G sudo <username>

Purge all packages that match some criteria:

    apt-get --purge remove postgresql* 

Fixing remote locale - first add this to your `~/.bash_profile`:

    export LANGUAGE="en"
    export LANG="C"
    export LC_MESSAGES="C"
    export LC_ALL="en_US.UTF-8"

Then run:

    sudo locale-gen en_US en_US.UTF-8
    sudo dpkg-reconfigure locales