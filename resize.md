# resize

Check if your file system has been changed to GPT:
```bash
fdisk -l /dev/vda
```

Fix GPT:
```bash
sgdisk -e /dev/vda
```

Now resize /dev/vda3 partition:
```bash
sudo fdisk /dev/vda
```
> take care of start and end sector:

Change the type to `Linux LVM` of partition 3:
```
t
```
> it was 31 for `Linux LVM` for me.

---

Check your list of storage:
```bash
xe sr-list
```

select local storage:
```bash
xe sr-list name-label=ca2e197d-1c66-29cc-966b-22085da4cbb8
```

check the volumes:
```bash
pvscan
```

Resize LVM partition
```bash
lvextend --resizefs -l +100%FREE /dev/mapper/XSLocalEXT--ca2e197d--1c66--29cc--966b--22085da4cbb8-ca2e197d--1c66--29cc--966b--22085da4cbb8
```




resize phisical volume:
```bash
pvresize /dev/vda3
```

https://community.spiceworks.com/how_to/32679-easily-resize-a-xenserver-storage-repository


xe sr-scan uuid=ca2e197d-1c66-29cc-966b-22085da4cbb8

rescan the device:
```bash
echo 1 > /sys/block/vda/device/rescan
```

