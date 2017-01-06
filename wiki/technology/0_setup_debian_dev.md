Setup Debian
--
I install debian with only the basic tools installed. I do not use GRUB and install install refind, you can do before or after install

1. Setup your user
	```
	su
	adduser zaq --shell /bin/bash/
	adduser zaq sudo
	apt-get install sudo
	exit
	```
1. During last installation 2016-12-29 connman was not in debian testing (stretch). Get it from unstable (jessie's is borked with testing dbus). Probably fine if you are from the future
	pre-defined configs go here
	```
	/var/lib/connman/
	```
	useful commands (run as root)
	```
	conmannctl
	rfkill // list and unblock wifi
	ifconfig // -a list interfaces, up <iface> to bring it up (if blocked check rfkill)
	```

1. Install nessasary programs, now would be a good time to bring in any existing ssh keys or generate them. If you're planning on using the [dotfiles](https://github.com/zaqthefreshman/dotfiles)
	```
	sudo apt-get install netselect-apt
	netselect-apt -s -n <distro/ eg. jessie >
	sudo mv sources.list /etc/apt/sources.list
	sudo apt-get install xserver-xorg-core i3 git curl xinit
	```

1. Bring in dotfiles
	```
	cd ~/projects
	git clone zaquestion/dotfiles

	dotfiles/setup.sh
	```

1. If you're having font troubles, more than likely the program is using fontconfig
	```
	FC_DEBUG=1 <program> // Will print font matching information
	```
