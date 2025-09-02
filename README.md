# alma-deploy

Almalinux deployment automation with kickstart

```bash
python -m http.server -b 0.0.0.0 80
```

```bash
#!/bin/bash

dnf -y update
dnf -y install epel-release && dnf -y update
dnf -y install hyperv* zram-generator nano curl \
    wget htop glibc-all-langpacks dnf-automatic git

dnf -y install podman podman-compose fuse-overlayfs
podman network create --driver bridge \
--subnet 10.10.90.0/24 --gateway 10.10.90.1 public_net
podman network create --driver bridge \
--subnet 10.10.91.0/24 --gateway 10.10.91.1 --internal private_net
```

```bash
mkdir /home/sysadmin/.config/containers/
touch /home/sysadmin/.config/containers/storage.conf


sudo bash -c "echo net.ipv4.ip_unprivileged_port_start=21 >> /etc/sysctl.conf"
sudo sysctl -p
```
