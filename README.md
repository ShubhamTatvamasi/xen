# xen

```bash
xsconsole
```

Update packages after install:
```bash
yum update -y
```
---

Ubuntu User Config
```yaml
#cloud-config
users:
- name: ubuntu
  plain_text_passwd: 'ubuntu'
  sudo: ALL=(ALL) NOPASSWD:ALL
  groups: sudo
  shell: /bin/bash
  lock_passwd: false
ssh_pwauth: True
packages:
- xe-guest-utilities
```

Ubuntu Network Config
```yaml
#network
  version: 2
  ethernets:
    eth0:
      addresses:
      - 192.168.0.101/24
      gateway4: 192.168.0.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
```

Magma Orchestrator Network Config
```yaml
#network
  version: 2
  ethernets:
    eth0:
      addresses:
      - 192.168.5.10/24
      - 192.168.5.11/24
      - 192.168.5.12/24
      - 192.168.5.13/24
      - 192.168.5.14/24
      gateway4: 192.168.5.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
```


---

User config:
```yaml
#cloud-config
users:
  - name: ubuntu
    ssh_authorized_keys:
      - ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOxN5VcvopmXS7fAA7ESjGYHNuAIWE7d0Fyj9Lh8lVZu shubhamtatvamasi@gmail.com
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: sudo
    shell: /bin/bash
```


Network config DHCP:
```yaml
#network:
  version: 2
  ethernets:
    eth0:
      dhcp4: true
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
        search: []
```

### Update Xen Orchestra

SSH into Xen Orchestra VM:
```bash
ssh xo@192.168.5.3
```

Clone the XenOrchestraInstallerUpdater repo:
```bash
git clone https://github.com/ronivay/XenOrchestraInstallerUpdater.git
cd XenOrchestraInstallerUpdater
git pull
```

Update Xen Orchestra:
```bash
sudo ./xo-install.sh --update
```

---

Jammy plugin:
```bash
sudo su
sudo echo "deb http://cz.archive.ubuntu.com/ubuntu focal main" > /etc/apt/sources.list.d/xen.list
sudo apt update
sudo apt install xe-guest-utilities
```

---

https://xcp-ng.org

Ubuntu Cloud Init Images: \
https://cloud-images.ubuntu.com/

Install VM Image: \
https://github.com/ronivay/XenOrchestraInstallerUpdater#image

Cloud Init Template images: \
https://sysmansquad.com/2021/07/07/creating-an-ubuntu-20-04-cloud-template-cloud-init-configuration-in-xen-orchestra/

Cloud Init Configs example: \
https://cloudinit.readthedocs.io/en/latest/topics/examples.html


