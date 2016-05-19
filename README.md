#Intel Edison Quick Start Guide
First install Ubilinux in Intel Edison (I did it because Ubilinux is more manageable than Yocto and can have an updated version of Node.js running).

##Installing Ubilinux
Go to this link and follow the instructions:

[Installing Ubilinux on Edison](https://learn.sparkfun.com/tutorials/loading-debian-ubilinux-on-the-edison)

NOTE: Better use vi than nano when editing /etc/network/interfaces, nano gave me some strange errors.

After the installation is complete run

	$ apt-get update

In order to avoid space problems I suggest deleting "edison" user by running

	$ deluser --remove-home edison
	
And then you always use the "root" user.

##Configuring NVM
NVM stands for Node Version Manager. It's used for having various installations of Node without conficts and without having to run some npm commands with sudo.

Before installing check if you have a .bashrc file in your home folder, if you don't create it by running:
	
	$ touch .bashrc

Go to this link and run the command to install:

[Installing NVM](https://github.com/creationix/nvm)

It's a simple command like:

	$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
	
Then logout from terminal running

	$ exit
	
Login again and run

	$ command -v nvm
	
If you see nvm you got it installed right.

###Troubleshooting
Sometimes Ubilinux nano text editor fails to edit or display correctly a file. If you have problems in editing files (to edit the ip config file for example) I suggest using vi editor, some helpful commands are listed here

To open a file in vi run

	$ vi <filename>

- To edit a file press "i" (you enter the edit mode)
- To save a edited file first press "Esc" to exit edit mode and then press "ZZ" (z in mayus)
- To discard changes done to a file and exit Vi first press "Esc" to exit edit mode and then press ":q" 


##Installing Node.js with NVM
To see the versions of Node available to install run

	$ nvm ls-remote
	
Then select you favorite version (4.4.4 LTS in my case), copy the name of the version, then run

	$ nvm install v4.4.4
	
After that I suggest to install the minimum npm packages to run a project created by Angular Fullstack generator, run

	$ npm install -g bower grunt-cli
	
There you have their github [Angular Fullstack Generator](https://github.com/angular-fullstack/generator-angular-fullstack)

To see Node versions installed run

	$ nvm ls
	
To use a specific version of Node run

	$ nvm use <selected Node version>

###Troubleshooting
	
If you want to use a project created with angular fullstack you may have problems when exctracting "phantomJS", you can fix it by installing

	$ apt-get install bzip2
	
(NOT WORKING YET) If you have problems with xdg-open you can fix it by running

	$ apt-get install xdg-utils
	
Bower can give you problems when running it in root mode, I personally recommend to use it by running

	$ bower install --allow-root
	


##Helpful commands
To know how much space is available in you Edison run

	$ df -h
	
To know how much space is used by a directory run

	$ du -hs
	
To reboot the Intel Edison run

	$ reboot
	
To acces the Intel Edison by ssh run
	
	$ ssh root@<EdisonIpDirection>

