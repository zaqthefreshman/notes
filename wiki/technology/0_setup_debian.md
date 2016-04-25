Setup Debian
--
I install debian with only the basic tools installed

1. Setup your user
	```
	su
	adduser zaq --shell /bin/bash/
	adduser zaq sudo
	exit
	```

2. Install nessasary programs, now would be a good time to bring in any existing ssh keys or generate them. If you're planning on using the [dotfiles](https://github.com/zaqthefreshman/dotfiles)
	```
	sudo apt-get install xserver-xorg-core i3 git chromium rxvt-unicode-256color vim-nox curl
	```

3. Make Directories
	```
	mkdir ~/scripts
	mkdir ~/projects
	```

4. (Optional) Get [Go](https://golang.org/dl/)
	```
	sudo tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz
	```

5. (Optional) Get [Node](https://nodejs.org/en/download/stable)
	```
	sudo tar -C /usr/local -xzf node

	```

6. (Optional) Get [hub](https://hub.github.com/)
	```
	cd ~/projects
	git clone https://github.com/github/hub.git
	cd hub
	script/build
	mv ./hub /usr/local/bin

	// Will be persisted when dotfiles are brought in
	alias git=hub
	```

7. Bring in dotfiles
	```
	cd ~/projects
	git clone zaqthefreshman/dotfiles

	cd dotfiles/
	sudo cp -R home/zaq /home/

	// You should look at these before you copy them, never good to just copy
	// arbitrary things into your root path
	sudo cp -R etc /
	sudo cp -R usr /
	```

8. Install remaining programs
	```
	sudo apt-get install keychain xsel xfonts-terminus spacefm-gtk3 scrot gksu graphviz keynav python-pip mercurial
	```

9. Install python packages
	```
	// If on mac or well into the future go ahead and try seqdiag first without the
	// version constraint
	sudo pip install pillow==2.7.0
	sudo pip install seqdiag==0.9.4
	```

10. Configure vim
	```
	git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
	vim +PluginInstall +qall
	vim +GoInstallBinaries +qall
	```
11. Optional Install [nvim](https://github.com/neovim/neovim/wiki/Building-Neovim)
	```
    	ln -s ~/.vim ~/.config/nvim
    	ln -s ~/.vimrc ~/.config/nvim/init.vim
	```

11. Build YCM, make sure to remove completer you didn't install the runtimes for
	```
	sudo apt-get install build-essential cmake

	cd ~/.vim/bundle/YouCompleteMe
	./install.py --clang-completer --gocode-completer --tern-completer
	```
