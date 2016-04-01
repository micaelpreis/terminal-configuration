# terminal_configuration
### Tutorial - How to Set Up Terminal on Mac

Having to work everyday with the Mac OS X Terminal and my desire of having everything simple, quick and intuitive was what made me spend some time trying to configure my Terminal. And if you are anything like me this tutorial is for you. 

This is how my Terminal is currently configured.

---

Image Home ![Terminal]()

Image Git

Image Folder and Ls

Image Shortcuts

---

In this tutorial I will show you how to set up your Terminal on Mac OS X just like mine. 

To do so, just follow these easy steps below.

### 1. Edit Terminal Preferences

First, start by openning **Terminal**, go to Preferences and perform this changes:

* In General, set Homebrew as your default profile on startup;
* In Profiles, click on Homebrew and set him as default;
* Set the font to 'Monaco 12 pt';
* Set the color for 'Text' as white;
* Check all boxes on 'Text' definitions.

### 2. Create bash_profile File

To create the bash_profile file start by opening the app **Terminal** on your Mac and run the following command.
	
	touch ~/.bash_profile

Now that the file is created just open it by typing the next command.

	open ~/.bash_profile

You can now start configuring your Terminal

### 3. Set Up Prompt And Terminal Colors

Paste the following commands on the file.

	# COLORS
	NOCOLOR="\[\033[0m\]"
	BLACK="\[\033[0;30m\]"
	RED="\[\033[0;31m\]"
	GREEN="\[\033[0;32m\]"
	YELLOW="\[\033[0;33m\]"
	BLUE="\[\033[0;34m\]"
	PURPLE="\[\033[0;35m\]"
	CYAN="\[\033[0;36m\]"
	WHITE="\[\033[0;37m\]"

	# COLORS BOLD
	B_BLACK="\[\033[1;30m\]"
	B_RED="\[\033[1;31m\]"
	B_GREEN="\[\033[1;32m\]"
	B_YELLOW="\[\033[1;33m\]"
	B_BLUE="\[\033[1;34m\]"
	B_PURPLE="\[\033[1;35m\]"
	B_CYAN="\[\033[1;36m\]"
	B_WHITE="\[\033[1;37m\]"

	# EDIT TERMINAL
	export CLICOLOR='true'
	export LSCOLORS=gafxcxdxbxegedabagacad
	export PS1="$B_GREEN\u@:$B_BLUE\w $B_BLUE\$$B_WHITE"

Now when you start a new window, you will have a beautiful and intuitive Terminal.

**Note:** If you want to change the way prompt is configured, you can check the step 7 of this tutorial.

### 4. Shortcuts

Adding shortcuts is something relatively simple and easy to do. They follow a simple pattern:

	alias desired_command = 'original_command'
	
Here are some of my shortcuts that I find really helpful. Just paste them on your bash_profile file if you want to use them.

	# GLOBAL SHORTCUTS
	alias cd.='cd ..'   				# Go back 1 directory level (for fast typers)
	alias cd..='cd ../../'   			# Go back 2 directory levels
	alias cd...='cd ../../../'  		# Go back 3 directory levels
	alias edit='subl'               	# Edit files in sublime text
	alias sublime='subl'            	# Open files with sublime text
	alias h='cd ~'                  	# Go To Home Folder
	alias c='clear'                 	# Clear terminal display

	# GIT SHORTCUTS
	alias gs='git status'				# Git Status
	alias gss='git status --short'		# Git Status (short way)
	alias ga='git add .'				# Git Add
	alias gc='git commit -m'			# Git Commit (you still need to write the commit message in front of the command) (ex: 'gc "commit message"')
	alias gp='git push origin'			# Git Push (you still need to write the branch in front of the command) (ex: 'gp development')
	alias gl='git log --decorate -2' 	# Git Log (you can still change the number of logs to show) (ex: 'gl -5')
	alias gls='git shortlog -2' 		# Git ShortLog (you can still change the number of logs to show) (ex: 'gls -5')

Other thing that I find really useful is to set up shortcuts for all my projects. For instance, for this specific project I created a shortcut that takes me directly to the project home folder. 

	# PROJECTS SHORTCUTS
	alias tc='cd ~/Documents/Projects/terminal_configuration' 		# Go To Project 'Terminal Configuration'

This way I don't take a long time writing the path to the folder, since I just need to type a simple keyword.

### 5. Git Integration

### 6. Other Configurations

##### Sublime Text

In order for you to be able to open files in sublime directly from you Terminal with the command 'subl', or with the ones that I added in step 4, you have to do two things.

First paste this line on your bash_profile file.

	export PATH=/usr/local/bin:$PATH

Then run the corresponding command on your Terminal and the Sublime Text shortcut will be set.

Sublime Text 2: 
	
	ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl

Sublime Text 3: 
	
	ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl

Now you can open files with Sublime Text on your Terminal.

---

##### Add Date and Time To Prompt

Below, four different configurations of date and time are listed, in case you want to add one of them of create your own to your prompt.

> (2016/04/01 10:21:30)
	
	(\$(date +%Y/%m/%d) \$(date +%H:%M:%S))

> (01/04/16) (10:21:30)
	
	(\$(date +%d/%m/%y)) (\$(date +%H:%M:%S))

> (01/04/2016)

	(\$(date +%d/%m/%Y))

> (10:21)

	(\$(date +%H:%M))

To add them to your prompt just paste them into your PS1, like this:

	export PS1="(\$(date +%H:%M)) $B_GREEN\u@:$B_BLUE\w $B_BLUE\$$B_WHITE"

### 7. Understanding Prompt Configuration
