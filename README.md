# harvester-notes
The installer doesn't work on my weird nodes. Boot to USB and do this:
- `configfile (hd0,1)/boot/grub2/grub.cfg`
- wait for menu then press `e`
- on the `$linux` line modify `tty1` to `tty2`
- `ctrl+x`
- wait for boot
- `sudo -i`
- `ip a` to get the inteface name
- `echo BOOTPROTO=dhcp > /etc/sysconfig/network/ifcfg-<interface name>`
- `wicked ifreload <interface name>`
- on another machine
- `ssh rancher@<ip>` with the password: `rancher`
- `sudo -i`
- `TTY="/dev/pts/0" harvester-installer`
