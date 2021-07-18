failed to start remount root and kernel file system after reboot
----------------------------------------------------------------

Make sure you're using genfstab correctly - not it's `genfstab -U /mnt`, not `genfstab -U /`

Network unreachable after connecting with iwctl
-----------------------------------------------

You probably still need to activate the built-in network configuration.
Add
```
[General]
EnableNetworkConfiguration=true

[Network]
EnableIPv6=true
```
to /etc/iwd/main.conf.
