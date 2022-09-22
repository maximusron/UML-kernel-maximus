# UML-kernel-maximus
An attempt to build my own User Mode Linux kernel to test buggy software and experiment with new drivers

```bash
dd if=/dev/zero of=disk_image_name bs=1 count=1 seek=16G
mkfs.ext4 ./disk_image_name && mount ./disk_image_name /mnt
debootstrap buster /mnt http://deb.debian.org/debian
```

Set root password

```bash
chroot /mnt
passwd
exit
```
Editing system network interface
```bash
# legacy UML network devices
auto eth0
iface eth0 inet dhcp

# vector UML network devices
auto vec0
iface vec0 inet dhcp
```
