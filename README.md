# libvert-size

```bash
sudo qemu-img resize /var/lib/libvirt/images/ubuntu20.04-k8s-try-emco-67.qcow2 50G

check 
sudo fdisk -l /dev/vda
sudo fdisk -l

start 
fdisk /dev/vda

p -> see old values
d -> delete 3 number drive
n -> create new drive with 3 number with same start sector
-t -> change drive 3 type to Linux LVM it was 31 number for me.
p -> see new values
w -> save changes

Do you want to remove the signature? [Y]es/[N]o: N

check volume 
pvscan
resize volume
pvresize /dev/vda3

root@ubunturohit:/home/ubuntu# df -h /
Filesystem                         Size  Used Avail Use% Mounted on
/dev/mapper/ubuntu--vg-ubuntu--lv   20G   16G  3.1G  84% /


lvextend --resizefs -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv 

```
