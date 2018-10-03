# vps_install

On Centos

yum update -y; yum upgrade -y

yum install vim -y

## Install Proxmox

## Change hostname
hostnamevar=proxmox_jdorel
domainnamevar=dorel.me
ip var=$(hostname --ip-address | grep -oP "(\.?\d{1,3}){4}$"

echo $hostnamevar $hostnamevar.$domainnamevar pvelocalhost >> /etc/hosts

## Add the Proxmox VE repository:
echo "deb http://download.proxmox.com/debian/pve stretch pve-no-subscription" > /etc/apt/sources.list.d/pve-install-repo.list

## Add the Proxmox VE repository key:
wget http://download.proxmox.com/debian/proxmox-ve-release-5.x.gpg -O /etc/apt/trusted.gpg.d/proxmox-ve-release-5.x.gpg
