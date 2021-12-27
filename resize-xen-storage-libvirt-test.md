# resize xen storage - libvirt test

Fix GTP partition:
```bash
sudo parted -l /dev/vda
```
> `Fix` & `Fix`


Now resize partition:
```bash
sudo fdisk /dev/vda
```
> take care of start and end sector:

Change the type to Linux LVM of partition 3:
```
t
```
> it was 31 for Linux LVM for me.

