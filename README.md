# xen

```bash
xsconsole
```


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




https://xcp-ng.org

Ubuntu Cloud Init Images: \
https://cloud-images.ubuntu.com/

Install VM Image: \
https://github.com/ronivay/XenOrchestraInstallerUpdater#image

Cloud Init Template images: \
https://sysmansquad.com/2021/07/07/creating-an-ubuntu-20-04-cloud-template-cloud-init-configuration-in-xen-orchestra/

Cloud Init Configs example: \
https://cloudinit.readthedocs.io/en/latest/topics/examples.html


