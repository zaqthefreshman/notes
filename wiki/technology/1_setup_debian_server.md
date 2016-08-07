Setup Debian for use as a server
--
This doc assumes the OS has been provisioned for you by some provider.

1. Setup your user
	```
	su
	adduser zaq --shell /bin/bash/
	adduser zaq sudo
	apt-get install sudo
	exit
	```

1. Setup apt
	```
	sudo apt-get install netselect-apt
	netselect-apt -s -n <distro/ eg. jessie >
	sudo mv sources.list /etc/apt/sources.list
	```

1. (Optional) Get [Go](https://golang.org/dl/)
	```
	sudo tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz
	```

1. Install useful programs
	```
	sudo apt-get install python-pip git curl
	```
