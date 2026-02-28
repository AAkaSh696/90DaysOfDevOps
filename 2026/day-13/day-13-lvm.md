## Commands Used :
- sudo su
- 
- lsblk
- pvs
- vgs
- lvs
- df -h
  
- pvcreate /dev/nvme1n1
- vgcreate dev-vg /dev/sdf
- lvcreate -L 3G -n dev-lv dev-vg

- mkdir /mnt/dev-lv-mount
- mkfs.ext4 /dev/dev-vg/dev-lv
- mount /dev/dev-vg/dev-lv  /mnt/dev-lv-mount

- lvextend -L +1G /dev/dev-vg/dev-lv
- resize2fs /dev/dev-vg/dev-lv

- df-h /mnt/dev-lv-mount

## What i learned:
- LVM separates physical storage from logical storage.
- Logical volumes can be resized without deleting data.
- Volume Groups act as storage pools.
- LVM is essential for production environments where storage must grow dynamically.
