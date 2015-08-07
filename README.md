syssetup
========

script to setup a new system

This is a script customized and originally cloned from github.com:startup-class/setup.git. It supports both interactive and headless install for Mac OS as well as Ubuntu, Redhat, CentOS, Fedora and Cygwin systems. If you intend to run this on a Mac, install the Xcode command line tools prior to executing the curl commands, below. If installing on Windows/Cygwin make sure the base Cygwin system has been installed first (cygwin.com/install.html) along with the curl dependencies.

setup.sh
=========
This setup script offers an interactive menu for setting up and ssh-agent for ssh keys (all private keys associated with .pub keys in ~/.ssh) as well as identifying the system parameters prior to invocation. 

The script has been updated to suport an AngularJS development environment using vim with ctags as well as eslint. The scripts will automatically re-index ctags when working with git repositories.

Run the following from a terminal window on your virtual machine to interactively setup your system:

```sh
curl https://raw.githubusercontent.com/jeffrey-l-turner/syssetup/master/setup.sh > ./setup.sh; bash ./setup.sh
```

Alternatively, you may also use a non-interactive setup using the defaults: 

`curl https://raw.githubusercontent.com/jeffrey-l-turner/syssetup/master/setup.sh | bash`

These defaults for non-interactive setup will not install editors, and are primarily designed for running a headless Node.js system.

After running interactive setup, you may optionally generate ssh keys. Place the public keys (~/.ssh/\*.pub) appropriately within your associated profiles/accounts (e.g. GitHub). 

Test by executing: ```ssh -T git@github.com```; and/or test by executing: ```ssh -vT git@heroku.com```
   *Note: shell request will fail but message will show: "Authentication succeeded (publickey)."*

Logout of shell and log back in to properly setup environment.

Then, execute:
```sh
 ~/.git_template/config.sh 
```
to finish setting up git for ctagging, etc. in the new shell.

See also http://github.com/jeffrey-l-turner/dotfiles

