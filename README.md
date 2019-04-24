# Laptop
Laptop is a script to set up an macOS laptop for software engineers in your office

It can be run multiple times on the same machine safely. 
It installs, upgrades, or skips packages based on what is already installed on the machine.

## Requirements
We support:

+ macOS High Sierra (10.13)

Older versions may work but aren't regularly tested. Bug reports for older versions are welcome.

## Install
Download the script:

```bash
curl --remote-name https://raw.githubusercontent.com/tsocial/laptop/master/mac
```

Review the script (avoid running scripts you haven't read!):

```bash
less mac
```

Execute the downloaded script:

```bash
sh mac 2>&1 | tee ~/laptop.log
```

Optionally, review the log:

```bash
less ~/laptop.log
```

Optionally, install tsocial/dotfiles.

## Debugging

Your last Laptop run will be saved to ~/laptop.log. 
Read through it to see if you can debug the issue yourself. 
If not, copy the lines where the script failed into a new GitHub Issue for us. 
Or, attach the whole log file as an attachment.

## What it sets up

macOS tools:

+ [Homebrew](https://brew.sh) for managing operating system libraries.
+ [Google Chrome](https://www.google.com/chrome/) for brower
+ [Slack](https://slack.com) for communication
+ [VSCode](https://code.visualstudio.com/) for code editor
+ [Docker](https://www.docker.com/) for container management

Unix tools:

+ [Git](https://git-scm.com/) for version control
+ [OpenSSL](https://www.openssl.org/) for Transport Layer Security (TLS)
+ [Zsh](http://www.zsh.org/) as your shell

Programming languages:

+ [Golang](https://golang.org/) and [Dep](https://golang.github.io/dep/), for running Go source code
+ [Node.js](http://nodejs.org/) and [NPM](https://www.npmjs.org/), for running apps and installing JavaScript packages
+ [Yarn](https://yarnpkg.com/en/) for managing JavaScript packages

## Customize in `~/.laptop.local`

Your `~/.laptop.local` is run at the end of the Laptop script. 
Put your customizations there. For example:

```bash
#!/bin/sh
brew install tig
```

Write your customizations such that they can be run safely more than once. 
See the mac script for examples.
Laptop functions such as `fancy_echo` and `brew_install_or_upgrade` can be used in your `~/.laptop.local`.


Contributing
Edit the mac file. Document in the README.md file. Follow shell style guidelines by using ShellCheck and Syntastic.

```bash
brew install shellcheck
```
