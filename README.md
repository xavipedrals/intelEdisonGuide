#Intel Edison Quick Start Guide
First install Ubilinux in Intel Edison (I did it because Ubilinux is more manageable than Yocto and can have an updated version of Node.js running).

##Installing Ubilinux
Go to this link and follow the instructions:

[Installing Ubilinux on Edison](https://learn.sparkfun.com/tutorials/loading-debian-ubilinux-on-the-edison)

NOTE: Better use vi than nano when editing /etc/network/interfaces, nano gave me some strange errors.

After the installation is complete run

	$ apt-get update

##Configuring NVM
NVM stands for Node Version Manager. It's used for having various installations of Node without conficts and without having to run some npm commands with sudo.

Before installing check if you have a .bashrc file in your home folder, if you don't create it by running:
	
	$ touch .basrc

Go to this link and run the command to install:

[Installing NVM](https://github.com/creationix/nvm)

It's a simple command like:

	$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
	
Then logout from terminal running

	$ exit
	
Login again and run

	$ command -v nvm
	
If you see nvm you got it installed right.


##Installing Node.js
To see the versions of Node available to install run

	$ nvm ls-remote
	
Then select you favorite version (4.4.4 LTS in my case), copy the name of the version, then run

	$ nvm install v4.4.4
	
After that I suggest to install Angular Fullstack generator, run

	$ npm install -g yo grunt-cli gulp-cli bower generator-angular-fullstack
	
There you have their github [Angular Fullstack Generator](https://github.com/angular-fullstack/generator-angular-fullstack)

	


