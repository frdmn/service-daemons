# start stop services / daemons

I've noticed that there are a lot of failed or non properly working **star/stop scripts** out there. That's why made the decision to build some example or default daemons for the popular distributions/operating systems. In this case our example daemon is Python's `SimpleHTTPServer` which starts an web server on port `80` and serves the current working directory to this web server. The server can easily executed by typing:

    python -m SimpleHTTPServer 8000

## Getting started
### Debian and Ubuntu (sysvinit)

1. Create an own unix user for the desired service/daemon.
1. Ensure the created user has full access to the binary you want to set up. (`/usr/bin/python`)
1. Copy following script to /etc/init.d/: `wget https://github.com/frdmn/asdas/master/raw/debian -O /etc/init.d/debian` (as root)
1. Make sure the script is marked as executable: `chmod +x /etc/init.d/debian`
1. Enable the daemon with `update-rc.d debian defaults`
1. Start with `service debian start`

### Ubuntu (_upstart_)

### CentOS 6 (_sysvinit_)

### Arch Linux (_rc.X_)

### Gentoo (_runscript_)

### Mac OS X (_launchd_)

### Windows (_nssm_)