# setup-machine
Script to setup a new *nix machine

# Usage
Just execute the `setup-machine` script.

# Limitations
For now, limited to Operating Systems with `apt-get` package manager available. Some programs are built by source but then others rely on `apt-get`; planning to move them as needed.

# Digital Ocean droplet setup

I've started using Digital Ocean. I decided to reuse my setup script to setup the droplet instance. However, there is a bit more that I need to do so here are the instructions:

- Create new droplet (debian, mba ssh keys)
- ssh into droplet as root
- run: `apt update && apt install --assume-yes git && mkdir code && cd code && git clone https://github.com/spraza/setup-machine.git && ./setup-machine/setup-debian`
    - follow instructions
- exit
- locally, run: `scp ~/.ssh/id_rsa* spraza@<rootIp>:~/.ssh/`
- then ssh into droplet as spraza
- then run: `mkdir code && cd code && git clone https://github.com/spraza/setup-machine.git && ~/code/setup-machine/setup-machine-impl`
- that should be it! :)

In order to start the webserver for my blog/website, run: 
- `~/code/setup-machine/start-website`
