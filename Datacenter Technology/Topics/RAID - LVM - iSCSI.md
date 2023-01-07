# RAID - LVM - iSCSI
#raid 
#lvm
#iSCSI

## Basics
Check disks
``fdisk``

check filesystems
``df -h``

mouting filesystems automatically is done with
``/etc/vfstab``

## Raid

RAID = Redundant Array of Independent Disks
RAID is a way of storing data on a set of multiple hard disks
RAID comes in different levels 

### RAID0 (Striping)
- Distributing the data over multiple disks
- Capacity increases (ex. 2 1TB disks become 1 2TB disk)
- Provides no redundancy
- only security is security against theft
- Better speed

### RAID1 (Mirroring)
- duplicating data over 2 disks
- no increased capacity (ex 2 1TB disks become 1 1TB disk)
- Provides full redundancy: any disk may fail
- better read speed

### RAID5 (Parity)
#xor-logical-operator 
- Capacity of 1 drive is sacrificed for redundancy
- Only possible with 3 or more drives
- Capacity of disks is the amount of the hard drives - 1
- single disk redundancy: one disk may fail
	- as soon as 2 disks fail all data is lost
- Parity calculations makes use of XOR

### RAID10 (Mirroring plus Stripe)
- Combination of RAID1 and RAID0 mirroring and then striping them together
- Only possible with 4 or more drives
- Capacity is amount of drives / 2
- single (or double) disk redundancy: any disk may fail and possibly a second
- Frequently used by enterprises

### RAID01 (Stripe plus Mirroring)
- Combination of RAID0 and RAID1 striping and then mirroring them together
- Only possible with 4 or more drives
- Capacity is amount of drives / 2
- single (or double) disk redundancy: any disk may fail and possibly a second
- No company uses this why?
	- If a disk fails than all 'load' is put on the other RAID0 array so it has a bigger risk of crashing aswell

### Software vs Hardware RAID
Hardware RAID has a dedicated RAID chip to do calculations while software RAID uses a shared processor (usually the CPU)

### Setup RAID
You can create raid partitions during the installation of debian
during the creation of partitions you can add a raid partition
when adding a raid partition make sure to cofigure it aswell 
"configure the software RAID" use this button to configure them

Config file used
``/etc/mdadm/mdadm.conf ``

``mdadm --detail <device>``

## LVM (Logical Volume Manager)
Technology to "carve" disks, RAID sets and volumes into new devices

uses 3 layers
PV (Physical Volumes)

VG (Volume Groups)

LV (Logical Volumes)

### Setup LVM 
Same as in raid you can set LVM partitions in the setup of debian

**Configuration of the LVM partition**
install lvm2
``apt install lvm2``

create a pv
``pvcreate <path>``

``pvdisplay``

create a vg
``vgcreate <name> <path>``

``vgdisplay``

``vgextend``

create a lv
``lvcreate -n <name> -L <size> <vg>

create a file system on the lv
``mkfs.ext4 /dev/<vg>/<lv>

mount a folder to the filesystem
``mount <lv path> /<folder>

## iSCSI
Setting up iSCSI with targetCLI

``apt install -y targetcli*

start using
``targetcli``

