# disk mount

check disk file type:
```bash
sudo lsblk -f
```

create ext4 file system:
```bash
sudo mkfs -t ext4 /dev/xvdc
```

mount disk:
```bash
sudo mount /dev/xvdc /mnt/
```
