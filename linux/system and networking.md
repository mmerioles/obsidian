ubuntu filesystem
 / - root
 /bin - essential user binaries
 /sbin - essential binaries to be run by root
 /boot - needed for booting
 /dev - devices in the system
 /etc - config files
 /home - home folders for users
/root - home folder for root user
/media - where removable media should be mounted
/mnt - temporary mount points
/opt - optional software packages, proprietary
/proc - kernel and process files
/tmp - temporarily stores files, deleted after reboot
/run - persistent version of tmp
/srv - contains data for services
/usr - contains read-only apps and files used by users
/var - stores data from /usr directories like logs

trick: (wc is word count)
`ls /bin | wc -l`

`df -h` to see human readable space utilization
`du -sh <directory>` - to see used file space 
Package Management
=
`apt-get update` - refreshes the package information
`apt-get upgrade` - upgrades installed packages
`apt-get install <package>` - installs a package
`apt-get remove <package>` - removes a package
`apt-cache search <package>` - find a package

Sudo
=
`/etc/sudoers.tmp` - sudoers file
`sudo visudo` - change who can elevate
`sudo adduser joe` - create new user joe
`sudo usermod -aG sudo joe` - give joe sudo


System config
=
`/etc/hostname` - system hostname
- to change, `set hostnamectl set-hostname new-name.local`
`/etc/hosts` - static dns
`/etc/resolv.conf` - dns servers (old)
`/etc/netplan` - modern network adapters


`/var/logs` - most logs here

Networking
=

legacy - `ifconfig`, `route`
modern - `ip addr`, `ip route`

`sudo ifconfig ens35 192.168.10.255/24` - set the ip address temporarily

`sudo ifconfig ens35 down/up`
`sudo route -n` - checking the route table
`sudo route add -net 192.168.2.0/24 gateway 192.168.10.2`
`sudo route add default gateway 10.30.10.1`

--> use del to remote the items

modern: using ip addr

`sudo ip addr show`
`sudo ip addr add 192.168.20.1/24` - can add as many addresses to an interface as we want
`ip route show` - can add or delete routes
`sudo ip route add 192.168.30.0/24` via 10.30.13.1
`sudo ip route show`

netplan
=

`cat /etc/netplan/00-inistaller-config.yaml`

