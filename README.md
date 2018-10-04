# vps_install

## TODO
  - PXE Loading
    - Kernel checksum verification
  - Disk encryption

On Debian

## Install Proxmox
Documentation from https://pve.proxmox.com/wiki/Install_Proxmox_VE_on_Debian_Stretch

### Change hostname
```
hostnamevar=proxmox_jdorel
domainnamevar=dorel.me
ip var=$(hostname --ip-address | grep -oP "(\.?\d{1,3}){4}$"

echo $hostnamevar $hostnamevar.$domainnamevar pvelocalhost >> /etc/hosts
```

### Add the Proxmox VE repository:
```
echo "deb http://download.proxmox.com/debian/pve stretch pve-no-subscription" > /etc/apt/sources.list.d/pve-install-repo.list
```
### Add the Proxmox VE repository key:
```
wget http://download.proxmox.com/debian/proxmox-ve-release-5.x.gpg -O /etc/apt/trusted.gpg.d/proxmox-ve-release-5.x.gpg
```

### Update your repository and system
```
apt update && apt dist-upgrade
```

### Install Proxmox VE packages
```
apt install proxmox-ve postfix open-iscsi
```

### Remove OS Prober
```
apt remove os-prober
```
