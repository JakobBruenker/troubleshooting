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
ResolvingNameService=systemd
```
to `/etc/iwd/main.conf`,
add
```
[Resolve]
DNS=1.1.1.1 2606:4700:4700::1111
```
to `/etc/systemd/resolved.conf.d/dns_servers.conf`
and run `systemctl enable systemd-resolved`, `systemctl start systemd-resolved`
